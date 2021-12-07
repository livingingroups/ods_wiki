# Project ReadMe Documentation for MPI-AB Ecology of Animal Societies Projects

After returning from the field all researchers are required to fill out a **Project ReadMe**. 
This includes all important details about data collection protocols, descriptions of what was done to maintain and organize data (or links to scripts and corresponding repositories and files), and details about who and what was invoved in data collection and methods. 
They also contain a brief summary of the project and its goals, things that happened in the field, hardware, software and  fieldnotes.

A really high quality **Project ReadMe** could serve as part of the methods section of a paper. Much of the work you did to create the data catalog entry for and the data management plan will be updated and placed into the project ReadMe.

The goal of this file should be that any researcher, not knowing what the project is, can pick it up and be able to make sense of what it contains. 

## Naming and File Standards for a Project ReadMe
A project readme can take the format of any file type you desire. However, plain text, version controlable formats are strongly recommended (i.e. `.md` , `.txt`, `.RmD` , `.TeX`).

File format name should be 'data_catalog_entry_id__projectname__project_readme.md'


## When do I complete my project README file?
In the days and weeks immediately following a field trip or conclusion of a local study/experiment.

## Where can I find examples of project ReadMe's?
In this folder you can templates.

Below are examples from other reearcher's projects.
1. Kat's Bonobo Project
2. Brendan's Coiba or Woodrat Project

# What should I include in the Project ReadMe?

## 1. Person in Charge of The Work: 
* Name and email

## 2. Project Summary: 

Aims, research questions, hypotheses, and predictions (1 paragraph)

## 3. All the information from the updated Data Catalog Entry Form. 
This can be linked or the file output can be pasted directly or formatted to your heart's desire.

### Species:
For each species used in the project:
* Common name (English)
* Local name
* Scientific name (*Genus species*)

### Locations:
For each location at which data was collected:
* Country
* State/Province/Region
* Name of protected area or research station
* Lat/Long

### Dates:
For each field season/trip:
* Arrival date in country/location
* Departure date from country/location
* Data collection start date
* Data collection end date

### People: 
For each person involved in project planning, data collection, data analysis, or writing: 
* Name
* Role (PI, collaborator, veterinarian/darter, HIWI/undergrad, field assistant, lab technician, data analyst)
* Institution
* Email
* Permanent contact information (e.g., WhatsApp, Facebook/Twitter, website, other emails, physical address)
* Dates in field (if applicable)

### Permits:
For all official permits or permissions obtained:
* Permit name
* Permit granting organization
* Permit number

Copies of all approved permits should be stored in your **server project folder**.

