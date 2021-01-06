# Research Drive protocol

This page contains information on how we deal with data on the SURF Research Drive in the SYNC lab, which can be accessed by logging in [here](https://eur.data.surfsara.nl/).



## 1. Folders

<ul>
<li>A project folder (at the root of the Research Drive) has to be created by the contract administrator (currently: Dorien). This means that each project is created <i>under</i> the contract. Information needed includes: </li> 
    <ol>
        <li>the <b>name of the folder</b> (preferably Year_ProjectName, e.g., "2018_Brainlinks"</li>
        <li>the <b>data steward</b> of the project folder</li>
        <li>the amount of <b>storage</b> needed (can be changed later)</li>
    </ol>
    <li><b>Storage</b>: our contract, “ESSB Brain and Development”, currently has 16 TB of storage capacity which is divided among the existing project folders. More storage capacity has to be requested with Research Data Management/Jeroen Rombouts (who in turn requests this at SURF) by the contract administrator</li>
</ul>

</ul>



## 2. Requesting and providing access

### Requesting access (users)

Request access to a folder with the data steward of the relevant project. You can find who is the data steward for which project in the file “[ResearchDrive_overview_Projects_Access_Groups](https://eur.data.surfsara.nl/index.php/apps/onlyoffice/3442795)” .



### Giving access (data stewards)

Select the folder and click the sharing icon. 

<img src="../img/RD_sharing.png" style="zoom:75%;" align="left"/>

<p style="clear:left;"></p>

In the area that appears, you can add individual users or groups and alternatively, create sharing links (URLs) with non-Research Drive users. Giving access to a folder means providing that selected access for **all subfolders** below the shared folder too.

Preferably **never give anyone sharing rights** (unless strictly necessary), because that person can give others more rights than they themselves have. This causes you to lose overview of who can access the data.



#### Custom groups

Give Research Drive users access via **personal access groups** (Settings > Custom groups). Members in such a group all receive the same rights when added to a folder. 

<img src="../img/RD_groups.JPG" style="zoom:50%;" align="left" />

<p style="clear:left;"></p>

The group owner is the only one who can add and remove access group members and see the members of the group. However, **all access group names** are visible for the entire Research Drive, so **aptly name the groups** according to the following format: **SYNC_ProjectName_Accesslevel**, e.g., "SYNC_Brainlinks_edit". If a new person needs access, they can be added to the relevant access group and automatically gains access to the same files/folders as the other group members. 

After you have made any changes in access groups, please **update** [the access document](https://eur.data.surfsara.nl/index.php/apps/onlyoffice/3442795).

#### Individual users

Add users to folders individually if they should not have the same permissions as the custom groups. This could for example be **outside researchers**. Please note that users of SURFdrive do not necessarily need a new Research Drive account, you can simply share the relevant files/folders with their [Federated cloud ID](https://wiki.surfnet.nl/pages/viewpage.action?pageId=11219960).

  

#### Students and other outside users 

Generally, when sharing data with students or outsiders, stick to the following guidelines:

- Share data only when the sharing serves a scientific goal
- Keep the amount of data shared to a minimum
- Pseudonymize or, if possible, anonymize data before sharing
- **Students** should sign a **non-disclosure agreement** and stick to the working guidelines for students

 

Give students and outside users access via **access links** that allow Download/View/Upload (edit only if it concerns a separate (Students) folder). Make use of the **password** and **end-date** functions: students and outside users should not have access to the data after their internships / the agreement have/has ended and the password will give extra protection against non-authorized use. Alternatively, you could add the external users or students as new Research Drive users (Dashboard > Add user), although for large amounts of users, this is not recommended.



## 3. Uploading data to Research Drive

### Rclone

Rclone is a command-line tool to upload data to any location. It can run easily in the background and is relatively simple.



#### Setting up

1. Download rclone: [https://rclone.org/downloads/](https://rclone.org/downloads/ ) (no admin rights needed)

2. Once downloaded, open your Command prompt (search for `cmd`)

3. Your command prompt shows a drive which it uses, e.g., `P:/`. Move the unwrapped rclone files (at least `rclone.exe`) to that drive.

4. In your command prompt, type `rclone config`

5. In your Research Drive account, create a new WebDAV password: Settings > Security > WebDAV passwords. Create a new password by filling in a name, e.g., “Rclone”. Copy the password that was just created to a temporary file/your clipboard.

6. Follow the instructions listed [here](https://wiki.surfnet.nl/display/RDRIVE/4.+Access+Research+Drive+via+Rclone). Use the following link for step 3: [https://eur.data.surfsara.nl/remote.php/nonshib-webdav/ ](https://eur.data.surfsara.nl/remote.php/nonshib-webdav/). Your username is `yourERNAid@eur.nl` and the password is the WebDAV password you just created (you will probably not see the password being pasted, but it is!). When you are asked for a `bearer token`, just press `Enter`

7. Example summary of the config: <br><img src="../img/RD_rcloneconfig.JPG" style="zoom:80%;" text-align = "center"/>


 <p style="clear:left;"></p>

#### Uploading data with Rclone

Upload files from your command window (type `cmd` in your search bar if you don't know where it is), using the following general format:

`rclone copy [flags] "source" RD:"destination"`



##### Example command

 `rclone copy -v -P --ignore-existing “J:\ResearchData\FSW\Brain and Development - Projects\2018_Brainlinks\Ouderstudie\” RD:“2018_Brainlinks (Projectfolder)/Brainlinks_Parentstudy”`

- copy the source contents to the destination folder
- print progress continuously (`-v` and `-P`) 
- skip already existing files (`--ignore-existing`)

 

#### Other Rclone commands

- List the files in the specified folder:`rclone ls RD:“2016_Zelfbeeld (Projectfolder)/Zelfbeeld_Data/Zelfbeeld_ProcessedData/”`
- Show configuration details: `rclone config show`
- Edit the configuration details: `rclone config e`

 

#### More information on Rclone

- On the [Research Drive wiki](https://wiki.surfnet.nl/display/RDRIVE/4.+Access+Research+Drive+via+Rclone)
- [Flags](https://rclone.org/flags/) to add to commands



### Rclone alternative: Cyberduck

Cyberduck is a graphical user interface for uploading data. It also has built-in encryption software (cryptomator), which allows simultaneously encrypting and uploading data. 



####  Setting up

1. Download and install [Cyberduck](https://cyberduck.io/download/) (the program is free, select $0 of donation) - you do need **admin access** for this tool.
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

 

Therefore, the following data need to be **encrypted** before uploading to Research Drive:

1. Participant databases with contact information - using a password on Microsoft Office documents is sufficient
2. MRI checklist information files (“Bijzonderhedenbestand”) containing information about past surgeries and other health information - using a password on Microsoft Office documents is sufficient
3. Files containing demographic data, responses about race, political views, religion, sexual life, criminal past and other potential health information. This type of file **can** be stored on Research Drive without encryption **only when** they are pseudonymized / not directly traceable to individuals.
4. Raw, **non-defaced** MRI images



In general, it is best to **avoid having to use encryption**, because passwords can be lost and software can deprecate. Data are much more durable if they can instead be anonymized or pseudonymized. For example, upload **defaced** MRI data and anonymized/pseudonymized health information to avoid having to encrypt them.



#### How to encrypt?

1. Keep it **local**: don't upload them to Research Drive. If this means you may lose data, don't do this
2. **Passwords**: put a password on a Microsoft Office document  (e.g., Excel, Word) and **keep the password at a safe location**. If you lose the password, the data is not accessible anymore
3. Use **encryption software**: we use Cryptomator to encrypt non-defaced MRI data.

  

##### **Using Cryptomator to encrypt data**

Use Cryptomator when you want to encrypt folders containing multiple sensitive files before uploading that folder to Research Drive: 

1. [Download](https://cryptomator.org/downloads/) and install the most recent version of Cryptomator
2. [Create an encrypted folder (vault)](https://docs.cryptomator.org/en/latest/desktop/getting-started/). Be sure to create **both** a password and a recovery key that can be used in case the password gets lost. **Save both at a safe location**! If you lose them, you cannot access the data anymore. 
3. [Open (decrypt) the vault](https://docs.cryptomator.org/en/latest/desktop/accessing-vaults/). In Cryptomator, select a Vault and click "Open vault". Select the cryptomator masterkey file. You will be prompted to fill out the password and afterwards, the folder will open. Note that you need the Cryptomator software to see the files in a normal way. In your file explorer, you will probably only see nonsense files in a folder called 'd'.
4. **Work with vault contents**: after opening a vault, the decrypted files will appear in a separate path on your computer (e.g., "Z://"). You can simply copy the path to tools (Matlab, R) or open files from here to work with them. After usage, remember to lock the vault again.
5. **Uploading encrypted folders** with rclone works the same way as uploading regular folders!



##### **Encryption within Cyberduck**

Cyberduck has in-built functionality to encrypt files using [Cryptomator](https://cryptomator.org/):

1. In Cyberduck, select the folder in which you want to create the encrypted folder
2. Right click and select “New locked vault” (Nieuwe versleutelde safe)
3. Give the vault a name (remember to put the Project name in there, e.g., “Brainlinks_Neural_data_raw”) and a password. **Store the password** somewhere safe immediately.
5. You can now upload folders into this encrypted folder as with normal folders. In the background, Cyberduck will decrypt your encrypted folders automatically (because it knows the password), which is why it looks no different than a normal folder in the Cyberduck environment. 

 

#### Saving and sharing passwords

A few safe options are:

-  **Lastpass** stores your passwords in a vault in the cloud (behind 1 master password). It can also store secure notes (such as Cryptomator recovery keys) and allows sharing passwords with others (premium version: Network center > Share item). 
-  **Network drive**: make sure that the drive is secured, backed up and only accessible to those who are allowed to decrypt the data
- **Locally**: keep in mind that when your PC is hacked, hackers may have access to the passwords and when your PC / drive crashes, the passwords may be lost.
- You can share passwords via **SURFfilesender**: per password and recovery key, create a txt file. Send it/them via [SURF filesender](https://filesender.surf.nl/) and make sure a password is required to download the file(s). Send the password to download to files to the receiver(s) via another way (e.g., text or slack message).



## 5. Working with data: editing and analysis

### Editing documents

The easiest way to edit documents is in your internet browser, because it allows **collaborative** editing (with OnlyOffice) and changes are automatically saved. If you mount Research Drive to your file explorer and then edit the document at the same time someone else does, there can be merging conflicts and the version with the last edit “wins”. 



### Mounting Research Drive to your file explorer

You can mount your Research Drive account to your file explorer, so that the Research Drive files can be accessed on your local PC. Note that collaborative editing is not possible this way, and merging conflicts may emerge when multiple people are working on the same files. OwnCloud is the recommended tool that is useful for working with small and few files. However, it is **not suitable** for synchronizing **large (numbers of)** **files**. 

- Download the OwnCloud via [this link](https://owncloud.com/client/) or in Research Drive, go Settings. Scroll all the way down until you see something like this. Click on "Desktop app": <br><img src="../img/RD_Owncloud.JPG" style="zoom:80%;" text-align="center" /> 
- Choose the installation location wisely: if you are going to work with large amounts of data, install Owncloud on a hard disk with sufficient storage space.

<ul>
    <li>See the <a href=https://wiki.surfnet.nl/display/RDRIVE/2.+ownCloud+desktop+client>Research Drive wiki page</a> for how to configure OwnCloud</li>
    <ul>
        <li>Use the link <strong>eur.data.surfsara.nl</strong> to connect with and authorize the share by logging in to your Research Drive account</li>
        <li>Choose <strong>Selective synchronization</strong> and select only the folders you need to work on from your local machine. All synced files are stored and synced on your local machine. If your Research  Drive storage is really high, you should <strong>not</strong> sync them all with your PC!</li>
        <li>Alternatively, choose <strong>Virtual file support</strong>, which makes sure that only files that are being worked on are downloaded</li>
    </ul>
    <li>To work with encrypted folders:</li>
    <ol>
        <li>synchronize the encrypted folder to your PC (somewhere with enough disk space) - this will probably take some time depending on the size of the folder</li>
        <li>open Cryptomator and select Open vault</li>
        <li>open the cryptomator masterkey file and fill out the password</li>
        <li>you should now be able to see your files and work with them. Bonus: your work will be automatically synchronized with Research Drive as long as you work in the synchronized folder</li>
    </ol></ul>



### Analyzing data from Research Drive

There are multiple ways that you can analyze data that are stored on Research Drive:

<ul>
    <li>Use <strong>OwnCloud</strong> and run analyses on data that are stored in Research Drive <i>as if</i> the data were stored on your local PC.</li>
    <ul>
        <li>Advantage: cloud synchronization</li>
        <li>Disadvantage: requires sufficient disk space, synchronization may take a long time</li>
    </ul>
    <li>Use a <strong>cloud computing service</strong>, such as Jupyter Hub (built into Research Drive) or the LISA cluster</li>
    <ul>
        <li>Advantage: no local copies needed, fast analysis</li>
        <li>Disadvantage: mostly meant for large data analysis, may take some getting used to</li>
    </ul>
        <li><strong>Locally</strong>: download the data to your local PC and analyze them there</li>
    <ul>
        <li>Advantage: no dependencies on your internet connection</li>
        <li>Disadvantage: not great for a lot of data, no cloud synchronization, requires manual upload to Research Drive afterwards</li>
    </ul>
</ul>



#### Working with MRI data: recommended method

1. Deface the MRI data before uploading them to Research Drive. If this is not possible (anymore), **encrypt** the folder that contains the relevant data as high as possible in the hierarchy, so that you only have to decrypt one folder for analyses.
2. When installing Owncloud, choose a location with sufficient disk space (e.g., an external hard disk)
3. Synchronize **only** the folder(s) that you need on your local PC via OwnCloud: your PC needs to have enough disk memory to save the data, also after processing! Note that syncing may take a while.
4. After synchronizing, if needed, use Cryptomator to decrypt the folder (enter the password)
5. The folder is now shown as a separate directory on your local PC (e.g., "Z:"). You can add this directory in SPM or Matlab for your analysis.
