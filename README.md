# Coursera_Cleaning-Data_Course-Project

This is for the course project in the Coursera open class "Getting and Cleaning Data"

Data is collected from the accelerometers from the Samsung Galaxy S smartphone. A full description is available at the site where the data was obtained. This data consists of train, test, subject, and other descriptive contents. 

With the R script named as 'run_anlysis', one can create tidy set of data by following steps.

1. Merges the training and the test sets to create one data set.
 - read data set into R using read.table function
 - bind data in the train, test set by rows in order to create three set of data : x, y, and subject
2. Extracts only the measurements on the mean and standard deviation for each measurement. 
 - read 'features' text indicating labels of variables seen in data 'x'
 - subset variables referring mean or standard deviation values using grep function
 - subset data set of x by previous subset from features
3. Uses descriptive activity names to name the activities in the data set
 - read 'activity_labels' text indicating lables of variables seen in data 'y'
 - match activities labels in the data 'y' with 'activities_lables'
4. Appropriately labels the data set with descriptive variable names. 
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
 - use ddply() from the plyr package is used to apply colMeans() and ease the development.
 - create text file which contains output of previous function
