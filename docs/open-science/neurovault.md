# NeuroVault: instructions and tips

[NeuroVault](https://neurovault.org/) is a repository for processed neuroimaging data (you can upload first and second level processed data). This type of data is anonymous, so it can be shared without any restrictions. We encourage you to do this!

## Why NeuroVault?
- Share data without sending files around
- Visualize your MRI contrasts and give the dataset a persistent identifier
- Make meta-analyses a lot easier
- Provide transparency to reviewers asking about your data
- Refer to the original paper and from the paper to your NeuroVault collection

Tips:

- Before uploading: Keep a good documentation of your contrasts during your data analysis so that it is easier to look up which contrast is which (since SPM is not good at file naming)
- Upload the images before you send in the first version of your paper. This way you can show the reviewers the data from the start (with the NeuroVault link)
- You can upload both t-maps and ROIs from many different modalities (see below)
- Include all analyses published in the paper and the main effects even if they are not included in the publication. This makes your analysis more transparent to the reviewers

## Which data can be uploaded into NeuroVault?
- Map types: t, z, F, chi-squared, p (given null hypothesis), 1-p ("inverted" probability), univariate beta map, multivariable beta map, ROI/mask, parcellation, anatomical, variance 
- Modalities: fMRI BOLD, fMRI-CBF, fMRI-CBV, diffusion MRI, structural MRI, PET FDP, PET [15O]-water, PET other, MEG, EEG, Other

Example datasets: [Renske van der Cruijsen](https://identifiers.org/neurovault.collection:4774), [Michelle Achterberg](https://identifiers.org/neurovault.collection:6070)

## Instructions
<ol>
    <li>Log in at https://neurovault.org/. If you have never used NeuroVault before, create an account (or use your Google account).</li>
    <li>Create a dataset, click “Get started and upload an image!” or “Add new collection” under the “Collections” tab. </li>
    <li>Fill in the following information (metadata): <b>Essentials</b></li>
    <ul>
        <li>Name of the collection: title of your article</li>
        <li>DOI of your article (if already present: always!!)</li>
        <li>Developmental neuroscience community</li>
        <li>Full dataset URL: for example a link to an OSF project, dataverseNL publication package, or Openneuro dataset, if applicable</li>
        <li>Contributors: add the last author of your paper (i.e., the NeuroVault username). In case you lose access to your account, the contributor can still make adaptations</li>
        <li>Accessibility: public, unless you are still in the reviewing process and only want the reviewers to see the data (with a view-only link)</li>
        <li>Subjects: Mean, min and max age of the sample (for easier meta-analysis)</li>
        <li>Design: type of design</li>
        <li>Acquisition, registration, preprocessing, first level and second level:  these details should be included in your paper. You can include them here as well but not necessarily.</li>
    </ul>
    <li>Click "Add image"</li>
    <ul>
        <li>Name: short & as clear as possible which map / contrast you are referring to (otherwise add a description)</li>
        <li>Map type (often t-map), modality (often fMRI BOLD) and template image (often MNI)</li>
        <li>Cognitive Atlas Paradigm: choose the task that resembles yours the best. This may not always be possible, however this field is mandatory</li>
        <li>You can upload .nii, .nii.gz and .hdr/.img files. Make sure to select the correct contrast (i.e., have good data documentation)!</li>
        <li>Cognitive paradigm description: if you have a task that is not well-known or widely used, e.g., the SNAT, you can refer to a document about the task in this field.</li>
        <li>Analysis level: often group (if single-subject, upload each contrast for each subject)</li>
        <li>No. of subjects</li>
        <li>Corresponding figure: not necessary but very insightful for reviewers</li>
    </ul>

</ol>