# Children interactive playing behavior 
__An eye-tracking study__

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
