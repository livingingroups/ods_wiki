# Old Stuff gfrom ODS wiki changed 6 Dec 2021
https://github.com/livingingroups/ods_wiki/wiki/Before-Data-Collection/
# Before Data Collection
**We collect valuable data that are accurate and reproducible.**
* Before starting data collection, we document how and what kind of data will be collected, and how those data will be stored and regularly backed up.
* Before starting data collection, we discuss and decide, among all collaborators, how the data will be collected, shared, used, and credited.

## 1. Data Management Plan
All researchers are required to fill out a data management plan before collecting data and going to the field.
This can be in whatever format the researcher desires.
We recommend version controllable formats like '.txt.', '.md', '.Rmd', '.txt' and 'yml' files. 
This file can get updated before, during, and after data collection. 

* Here is a [template Project ReadMe file](https://github.com/livingingroups/ods_wiki/wiki/Project-ReadMe-template) created by Vlad, Roi, Brendan, and Tracy. 
* Here is a [checklist](https://drive.google.com/file/d/1gktgpSEcRFaZqkQIjtechuP7vRVURgPE/view?usp=sharing) for the Project ReadMe created by Angie. 

## 2. Data Catalog Entry Form

#### Notes:

Tracy is not sure how the project metadata file will fit into the Project ReadMe (or if we want to call it a Project ReadMe or a DMP), but I tried to include all the relevant information in the updated Project Readme template for easy extraction using exif or something like that. 

If we move forward with the new draft Project ReadMe template, we only have partial examples. 

* [Project metadata example](https://github.com/livingingroups/project_metadata/blob/main/project_metadata/metadata_template.txt) (by Brendan) 
* [Project summary / some data stuff example](https://github.com/livingingroups/project_metadata/blob/main/project_readme/README_examples_KStewart.md#readme-example-1) (by Kat) 

Should we include these, make new examples, or not have any examples stored publicly?

Here are the old drafts of the various components that are now in the new draft Project ReadMe template:

* [Brendan's project metedata](https://github.com/livingingroups/project_metadata/blob/main/project_metadata/project_metadata.md)
* [Brendan's project readme](https://github.com/livingingroups/project_metadata/blob/main/project_readme/README.md)
* [Vlad & Roi's project readme](https://drive.google.com/file/d/1Nx3x_GRuTlbTcTjuh4VipTwN9jFYdn54/view)

Here are some comments from the previous version of this page that I kept for posterity:

Brendan thinks this [project metadata] should be a combination select from chosen options (country, researcher, species) free form text entry file.
It should easily interface with Andreas' backing up of the data to Garching. 
A `.yaml` might be the best format, but we might want to generate a form or something  that fills out `.yaml` files automagickly for everyone.
This needs to be figured out by Brendan and Angie, with input from group at large. 

# Code Commenting
## What kind of code needs to be commented?
All code that will be read and run by a human being (including yourself!) at any point needs to be appropriately commented on.
As our department is committed to making our code openly available alongside published papers, this is doubly important -- because uncommented
code can be just as useful as no code! 
Further, internal code review will be a crucial step for code written by EAS, so writing reader-friendly code ensures that you can get helpful feedback
from your code reviewers.

## What information goes in the comments?
This is a significantly more tricky question. First, tell the reader what the code does, and in the simplest terms, what steps are followed. 
Make sure that there is:

- **No redundant information.**
For instance: 

	```AverageVelocity = sum(AllVelocities)/len(AllVelocities) #Averaging over list of AllVelocities.```

	In this example, the comment is unnecessary.

- **No incomplete or inaccessible information** 
	Specifically, all *coding related* information that goes into the comments needs to be accessible within the same file or repository.
  However, comments might contain *content related* information that points at resources, to explain what the code is exactly doing.

- **Nothing that belongs implicitly.**
Avoid writing code that looks like:

	```
	a = open("file1.txt", "r") # file object containing contents of file1.txt
	a2 = [x for x in a] # list containing lines of a2
	
	for x in a2:
		do_foo(x) # apply function for all lines of file1 sequentially.

	```

	Instead, consider:

	```
	file1Object = open("file1.txt", "r")
	LinesIn_file1 = [line for line in file1Object]

	for line in LinesIn_file1:
		sensibly_named_function(line)
	```

	In other words, name code entities such that they are self-descriptive.
	
- **Functions need special attention.**
This is because functions are written so that they get called multiple times, sometimes in different contexts. First, it is important to
name functions in a sensible, consistent way. Preferably use short, verb-based names: `generate_freq_dyn_plots(x)` as opposed to `freq_dyn_plot_generator(x)`,
simply because this is more intuitive while reading the code. Next, use either docstrings or comments to mention 
	1. what all the arguments are (type and meaning),
	2. what the function returns, and
	3. what errors the functions might raise.

	For example,

	```
	def plot_histogram(file, bins):
		"""
		Reads numbers from a file, and plots their histogram.
		Args:
			- file (str): file containing the data.
			- bins (int): number of bins in the histogram.

		Returns:
			none

		Raises:
			NameError: If file doesn't exist.
		"""

		with open(file, "r") as FileObject:
			lines = [float(line.rstrip()) for line in FileObject]

		plt.histogram(lines, n=bins)
	```

	In the above example, the documentation for the function is in docstrings ("""...""") because python supports it. Otherwise, the same information will be in
	comments. Similarly detailed comments might also be necessary for important global variables and user-defined data structures.



Apart from this, it is important to note whether the information in your comments belongs in the code or in your README file. 
Some metadata about the code, and warnings, if any, also need to be incorporated, along with any information needed for people running, validating, or editing the code.

# Code Reproducibiltiy
https://github.com/livingingroups/ods_wiki/wiki/Code-reproducibility/
# READMEs

Your project should always include a README file with basic information that (at minimum) explains how to install and use your code and access any relevant datasets. Ideally the README should also include details about how the project is organized and links to any relevant information outside of the software repo (such as the publication the analysis was used for). For more information on READMEs, what they should include, and why you should use them, see:

- https://www.makeareadme.com/
- https://guides.github.com/features/wikis/

There are also numerous project templates that you can take advantage of to help you get started:

For R:

- https://github.com/KentonWhite/ProjectTemplate
- https://github.com/Pakillo/template
- https://github.com/TheZetner/r-project-template

For Python:

- https://github.com/pyscaffold/pyscaffold
- https://github.com/seanfisk/python-project-template
- https://github.com/drivendata/cookiecutter-data-science

# Managing dependencies

Often the most difficult part of reproducing an analysis is installing the correct dependencies for running the code. At minimum, you should include in your README the names and versions of every software package your code depends on to run. However, there are also tools to automate this process by reproducing the exact programming environment the code was developed with, and you should take advantage of these tools whenever possible.

For R:
- https://rstudio.github.io/renv/articles/renv.html

For Python:
- https://python-docs.readthedocs.io/en/latest/dev/virtualenvs.html
- https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html
- https://pip.pypa.io/en/latest/user_guide/#requirements-files

For managing dependencies outside of R or Python:
- https://www.docker.com/
- https://kubernetes.io/

# Data storage and access

Ideally your data should be stored on an open access database, where it can be downloaded and used to reproduce your results. Examples of general-purpose databases include:

- https://datadryad.org/stash
- https://zenodo.org/
- https://figshare.com/

However, this is not an exhaustive list, and there may be specialized repositories for the specific type of data you are working with.

# Minimal reproducible example

If your code or data are too computationally or memory intensive to fully reproduce the results of your analysis outside of your computing environment, you should instead strive to provide a minimal reproducible example with a subset of the data and a short script that reproduces the analysis for the provided data. Often a minimal reproducible example is used in the context of debugging, but the same principles apply for reproducibility. Some useful guides on the topic include:

- https://stackoverflow.com/questions/5963269/how-to-make-a-great-r-reproducible-example
- https://gist.github.com/hadley/270442
- https://stackoverflow.com/help/minimal-reproducible-example

# Data Metdata
https://github.com/livingingroups/ods_wiki/wiki/Data-metadata/

All raw and cleaned/processed data should include the following metadata, stored in a corresponding `ReadMe.txt` file that explains what the data is and how it was collected/processed. The goal of this `ReadMe.txt` file should be that any researcher, not knowing what the project is, can pick up the data file and be able to make sense of what it contains.

* If the data is plain text, the corresponding `ReadMe.txt` file should explain the contents of each column. For a csv, this file should have the variables/columns and their associated description, units, and value labels; the number of cases/rows; relevant codes for missing data (NA vs blank); and other specialized abbreviations.
* If the data is not plain text, the corresponding `ReadMe.txt` file should explain what the data is and how it was collected, cleaned, or processed.

An example, created by Kat, is [here](https://github.com/livingingroups/project_metadata/blob/main/project_readme/README_examples_KStewart.md#readme-example-2).

# old dmp
# Data Management Workflow

## Before 

Before researchers go out into the field they have to create a **data management plan** and fill out a **data catalogue entry form**. This needs to get emailed to and approved by Angie before field work. The DMP includes all of the info that will go into the DCEF, but the DCEF is a `yaml` that will allow us to search across years of data, and create a database of all the Garching Data Pallette/Uploads easily. In theory, researchers could save their DMP as a `.yaml` using the DCEF tool and just have one file.

### Data Management Plan (DMP)
For the Data Management Plan, researchers should record:
- What data do you plan to collect 
    - Give details on the kind of data: for example numeric (databases, spreadsheets), image, audio, video, and/or mixed media. 
- How will the data be organized 
    - what is structure of folder system?
    - How will files be named?
    - if data is in a spreadsheet, where will the **datatable metadata** `.txt` or `.md` file be stored and what does each column include/mean (this can also be saved for after data collection but some initial thought should be given before hand)
    (i.e. what is the structure and how will the files be named and indexed)
- Where you will store your data while in the field (e.g. hard drives)
- How you will back up your data in the field (you must store your data in at least 2 places e.g. separate hard drives stored in different locations)
- Plan for how often / at what point you will transfer + backup data
- Ensure that you have the equipment required to transfer and store your data while in the field

This data management plan should also include all the info that goes into a standalone data catalog entry form, or the initial data catalog entry from `.yaml` can be drafted at this time and included with the DMP.

### Data Catalog Entry Form (DCEF)
This Data Catalog entry form will eventually be formatted to a `yaml` to be sent to Garching. 
Researchers can create/store this info however they want, but creating a `yaml` using our website/Shiny app and updating it in the future will save them time in our department's workflow. I strongly recommend this from the beginning if possible.

Data that should be (propsed, but we need to decide) are recorded in the data catalog entry form are:

1. Project Name (`proj_name`)
    Projects should have a unique project id associated with them. This could/should be the name on the server folders. We might want to make this a selection from the dropdown menu.

2. People (`person`)
For each person we should have:
    1. Name
    2. Institution 
    3. Email
    4. Role 
        1. PI
        2. Collaborators
        3. HIWIs
        4. Field Assistants 
        5. Lab Assistant 
        6. Analyst
    5. Dates in Field
    *It might be worth considering having a website, twitter, email or other means of contact as institutions change or if working with folks locally (i.e. WhatsApp or Address)*

3. Locations (`location`)
    1. Country
    2. State/Province/Region
    3. Name of protected area if applicable
    4. name of research station if applicable
    4. Lat/Long (need to decide on a format)

4. Species (`species`)
    1. common name in English
    2. local name at field site
    3. Scientific name (*Genus species*)

5. File types (`file_types`)
    1. .txt
    2. .csv
    3. .md
    4. .yaml
    5. .json
    6. .gpx
    7. .tiff (or other spatial formats)
    8. .mp4 (or other video formats)
    9. .mp3 (or other audio formats)
    10. .pdf (i.e. scans)
    11. .tex

5. Data Description (`data_description`)
    1. Behavioral (focal follows, scans, etc., annotations)
    2. Movement (gps collar, telemetry data, accelerometer)
    3. Vocalizations
    4. Ecological (i.e. species, plant surveys, soil samples)
    5. Climatic 
    6. Camera Trap
    7. Spatial (i.e. GPS)
    8. Drone Imagery
    9. DNA_samples
    10. Tissue_smaples

6. Dates (`dates`)
    1. Field Trip Duration
    2. Data Collection Duration
    3. Project Duration
    
7. Funding sources
    1. Grants and Fellowships that contributed to paying for this project or giving researchers salaries.   

8. Intellectual property
    1. Data owner(s)
    2. Stakeholders
    3. Creative commons liscence
    4. Embargo and justification

9. Tools
    1. list of special tools/hardware needed to collect data
    2. list of special software needed to open/access data

10. Research Overview
    1. research area focus (i.e. movement ecology, bioacoustics, social learning, physiology)
    2. intended audience
    3. general goals (a few sentence summary of project goals)

11. Data Management
    1. Backups (text describing this process and their location)
    2. Secondary storage sites
    3. Version comtrol  (i.e. if code used to clean process data or stored in repos, give link to commit)

12. Data narrative
    1. Any Additional information that will help you understand the data. Free text entry that could be linked to above

## BJB to do-- add a timestamp of creation automajically to DCEF in shiny app


## During Data Collection
DMP and DCEF updated if necessarey. Data is contasntly backed up.

## After Data Collection
As soon as possible after you return from the field (e.g. your first day back in the office), you should deposit your raw data (in whatever form it is upon your arrival) onto the EAS data server. This should be done at the same time as filling out post-travel paperwork (for reimbursements) and returning / storing equipment. 

#### Process of Initial Data Dump:

1. Upload all of your data into a single folder inside `/EAS_shared/project_folder/working/UPLOADS/` on the server. The name of the folder should be your project name. The data will only be here temporarily while you are organizing it.
2. Update the Data Catalog Entry form to what will be sent to Garching with the packet of field data
3. In an overview/admin folder the DMP, DCEF, and any other important documents (i.e. `.txt` files explaining datatable metadata) should get depositef
3. Let Angie know that this has been updated and share with her the path on the server, and she can access the Data Catalog Entry Form. Angie will check over it, then initiate the process of initial data deposit and let you know when it is completed. Angie will store these Once completed, your data is backed up and you can begin the process of organizing it (without worrying about messing it up, as the raw data will always be recoverable!). 

**Note:** If you have data from multiple projects, you can store them in multiple folders and provide a separate Data Catalog Entry Form for each project.

### Behind the scenes:
1. Angie checks for completeness of metadata, passes metadata sheet and path to folder to Andreas
2. Andreas archives folder to Garching. Makes note of ZFS dataset and adds this to metadata sheet.
3. Andreas uploads metadata document to a version controlled metadata library (e.g. Github repository).

##### A similar process can occur for organized data, which we will update later

## data catalog entry form `.yaml` example
```yaml
# Project Metadata: Coiba_Capuchins_2021_07
project_name: Coiba_Capuchins_2021_07
person_01:
  name: Brendan Barrett
  institute: MPI-AB
  email: bbarrett@ab.mpg.de
  role: PI
  date: 2021-07-14 - 2021-07-27
person_02:
  name: Zoë Goldsborough
  institute: MPI-AB
  email: zgoldsborough@ab.mpg.de
  role: PhD Student
  date: 2021-07-14 - 2021-07-27
person_03:
  name: Claudio Monteza
  institute: MPI-AB
  email: cmonteza@ab.mpg.de
  role: PhD Student
  date: 2021-07-14 - 2021-07-22
person_04:
  name: Meredith Carlson
  institute: UC Davis
  email: mkcarlson@ucdavis.edu
  role: PhD Student
  date: 2021-07-14 - 2021-07-26
person_05:
  name: Evelyn del Rosario
  institute: UC Davis
  email: delrosarioev@gmail.com
  role: Field Assistant
  date: 2021-07-14 - 2021-07-26
species_1:
  name_eng: white-faced capuchin monkey
  name_loc: mono cariblanco
  name_sci: Cebus imitator
location_1:
  country: Panama
  region: Veraguas
  park: Coiba National Park
  field_station: Rancheria
  lat_log: 7.4264649608 N; -81.7595969616 E
data_file_type_overview:
  file_type_1: csv
  file_type_2: gpx
  file_type_3: jpg
  file_type_4: mp4
  file_type_5: XLSform
data_description:
  data_desc_1: Ecological (i.e. species, plant surveys, soil samples)
  data_desc_2: Camera Trap
  data_desc_3: Spatial (i.e. GPS)
  data_desc_4: DNA Samples
dates:
  Field Trip: 2021-07-17 - 2021-07-25
  Data Collection: 2021-07-17 - 2021-12-31
  Project Duration: 2017-03-20 - 2021-12-31
funding_sources:
  fund_1: Max Planck Geschellschaft
  fund_2: Packard Foundation Fellowship (2016-65130)
```
https://github.com/livingingroups/ods_wiki/wiki/data_management_plan_and_data_catalog_entry_form

# During Data analysis
https://github.com/livingingroups/ods_wiki/wiki/During-Data-Analysis

**We analyze data clearly, honestly, and reproducibly.**
* We are intentional about how we organize projects, storing our data, metadata, scripts, figures, and publications in a clear file structure that is user-friendly.
* These file structures are backed up, with clear version controlling. 
* The rationale for our analytical choices is clearly commented in our code, our notebooks, and our publications.
* When possible, we engage in internal code review with collaborators before submitting a manuscript, and give credit to those reviewers.

## 1. Organize data analysis in a reproducible, accessible, and version-controlled way

* Tips for [project organization](https://github.com/livingingroups/ods_wiki/wiki/R-Project-folder-organization) for R projects and data analyses
* Suggestions for [reproducibility and accessibility](https://github.com/livingingroups/ods_wiki/wiki/Code-reproducibility)
* Guidelines for [version control](https://github.com/livingingroups/ods_wiki/wiki/Version-control)

## 2. Clearly track and explain analysis choices

* Keep a [research notebook](https://github.com/livingingroups/ods_wiki/wiki/Research-notebooks)
* Use clear [code commenting](https://github.com/livingingroups/ods_wiki/wiki/Code-commenting)

## 3. Engage in [internal code review](https://github.com/livingingroups/ods_wiki/wiki/Code-review)

# During Data Processing
https://github.com/livingingroups/ods_wiki/wiki/During-Data-Processing

**We process data carefully, deliberately, and reproducibly.**
* Before cleaning or processing, raw data are archived on the MPI servers.
* Data cleaning, when possible, is done reproducibly with version-controlled scripts.  Any non-scripted steps are clearly documented in an accompanying 'ReadMe' text file alongside up-to-date **data metadata** describing all variables/types of data.
* Final cleaned and processed data are made available for internal use in the department, with collaborators, and/or as part of a publication.
* Whether working on our projects in the field, in the lab, or on the computer, we document our scientific process fully in a sharable, backed-up, and version-controlled format that is appropriate for the conditions and constraints of our situation.

## 1. Back up raw data

Raw data is files that have not been touched, renamed, or edited. 
This includes audio files, video files, images, forms from data collection apps like ODK, GPS data, and photos or scans of paper data.

Raw data should be backed up in the field according to the Project ReadMe. 
When a researcher returns from the field, all of their raw data should be uploaded to `/EAS_shared/project_folder/working/UPLOADS/` on the server. The data will only be here temporarily while you are organizing it. 
Remember to add the appropriate [**data metadata**](https://github.com/livingingroups/ods_wiki/wiki/Data-metadata) to all your raw data folders and files during this organization process. 

Information on how to access the server and back up data to your project folder is [here](https://docs.google.com/document/d/1vr5eixo8s2JO7fcm9A3_HDylsmC_Rpawt2IreoC8cQg/edit?usp=sharing).

The **Data Catalog Entry Form** should be updated and sent to Angie. This form will contain **project metadata**.

#### Notes:

Tracy thinks that more information would be helpful here.
What happens after the temporary working uploads? Where does the raw data end up? What is the Data Catalog entry form? When should it be filled out?

## 2. Update Project ReadMe, Project Metadata, and field folder

After returning from the field, the [Project ReadMe](https://github.com/livingingroups/ods_wiki/wiki/Project-ReadMe-template) should be updated to match what actually happened in the field. This includes [updating the project metadata YAML](https://github.com/k-hench/shiny_yml).
Include as much detail as possible, including errors/mishaps that might affect the data.
Because the Project ReadMe is version-controlled, your original plans will also be saved.

The field folder in your **server project folder** should also be updated with relevant information as to the field site, logistics, and other details that will be helpful for future researchers or for future you. 
All field researchers should collaborate together to include as much necessary information as possible. 

Please also add copies of any additional permits (e.g., export permits) obtained in the field, and add that info to the project metadata as well.

#### Notes: 

Tracy added this section in response to section 12 of [Brendan's Project ReadMe](https://github.com/livingingroups/project_metadata/blob/main/project_readme/README.md). 
It seems like these field details that change dramatically between field seasons and that do not affect the data do not really belong in the Project ReadMe. 
However, I agree that they should be written down somewhere and suggest above that we make a field folder in the project folder on the server. 
What do you think? Feel free to change/delete at will.

## 3. Version-control data cleaning and processing

All of our steps for data cleaning and processing will be versioned controlled.

Anything that is not done via scripting will have a clearly laid out explanation and instructions in a ReadMe file.

Resources for version control are [here](https://github.com/livingingroups/ods_wiki/wiki/Version-control). 
Resources for scripting and many other aspects of open data science are [here](https://github.com/livingingroups/resource_and_tutorials) and [here](https://github.com/livingingroups/ods_wiki/wiki/Code-reproducibility).

## 4. Back up cleaned data

Cleaned data, along with the code used to clean it, should go into the "processed" folder of the "working" folder in your **server project folder**.
This includes reorganized, reinventoried, and renamed files as well as output from behavioral annotation.
Remember to add the appropriate [data metadata](https://github.com/livingingroups/ods_wiki/wiki/Data-metadata) to all your cleaned/processed data folders and files. 

Recommended file naming conventions include using yyyy.mm.dd for all multimedia files and data files collected on a single day.
For images, videos, and audio files (and some others) this can be automated using exiftool in batch format in the command line. 

# During Data Analysis
**We analyze data clearly, honestly, and reproducibly.**
* We are intentional about how we organize projects, storing our data, metadata, scripts, figures, and publications in a clear file structure that is user-friendly.
* These file structures are backed up, with clear version controlling. 
* The rationale for our analytical choices is clearly commented in our code, our notebooks, and our publications.
* When possible, we engage in internal code review with collaborators before submitting a manuscript, and give credit to those reviewers.

## 1. Organize data analysis in a reproducible, accessible, and version-controlled way

* Tips for [project organization](https://github.com/livingingroups/ods_wiki/wiki/R-Project-folder-organization) for R projects and data analyses
* Suggestions for [reproducibility and accessibility](https://github.com/livingingroups/ods_wiki/wiki/Code-reproducibility)
* Guidelines for [version control](https://github.com/livingingroups/ods_wiki/wiki/Version-control)

## 2. Clearly track and explain analysis choices

* Keep a [research notebook](https://github.com/livingingroups/ods_wiki/wiki/Research-notebooks)
* Use clear [code commenting](https://github.com/livingingroups/ods_wiki/wiki/Code-commenting)

## 3. Engage in [internal code review](https://github.com/livingingroups/ods_wiki/wiki/Code-review)

# Internal Code Review
>*"When possible, we engage in internal code review with collaborators before submitting our manuscript, and give credit to those reviewers."*  

### Overview  
A critical component of reproducible and open science is the quality of code that we produce. The code used to process our data, conduct analyses, and visualize results will be [stored securely]() (link to other section), [shared alongside our scientific products]() (link to other section), and will meet quality standards. As a department, we commit to producing code that:

1. is understandable, 
2. can be run by others, and 
3. does what we claim it does. 

To achieve these goals, code published by members of the department will undergo review by one or more other scientists in the department. We recognize that code review is a labor intensive process, so we commit to crediting code reviewers for their work. We also recognize that the format, timing, workload, and credit associated with code review will vary from project to project. Finally, we also recognize that code review is a good opportunity for mentorship, so we encourage mentorship-oriented code review formats such as group code review or joint code review by authors and reviewers.

With flexibility in mind, we first commit to minimal requirements for code review within the department, then discuss additional models for implementing code review, and present a template to guide organization and documentation of code review. 

### Minimal Requirements
Before publishing a scientific product, we commit to ensuring that our code is reviewed by someone else. Minimally, code should be reviewed immediately prior to submission of the scientific product, but iterative code review throughout the project is also acceptable. Code reviewers and authors should discuss how the code reviewer(s) will be credited before engaging in code review. When approaching potential code reviewer(s), authors should consider the expertise of the code reviewer(s), the workload and complexity of the code, and the potential for code review as a venue for mentorship. If code reviewers need assistance reviewing the code, authors and code reviewers can walk through code together, or multiple code reviewers can work as a team. Here is a minimal code review checklist: 

#### Minimal code review process checklist

- [ ] Author identifies and approaches potential code reviewer(s)
- [ ] Author sends results and code to potential code reviewer(s) to give an idea of workload
- [ ] Author specifies what code reviewer(s) should evaluate (minimal list described below in outcomes checklist)
- [ ] Author and code reviewer(s) together determine how code reviewer(s) will receive credit for code review
- [ ] Author and code reviewer(s) together discuss the specific mechanics of code review (e.g., how feedback will be delivered and documented)
- [ ] Author and code reviewer(s) together determine a deadline for code review
- [ ] The terms of code review are documented and shared with code reviewer(s) and author(s)


#### Minimal code review outcomes checklist  

- [ ] Check that code is commented, organized, and understandable
- [ ] Check that code runs on a new machine 
- [ ] Check that reported results are reproduced on new machine
- [ ] Code reviewer receives credit for their contribution to the project
- [ ] The full code review process (agreement, feedback, and code changes) is documented and backed up alongside other project files

### Credit for code review
Below is a non-exhaustive list of ways code reviewers could be credited. It is critical that authors and code reviewers engage in early discussion of how code reviewers will be credited for their work. If circumstances of code review change, authors and code reviewers should re-open discussion about credit for code review as soon as possible. Guidelines here are necessarily flexible, as code review can entail very different workloads depending on the project and the expectations agreed upon by code reviewers and authors. 

* Authorship on manuscript
* Authorship on separate data/code publication
* Authorship on data repository (e.g., Dryad) submission
* Acknowledgements
* Commitment to reciprocal code review

### Advanced code review
Although the above are the minimal requirements for code review, members of the department are encouraged to engage in more extensive code review that is tailored to meet the needs and strengths of authors and code reviewers. Advanced code review should be accompanied by appropriate credit to code reviewers, as it is a large intellectual and time investment. As an example format, advanced code review might occur iteratively and lead to authorship on the manuscript for the reviewer. Here are some important potential goals of advanced code review that are not met by the minimal requirements:  

* Check for mistakes in code (i.e., "does code do what it says it does?" )
* Evaluate analysis decisions
* Evaluate efficiency of code

### Summary
We commit to ensuring the reproducibility of our science through code review, and to crediting code reviewers. Products from the department must meet minimal code review requirements. The terms of code review, the feedback from code reviewers, and resulting changes to code will be documented and backed up alongside other project files. We recognize and value code review as a venue for mentorship and training, and authors and code reviewers should work closely early in the process to ensure that code review provides the most benefit to the project, the department, and the individuals involved. 

***


<h1 align = "center"> Code Review Template </h1>

##### Author(s) _______________________________________  
  
##### Code reviewer(s) ___________________________________________

### Code review agreement  

##### Date ___________________  

- [ ] Author identifies and approaches potential code reviewer(s)
- [ ] Author sends results and code to potential code reviewer(s) to give an idea of workload
- [ ] Author specifies what code reviewer(s) should evaluate (minimal list described below in outcomes checklist)
- [ ] Author and code reviewer(s) together determine how code reviewer(s) will receive credit for code review
- [ ] Author and code reviewer(s) together discuss mechanics of code review (e.g., joint vs. independent code review, how feedback will be delivered, etc.)
- [ ] Author and code reviewer(s) together determine a deadline for code review
- [ ] The terms of code review are documented and shared with code reviewer(s) and author(s)

What will the code reviewer(s) evaluate (must at least meet minimum requirements)?
  
  
How will the code reviewer(s) be credited?
  
  
Describe the specifics of how code review will take place. How will feedback be delivered and documented? If multiple code reviewers and/or authors will be involved, how will this be coordinated? How will resulting code changes be documented?
  
  
When will the code reviewer(s) submit their feedback to the author(s)?
  
  
Other notes from initial meeting:  
    
  
  
### Code review outcomes
- [ ] Check that code is commented, organized, and understandable
- [ ] Check that code runs on a new machine 
- [ ] Check that reported results are reproduced on new machine
- [ ] Code reviewer receives credit for their contribution to the project
- [ ] The full code review process (agreement, feedback, and code changes) is documented and backed up alongside other project files

Have other elements of the code review agreement been met? List these here: 

# project read me template old
https://github.com/livingingroups/ods_wiki/wiki/Project-ReadMe-template/_edit

# Project Name 

Your project name should match the name of your **server project folder**.

## Person in Charge of The Work: 
* Name and email

## Project Metadata: 

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

## Project Summary: 

Aims, research questions, hypotheses, and predictions (1 paragraph)

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

# R project Folder organization
https://github.com/livingingroups/ods_wiki/wiki/R-Project-folder-organization

# How to organize your R project for analysis
Our general approach is that we are intentional and explicit about how we organize projects, storing our data, metadata, scripts, figures, and publications in a clear file structure that is user-friendly.

A very common, and extremely helpful, recommendation to realize this aim is to organize projects in folders (Wilson et al. 2017). This means that all files that are used for a project (including code, text, results, plots, and data) should be included in a single folder. The following structure largely follows the suggestions by Wilson et al. 2017 with some modifications and references to discussions that came up during our meetings addressing some of the potential exceptions.

## 1. The project folder should be named after the project
This folder should include a readme file briefly describing the project (e.g., aims, collaborators)

## 2. Use the following sub-folders (names are just suggestions)

### \doc
For text documents, such as drafts for manuscripts, documentation of the observational methods and experiments, discussion notes, electronic notebooks, etc.

### \data
This folder should include the data used for the analysis or at least an example data set to reproduce the analysis (link to other part). The metadata in the folder should include a description of the data.

### \results
This folder includes the processed data and generated files (cleaned data, simulated data), results of statistical models (either saved model objects and/or tables with results), and possibly plots.

### \plots
Optional if the plots are not included in the results folder. 

### \src
Includes the source code required for the project. In addition to the code required to prepare the data, to run the analysis, and to create summary tables and plots, this folder should also include one (or multiple) 'controller scripts' in the main \src folder (something like 'runall'), which can be used to run the entire analysis (_provide example for R?_). This script can also be used to set some of the global parameters. Alternative name: "\code".

### \bin
For projects using compiled language (e.g., C++), this folder contains the executable programs compiled from src

## 3. Name files to reflect their content or function
For example, name the script for preparing the focal observation data for further analyses `prepare_focal_data.R`, or the results from home range estimates `home_range_estimates.gpkg`

## 4. Synchronized the folder with GitHub
A great option to enable version control for your entire project and to always have a backup is to make the entire project folder git-controlled. This is also great for collaborative projects. In case the project is not yet ready for the public, this can be done in a 'private' repository

## 5. Additional considerations

### 5.1 Data
There are some situations when it is not feasible or helpful to include the entire data set in a project folder:
- For example, when analyzing large datasets of videos, it might not be possible or desirable to put all these files in the project folder and synchronize all these files, e.g., with GitHub.
- Also, if several projects are using the same datasets, having multiple copies of these datasets can create issues with having multiple, but somehow different copies of the same data (in case these datasets were further processed/cleaned for each  project).
- If data are downloaded from a data base, only include the actual data used for the project, the code used to get the data from the data base, and information about the date when the data was fetched.

### 5.2 Splitting up project
In many cases, it might be helpful to have one project folder per manuscript/paper as this is the 'natural unit' of scientific analyses. However, sometimes several projects are closely related and use the same data set. In such cases it might good to 'outsource' some of the data preparation and processing steps into a separate folder that is referred to in the main projects. Nevertheless, the processed dataset to run the final analysis should still be included.

### 5.3 Where to put commonly used code?
Sometimes, several projects use the exact same scripts, such as complex code to calculate food resources in a home range. In such cases, one possibility is to create a package. In this case, however, it is important to either keep track of the version of the package used for a specific analysis or to make a copy of the entire package, which can be included into the project folder as well.

### 5.4 Example for the folder structure of a project

- my_research_project
	- doc
	- data
	- src
		- runall.R
		- \data_preparation_scripts
			- prep_behavioral_data.R
			- prep_ecological_data.R
		- \analysis_scripts
			- run_models.R
		- \plotting_scripts
			- create_ranging_plot.R
	- results
	- plots
  





