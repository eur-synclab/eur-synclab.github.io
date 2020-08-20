# Folder structure

It is important to have a folder structure that provides a good overview of your project and that maintains all data and documentation of your project logically. Important aspects of a good project structure are:

1. Separate source and **raw data from further processed data**. Preferably make raw data read-only so they cannot be edited.
2. Separate different **types of data**, when necessary
3. Provide scripts or descriptions that were used to go from the raw data to all processed data > make sure your analyses from start to finish are **reproducible**! 
4. Provide sufficient **metadata** about your project, e.g., preregistrations, study protocol, codebooks/data dictionaries, a data management plan, general information about the project, the ethics protocol, etc. Provide readme.txt files were necessary.
5. Provide all **materials and instructions** used to collect the data, e.g., tasks, questionnaires and instructions
6. Overall: use self-explanatory **file and folder names** or provide documentation explaining which files can be found where. Also keep in mind **versioning** (e.g., use the date in the filenames, the version or use a formal version control system like git)
7. Finally, use your folders **consistently**, e.g., place all data in the Data folder.



## Example folder structure

Below, you can find an example folder structure of the project "YYYY_ProjectName". You are encouraged to use this or a similar format, but don't feel obliged!

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
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="behavioral_data" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              <strong>Behavioral_data</strong>
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-submenu">
                  <a  class="dropdown-item" tabindex="-1" href="#"><strong>Task_x</strong></a>
                  <ul class="dropdown-menu">
                      <li class="dropdown-submenu"><a class="dropdown-item" href="#"><strong>analysis</strong></a>
                      <ul class="dropdown-menu">
                          <li class="dropdown-item"><a href="#">(link to) pipeline/manual used for processing</a></li>
                          <li class="dropdown-item"><a href="#">analysis log</a></li>
                          <li class="dropdown-item"><a href="#">scripts/macros</a></li>
                          <li class="dropdown-item"><a href="#">quality check document</a></li>
                      </ul>
                    </li>
                    <li class="dropdown-item"><a tabindex="-1" href="#"><strong>processed_data</strong></a></li>
                    <li class="dropdown-item"><a tabindex="-1" href="#"><strong>raw_data</strong></a></li>
                  </ul>
                </li>
              </ul>
        </div>
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="neural_data" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              <strong>Neural_data</strong>
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-submenu"><a class="dropdown-item" tabindex="-1" href="#"><strong>analysis</strong></a>
                  <ul class="dropdown-menu">
                    <li class="dropdown-item"><a tabindex="-1" href="#">(link to) pipeline/manual used for processing</a></li>
                    <li class="dropdown-item"><a tabindex="-1" href="#">analysis log</a></li>
                    <li class="dropdown-item"><a tabindex="-1" href="#">scripts/macros</a></li>
                    <li class="dropdown-item"><a tabindex="-1" href="#">quality check document</a></li>
                    </ul></li>
               <li class="dropdown-submenu">
                  <a class="dropdown-item" tabindex="-1" href="#"><strong>processed_data</strong></a>
                  <ul class="dropdown-menu">
                      <li class="dropdown-item"><a tabindex="-1" href="#"><strong>analysis_x</strong></a></li>
                      </ul></li>
                <li class="dropdown-submenu">
                  <a class="dropdown-item" href="#"><strong>raw_data</strong></a>
                  <ul class="dropdown-menu">
                        <li class="dropdown-submenu"><a class="dropdown-item" href="#"><strong>participant_number</strong></a>
                        <ul class="dropdown-menu">
                            <li class="dropdown-item"><a href="#"><strong>anat</strong></a></li>
                            <li class="dropdown-item"><a href="#"><strong>dwi</strong></a></li>
                            <li class="dropdown-item"><a href="#"><strong>func</strong></a></li>
                        </ul>
                      </li>
                  </ul>
                </li>
          </ul>
    </div> 
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="physiological_data" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              <strong>Physiological_data</strong>
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-submenu"><a  class="dropdown-item" href="#"><strong>analysis</strong></a>
                      <ul class="dropdown-menu">
                          <li class="dropdown-item"><a tabindex="-1" href="#">(link to) pipeline/manual used for processing</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">analysis log</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">scripts/macros</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">quality check document</a></li>
                      </ul>
                    </li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>processed_data</strong></a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>raw_data</strong></a></li>
                  </ul>
                </li>
              </ul>
        </div>
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="questionnaire_data" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              <strong>Questionnaire_data</strong>
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-submenu"><a  class="dropdown-item" href="#"><strong>analysis</strong></a>
                      <ul class="dropdown-menu">
                          <li class="dropdown-item"><a tabindex="-1" href="#">(link to) pipeline/manual used for processing</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">analysis log</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">scripts/macros</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">data dictionary/codebook</a></li>
                      </ul>
                    </li>                
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>processed_data</strong></a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>raw_data</strong></a></li>
                  </ul>
                </li>
              </ul>
        </div>
