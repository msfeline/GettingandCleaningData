This file describes the variables, the data, transformations to clean up the data.
•	where the data was obtained:
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

where data for the project was obtained
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

•	Steps to clean the data using the run_analysis.R script:

1)	Read X_train.txt, y_train.txt and subject_train.txt from the "./UCI HAR Dataset/train/" folder and store them in trainData,trainLabel and trainSubject variables respectively.

2)	Read X_test.txt, y_test.txt and subject_test.txt from the "./UCI HAR Dataset/test/" folder and store them in testData, testLabeland testsubject variables respectively.

3)	Concatenate testData to trainData to generate a 10299x561 data frame, joinData; concatenate testLabel totrainLabel to generate a 10299x1 data frame, joinLabel; concatenate testSubject to trainSubject to generate a 10299x1 data frame, joinSubject.

4)	Read the features.txt file from the "./UCI HAR Dataset" folder and store the data in a variable called features. Extract the measurements on the mean and standard deviation. Get a subset ofjoinData with the 66 corresponding columns.

5)	Clean the column names of the subset by removing "()" and "-" symbols in the names, as well as make the first letter of "mean" and "std" a capital letter "M" and "S" .

6)	Read the activity_labels.txt file from the "./UCI HAR Dataset" folder and store the data in a variable called activity.

7)	Clean the activity names in the second column of activity. Convert all names to lower cases. Underscore are removed and  the letter immediately after the underscore are capitalized.

8)	Transform the values of joinLabel according to the activity data frame.

9)	Combine the joinSubject, joinLabel and joinData by column to get a new cleaned 10299x68 data frame,cleanedData. Properly name the first two columns, "subject" and "activity". The "subject" column contains integers that range from 1 to 30 inclusive; the "activity" column contains 6 kinds of activity names; the last 66 columns contain measurements that range from -1 to 1 exclusive.

10)	Write the cleanedData out to "merged_data.txt" file in "./UCI HAR Dataset" folder.

11) Finally, generate a second independent tidy data set with the average of each measurement for each activity and each subject. We have 30 unique subjects and 6 unique activities, which result in a 180 combinations of the two. Then, for each combination, we calculate the mean of each measurement with the corresponding combination. So, after initializing the result data frame and performing the two for-loops, we get a 180x68 data frame.

12)	Write the result out to "data_with_means.txt" file in current working directory.

