# Data Management Plan
Before researchers collect data and travel to the field they have to create a data management plan (DMP).
The data management plan essentially answers three questions: the how, what and who about data collection.
Its purpose is to help you think through how and what you are collecting, to ensure qualoty control, and help you think through what equipment you need to collect ans store information

# Project + Field Trip Overview
- Include project_name (if there is an associated server folder) and brief summary of goals of field trip.
- Who is involved in the project and what are their roles?

# Who's permission to collect data do we have and need?
-Have you gotten permission to do field work and secured all the permits required for entry and collection? List permit numbers if available. List what is still needed.

# What Data Will Be Collected?
Categorize your data in a way that makes intuitive sense to you.
This is likely easiest be by data type/category (i.e. camera trap images, gps collar data, stone tools, field photos, fruit abundance paperforms)
Data could be:
1. digital (i.e. files), 
2. paper (i.e. handwritten sheets or field notebooks)
3. physical (DNA samples, tissues, geological samples)


# For All Data:
1. What "data type" is it? Behavioral, Ecological, Movement, Drone Imagery, Tissue Samples, Plant Material etc.
2. How will the data be collected?
	- camera traps
	- GPS trackers
	- accelerators
	- special software
	- surgery
	- rainfall gauges
	- interviews
	- drone flights
	- forms (i.e. ODK collect)

# For Paper Data
- How will this be collected? In what languages?
- Is there a template sheet that will be filled out (link if available)?
- How will you avoid common transcription errors 
	- i.e. underline numbers but not letters in things like 0S&O41LU8G4"
	- standardize a case (lower or upper) to be used
	- get a writing sample of all field assistants for their alphabet
- How and when will you digitally back this up? 
	- Photos in the field? 
	- Scans?
- 
# For Physical Data
- How will samples (i.e. tissue, poop, or plant)  be collected?
- How and where will samples be stored?
- How/if/where will samples be shipped (if known)?

# For digital data

## File Formats
1. What file format will it be in? (i.e.'.csv' , '.gpx' , '.shp' , '.txt' , .'mp4', '.tiff')
2. Do we need special hardware, software, or OS to view or collect data?

## File Organization
# How will you organize you data?
1. What is the folder structure your data will be stored in? 
 For this, verbal description, screenshots or print outs of working directories can be useful.
2. What will you name files so they are uniquely IDed and how?
	- i.e. all images are 'yyyymmddd_hhmmss_cameratraplocation_deployment'
	- i.e. for drone data 'yyyymmdd_fieldsite_sceneid'
	- Will this be done manually or via code using exiftool, sha4 hashing, and R package, or something else?
3. What will you label you columns in data collection for '.csv'
	- this can be a verbal description of what will go in the corresponding datatable metadata 'Readme' that explains each column or link to that file. Forethought is recommended.
	- a consistent style is useful
	- replacing whitespace with an _ or . or -
	- add units (e.g. mm or g)
	- avoid uppercase if possible
	- i.e. "tarsus_length_mm"

## Data Storage and Backup
# What is your plan for data storage and backup?
1. How much data (samples, gigabytes) do you plan to collect?
2. How  and how often you will back up your data in the field (you must store your data in at least 2 places (e.g. separate hard drives stored in different locations)
3. Do you have/need a special laptop, hardware, cables, or other equipment for data backup?
4. How many Hard Drives/ USB sticks/ SD cards do you need for backup
5. When will you be able to back up a version on the data to the cloud or Github?
6. When will you get the data on the MPI server?
7. Who performs data dumping and backup?

## Link to Data Catalog Entry Form (DCEF)
Please link to the location of the data catalog entry form or paste `.yaml` text here is possible
