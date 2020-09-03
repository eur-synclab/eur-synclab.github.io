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

 

Give students and outside users access via **access links** that allow Download/View/Upload (edit only if it concerns a separate (Students) folder). Please make use of the **password** and **end-date** functions: students and outside users should not have access to the data after their internships / the agreement have/has ended and the password will give extra protection against non-authorized use. Alternatively, you could add the external users or students as new Research Drive users (Dashboard > Add user), although for large amounts of users, this is not recommended.



## 3. Uploading data to Research Drive

### Rclone

Rclone is a command-line tool to upload data to any location. It can run easily in the background and is relatively simple.



#### Setting up

1. Download rclone: [https://rclone.org/downloads/](https://rclone.org/downloads/ ) (no admin rights needed)

2. Once downloaded, open your Command prompt (search for `cmd`)

3. Your command prompt shows a drive which it uses, e.g., `P:/`. Move the unwrapped rclone files (at least `rclone.exe`) to that drive.

4. In your command prompt, type `rclone config`

5. In your Research Drive account, create a new WebDAV password: Settings > Security > WebDAV passwords. Create a new password by filling in a name, e.g., “Rclone”. Copy the password that was just created to a temporary file/your clipboard.

6. Follow the instructions listed [here](https://wiki.surfnet.nl/display/RDRIVE/4.+Access+Research+Drive+via+Rclone). Use the following link for step 3: [https://eur.data.surfsara.nl/remote.php/nonshib-webdav/ ](https://eur.data.surfsara.nl/remote.php/nonshib-webdav/). Your username is `yourERNAid@eur.nl` and the password is the Webdav password you just created (you will probably not see the password being pasted, but it is!). When you are asked for a `bearer token`, just press `Enter`

7. Example summary of the config: <br><img src="../img/RD_rcloneconfig.JPG" style="zoom:80%;" text-align = "center"/>


 <p style="clear:left;"></p>

#### Uploading data using Rclone

With rclone, you can upload files from your command windows, using the following general format:

`rclone copy [flags] "source" RD:"destination"`



For example: `rclone copy -v -P --ignore-existing “J:\ResearchData\FSW\Brain and Development - Projects\2018_Brainlinks\Ouderstudie\” RD:“2018_Brainlinks (Projectfolder)/Brainlinks_Parentstudy”`

- copy the source contents to the destination folder
- print progress (`-v` and `-P`) 
- skip already existing files (`--ignore-existing`)

 

#### Other Rclone commands

- List the files in the specified folder:`rclone ls RD:“2016_Zelfbeeld (Projectfolder)/Zelfbeeld_Data/Zelfbeeld_ProcessedData/”`
- Show configuration details: `rclone config show`
- Edit the configuration details: `rclone config e`

 

#### More information on Rclone

- On the [Research Drive wiki](https://wiki.surfnet.nl/display/RDRIVE/4.+Access+Research+Drive+via+Rclone)
- [Flags](https://rclone.org/flags/) to add to commands



### Cyberduck

Cyberduck is not a command-line tool but has a GUI (graphical user interface) for uploading data. It also has built-in encryption software (cryptomator), which allows simultaneously encrypting and uploading data. 



####  Setting up

1. Download and install [Cyberduck](https://cyberduck.io/download/) (the program is free, select $0 of donation) - you do need admin access for this tool.
2. Read the [wiki page](https://wiki.surfnet.nl/display/RDRIVE/3.+Access+Research+Drive+via+Cyberduck) of SURF Research Drive and from there download the [Research Drive cyberduck profile](https://wiki.surfnet.nl/download/attachments/11219959/surfresearchdrive.cyberduckprofile?version=1&modificationDate=1562069941090&api=v2). Save the Research Drive cyberduck profile in the “Profiles” folder within your Cyberduck program files folder (e.g., “C:\Program Files\Cyberduck\profiles”) 
3. In your Research Drive account, create a WebDAV password: Settings > Security > WebDAV passwords. Create a new password by filling in a name, e.g., “Cyberduck”. Copy the password that was just created to a temporary file/your clipboard.
4. (Re)Start Cyberduck
5. Click “New connection” (Nieuwe verbinding). 
6. In the pop-up window that appears, select the SURF Research Drive profile, change the server to eur.data.surfsara.nl and fill out your username (ERNA ID) and the WebDAV password that you just created. 
7. Do not forget to select “**Save password**” (Bewaar wachtwoord)! Then, select “Connect” (Verbind). <br><img src="../img/Cyberduck_connect.JPG" style="zoom:80%;" text-align="center"/>

<p style="clear:left;"></p>

After having made the connection, you should be able to navigate your (project) folders like in Research Drive. Every time Cyberduck restarts, this connection will be made, except when you explicitly disconnect (then you have to re-connect again).



####  Uploading data in Cyberduck

1. Turn on Checksum (Edit > Preferences > Wachtrij (Queue) > Checksum)
2. Select a folder in which you want to upload files
3. Click Upload and select the files to be uploaded. 
4. Once your files have been uploaded, they should appear in your Research Drive!



## 4. Uploading *sensitive* data to Research Drive

### Encryption

Research Drive **cannot** contain **special** types of personal data (bijzondere persoonsgegevens). These comprise of:

- Race, ethnicity, political views, religion
- Sexual life/preferences
- Genetic or biometric data with the purpose of unique identification
- Health information, among which medical data (MRI data!)
- Criminal past

 

Most of this information is collected via questionnaires and during the call to select participants (e.g., MRI checklist). Raw MRI data containing faces should also be considered special personal data. The following data need to be **encrypted** before uploading to Research Drive:

1. Participant databases with contact information
2. MRI checklist information files (“Bijzonderhedenbestand”) containing information about past surgeries and other health information
3. Files containing demographic data, responses about race, political views, religion, sexual life, criminal past and other potential health information. This type of file *can* be stored on Research Drive without encryption *only in case* that the data are pseudonymized / not directly traceable to individuals.
4. Raw, non-defaced MRI images



In general, it is best to **avoid having to use encryption**, because passwords can be lost and software can deprecate. Data are much more durable if they can instead be anonymized or pseudonymized. For example, upload **defaced** MRI data and anonymized/pseudonymized health information to avoid having to encrypt them.



#### How to encrypt?

##### **Keep it local**

The simplest way to keep data safe is to not upload them to the Research Drive, but to keep them on a local EUR drive. This may however result in some access issues and may therefore not be desirable.



##### **Passwords**

Putting a password on an individual Excel or Word file is a safe form of encryption. Be sure to **keep the password at a safe location**: If you lose the password, the data is not accessible anymore.

 

##### **Within Cyberduck**

Cyberduck has in-built functionality to encrypt files using [Cryptomator](https://cryptomator.org/). To encrypt files, you first need to create an encrypted folder. 

1. In Cyberduck (after having been connected to your Research Drive), select the folder in which you want to create the encrypted folder
2. Right click and select “New locked vault” (Nieuwe versleutelde safe)
3. Give the vault a name (remember to put the Project name in there, e.g., “Brainlinks_Neural_data_raw”) and a password (passphrase).
4. **Store the password** in your password manager or somewhere else safe immediately. If you lose this password, the data cannot be accessed anymore! Cyberduck will also save the password, but if others besides you need to be able to access the folder as well, they need the password too to decrypt the files.
5. You can now upload folders into this encrypted folder as with normal folders.   In the background, Cyberduck will decrypt your own encrypted folders for you automatically (because it knows the password), which is why it looks no different than a normal folder in your own Cyberduck environment. However, if you look in your Research Drive, you will see nonsense files and/or folders. 

 

##### **Cryptomator outside of Cyberduck**

You do not necessarily need Cyberduck in order to encrypt folders. For example, when you use Rclone to upload data, you may still need to encrypt some of the data before uploading. In order to do this, you will use Cryptomator separately.

1. [Download](https://cryptomator.org/downloads/) and install Cryptomator
2. [Create an encrypted folder](https://docs.cryptomator.org/en/latest/desktop/getting-started/). Be sure to create **both** a password and a recovery key that can be used in case the password gets lost. **Save both at a safe location**!
3. [Open (decrypting) the encrypted folder](https://docs.cryptomator.org/en/latest/desktop/accessing-vaults/). When decrypted, the folder will appear in a separate path (drive), which you can give to tools such as Matlab and R to work with them. After usage, remember to lock the vault again!

 

#### Saving and sharing passwords

After encryption, both you and your colleagues need to be able to re-access the data. Therefore, store the passwords in a safe place:

-  **Lastpass** stores your passwords in a vault the cloud (behind 1 main, strong password). It can also store secure notes (such as Cryptomator recovery keys) and allows sharing passwords with others (in the premium version). As an extention in your web browser, it also autofills the saved passwords. 
- Storing on a **network drive**: make sure that that drive is secured, backed up and only accessible to those who are allowed to decrypt the data

- Storing files **locally** is also an option, but keep in mind that when your PC is hacked, hackers may have access to the passwords and when your PC / drive crashes, the passwords may be lost.



The following ways are recommended to safely share a password (or other sensitive files):

- Via the network drive: make sure that the drive or folder is only accessible to those allowed
- Via **Lastpass**: Network center > Share item. If you have the free version and you want to share the password with more than 1 person, this is not the best option.
- Via **SURFfilesender**: per password and recovery key, create a txt file. Send it/them via [SURF filesender](https://filesender.surf.nl/), make sure a password is required to download the file(s). Send the password to download to files to the receiver(s) via another way (e.g., text or slack message).



## 5. Working with data: editing and analysis

### Editing documents

The easiest way to edit documents is in your internet browser, because it allows **collaborative** editing (using OnlyOffice) and changes are automatically saved. If you mount Research Drive to your file explorer and then edit the document at the same time someone else does, there can be merging conflicts and the version with the last edit “wins”. 



### Mounting Research Drive to **your** **file explorer** with OwnCloud

You can mount your Research Drive account to your file explorer, so that the Research Drive files can be accessed on your local PC. Note that collaborative editing is not possible this way, and merging conflicts may emerge when multiple people are working on the same files.  OwnCloud is the recommended tool that is useful for working with small and few files. However, it is **not suitable** for synchronizing **large (numbers of)** **files**. 

- To download the OwnCloud client, go to [this link](https://owncloud.com/client/) or in Research Drive, go Settings. Scroll all the way down until you see something like this. Click on "Desktop app": <br><img src="../img/RD_Owncloud.JPG" style="zoom:80%;" text-align="center" />

<ul><li>See the <a href=https://wiki.surfnet.nl/display/RDRIVE/2.+ownCloud+desktop+client>Research Drive wiki page</a> for how to configure OwnCloud
    <ul>
        <li>Use the link <strong>eur.data.surfsara.nl</strong> to connect with and authorize the share by logging in to your Research Drive account</li>
        <li>Choose <strong>Selective synchronization</strong> and select only the folders you need to work on from your local machine. All synced files are stored and synced on you local machine. If your Reseaerch  Drive storage is really high, you should <strong>not</strong> sync them all with your PC!</li>
        <li>Alternatively, choose <strong>Virtual file support</strong>, which makes sure that only files that are being worked on are downloaded</li>
    </ul></ul>

**Note**: OwnCloud does not show encrypted files and folders and so does not allow to work with them.



### Analyzing data from the Research Drive

There are multiple ways that you can analyze data that are stored on the Research Drive:

<ul>
    <li><strong>Locally</strong>: download the data to your local PC and analyze them there</li>
    <ul>
        <li>Advantage: no dependencies on your internet connection</li>
        <li>Disadvantage: not great for large (numbers of) files, no cloud synchronization, takes up double the amount of storage space (both on the Research Drive and your local PC)</li>
    </ul>
    <li>Use <strong>OwnCloud</strong> and run analyses on data that are stored in Research Drive <i>as if</i> the data were stored on your local PC. Make sure to only synchronizee files that y ou really need! </li>
    <ul>
        <li>Advantage: cloud synchronization</li>
        <li>Disadvantage: data that are used will be stored at your local hard disk (except when using virtual file support). This can cause your PC to become very slow. This method is also not suitable for large (numbers of) files, because synchronizating those files will take a very long time</li>
    </ul>
    <li>Use a <strong>cloud computing service</strong>, such as Jupyter Hub (built into Research Drive) or the LISA cluster</li>
    <ul>
        <li>Advantage: no local copies need to be made and the analysis runs fast, since the cluster has a large computing capacity</li>
        <li>Disadvantage: the cluster is mostly meant for MRI data analysis and can be expensive if used a lot. It also takes some getting used to to work with the cluster</li>
    </ul>
</ul>



#### Working with MRI data: recommended methods

#####  1. <u>Defaced</u> MRI data synchronized with your local PC

1. Deface the MRI data before uploading them to the Research Drive. First deface them, then turn the files into .hrd and .img files and upload them to Research Drive.

2. Synchronize **only** the folder(s) that you need on your local PC via OwnCloud: your PC needs to have enough disk memory to save the data, also after processing! After synchronizing, you can enter the path to the OwnCloud folder that was synchronized to your PC in SPM or Matlab for your analysis.

 

##### 2. <u>Encrypted</u> MRI data synchronized with your local PC

Encrypted folders are useless if you do not have the encryption key: they contain random files with weird names. 

2. Encrypting: When uploading encrypted MRI data to the Research Drive, encrypt a folder as highest as possible in the hierarchy (e.g., Neural data), so that you only have to **decrypt one folder** to do analyses on that data. 
3. Synchronize **only** the folder(s) that you need on your local PC via OwnCloud. Use Cryptomator to decrypt the folder (enter the password) and click Reveal.
4. The main folder (e.g., Neural data) is shown as a separate directory on your local PC (e.g., "Z:"). You can add this directory in SPM or Matlab for your analysis.
