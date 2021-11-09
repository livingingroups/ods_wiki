Before researchers go out into the field they have to create a data management plan (DMP).
The DMP needs to get emailed to and approved by Angie before field work. 
The goal of the DMP is to make sure researchers think through what data will be collected, how it will be organized and named, and backed up.
It is also closely linked to the data cataliog entry form, and much of the information used in that can be submittted with the DMP.

Data Management Plan (DMP)
For the Data Management Plan, researchers should record:

What data do you plan to collect
Give details on the kind of data: for example numeric (databases, spreadsheets), image, audio, video, and/or mixed media.
How will the data be organized
what is structure of folder system?
How will files be named?
if data is in a spreadsheet, where will the datatable metadata .txt or .md file be stored and what does each column include/mean (this can also be saved for after data collection but some initial thought should be given before hand) (i.e. what is the structure and how will the files be named and indexed)
Where you will store your data while in the field (e.g. hard drives)
How you will back up your data in the field (you must store your data in at least 2 places e.g. separate hard drives stored in different locations)
Plan for how often / at what point you will transfer + backup data
Ensure that you have the equipment required to transfer and store your data while in the field
This data management plan should also include all the info that goes into a standalone data catalog entry form, or the initial data catalog entry from .yaml can be drafted at this time and included with the DMP.

Data Catalog Entry Form (DCEF)
This Data Catalog entry form will eventually be formatted to a yaml to be sent to Garching. Researchers can create/store this info however they want, but creating a yaml using our website/Shiny app and updating it in the future will save them time in our department's workflow. I strongly recommend this from the beginning if possible.

Data that should be (propsed, but we need to decide) are recorded in the data catalog entry form are:

Project Name (proj_name) Projects should have a unique project id associated with them. This could/should be the name on the server folders. We might want to make this a selection from the dropdown menu.

People (person) For each person we should have:

Name
Institution
Email
Role
PI
Collaborators
HIWIs
Field Assistants
Lab Assistant
Analyst
Dates in Field It might be worth considering having a website, twitter, email or other means of contact as institutions change or if working with folks locally (i.e. WhatsApp or Address)
Locations (location)

Country
State/Province/Region
Name of protected area if applicable
name of research station if applicable
Lat/Long (need to decide on a format)
Species (species)

common name in English
local name at field site
Scientific name (Genus species)
File types (file_types)

.txt
.csv
.md
.yaml
.json
.gpx
.tiff (or other spatial formats)
.mp4 (or other video formats)
.mp3 (or other audio formats)
.pdf (i.e. scans)
.tex
Data Description (data_description)

Behavioral (focal follows, scans, etc., annotations)
Movement (gps collar, telemetry data, accelerometer)
Vocalizations
Ecological (i.e. species, plant surveys, soil samples)
Climatic
Camera Trap
Spatial (i.e. GPS)
Drone Imagery
DNA_samples
Tissue_smaples
Dates (dates)

Field Trip Duration
Data Collection Duration
Project Duration
Funding sources

Grants and Fellowships that contributed to paying for this project or giving researchers salaries.
Intellectual property

Data owner(s)
Stakeholders
Creative commons liscence
Embargo and justification
Tools

list of special tools/hardware needed to collect data
list of special software needed to open/access data
Research Overview

research area focus (i.e. movement ecology, bioacoustics, social learning, physiology)
intended audience
general goals (a few sentence summary of project goals)
Data Management

Backups (text describing this process and their location)
Secondary storage sites
Version comtrol (i.e. if code used to clean process data or stored in repos, give link to commit)
Data narrative

Any Additional information that will help you understand the data. Free text entry that could be linked to above
BJB to do-- add a timestamp of creation automajically to DCEF in shiny app
During Data Collection
DMP and DCEF updated if necessarey. Data is contasntly backed up.

After Data Collection
As soon as possible after you return from the field (e.g. your first day back in the office), you should deposit your raw data (in whatever form it is upon your arrival) onto the EAS data server. This should be done at the same time as filling out post-travel paperwork (for reimbursements) and returning / storing equipment.

Process of Initial Data Dump:
Upload all of your data into a single folder inside /EAS_shared/project_folder/working/UPLOADS/ on the server. The name of the folder should be your project name. The data will only be here temporarily while you are organizing it.
Update the Data Catalog Entry form to what will be sent to Garching with the packet of field data
In an overview/admin folder the DMP, DCEF, and any other important documents (i.e. .txt files explaining datatable metadata) should get depositef
Let Angie know that this has been updated and share with her the path on the server, and she can access the Data Catalog Entry Form. Angie will check over it, then initiate the process of initial data deposit and let you know when it is completed. Angie will store these Once completed, your data is backed up and you can begin the process of organizing it (without worrying about messing it up, as the raw data will always be recoverable!).
Note: If you have data from multiple projects, you can store them in multiple folders and provide a separate Data Catalog Entry Form for each project.

Behind the scenes:
Angie checks for completeness of metadata, passes metadata sheet and path to folder to Andreas
Andreas archives folder to Garching. Makes note of ZFS dataset and adds this to metadata sheet.
Andreas uploads metadata document to a version controlled metadata library (e.g. Github repository).
