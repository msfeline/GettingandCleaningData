GettingandCleaningData
======================


This readme file describes how run_analysis.R script works.

First, we have to unzip the data from https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
i use the default "UCI HAR Dataset" folder name
Make sure the folder "UCI HAR Dataset" and the run_analysis.R script are both in the current working directory.
Second, use source("run_analysis.R") command in RStudio.
Third, you will find two output files are generated in the current working directory:
merged_data.txt : it contains a data frame called cleanedData with 10299*68 dimension.
data_with_means.txt : it contains a data frame called result with 180*68 dimension.
Finally, use data <- read.table("data_with_means.txt") command in RStudio to read the file.
