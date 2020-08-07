# Folder structure

It is important to have a folder structure that provides a good overview of your project and that maintains all data and documentation of your project logically. Important aspects of a good project structure are:

1. Separate source and **raw data from further processed data**. Preferably make raw data read-only so they cannot be edited.
2. Separate different **types of data**, when necessary
3. Provide scripts or descriptions that were used to go from the raw data to all processed data > make sure your analyses from start to finish are **reproducible**! 
4. Provide sufficient **metadata** about your project, e.g., preregistrations, study protocol, codebooks/data dictionaries, a data management plan, general information about the project, the ethics protocol, etc.
5. Provide all **materials and instructions** used to collect the data, e.g., tasks, questionnaires and instructions
6. Overall: use self-explanatory **file and folder names** or provide documentation explaining which files can be found where. Also keep in mind **versioning** (e.g., use the date in the filenames, the version or use a formal version control system like git)
7. Finally, use your folders **consistently**, e.g., place all data in the Data folder.



## Example folder structure

Below, you can find an example folder structure of the project "YYYY_ProjectName". You are encouraged to use this format, but don't feel obliged. Also, it is recommended to include readme.txt files where deemed necessary.



### Mixed dropdown menu

**Nog doen:** bij data de volgorde analysis-processed-raw aanhouden

 

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
    If necessary, add another folder here for each timepoint or sub-project.<br>
    <br>
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="behavioral_data" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              Behavioral_data
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-submenu">
                  <a  class="dropdown-item" tabindex="-1" href="#">Task_X</a>
                  <ul class="dropdown-menu">
                    <li class="dropdown-item"><a tabindex="-1" href="#">raw_data</a></li>
                    <li class="dropdown-item"><a tabindex="-1" href="#">processed_data</a></li>
                    <li class="dropdown-submenu"><a class="dropdown-item" href="#">analysis</a>
                      <ul class="dropdown-menu">
                          <li class="dropdown-item"><a href="#">(link to) pipeline/manual used for processing</a></li>
                          <li class="dropdown-item"><a href="#">analysis log</a></li>
                          <li class="dropdown-item"><a href="#">scripts/macros</a></li>
                          <li class="dropdown-item"><a href="#">quality check document</a></li>
                      </ul>
                    </li>
                  </ul>
                </li>
              </ul>
        </div>
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="neural_data" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              Neural_data
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-submenu"><a class="dropdown-item" tabindex="-1" href="#">analysis</a>
                  <ul class="dropdown-menu">
                    <li class="dropdown-item"><a tabindex="-1" href="#">(link to) pipeline/manual used for processing</a></li>
                    <li class="dropdown-item"><a tabindex="-1" href="#">analysis log</a></li>
                    <li class="dropdown-item"><a tabindex="-1" href="#">scripts/macros</a></li>
                    <li class="dropdown-item"><a tabindex="-1" href="#">quality check document</a></li>
                    </ul></li>
               <li class="dropdown-submenu">
                  <a class="dropdown-item" tabindex="-1" href="#">processed_data</a>
                  <ul class="dropdown-menu">
                      <li class="dropdown-item"><a tabindex="-1" href="#">analysis_x</a></li>
                      </ul></li>
                <li class="dropdown-submenu">
                  <a class="dropdown-item" href="#">raw_data</a>
                  <ul class="dropdown-menu">
                        <li class="dropdown-submenu"><a class="dropdown-item" href="#">participant_number</a>
                        <ul class="dropdown-menu">
                            <li class="dropdown-item"><a href="#">anat</a></li>
                            <li class="dropdown-item"><a href="#">dwi</a></li>
                            <li class="dropdown-item"><a href="#">func</a></li>
                        </ul>
                      </li>
                  </ul>
                </li>
          </ul>
    </div> 
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="physiological_data" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              Physiological_data
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">raw_data</a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">processed_data</a></li>
                <li class="dropdown-submenu"><a  class="dropdown-item" href="#">analysis</a>
                      <ul class="dropdown-menu">
                          <li class="dropdown-item"><a tabindex="-1" href="#">(link to) pipeline/manual used for processing</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">analysis log</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">scripts/macros</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">quality check document</a></li>
                      </ul>
                    </li>
                  </ul>
                </li>
              </ul>
        </div>
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="questionnaire_data" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              Questionnaire_data
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">raw_data</a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">processed_data</a></li>
                <li class="dropdown-submenu"><a  class="dropdown-item" href="#">analysis</a>
                      <ul class="dropdown-menu">
                          <li class="dropdown-item"><a tabindex="-1" href="#">(link to) pipeline/manual used for processing</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">analysis log</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">scripts/macros</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">data dictionary/codebook</a></li>
                      </ul>
                    </li>
                  </ul>
                </li>
              </ul>
        </div>
</details>

<details>
    <summary>Finances</summary>
    <ul>
        <li>Applications participant money</li>
        <li>Overviews</li>
        <li>Receipts (kwitanties)</li>
        <li>Travel expenses</li>
    </ul>
</details>

<details>
    <summary>Literature_resources</summary>
    <ul>
        <li>Papers usable or used</li>
        <li>Reference manager files</li>
    </ul>
</details>

<details>
    <summary>Measures</summary>
        <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="Questionnaires" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              Questionnaires
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">List of questionnaires</a></li>
                <li class="dropdown-submenu"><a  class="dropdown-item" href="#">Questionnaire_x</a>
                      <ul class="dropdown-menu">
                          <li class="dropdown-item"><a tabindex="-1" href="#">papers</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">manuals, scoreforms</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">software</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">scripts</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">instructions</a></li>
                      </ul>
                    </li>
                  </ul>
                </li>
              </ul>
        </div>
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="Tasks" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              Tasks
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-submenu">
                  <a class="dropdown-item" tabindex="-1" href="#">Task_X</a>
                  <ul class="dropdown-menu">
                      <li class="dropdown-item"><a tabindex="-1" href="#">software</a></li>
                      <li class="dropdown-item"><a tabindex="-1" href="#">scripts</a></li>
                      </ul></li>
                </li>
          </ul>
    </div> 
</details>

<details>
    <summary>Outreach_recruitment</summary>
    <ul>
        <li>Presentations, website texts, education, newsletters</li>
        <li>Recruitment emails, flyers, folders, contact with schools</li>
        <li>Quotes from participants</li>
        <li>Contents of the goodiebag</li>
    </ul>
</details>

<details>
    <summary>Publication_packages</summary>
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="pubpakage" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              Author_et_al_(year)_journal
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">1. Manuscript</a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">2. Task instructions, questionnaires, stimuli, scripts</a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">3. Anonymized raw data</a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">4. Data processing files (scripts)</a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">5. Processed data</a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">6. Ethics protocol</a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">Readme.txt</a></li>                
                  </ul>
                </li>
              </ul>
        </div> 
</details>




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