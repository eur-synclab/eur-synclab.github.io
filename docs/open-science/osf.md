# The Open Science Framework

The Open Science Framework (OSF) is a project management, storage and collaboration platform that is used by many scientists. In an OSF project, you can:
- Register a preregistration
- Register a preprint
- Store and share project documentation
- Link external services, such as git(hub) repositories, publication packages, Research Drive (owncloud) folders, etc.
- ... and much more, such as obtaining [Open science badges!](https://osf.io/tvyxz/wiki/1.%20View%20the%20Badges/).

See [this link](https://www.cos.io/our-products/osf) for more information on the functionality of OSF and the [**OSF guides**](https://help.osf.io/hc/en-us) for many FAQs and technical documentation.

## Recommended use of the OSF

We recommend using the OSF as a central place for your project, especially if you will produce multiple publications in a project. 

1. Link your OSF project to the **[SYNC lab OSF page](https://osf.io/5hbsm/)** (Log in > Components > Link Projects). No worries, the SYNC lab collaborators cannot automatically edit your linked project!
2. **Register preregistrations** (Registrations > New registration) **and Preprints** in the relevant components. If your preregistration concerns one manuscript, we recommend creating a separate component in which you link all relevant materials (publication package, preregistration, code, preprint if applicable, etc.) belonging to that manuscript. A project can contain multiple Registrations and Preprints. Be sure to provide good metadata, preferably choose a CC BY 4.0 license and create a DOI so that your preregistration is citable.
3. **Data**: you can link OSF with external storage (see below) or store data on the OSF itself (choose the German storage). On the OSF itself, there is no storage limit (max.file size is currently 5 GB), but please do take privacy into account at all times
4. **Code and software**: you can link OSF with a Github repository in case your preprocessing pipeline, processing steps or experimental files are stored there (see below). If your code is however not code-worthy, we recommend storing the code in the publication package or on OSF itself. 
5. Link your OSF profile to your **[ORCID](https://orcid.org/)** account so that there cannot be any confusion as to who you are.

## Connecting the OSF to external services

Via the Add-on tab, you can connect the OSF with several external services. Note that this will not store data on the OSF itself!

### SURF Research Drive (via Owncloud)

Connecting with an Owncloud service like the Research Drive goes via a WebDAV connection. All changes made in the selected Research Drive folder will become visible in the OSF component, but the data are still stored at the EUR. Note that you can only make 1 Research Drive connection per OSF component (multiple connections per project are possible).

Please note the following:

- Make sure the access level is read-only, unless you want your collaborators to be able to adjust the Research Drive contents
- Think about anonymity: if you make the project/component public, data that are shared have to be anonymous or consented by participants to share publicly
- Linking an Owncloud folder is not a FAIR solution: there is no curated metadata and no license. Also, the Research Drive is not meant to archive data after the project is finished, so this will always be a temporary solution.

**How to link a Research Drive folder to OSF**

- Create a WebDAV password in Research Drive (Account > Settings > Security > WebDAV passwords). Copy the WebDAV password you created and click "done"
- Go to the component in your OSF project in which you want to add the Research Drive folder (if you are not in the right component, the Research Drive folder will be linked to the incorrect location)
- Select “Add-on” to add the ownCloud Add-on in OSF
- Configure the add-on in OSF:
  - URL: https://eur.data.surfsara.nl
  - Username: erna-id@eur.nl 
  - Password: WebDAV password you just made

### Figshare or a publication package in the EDR

You can link 1 publication package (1 Figshare link) per OSF component, so that the publication package appears in your OSF project. This way, you can license your data (not possible in OSF) and provide metadata but still link it to your OSF project for more context. Click [here](https://help.osf.io/hc/en-us/articles/360019929793-Connect-figshare-to-a-Project) for a tutorial. 

### Github repository

If you stored code on Github (for re-use, think about licensing!), you can link your repository to an OSF component. Again, you can only link 1 repository per OSF component. See [this link](https://help.osf.io/hc/en-us/articles/360019929813-Connect-GitHub-to-a-Project) for how to do this.
