# Data Management Plan Coiba Capuchins Des 2021-Jan 2022

## Project Overview
### Project Name and Server Folder
"coiba_capuchin" on `10.126.19.90/EAS_shared/capuchin_coiba/working/newdata/capuchins_coiba_dec_2021_jan_2022 `

### Summary of study
This project has existed since 2017 studying stone tool use, social behavior, genetic uniqueness, and archaeology of the only tool using populations of the genus *Cebus* in the world.

## Field Trip Summary
### Goals of Field Trip
The goals of this 18 day (in total) field trip are to:
1. Continue baseline camera trap data collection and collect old data
2. Set up baseline phase on *Nerita scabricosta* and material selectivity experiments for ZG and MC dissertations
3. Evaluate effectiveness of modified camera sampling protocol
4. Conduct routine archaeological surveys
5. Get Meredith out to Coiba to get material availability data, set up her accumulation studies, and see site
6. Have Tamara measure material hardness in fields an collect hair and food for isotope and nutrient analysis
7. Explore and set up an array of cameras at Rio Escondido
8. Collect additional hammerstones for Lydia Luncz
9. Intensive DNA sampling
10. Photograph capuchins (Christian)

### Personel
Brendan Barrett, Zoë Goldsborough, Evelyn del Rosario, Tamara Dogandzic (MPI-EvAn), Meredith Carlson (UC Davis), Pedro Castillo, Tobias Beeger, Christian Ziegler, Meg Crofoot (maybe?), Odd Jacobson

## Permits
This research is approved under SE/A-6-2020 and associated addendumz. A addendum for snail collection permissions is currently in review. A fecal/hair export permit will be applied for in Dec 2021, but collection is feasible under current permit.

## Data To Be Collected

### Camera Trap Images
We will deploy our routine 10 video cameras (Ultrafire II Professional) and still (traps (Hyperfire II Professional) at Jicaron and collect Data from old SD cards.
We will add a secondary camera to the location when possible.
3 Tidelapse Cameras Will be collected on Coiba and Jicaron, and potentially  another 8-10 will be deployed if preliminary results look promising.
We will also collect 9 streambed cameras and deploy up to 16 more.
Up to 10 cameras will be deployed at Rio Escondido.
Cameras are preprogrammed, loaded with lithium batteries, and SD cards before going into the field.

Camera Trap collected on this trip is Deployment R10.

Images (`.jpg`) and videos (`.mp4`) are named using location_id__deployment_ID__yyyy_mm_dd__hh_mm_ss_(seq_id) using exiftool and R scripts version controlled in [this GitHub Repo](https://github.com/bjbarrett/camtrap_coiba/tree/main/exiftool_renaming). Files folders are created this way for dumping as well.

We will need a computer w/ SD card slot or SD card adapter for the Field to download this data.

Camera Trap Data Deployment Infor is Collected using an Kobo Collect Form app on (2) Android Phones.

### GPS Points
GPS Points are Collected Using a Trimble R1 and (2) Handheld Garmin GPS devices. 
Trimble needs to be locally calibrated for 24 hours before being used in the field.
Garmin Files `.gpx` are names by day collected i.e. `coiba_dec2021_jan2022_yyyymmdd`. 
Other coordinates are collected into Kobo Collect Form.

### Stone Tool Data
#### Surveys
Using calipers and hanging scales we collect measurement of dimensions, weight, and height or tool sites. 
Coordinates and Photos of Sites are taken as well.
This is all saved as am `.xls` form, `.csv` , and `.jpg` files built into, and managed with an existing, version controlled Kobo Collect Form.
Template [is here](https://github.com/bjbarrett/coibatooldata/tree/master/data/tool_data/coiba_capuchin_tool_survey_kobo) 

#### Raw Material Availability
This data (length and width in mm @ 25,50,75 percent , height in mm, and mass in g ) and shape (Indeterminate, Rectangular, Oblate, Spheroid, Irregular) is recorded in a write in the rain notebook. This is photographed at the end of each day and manually entered into a `.csv` [Example file is here for dataframe structure](https://github.com/bjbarrett/coibatooldata/blob/master/data/tool_data/raw_material_survey/TransectsJicaron.csv)/

### DNA Samples
Poop (~ 5 mL) is stored in 5 mL of RNA-later in a 15 mL falcon tube.
These are stored at room temperature to await export to Leipzig in Linda Vigilant's lab in Winter 2022.
Hair is stored in coin envelopes.

All samples are labeled (doubly bag and tube for poop) with yyyy.mm.dd.location.number.collector and info about age, sex, and id of individual is recorded if known.

GPS coordinates of samples are taken on Garmin.

Sample info is recorded into personal notebooks, and uploaded to a Google Doc and `.csv` which is version controlled.

### Data for Isotopes
Get Tamara's Input

## Data Organization
```{bash}
 ls -l /Volumes/EAS_shared/capuchin_coiba/working/newdata/capuchins_coiba_dec_2021_jan_2022
total 192
drwx------  1 sifaka  staff  16384 Nov 15 12:11 camera_trap_data
drwx------  1 sifaka  staff  16384 Nov 15 12:17 field_notes
drwx------  1 sifaka  staff  16384 Nov 15 12:11 gpx
drwx------  1 sifaka  staff  16384 Nov 15 12:12 images
drwx------  1 sifaka  staff  16384 Nov 15 12:11 sample_inventory_csvs
drwx------  1 sifaka  staff  16384 Nov 15 12:11 stone_tool_data
```

Camera Traps Data Gets Stored in it own folder with each camera containing a subfolder.
Tool Data Is stored in a sub folder containing Kobo Collect forms and output as well as material avaialbilty `.csv`.

## Data Backup Plan
We will need a dongle to link to USBs and SD cards, Brendan and Zoe's laptop, and two 2 TB hard drives (Brendan brings one he has on hand). 
Brendan or Zoë will upload to server upon return to Konstanz at the end of January.

### Camera Trap Images
Data collected on SD cards are stored in a waterproof container. 
When we go to Rancheria and have electricity, it is backed up to Brendan's laptop and a 2 TB La Cie External Hard Drive. 
If sufficient internet speed is procured, a cloud based version on Brendan's Dropbox will be backed up as well.
SD cards will be placed with Zöe to have original data on a different person.
Raw Data will be uploaded to server upon return from field in Konstanz.

### Kobo Collect Data
This (camera trap deployment info and tool survey) is stored locally on each Android Device, and gets backed up using this code onto laptop when we are on Rancheria: https://bitbucket.org/hijmans-lab/odklocal/src/master/


### Field Notebooks
These paper notebooks contain info about samples collected for DNA, daily goings on, raw material surveys, and get photographed each night with smartphone. 
They back up to cloud automatically when internet is accessed.

### GPX Data
This gets backed up when at Rancheria, or tracks get sent automatically to sky if on an inreach where they are stored on Garmin website.

## Sample Storage
### Stone Tools
These get labeled yyyymmdd_T01 , where the integer corresponds with the number tool collected that day and corresponding kobo collect app. They are placed in ziploc bags labeled with sharpie. A piece of paper with tool id is also placed in the bag. These get wrapped in ubble wrap for flight.

### Poop and Hair
Poop stored in 15 mL tubes upright at room temperature. Labeled with sharpie. Hair stored in coin evelopes in a dry place and labeled accordingly.

### Isotopes
Samples stored in magic solution nut Tamara needs to be consulted.

## DCEF Link
https://github.com/livingingroups/data_catalog_entry_form_shiny_yml/blob/master/coiba_capuchins_july_2021_20211019_123741.yml
