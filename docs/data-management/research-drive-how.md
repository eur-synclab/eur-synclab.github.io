# Research Drive protocol

This page contains information on how we deal with data on the SURF Research Drive in the SYNC lab.



## 1. Folders

- A project folder (at the root of the Research Drive) has to be created by the contract administrator (currently: Dorien Huijser, later also Eveline Crone). This means that each project is created *under* the contract. Information needed includes (1) the **name of the folder** (preferably Year_ProjectName, e.g., “2018_Brainlinks”), (2) the **data steward** of the project folder and (3) the amount of **storage** needed (can still be changed later)
- **Storage**: our contract, “ESSB Brain and Development”, currently has 16 TB of storage capacity which is divided among the existing project folders. More storage capacity has to be requested with Research Data Management/Jeroen Rombouts (who in turn requests this at SURF) by the contract administrator.



## 2. Requesting and giving access

### Requesting access (users)

Request access to a folder with the data steward of the relevant project. You can find who is the data steward for which project in the file “[ResearchDrive_overview_Projects_Access_Groups](https://eur.data.surfsara.nl/index.php/apps/onlyoffice/3442795)” .



### Giving access (data stewards)

Select the folder and click the sharing icon. 

<img src="../img/RD_sharing.png" style="zoom:75%;" align="left"/>

<p style="clear:left;"></p>

In the area that appears, you can add individual users or groups and alternatively, create sharing links (URLs) with non-Research Drive users. Giving access to a folder means providing that selected access for **all subfolders** below the shared folder too.

Give only the necessary access: preferably **never give anyone sharing rights** (unless strictly necessary), because that person can give others more rights than they themselves have. This causes you to lose overview of who can access the data.



#### Giving access to Research Drive users

##### Custom groups

Give Research Drive users access via **personal access groups** (Settings > Custom groups). Members in such a group all receive the same rights when added to a folder. 

<img src="../img/RD_groups.JPG" style="zoom:50%;" align="left" />

<p style="clear:left;"></p>

The owner of the group is the only one who can add and remove access group members and see the members of the group. However, **all access group names** are visible for the entire Research Drive, so please **aptly name the groups** according to the following format: **SYNC_ProjectName_Accesslevel**, e.g., "SYNC_Brainlinks_edit". If a new person needs access, they can be added to the relevant access group and automatically gains access to the same files/folders as the other group members. 

After you have made any changes in access groups, please **update** “[ResearchDrive_overview_Projects_Access_Groups](https://eur.data.surfsara.nl/index.php/apps/onlyoffice/3442795)” (in SYNC_General/ Research_Drive) so we can keep an overview of who has access to what and who owns which access group.

##### Individual users

Add users to folders individually if they should not have the same permissions as the custom groups. This could for example be outside researchers. Please note that users of SURFdrive do not necessarily need a new Research Drive account, you can simply share the relevant files/folders with their [Federated cloud ID](https://wiki.surfnet.nl/pages/viewpage.action?pageId=11219960).



 #### Students and other outside users

Generally, when sharing data with students or outsiders, stick to the following guidelines:

- Share data only when the sharing serves a scientific goal
- Keep the amount of data shared to a minimum (only the data necessary to reach the scientific goal)
- Pseudonymize or, if possible, anonymize data before sharing (e.g., by removing direct and indirect identifiers)
- **Students** should additionally sign a **non-disclosure agreement** and stick to the working guidelines for students

 

Give students and outside users access via **access links** that allow Download/View/Upload (edit only if it concerns a separate (Students) folder). Please make use of the **password** and **end-date** functions: students and outside users should not have access to the data after their internships / the agreement have/has ended and the password will give extra protection against non-authorized use. Alternatively, you could add the external users or students as new Research Drive users (Dashboard  > Add user), although for large amounts of users, this is not recommended.



## 3. Uploading data to Research Drive

### Rclone

Rclone is a command-line tool to upload data to any location. It can run easily in the background and is relatively simple.

1. Download rclone: https://rclone.org/downloads/ (no admin rights needed)
2. Once downloaded, open your Command prompt (search for cmd)
3. Your command prompt shows a drive which it uses, e.g., P:/. Move the unwrapped rclone files (at least rclone.exe) to that drive.
4. In your command prompt, type `rclone config`
5. In your Research Drive account, create a WebDAV password: Settings > Security > WebDAV passwords. Create a new password by filling in the name, e.g., “Rclone”. Copy the password that was just created to a temporary file/your clipboard.
6. Follow the instructions listed [here](https://wiki.surfnet.nl/display/RDRIVE/4.+Access+Research+Drive+via+Rclone). Use the following link (step 3): [https://eur.data.surfsara.nl/remote.php/nonshib-webdav/ ](https://eur.data.surfsara.nl/remote.php/nonshib-webdav/), username: ERNAid@eur.nl; password: Webdav password you just created (you will probably not see the password being pasted,  but it is!). When you are asked for a "bearer token", just press `Enter`
7. Example summary of the config:

`[RD]`

`type = webdav`

`url = https://eur.data.surfsara.nl/remote.php/nonshib-webdav/`

`vendor = owncloud`

`user = 75800lvc@eur.nl`

`pass = gqxEPZP1TQWhsOT4pEMkEhJGcOXYiG-mV-gR_UMM`

 

#### Uploading data using Rclone

General format: `rclone copy [flags] ‘source’ RD:‘destination’`

Example command   (run from your command window): `rclone copy -v -P --ignore-existing “J:\ResearchData\FSW\Brain and Development - Projects\2018_Brainlinks\Ouderstudie\” RD:“2018_Brainlinks (Projectfolder)/Brainlinks_Parentstudy”`, meaning: Copy folder 1 contents (source) to folder 2 (destination), print progress (-v and -P) and skip already existing files

 

#### Other Rclone commands

- List the files in the specified folder:`rclone ls RD:“2016_Zelfbeeld (Projectfolder)/Zelfbeeld_Data/Zelfbeeld_ProcessedData/”`
- Show configuration details: `rclone config show`
- Edit the configuration details: `rclone config e`

 

#### More information on Rclone

- Wiki: https://wiki.surfnet.nl/display/RDRIVE/4.+Access+Research+Drive+via+Rclone
- Flags to add to commands: https://rclone.org/flags/



### TROEP  

NOG DOEN

**Cyberduck - setting up**

Cyberduck is not a command-line tool but has a GUI (graphical user interface) for uploading data. It also has built-in encryption software (cryptomator), which allows simultaneously encrypting and uploading data. 

1. Download and install [Cyberduck](https://cyberduck.io/download/) (the program is free so select 0$ of donation) - you do need admin access for this tool.
2. Read the [wiki page](https://wiki.surfnet.nl/display/RDRIVE/3.+Access+Research+Drive+via+Cyberduck) of SURF Research Drive and from there download the [Research Drive cyberduck profile](https://wiki.surfnet.nl/download/attachments/11219959/surfresearchdrive.cyberduckprofile?version=1&modificationDate=1562069941090&api=v2). Save the Research Drive cyberduck profile in the “Profiles” folder within your Cyberduck program files folder (e.g., “C:\Program Files\Cyberduck\profiles”) 
3. In your Research Drive account, create a WebDAV password:
4. go to Settings (Instellingen) at the top right of the homescreen
5. select the Security (Beveiliging) tab and scroll down to “WebDAV passwords”
6. create a new password by filling in the name, e.g., “Cyberduck”
7. copy the password that was just created to a temporary file/your clipboard
8. (Re)Start Cyberduck
9. Click “New connection” (Nieuwe verbinding). 
10. In the pop-up window that appears
11. select the SURF Research Drive profile
12. change the server to eur.data.surfsara.nl
13. fill out your username (ERNA ID) and the WebDAV password that you just created in Research Drive. 
14. Do not forget to select “**Save password**” (Bewaar wachtwoord)!
15. Select “Connect” (Verbind).



 

After having made the connection, you should see your (project) folders like in Research Drive. Every time Cyberduck restarts, this connection will be made, except when you explicitly disconnect (then you have to re-connect again).

 

*Uploading data in Cyberduck*

1. Turn on Checksum (Edit > Preferences > Wachtrij (Queue) > Checksum)
2. Select a folder in which you want to upload files
3. Click Upload and select the files to be uploaded. 
4. Once your files have been uploaded, they should appear in your Research Drive!

## **4.** **Uploading** ***sensitive*** **data to Research Drive**

**What to encrypt?**

Research Drive **cannot** contain special types of personal data (bijzondere persoonsgegevens). These comprise of:

- Race, ethnicity, political views, religion
- Sexual life/preferences
- Genetic or biometric data with the purpose of unique identification
- Health information, among which medical data (MRI data!)
- Criminal past

 

Most of this information is collected via questionnaires and during the call to select participants (e.g., MRI checklist). Raw MRI data containing faces should also be considered special personal data. The following data need to be **encrypted** before uploading to Research Drive:

1. Participant databases with contact information*
2. MRI checklist information files (“Bijzonderhedenbestand”) containing information about past surgeries and other health information*
3. Files containing demographic data, responses about race, political views, religion, sexual life, criminal past and other potential health information**
4. Raw, non-defaced MRI images (esp. anatomical images)

 

*Besides encryption, you can also store these files at EUR locally, but files 1-3 still need to be protected with a password.

** This type of file can be stored on Research Drive without encryption *only in case* that the data are pseudonymized / not directly traceable to individuals.

 

**How to encrypt?**

*1) Passwords*

Putting a password on an Excel or Word file is **also** a safe form of encryption. Be sure to keep the password at a safe location: If you lose the password, the data is not accessible anymore.

 

*2) Within Cyberduck*

Cyberduck has in-built functionality to encrypt files using [Cryptomator](https://cryptomator.org/). To encrypt files, you first need to create an encrypted folder. 

1. In Cyberduck (after having been connected to your Research Drive), select the folder in which you want to create the encrypted folder
2. Right click and select “New locked vault” (Nieuwe versleutelde safe)
3. Give the vault a name (remember to put the Project name in there, e.g., “Brainlinks_Neural_data_raw”) and a password (passphrase).
4. Store the password in your password manager or somewhere else safe immediately. If you lose this password, the data cannot be accessed anymore! Cyberduck will also save the password, but if others besides you need to be able to access the folder as well, they need the password too to decrypt the files.
5. You can now upload folders into this encrypted folder as with normal folders.

 

In the background, Cyberduck will decrypt your own encrypted folders for you automatically (because it knows the password), which is why it looks no different than a normal folder in your own Cyberduck environment. However, if you look in your Research Drive, you will see nonsense files and/or folders. Also, if others create an encrypted folder, Cyberduck will ask you for the password to decrypt because it does not know it yet.

 

*3) Using Cryptomator*

You do not necessarily need Cyberduck in order to encrypt folders. For example, when you use Rclone to upload data, you may still need to encrypt some of the data before uploading. In order to do this, you do need to install the newest version of Cryptomator separately:

1. Download and install Cryptomator: https://cryptomator.org/downloads/
2. Creating an encrypted folder: https://docs.cryptomator.org/en/latest/desktop/getting-started/
3. Opening (decrypting) an encrypted folder: https://docs.cryptomator.org/en/latest/desktop/accessing-vaults/. When decrypted, the folder will appear in a separate path (drive), which you can give to tools such as Matlab and R to work with them. After usage, remember to lock the vault again!

 

**Note**: Cryptomator asks for a password, but also allows saving a recovery key for when the password gets lost. Please also save this key, so that the data can never be lost!

 

**When to encrypt?**

- Old projects: save both the source MRI data (non-defaced) and the raw defaced data. Encrypt the non-defaced data. 
- New projects: immediately deface the MRI data so that encryption is not needed

 

**Saving passwords**

When encrypting files or folders, we recommend storing the passwords in a safe place:

- **Lastpass** stores your passwords in a vault the cloud (behind 1 main, strong password). It can also store secure notes (such as Cryptomator recovery keys) and allows sharing passwords with others (although the free version only allows sharing with 1 other account). As an extention in your web browser, it also autofills the saved passwords. 
- Storing files **locally** is also an option, but keep in mind that:
- When your PC is hacked, hackers may have access to the passwords
- When your PC / drive crashes, the passwords may be lost
- Storing on a **network drive**: make sure that that drive is secured, backed up and only accessible to those who are allowed to decrypt the data

 

**Sharing passwords**

When sharing encryption passwords, do it safely!

- Via **Lastpass**: Network center > Share item. If you have the free version and you want to share the password with more than 1 person, this is not the best option.
- Via SURFfilesender: per password and recovery key, create a txt file. Send it/them via [SURF filesender](https://filesender.surf.nl/), make sure a password is required to download the file(s). Send the password to the receiver(s) via another way (e.g., text or slack message).**
  ** 

## **5.** **Working with data (editing and analysis)** 

**Editing documents**

The easiest way to edit documents is in your browser. The main advantage of this is that the browser (OnlyOffice) allows **collaborative** editing and changes are automatically saved. If you mount Research Drive to your file explorer and then edit the document at the same time someone else does, there will be merging conflicts and the version with the last edit “wins”. 

 

**Mounting Research Drive to** **your** **file explorer**

You can mount your Research Drive account to your file explorer, so that the Research Drive files can be accessed on your local PC. Note that collaborative editing is not possible this way, and merging conflicts may emerge when multiple people are working on the same files. Tools:

 

\1. **OwnCloud**: This is the tool recommended by SURF which is handy for working with small and few files. However, it is **not suitable** for synchronizing **large (numbers of)** **files**. 

- Go to [this link](https://owncloud.com/client/) OR in Research Drive, go to your name in the right upper corner and select Settings (Instellingen). Scroll all the way down until you see something like this:

...

- Download the OwnCloud client suitable for your operating system
- See the [Research Drive wiki page ](https://wiki.surfnet.nl/display/RDRIVE/2.+ownCloud+Client)for how to configure OwnCloud further. 
- Use the link **eur.data.surfsara.nl** to connect with and authorize the share by logging in to your Research Drive account.
- Choose **Selective synchronization** and select only the folders you need to work on from your local machine. All synced files are stored and synced on your local machine. If your Research Drive storage is really high, you should not sync them all with your PC.
- Alternatively, choose **Virtual file support**, which makes sure that only documents that are being worked on are downloaded.
- **Note**: ownCloud does not show encrypted files and folders and so does not allow to work with them.

 

\2. Access as a network drive via **WebDAV**. The main advantage of this way is that no files are actually synced or stored at your harddisk. The disadvantage is that you only have access to the files with an internet connection (accessing files can be slow) and the native Windows and Mac OS implementations are not great. See [this link ](https://wiki.surfnet.nl/pages/viewpage.action?pageId=22413688)for how to configure this 

- The password you need is a WebDAV password again: Settings > Security > WebDAV passwords > Create new password, e.g. “20200417_WebDAV” > Copy the password.
- Note: WebDAV does show encrypted files and folders, but does not decrypt them.

 

**Analyzing data - options**

There are multiple ways that you can analyze data:

- Locally: download the data to your local PC and analyze them there. 
- Advantages: no dependencies on your internet connection
- Disadvantages: not great for large (numbers of) files, no cloud synchronization, data are stored at your local PC, so there will be multiple copies of the data
- Use a mounting tool (see above) and run analyses on data that are stored in Research Drive *as if* the data were stored at your local PC
- Advantages: cloud synchronization, no download necessary
- Disadvantages: 
- Not great for large (numbers of) files
- In owncloud, data that is used will (at least temporarily) be stored at your local harddisk (except when using virtual file support). This can cause your PC to become very slow.
- Via WebDAV, the speed of processing depends on your internet connection (you will work via a network drive)
- Synchronization will take a while if you create/edit large numbers of files. Make sure to only synchronize files that you really need if you want to analyze data this way.
- Use a cloud computing service, e.g., Jupyter Hub (also built into Research Drive) and the SURF LISA cluster
- Advantages: no local copies need to be made, fast data analysis since the cluster has large computing capacity
- Disadvantages: mostly meant for MRI data analysis, can be expensive if used a lot

 

**Working with MRI data: recommended methods**

*Defaced data synchronized with PC*

- Deface before uploading data to RD. First deface, then turn into .hrd and .img files 
- Upload data to RD and synchronize ONLY the folder(s) that you need on your PC via OwnCloud (your PC needs to have enough memory to save the data, also after preprocessing/analysis). You can then enter the path to the OwnCloud folder that was synchronized to your PC in SPM when you do batch preprocessing or first level analysis.

 

*Defaced data not synchronized with PC*

When data is not synchronized, you cannot give SPM a valid path name. This is therefore not possible.

 

*Encrypted data synchronized with PC*

1. Encrypted folders are useless (they contain random files with weird names) if you do not have the key. 
2. Encrypting: Upload the data to RD, encrypt a folder as highest as possible in the hierarchy (e.g., Neural data) so that you only have to decrypt one folder to do analyses on that data. 
3. Synchronize ONLY the folder(s) that you need on your PC. Use Cryptomator to decrypt the folder (enter the password) and click Reveal
4. The main folder (e.g., Neural data) is shown as a separate directory on your PC. You can add this directory to your Matlab/SPM path.

 

**Getting Research Drive data into the LISA Cluster (Eduard)**

IN PROGRESS





TROEP

Securing data

- Client-side encryption with Cryptomator (secure vault with password encrypted and saved keys) – currently supported
- Secure vault with password encrypted and saved keys
- Downside: when sharing data you need to provide the password to the person with whom you are sharing

 

Mounting Research Drive

- Research Drive can be mounted in any OS using tools that support WebDAV. In Windows, Linux or MacOS mount it as network or remote storage
- On LISA or Cartesius, use a tool like RClone
- Required: WebDAV password generated in RD web interface
- Config: rclone config

storage type: webdav, provide the remote WebDAV URL of your instance, choose “owncloud” as vendor, name it “RD” or more specific

- List files: rclone ls RD
- Copy files: rclone copy RD:/file.txt file.txt