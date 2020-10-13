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


## Copying data from Research Drive to Lisa HPC

In the future, it might be possible to mount data directly from Research Drive on Lisa. In that way, you should be able to directly work with data on the Research Drive on the LISA cluster.

Currently, this is not yet possible. Therefore, you first need to copy data from Research Drive to Lisa. 
#### This can be done using **Rclone**:
- see Surf instructions [here](https://wiki.surfnet.nl/display/RDRIVE/4.+Access+Research+Drive+via+Rclone) for setting up a connection between Research Drive and Lisa.
- In short, you need to setup a config file on Lisa. 
- You can find the URL and username when you log in on Research Drive, under 'Settings/Instellingen' and 'Security/Beveiliging'. There, under 'WebDAV passwords' you can create a new password specifically for your connection with Lisa.

#### Some useful Rclone commands, once you have set up your connection:
- on the Lisa cluster command line, you can list your directories and files using a combination of `rclone` and `ls`, for example:
    - `rclone ls RD:"2010_Braintime (Projectfolder)/data"` > this will show the content of the 2010_Braintime data folder on Research Drive (assuming your connection is setup properly and that you have access to this folder)
- Copying data from Research Drive to a folder on your Lisa home:
    - `rclone copy RD:"2010\_Braintime (Projectfolder)/data/" /data`
    - or to check whether the command is working without actually copying you can use `--dryrun`: `rclone copy --dry-run RD:"2010\_Braintime (Projectfolder)/data/" /data`
- using [filtering](https://rclone.org/filtering/) you can copy a part of the data, e.g. only copying contents of subjects starting with 'sub-BTP0':
    - `rclone --include "sub-BTP0*" copy RD:"2010_Braintime (Projectfolder)/data/" data`

#### To copy other files (e.g., scripts) from locations outside Research Drive, you could use rsync
- here is an example command for copying a file to Lisa: `rsync -rvaz /Users/eduardklapwijk/sbatch-fmriprep.slurm -e ssh <username>@lisa.surfsara.nl:/home/<username>`

## Running analyses on the Lisa HPC

#### Using fmriprep and mriqc

- Extensive documentation for these tools can be found at [fmriprep](https://fmriprep.org/en/latest/index.html) and [mriqc](https://mriqc.readthedocs.io/en/latest/). Here, I will give a short summary and basic steps to use fmriprep on the Lisa cluster.

1. First go to an interactive node (e.g., `srun --time=1:00:00 --ntasks=1 --nodes=1 --pty /bin/bash`. Then download the Singularity image (this is a container containing all the software to run fmriprep): `singularity build /images/fmriprep-20.2.0.simg docker://nipreps/fmriprep:20.2.0` (replace with latest version number)
2. This will create an image (.simg file) on the Lisa cluster, see the fmriprep [documentation](https://fmriprep.org/en/latest/singularity.html#) with very helpful troubleshooting steps and an example of an sbatch script to run fmriprep with your study [here](https://fmriprep.org/en/latest/singularity.html#running-singularity-on-a-slurm-system). I have used this example to create an sbatch script that works on the Lisa cluster:

.. literalinclude:: _static/sbatch-fmriprep.slurm
   :language: bash
   :name: sbatch.slurm
   :caption: \*\*sbatch-fmriprep.slurm\*\*:
