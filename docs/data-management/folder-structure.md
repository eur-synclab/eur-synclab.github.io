# Folder structure

It is important to have a folder structure that provides a good overview of your project and that maintains all data and documentation of your project logically. Important aspects of a good project structure are:

1. Separate source and **raw data from further processed data**. Preferably make raw data read-only so they cannot be edited.
2. Separate different **types of data**, when necessary
3. Provide scripts or descriptions that were used to go from the raw data to all processed data > make sure your analyses from start to finish are **reproducible**! 
4. Provide sufficient **metadata** about your project, e.g., preregistrations, study protocol, codebooks/data dictionaries, a data management plan, general information about the project, the ethics protocol, etc.
5. Provide all **materials and instructions** used to collect the data, e.g., tasks, questionnaires and instructions
6. Overall: use self-explanatory **file and folder names** or provide documentation explaining which files can be found where. Also keep in mind **versioning** (e.g., use the date in the filenames, the version or use a formal version control system like git)
7. Finally, use your folders **consistently**, e.g., place all data in the Data folder.



Below, you can find an example folder structure:



### Attempt 1 with dropdown menu: cannot be nested

<details>
    <summary>About the project</summary>
    <ul>
        <li>Preregistration(s) and/or study protocol (or links to them)</li>
        <li>Data dictionary/codebook</li>
        <li>Data management plan (DMP) and/or Data protection impact assessment (DPIA)</li>
        <li>Data sharing agreement (if applicable)</li>
        <li>Involved researcheres and their contact information</li>
        <li>Description of the project</li>
        <li>Overview of published manuscripts</li>
        <li>Organizational files about planning, availability, task divisioin, etc.</li>
    </ul>
</details>

<details>
    <summary>Ethics/CME/METC</summary>
    <ul>
        <li>Application</li>
        <li>Responses</li>
        <li>Final approved protocol</li>
    </ul>
</details>

<details><summary>Data</summary>
    <details><summary>Timepoint/Sub-project_X</summary>
    <details><summary>Behavioral_data</summary>
        <details><summary>Task_x</summary>
        <details><summary>Analysis</summary>
            <ul>
                <li>(Link to) pipeline used/manual</li>
                <li>Analysis log</li>
                <li>Scripts or macros</li>
                <li>Quality check document</li>
            </ul>
            </details>
        </details>
        </details>
    </details>
</details>

### Another type of dropdown: edit the text, or make it clickable?



<div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="Abouttheproject" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              About the project
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-item">Preregistration(s) and/or study protocol (or links to them)</li>
        		<li class="dropdown-item">Data dictionary/codebook</li>
         		<li class="dropdown-item">Data management plan (DMP) and/or Data protection impact assessment (DPIA)</li>
         		<li class="dropdown-item">Data sharing agreement (if applicable)</li>
         		<li class="dropdown-item">Involved researcheres and their contact information</li>
        		 <li class="dropdown-item">Description of the project</li>
             	<li class="dropdown-item">Overview of published manuscripts</li>
        		 <li class="dropdown-item">Organizational files about planning, availability, task divisioin, etc.</li>
              </ul>
        </div>



#### Test dropdown

<div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              Dropdown
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-item"><a href="#">Some action</a></li>
                <li class="dropdown-item"><a href="#">Some other action</a></li>
                <li class="dropdown-divider"></li>
                <li class="dropdown-submenu">
                  <a  class="dropdown-item" tabindex="-1" href="#">Hover me for more options</a>
                  <ul class="dropdown-menu">
                    <li class="dropdown-item"><a tabindex="-1" href="#">Second level</a></li>
                    <li class="dropdown-submenu">
                      <a class="dropdown-item" href="#">Even More..</a>
                      <ul class="dropdown-menu">
                          <li class="dropdown-item"><a href="#">3rd level</a></li>
                            <li class="dropdown-submenu"><a class="dropdown-item" href="#">another level</a>
                            <ul class="dropdown-menu">
                                <li class="dropdown-item"><a href="#">4th level</a></li>
                                <li class="dropdown-item"><a href="#">4th level</a></li>
                                <li class="dropdown-item"><a href="#">4th level</a></li>
                            </ul>
                          </li>
                            <li class="dropdown-item"><a href="#">3rd level</a></li>
                      </ul>
                    </li>
                    <li class="dropdown-item"><a href="#">Second level</a></li>
                    <li class="dropdown-item"><a href="#">Second level</a></li>
                  </ul>
                </li>
              </ul>
        </div>


#### Nog te verwerken informatie

Project folder name: [YEAR]_[NameProject]
Within the project folder: 

Data
	Timepoint/Sub-project x
Behavioral data
Task x
Analysis
(Link to) pipeline used / Manual
Analysis log note what you have done during the analysis; include exclusions and why those subjects were excluded
Analysis scripts/syntax if possible, split on preprocessing, analyses, data visualization files/make folders
Macros
Quality-check document which aspects were checked, by whom, etc.
ReadMe_AnalysisTaskX.txt
Raw data Unprocessed files
				ReadMe_TaskX.txt what is in this folder?

Daily diaries data
Analysis
 (Link to) pipeline used / Manual
Analysis log note what you have done during the analysis; include exclusions and why those subjects were excluded
Analysis scripts/syntax if possible, split on preprocessing, analyses, data visualization files/make folders
Macros
Quality-check document which aspects were checked, by whom, etc.
ReadMe_AnalysisTaskX.txt ReadMe_Analysis_DailyDiaries.txt
Raw data Unprocessed files

Neural data ((f)MRI/EEG/DTI)
Analysis
(Link to) pipeline used / Manual
Analysis log note what you have done during the analysis; include exclusions and why those subjects were excluded
Macros e.g., for creating csv files from raw Eprime data
Analysis scripts/syntax if possible, split on preprocessing, analyses, data visualization files/make folders
Quality-check document which aspects were checked, by whom, etc.
ReadMe_Analysis_Neuro.txt required software, analyzed when/by whom, etc.
Analysis_x 
Raw Data Unprocessed par & rec or nifti files
ParticipantNumber
		anat
		dwi
func
func-rest
ReadMe_RawNeuralData.txt

Physiological data
Analysis
(Link to) pipeline used / Manual
Analysis log note what you have done during the analysis; include exclusions and why those subjects were excluded
Macros e.g., for creating csv files from raw Eprime data
Analysis scripts/syntax if possible, split on preprocessing, analyses, data visualization files/make folders
Quality-check document which aspects were checked, by whom, etc.
ReadMe_Analysis_Physiological.txt
Raw data Unprocessed files

Questionnaire data
ReadMe_Questionnaire.txt
Analysis
(Link to) pipeline used / Manual recoding, constructing subscales, etc.
Analysis log note what you have done during the analysis; include exclusions and why those subjects were excluded
Analysis scripts
Data dictionary what does each variable mean? Include: the long name + possible levels
Macros
ReadMe_Analysis_Questionnaire.txt
Raw data

Finances
Applications participant money
Overviews
Receipts (kwitanties)
Travel expenses
	Readme_Finances.txt what is in this folder?

Literature/resources
Papers usable or used
Reference manager / BibTex files
ReadMe_Literature.txt

Measures
Readme_Measures.txt short description of measures per time point

Questionnaires
Questionnaire x: papers, manuals, software, instructions, score forms, etc.
		(List of all questionnaires)
		(if already in the lab: syntax to compute subscales and total scales)	
Readme_Questionnaires.txt what is in this folder? 

Tasks
ReadMe_Tasks.txt
Task x: 
Software and/or scripts
Possibly: Readme_taskx.txt short description of task (see study protocol), if applicable: scanner settings (e.g., number of dynamics)

Outreach and recruitment
 	ReadMe_OutreachRecruitment.txt what is in this/these folder(s)?
Presentations, Website texts, Education, Newsletters
Recruitment emails, Flyers, Folders, Contact with schools
Quotes from participants
Contents goodiebag

Publication packages
ReadMe_PublicationPackages.txt
Author name
Author et al. (year) publication package (can also be in prep)
		1. Manuscript
2. Task instructions, questionnaires, stimuli, scripts
		3. Anonymized raw data
		4. Data processing files (scripts)
		5. Processed data
6. Ethics protocol
Readme_PublicationX.txt Who collected the data, when collected, who analyzed, exclusions, corrupted data files, etc.  refer to preregistration?

Students
	Year_NameStudent
		ReadMe_StudentName.txt
		Data
			ReadMe_DataStudent.txt
		Manuscript

Work documents Ongoing stuff
ReadMe_WorkDocuments.txt
Data collection protocols
	ReadMe_Data_collection_protocols.txt what is in this/these folder(s)?
   		Documents for example:
•	Documents for subject folder
•	Instruction protocol
•	MRI checklist
•	Subject checklist
•	Forms brevethouder & portier
•	Aanvraagformulieren HIX
•	Planning schedules
•	Scanlogs
•	Scanning protocol
•	What to take with you to a scanning day.docx

Meetings
Agendas
Minutes (notulen)
		Readme_meetings.txt what is in this folder?

Planning of participants
		ReadMe_Participants.txt what is in this/these folder(s)?
Documents, for example:
•	Calling and planning
o	Bijzonderhedenbestand (secured with password)
o	Calling protocol
o	Coupling subjects - numbers (secured with password)
o	MRI checklist
o	Optional: Call planning (who calls when).xlsx
o	Recruitable and planned in subjects (secured with password)
•	Emailing
o	Confirmation email + appendices e.g., MRI checklist, instructions hormone collection, practical information (location, time, parking), information letter and informed consent
o	Reminder email + appendices e.g., MRI checklist, instructions hormone collection, practical information (location, time, parking), information letter and informed consent
•	DocumentOfParticipantsRequestingTheirOwnMRIScan