If you are not required to get ethical permission to conduct research, include a link to the ethical and animal welfare guidelines you will be following. See suggestions [here](https://github.com/livingingroups/ods_wiki/wiki/Before-Data-Collection#2-ethics-and-permits).

### Funding:
Record all institutes that contribute to paying for the project or for research salaries. 

For each grant or fellowship that contributed to paying for the project or researcher salaries:
* Grant name/type
* Grant awardee (individual)
* Grant number

## 4. Details about Data Collected and where they are Stored

### Folder Structure and Organization
This can be updates infor from your data management plan. 
Include server locations and github repos. 
Information can be copied frpom data managemnt plan and updated.

### File Naming Conventions

### File MetaData
Details about what files are where and links to or information about corresponding *datafile metadata*.
This is information about is in each column, units, and titles to help another person make sense of data `.csvs`


### 5. Hardware for Data Collection

Having an idea of who used what in the field might be ideal to know what things were collected with. 
I am thinking of models of devices where their accuracy, or sensitivty changes over years, with enough of an impact to affect inference 
(i.e. consider accuracy of GPS collars changing oer the years, or sensitivty of camera traps changing with models). 
This matters for analysis.
If this equipment gets checked out from Angie, we can link to that info. 
Otherwise we case have researchers add details.
1. Device Manufacturer and Version (i.e. Reconyx Hyperfire 2 or Garmin Inreach GPSs60)
2. Serial No or internal code (if this matters...)
Some of this data can be extracted from the raw data if need be (i.e. camera model and serial number info using EXIFtool). We should inform where that can be found.

### 6. Software for Data Collection and Viewing
If special proprietary software or code was used for data collection in the field, info on it should be provided (or links to source code). Examples include:
1. Software name, make, serial number
2. Link to source code
3. Link to form (i.e. if something like ODK or KOBO collect is used)

### 7. Methods
Describe methods for data collection so we know how data came into existence. 
This can go in your paper anyway, and writing it up now will save headache down the line in 10 years once you finally get around to writing these papers we think will just take "a few weeks." This includes:
	1. Sampling Design
	2. Sampling Effort
	3. Animal handling/Collaring Protocols

* **Animal capture/handling procedures**: Include your capture protocol, as well as the drugs/anesthetic, dosages, and supplies used. Record the number of individuals and groups sampled and their respective dates and times of capture.

* **Biological sample collection and storage**: Include how samples are collected, by whom, and using what supplies. Detail where/how samples are stored in the field, how samples are recorded and tracked, and how samples are exported to another country. Include the medical supplies (manufacturer and model) used for sample collection and storage. 

* **Tag data (often GPS/ACC data)**: Include the manufacturer and model of the tags and the sensors used. Record the start and stop dates and times of the tags, on which individuals they are deployed, and the sampling resolution. Keep extremely detailed records of the tag/sampling settings and store those with the data. Detail how tags are deployed, how data are downloaded, and how tags are retrieved. 

* **Experimental procedures**: Record experimental procedures, dates, times, and notes.

* **Observational behavioral data**: Include behavioural sampling protocols for demographics, movement, and behavior. 

* **GPS data**: Sampling Protocol of GPS, Model, Measurement Units

* **Ecological data**: 

* **Climatic data**: Record how and when temperature, rainfall, and other climactic data are collected.

* **Camera trap data**: Camera Settings, Batteries Used, Models, Mounting Technique

* **Vocalization data**: 

* **Drone imagery**: Include the drone manufacturer and model number, drone flight plan (flight path and sampling resolution), drone pilot, and the dates and times of flights. 

	
### 8. Field Notes
	Having a text file of useful field notes would be a good idea, aprticularly if someone pick up your project or visits your site in the future.
	This can also include helpful contacts (i.e. cab drivers, friends), places(safe places to stay, restaurants), stores (where to get the weird equipment you need in a city).
	Perhaps things related to "the field" vs, the logistics in getting to the field could be separated. 
	This should also include relevant permit numbers. 




## Description of The Data: 

### What data (for example the kind, formats, and volumes) will be collected, produced, or re-used? 
* Give details on the kind of data: for example, numeric (databases, spreadsheets), textual (documents), image, audio, video, and/or mixed media.
* Give details on the data format: the way in which the data is encoded for storage, often reflected by the filename extension (for example pdf, xls, doc, txt, or rdf).
* Justify the use of certain formats. For example, a preference for open formats, standards accepted by data repositories, widespread usage within the research community, or on the software or equipment that will be used. 
* Give preference to open and standard formats as they facilitate sharing and long-term re-use of data (several repositories provide lists of such ‘preferred formats’).
* Give details on the volumes (they can be expressed in storage space required (bytes), and/or in numbers of objects, files, rows, and columns). 

### How will new data be collected or produced and/or how will existing data be re-used?
* Explain which methodologies or software will be used if new data are collected or produced. Include the names and models of all hardware, software, or specialized supplies that you use to collect data. If detailed protocols already exist, you can link to separate files in your **server project folder** by including the exact file name and location in the sections below. 
* State any constraints on re-use of existing data if there are any. 
* Briefly state the reasons if the re-use of any existing data sources has been considered but discarded.

Fill out your planned methodology prior to your field season, and update this document upon your return. 

* **Animal capture/handling procedures**: Include your capture protocol, as well as the drugs/anesthetic, dosages, and supplies used. Record the number of individuals and groups sampled and their respective dates and times of capture.

* **Biological sample collection and storage**: Include how samples are collected, by whom, and using what supplies. Detail where/how samples are stored in the field, how samples are recorded and tracked, and how samples are exported to another country. Include the medical supplies (manufacturer and model) used for sample collection and storage. 

* **Tag data (often GPS/ACC data)**: Include the manufacturer and model of the tags and the sensors used. Record the start and stop dates and times of the tags, on which individuals they are deployed, and the sampling resolution. Keep extremely detailed records of the tag/sampling settings and store those with the data. Detail how tags are deployed, how data are downloaded, and how tags are retrieved. 

* **Experimental procedures**: Record experimental procedures, dates, times, and notes.

* **Observational behavioral data**: Include behavioural sampling protocols for demographics, movement, and behavior. 

* **GPS data**: 

* **Ecological data**: 

* **Climatic data**: Record how and when temperature, rainfall, and other climactic data are collected.

* **Camera trap data**: 

* **Vocalization data**: 

* **Drone imagery**: Include the drone manufacturer and model number, drone flight plan (flight path and sampling resolution), drone pilot, and the dates and times of flights. 

* **Field notes**: Record how field personnel keep track of daily activities and take notes on unusual circumstances.

## Data Quality and Standards: 

### What data quality control measures will be used? 
* Explain how the consistency and quality of data collection will be controlled and documented. This may include processes such as calibration, repeated samples or measurements, standardized data capture, data entry validation, peer review of data, or representation with controlled vocabularies.


## Storage and Backup During the Research Process:

### For each type of data listed above:
* Include a detailed plan of where the data will be stored and backed up during research activities and how often the backup will be performed. It is recommended to store data in least at two 
separate locations. 
* When you return to Germany, upload your data to your **server project folder**. Instructions are [here](https://github.com/livingingroups/ods_wiki/wiki/During-Data-Processing#1-back-up-raw-data).
* Include the file type, names, and location of all raw data, as well as of all cleaned/processed data. Each file or type of raw data should have [metadata] https://github.com/livingingroups/ods_wiki/wiki/Data-metadata) stored in a separate text file that located with the raw data.

## For sensitive data, particularly personal data: Ensure that when dealing with personal data, data protection laws (for example GDPR) are complied with:
* Gain informed consent for preservation and/or sharing of personal data.
* Consider anonymization of personal data for preservation and/or sharing (truly anonymous data are no longer considered personal data).
* Consider encryption (the encryption key must be stored separately from the data, for instance by a trusted third party).
* Explain whether there is a managed access procedure in place for authorized users of personal data.
* Explain who will have access to the data during the research and how access to data is controlled, especially in collaborative partnerships. 
* Consider data protection, particularly if your data is sensitive (for example containing personal data, politically sensitive information, or trade secrets). Describe the main risks and how these will be managed.
*  Explain which institutional data protection policies are in place.

