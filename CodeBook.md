Getting and Cleaning Data Project 
===========

# The code book

The code book contain below information.

1. Information about the variables in the data set 

2. Information about the transformation work to clean up the data

## Transformation work to clean up the data

Source of the original data: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

Original description: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The source data was collected from the above URL to complete this assignment. The assignment involved working with the data set and producing tidy data representation of the source data. The following are the steps performed to achieve the results.

1) Downloaded the data set from above URL.

2) Unzipped the data set into local folder.

3) Loaded test and training data sets into data frames and merged the data frames into 1 data frame using rbind() function.

4) Extracted only the measurements on the mean and standard deviation for each measurement by searching variable names with -mean() and -std() words.

5) Used descriptive activity names to name the activities in the data set for readability. Changed the activity name to lower case.

6) Labelled the data set with descriptive variable names. Removed the open and close bracket and changed the variable name to lower case.

7) Combined the data frames to produce one data frame containing the subjects, activities and measurements. 

8) Created an independent tidy data set with the average of each variable for each activity and each subject. This was achieved by using the data.table library to easily group the tidy data by subject and activity. It can be done using lapply() or melt()/cast() function with mean function. Sort the tidy data based on subject and activity.

9) Generated "tidy_data_average.txt" from the tidy data as the expected output.


## Variables

subject: 1 to 30 each representing 30 volunteers within an age bracket of 19-48 years.

activity: the activity that the subject was doing at the time of the measurement: WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS,
SITTING, STANDING, LAYING

mean and standard deviation variables as listed below.

1. tBodyAcc-mean-X

2. tBodyAcc-mean-Y

3. tBodyAcc-mean-Z

4. tBodyAcc-std-X

5. tBodyAcc-std-Y

6. tBodyAcc-std-Z

7. tGravityAcc-mean-X

8. tGravityAcc-mean-Y

9. tGravityAcc-mean-Z

10. tGravityAcc-std-X

11. tGravityAcc-std-Y

12. tGravityAcc-std-Z

13. tBodyAccJerk-mean-X

14. tBodyAccJerk-mean-Y

15. tBodyAccJerk-mean-Z

16. tBodyAccJerk-std-X

17. tBodyAccJerk-std-Y

18. tBodyAccJerk-std-Z

19. tBodyGyro-mean-X

20. tBodyGyro-mean-Y

21. tBodyGyro-mean-Z

22. tBodyGyro-std-X

23. tBodyGyro-std-Y

24. tBodyGyro-std-Z

25. tBodyGyroJerk-mean-X

26. tBodyGyroJerk-mean-Y

27. tBodyGyroJerk-mean-Z

28. tBodyGyroJerk-std-X

29. tBodyGyroJerk-std-Y

30. tBodyGyroJerk-std-Z

31. tBodyAccMag-mean

32. tBodyAccMag-std

33. tGravityAccMag-mean

34. tGravityAccMag-std

35. tBodyAccJerkMag-mean

36. tBodyAccJerkMag-std

37. tBodyGyroMag-mean

38. tBodyGyroMag-std

39. tBodyGyroJerkMag-mean

40. tBodyGyroJerkMag-std

41. fBodyAcc-mean-X

42. fBodyAcc-mean-Y

43. fBodyAcc-mean-Z

44. fBodyAcc-std-X

45. fBodyAcc-std-Y

46. fBodyAcc-std-Z

47. fBodyAccJerk-mean-X

48. fBodyAccJerk-mean-Y

49. fBodyAccJerk-mean-Z

50. fBodyAccJerk-std-X

51. fBodyAccJerk-std-Y

52. fBodyAccJerk-std-Z

53. fBodyGyro-mean-X

54. fBodyGyro-mean-Y

55. fBodyGyro-mean-Z

56. fBodyGyro-std-X

57. fBodyGyro-std-Y

58. fBodyGyro-std-Z

59. fBodyAccMag-mean

60. fBodyAccMag-std

61. fBodyBodyAccJerkMag-mean

62. fBodyBodyAccJerkMag-std

63. fBodyBodyGyroMag-mean

64. fBodyBodyGyroMag-std

65. fBodyBodyGyroJerkMag-mean

66. fBodyBodyGyroJerkMag-std


