# GETTING & CLEANING DATA PROGRAMMING ASSIGNMENT

## GOAL
The exercise asks for collecting, working and cleaning the data from a experiment of *Human Activity Recognition Using Smartphone* in order to get a tidy dataset for further analysis and investigation.
The project contains 5 steps to comply:
1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement.
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names.
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

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
* Run: 
``` [R]source('run_analysis.R');run_analysis("*filename*")```

*filename: It's the name of the txt file with resulting dataset*

## run_analysis.R STRUCTURE
The file contains the following functions:
### get_and_join_files
This function receives the path of the txt files of observations, activities( labels and literals) and subjects of one of the folders(TRAIN or TEST) and return a dataset with all the data joined. 
The function:
1. Stores every file in its corresponding dataframe
2. Checks that the number of rows of every one of them is correct. If it wasn'tm it returns a message error and does not allow to continue.
3. Changes the label id by the literal of every activity(see step 3 of **GOAL** section)
4. Merges the 3 datasets in only one. The order of the columns are Subject, activities and
### getVectorStdMean
This functions receives the path of the text file with name of the variables and returns a vector with the positions and the text of those positions of the meassures that are means or standard variations.
The function:
1. Stores the text file with the column names on a dataframe
2. Creates a vector with the positions of the means and standard variations
3. Creates a vector with the complete names of the means and standard variations
4. Returns them after increasing the positions in 2 as the dataset of the previous function has added the subject and activity columns.

*NOTE: The meanFreqs meassures have been discarded as they are not pure means*
### run_analysis
Main function of the script. It receives the path where the users wants to store the resulting tidy data set.
The function:
1. Gets the dataset from *train* and *test* folders using **get_and_join_files**
2. Joins them in only one. (see step 1 of **GOAL** section)
3. Renames the first two columns as *Subject* and *Activity* in order of eliminating duplicated column names
4. Gets the positions and the name of those positions with the function **getVectorStdMean**
5. Extracts those columns from the merged dataset and stores them on a new one. (see step 2 of **GOAL** section)
6. Renames the columns of the dataset with the names obtained on step 4 after removing special characters not allowed on tidy data.(see step 4 of **GOAL** section)
7. Groups the dataset by *Subject* and *Activity*, aggregating the meassures by *mean* function and stores them in the final data set.
8. It writes the dataset in the text file passed as parameter (see step 5 of **GOAL** section)



