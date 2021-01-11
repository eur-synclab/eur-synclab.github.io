# Using the Lisa cluster

If you want to process a lot of data, using a high performance cluster will save a lot of time. We can use the [Lisa Cluster](https://userinfo.surfsara.nl/systems/lisa) from SURFsara  
More information about high perfomance computing options at the EUR can be found [here](https://www.eur.nl/en/library/node/20736)

## Obtaining an account

- See also under 'How to Access' on this [EUR page](https://www.eur.nl/en/library/node/20736):
	
    1. Download the [application form](https://userinfo.surfsara.nl/sites/default/files/2015-11-11-Lisa-Application-form-EUR.doc) for resources at SURFsara, fill it in and return it for EUR approval by e-mail to [edsc@eur.nl](mailto:edsc@eur.nl?SUBJECT=High%20Performance%20Computing). You can ask for 10.000 hours computing time for a start, this will normally be approved quite fast 
    2. After EUR approval: SURFsara requests you, for each user in the Application form to sign the [Usage agreement Supercomputer systems](https://userinfo.surfsara.nl/sites/default/files/2013-01-25_HPC-System-Usage-Agreement-SURFsara.doc), and send it to [helpdesk@surfsara.nl](mailto:helpdesk@surfsara.nl)
    3. At SURFsara they will create an account for you on LISA and you will receive an email with instructions on how to login

## SLURM usage

Lisa runs a Unix-based operating system, which is text based. For submitting batches of jobs, SLURM is used.
There is a dedicated Lisa [User Guide](https://userinfo.surfsara.nl/systems/lisa/user-guide), here are some basics that are good to know:


### Copying data from Research Drive to Lisa HPC

In the future, it might be possible to mount data directly from Research Drive on Lisa. In that way, you should be able to directly work with data on the Research Drive on the LISA cluster.

Currently, this is not yet possible. Therefore, you first need to copy data from Research Drive to Lisa. This can be done using **Rclone**.
#### copy data using **rclone**:
- see Surf instructions [here](https://wiki.surfnet.nl/display/RDRIVE/4.+Access+Research+Drive+via+Rclone) for setting up a connection between Research Drive and Lisa.
- In short, you need to setup a config file on Lisa. 
- You can find the URL and username when you log in on Research Drive, under 'Settings/Instellingen' and 'Security/Beveiliging'. There, under 'WebDAV passwords' you can create a new password specifically for your connection with Lisa.

#### Some useful rclone commands
- Once you have set up your connection, you can use these commands to work with the data
- On the Lisa cluster command line, you can list your directories and files using a combination of `rclone` and `ls`, for example:
    - `rclone ls RD:"2010_Braintime (Projectfolder)/data"` > this will show the content of the 2010_Braintime data folder on Research Drive (assuming your connection is setup properly and that you have access to this folder)
- Copying data from Research Drive to a folder on your Lisa home:
    - `rclone copy RD:"2010_Braintime (Projectfolder)/data/" /data`
    - or to check whether the command is working without actually copying you can use `--dryrun`: `rclone copy --dry-run RD:"2010_Braintime (Projectfolder)/data/" /data`
- using [filtering](https://rclone.org/filtering/) you can copy a part of the data, e.g. only copying contents of subjects starting with 'sub-BTP0':
    - `rclone --include "sub-BTP0*" copy RD:"2010_Braintime (Projectfolder)/data/" data --progress`

#### copy data using **rsync**
- To copy other files (e.g., scripts) from locations outside Research Drive, you could use **rsync**
- here is an example command for copying a file to Lisa: `rsync -rvaz /Users/eduardklapwijk/sbatch-fmriprep.slurm -e ssh <username>@lisa.surfsara.nl:/home/<username>`

## Running analyses on the Lisa HPC

#### Using fmriprep and mriqc

Extensive documentation for these tools can be found at [fmriprep](https://fmriprep.org/en/latest/index.html) and [mriqc](https://mriqc.readthedocs.io/en/latest/). Here, I will give a short summary and basic steps to use fmriprep on the Lisa cluster.

1. First go to an interactive node (e.g., `srun --time=1:00:00 --ntasks=1 --nodes=1 --pty /bin/bash`), otherwise you run into memory problems when unpacking the image. In the interactive session, download the Singularity image (this is a container containing all the software to run fmriprep): `singularity build /images/fmriprep-20.2.0.simg docker://nipreps/fmriprep:20.2.0` (replace with latest version number)  
2. This will create an image (.simg file) on the Lisa cluster, see the fmriprep [documentation](https://fmriprep.org/en/latest/singularity.html#) with very helpful troubleshooting steps and an example of an sbatch script to run fmriprep with your study [here](https://fmriprep.org/en/latest/singularity.html#running-singularity-on-a-slurm-system). I have used this example to create an sbatch script that works on the Lisa cluster:        
        
```
#!/bin/bash
#
#SBATCH -J fmriprep
#SBATCH --time=48:00:00
#SBATCH -n 1
#SBATCH --cpus-per-task=16
#SBATCH --mem-per-cpu=4G
#SBATCH -p normal  # Queue names you can submit to
# Outputs ----------------------------------
#SBATCH -o log/%x-%A-%a.out
#SBATCH -e log/%x-%A-%a.err
#SBATCH --mail-user=<your@email>
#SBATCH --mail-type=ALL
# ------------------------------------------

BIDS_DIR="$STUDY/data"
DERIVS_DIR="derivatives/fmriprep-20.2.0"

# Prepare some writeable bind-mount points.
TEMPLATEFLOW_HOST_HOME=$STUDY/.cache/templateflow
FMRIPREP_HOST_CACHE=$STUDY/.cache/fmriprep
mkdir -p ${TEMPLATEFLOW_HOST_HOME}
mkdir -p ${FMRIPREP_HOST_CACHE}

# Prepare derivatives folder
mkdir -p $STUDY/${DERIVS_DIR}

# This trick will help you reuse freesurfer results across pipelines and fMRIPrep versions
mkdir -p $STUDY/derivatives/freesurfer-6.0.1
 if [ ! -d $STUDY/${DERIVS_DIR}/freesurfer ]; then
     ln -s $STUDY/derivatives/freesurfer-6.0.1 $STUDY/${DERIVS_DIR}/freesurfer
 fi

# Make sure FS_LICENSE is defined in the container.
export SINGULARITYENV_FS_LICENSE=$STUDY/images/freesurfer.txt

# Designate a templateflow bind-mount point
export SINGULARITYENV_TEMPLATEFLOW_HOME="/templateflow"
SINGULARITY_CMD="singularity run --cleanenv -B $BIDS_DIR:/data -B $DERIVS_DIR:/deriv -B ${TEMPLATEFLOW_HOST_HOME}:${SINGULARITYENV_TEMPLATEFLOW_HOME} -B $STUDY:/work $STUDY/images/fmriprep-20.2.0.simg"

# Parse the participants.tsv file and extract one subject ID from the line corresponding to this SLURM task.
subject=$( sed -n -E "$((${SLURM_ARRAY_TASK_ID} + 1))s/sub-(\S*)\>.*/\1/gp" ${STUDY}/data/participants.tsv )

# Remove IsRunning files from FreeSurfer
find $STUDY/derivatives/freesurfer-6.0.1/sub-$subject/ -name "*IsRunning*" -type f -delete

# Compose the command line
cmd="${SINGULARITY_CMD} /data /deriv participant --participant-label $subject -w /work/ -vv --omp-nthreads 8 --nthreads 12 --mem_mb 60000 --output-spaces MNI152NLin2009cAsym:res-2 anat fsnative fsaverage5 --use-aroma --bids-filter-file ${STUDY}/scripts/bids-filter.json"

# Setup done, run the command
echo Running task ${SLURM_ARRAY_TASK_ID}
echo Commandline: $cmd
eval $cmd
exitcode=$?

# Output results to a table
echo "sub-$subject   ${SLURM_ARRAY_TASK_ID}    $exitcode" \
      >> ${SLURM_JOB_NAME}.${SLURM_ARRAY_JOB_ID}.tsv
echo Finished tasks ${SLURM_ARRAY_TASK_ID} with exit code $exitcode
exit $exitcode
```  

- This sbatch script assumes a couple of things in place:  
    - a /data folder with your data in BIDS format + a participants.tsv file (note: you can also make a custom participants.tsv file to run only a subset of your data)  
    - a Freesurfer license file, here in the /images folder. You can obtain a Freesurfer license for free [here](https://surfer.nmr.mgh.harvard.edu/registration.html)  
    - a bids-filter-file. This is a very useful filter when you want to run only certain sessions or certain modalities with fmriprep. See more info at the [fmriprep website](https://fmriprep.org/en/20.2.0/faq.html#how-do-i-select-only-certain-files-to-be-input-to-fmriprep). This is an example when you only want to use T1w and one task ('feedback') from session ses-01:
```  
{
    "t1w": {
        "datatype": "anat",
        "session": "01",
        "suffix": "T1w"
    },
    "bold": {
        "datatype": "func",
        "task": "feedback",
        "session": "01",
        "suffix": "bold"
    }
}
```    
- Now you are ready to set your $STUDY directory:  
`export STUDY=/home/<username>` (or whatever directory is your root)  
- Next you can run run the slurmbatch script for all participants in tsv file:  
`sbatch --array=1-$(( $( wc -l $STUDY/participants.tsv | cut -f1 -d' ' ) - 1 )) scripts/sbatch-fmriprep.slurm`

##### mriqc specific commands:

- 