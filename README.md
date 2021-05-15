# Eye-Tracking Study  

## Description
This repository contains all scripts used to clean, wrangle, visualize, and prepare the data for subsequent analysis by Mihaela Taranu. 
In the experiment, 7 children played with 14 LEGO bricks across 3 consecutive iterations. Eye tracking data were recorded with Pupil Labs. The videos extracted from Pupil Labs were subsequently manually annotated in Boris. Each time a new fixation was made on a different brick a new manual code was annotated. Thus, the raw data partly originates from Pupil Lab and partly from Boris. Both Pupil Lab and Boris generated a csv-file for every iteration (block) resulting in a total of 21 Boris files and 21 Pupil Lab files. As information from both the Pupil Lab and the Boris files are crucial for the study, all the files are being gathered into a single csv-file.

## Repository structure and files
This repository has the following directory structure:

| Column | Description|
|--------|:-----------|
```data``` | The folder containing all data including the output from Pupil Lab and Boris as well as the cleaned and gathered files.
```documents```| The folder with documents related to the project including the first explorative report, project description, plan etc.
```scripts``` | The folder with all R-markdown files used to pre-process, clean, and gather the data. 
```LICENSE```| An MIT license 
```README.md``` | This readme file.

## Usage (reproducing the results)

There are several scripts and they should be executed in an appropriate order. 

__Clean and gather the Boris files__
The script 'clean_boris_files.Rmd' will import all files in the folder ```Boris_cleaned```, gather them into a single dataframe and drop redundant columns. The single output file will be stored in the folder ```gathered_files``` as 'boris_cleaned.csv'.

__Clean and gather the Pupil Lab files__
The script 'clean_pupil_files.Rmd' will import all files in the folder ```Pupil_Labs_raw_data```, gather them into a single dataframe and drop redundant columns. The single output file will be stored in the folder ```gathered_files``` as 'pupil_cleaned.csv'.

__Merge the Pupil Lab and the Boris data__
The script 'merge_data.Rmd' will take the two files, 'boris_cleaned.csv' and 'pupil_cleaned.csv', and merge them according to approximate timestamps. The timestamps in 'boris_cleaned.csv' are relative to each block of the experiment while the timestamps in 'pupil_cleaned.csv' are not. By subtracting the start recording timestamp of each block, the timestamps corresponding to the timestamps in 'boris_cleaned.csv' can be obtained. A more elaborate explanation of this method can be found [here](https://github.com/pupil-labs/pupil/issues/1823). The start recording timestamps are provided in the metadata of Pupil lab in the folder ```export_info``` under ```Pupil_Labs_raw_data```.