<br>
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
              <strong>Questionnaires</strong>
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-submenu"><a  class="dropdown-item" href="#"><strong>Questionnaire_x</strong></a>
                      <ul class="dropdown-menu">
                          <li class="dropdown-item"><a tabindex="-1" href="#">papers</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">manuals, scoreforms</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">software</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">scripts</a></li>
                          <li class="dropdown-item"><a tabindex="-1" href="#">instructions</a></li>
                      </ul>
                    </li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">List of questionnaires</a></li>
                  </ul>
                </li>
              </ul>
        </div>
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="Tasks" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              <strong>Tasks</strong>
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-submenu">
                  <a class="dropdown-item" tabindex="-1" href="#"><strong>Task_x</strong></a>
                  <ul class="dropdown-menu">
                      <li class="dropdown-item"><a tabindex="-1" href="#">software</a></li>
                      <li class="dropdown-item"><a tabindex="-1" href="#">scripts</a></li>
                      </ul></li>
                </li>
          </ul>
    </div> 
<br>
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
                <strong>Author_et_al_(year)_journal</strong>
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>1_Manuscript</strong></a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>2_Task_instructions-questionnaires-stimuli-scripts</strong></a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>3_Anonymized_raw_data</strong></a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>4_Data_processing_files-scripts</strong></a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>5_Processed_data</strong></a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>6_Ethics_protocol</strong></a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">Readme.txt</a></li>                
                  </ul>
                </li>
              </ul>
        </div> 
</details>

<details>
    <summary>Students</summary>
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="pubpakage" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              <strong>Year_NameStudent</strong>
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>Data</strong></a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>Manuscript</strong></a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">Readme_StudentName.txt</a></li>
                  </ul>
                </li>
              </ul>
        </div> 
</details>

<details>
    <summary>Work_documents</summary>
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="pubpakage" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              <strong>Data_collection_protocols</strong>
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">Subject folder documents (during data collection)</a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">Instruction protocol</a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">Forms brevethouder and portier</a></li>      
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">Forms brevethouder and portier</a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">Requests for the HIX system</a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">Planning schedules</a></li>        
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">Scan logs</a></li>        
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#">Scanning & data collection protocols</a></li>               
                  </ul>
                </li>
              </ul>
        </div> 
    <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="pubpakage" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              <strong>Meetings</strong>
            </button>
            <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
                <li class="dropdown-divider"></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>Agendas</strong></a></li>
                <li class="dropdown-item"><a  class="dropdown-item" tabindex="-1" href="#"><strong>Minutes</strong></a></li>
                  </ul>
                </li>
              </ul>
        </div> 
<div class="dropdown">
        <button class="btn btn-secondary dropdown-toggle" type="button" id="questionnaire_data" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          <strong>Planning_of_participants</strong>
        </button>
        <ul class="dropdown-menu multi-level" role="menu" aria-labelledby="dropdownMenu">
            <li class="dropdown-divider"></li>
            <li class="dropdown-submenu"><a  class="dropdown-item" href="#"><strong>Calling_and_planning</strong></a>
                  <ul class="dropdown-menu">
                      <li class="dropdown-item"><a tabindex="-1" href="#">Bijzonderhedenbestand (encrypted)</a></li>
                      <li class="dropdown-item"><a tabindex="-1" href="#">Calling protocol</a></li>
                      <li class="dropdown-item"><a tabindex="-1" href="#">Coupling subjects-numbers (encrypted)</a></li>
                      <li class="dropdown-item"><a tabindex="-1" href="#">Contact information (encrypted)</a></li>
                  </ul>
                </li>                
            <li class="dropdown-submenu"><a  class="dropdown-item" href="#"><strong>Emailing</strong></a>
                  <ul class="dropdown-menu">
                      <li class="dropdown-item"><a tabindex="-1" href="#">Confirmation and reminder emails</a></li>
                      <li class="dropdown-item"><a tabindex="-1" href="#">MRI checklist</a></li>
                      <li class="dropdown-item"><a tabindex="-1" href="#">Practical information and instructions (location, time, hormone collection, etc.</a></li>
                      <li class="dropdown-item"><a tabindex="-1" href="#">Information letter and informed consent form</a></li>
                  </ul>
                </li>            
              </ul>
            </li>
          </ul>
    </div> 
</details>
LOOK AT OTHER DROPDOWNS HERE: https://www.w3schools.com/code/tryit.asp?filename=GHXH074WVN2W

Problem: buttons are not clickable anymore