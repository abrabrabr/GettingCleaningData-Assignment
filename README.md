# GETTING & CLEANING DATA PROGRAMMING ASSIGNMENT

## GOAL
The exercise asks for collecting, working and cleaning the data from a experiment of *Human Activity Recognition Using Smartphone* in order to get a tidy dataset for further analysis and investigation.

## FILES
* All the program units are located on the file **run_analysis.R**.
* The tidy dataset is stored on the file **tidySet.txt**. You can read it in R using read.table instruction or open it directly with Notepad ++ or similar advanced text editor.
* You can have a closer look at the Variables used on the dataset on the file **codeBook.md**.
* The **README.md** file you are reading right now with the basic information of the project.

## EXECUTION
### Requisites
* You need to keep the original files' structure, with the *TEST* and *TRAIN* folders, of the zip file on your **R** working folder.
* Copy **run_analysis.R** on your working folder.
### Code to execute
* Run: source('run_analysis.R'); run_analysis("*filename*")

*filename: It's the name of the txt file with resulting dataset

## run_analysis.R STRUCTURE
The file contains the following functions:
### get_and_join_files
This function receives the path of the txt files of observations, activities( labels and literals) and subjects of one of the folders(TRAIN or TEST) and return a dataset with all the data joined. 
The function:
1. Stores every file in its corresponding dataframe
2. Checks that the number of rows of every one of them is correct. If it was
