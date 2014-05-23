## Codebook 
### Study Design
#### Data Collection
The raw data was collected as part of the UCI Human Activity Recognition Using Smartphones project, which you can read more about here: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

#### Purpose of Data Processing
The goal of the data processing is to create a tidy data set with the average mean and standard deviations for each subject and activity level for the primary measured quantities in the dataset. 

#### Features Used
The output for the script is the average mean and standard deviation for the following variables:
- tBodyAcc-XYZ
- tGravityAcc-XYZ
- tBodyAccJerk-XYZ
- tBodyGyro-XYZ
- tBodyGyroJerk-XYZ
- tBodyAccMag
- tGravityAccMag
- tBodyAccJerkMag
- tBodyGyroMag
- tBodyGyroJerkMag
- fBodyAcc-XYZ
- fBodyAccJerk-XYZ
- fBodyGyro-XYZ
- fBodyAccMag
- fBodyAccJerkMag
- fBodyGyroMag
- fBodyGyroJerkMag

We ignored the angle measurements provided, which are derived from average measurments of other quantities, and the frequency means, which are the average frequencies. 

### Output variables
- Subject: Subject number (1-30)
- Acitivity: Activity undertaken by subject. walk=Walking, walkup=Walking Upstairs, walkdown=Walking Downstairs, others are as is.
- Other variables names have multiple components and each component in the names can be interpreted as follows:
    - BodyAcc: body acceleration
    - GravityAcc: gravitational acceleration
    - Jerk: the jerk on the respective acceleration
    - Gyro: gyroscope signal
    - Mag: magnitude of 3d signal
    - XYZ: the direction of the acceleration
    - t: time-domain signal
    - f: frequency domain, calculate from a Fast Fourier Transform (FFT) of time domain data
    - mean, std: whether or not the value is the average mean or standard deviation
- For example, the variable name "fBodyAccJerkX" is the jerk of the body acceleration measured by accelerometer in the X direction in the frequency domain

### Variables used in data processing script
- samsungurl: url to download raw data from (string)
- activitylbls: raw data activity labels (6x2)
- features: raw data features list (561x2)
- subj.test: subject numbers for test data (29741x1)
- subj.train: subject numbers for training data (7352x1)
- x.test: values for each features for test data (2947x561)
- y.test: activities for each measurement in x.test (2947x1)
- x.train: values for each features for train data (7352x561)
- y.train: activities for each measurement in x.train (7352x1)
- meanstd: index for features that are either a mean or standard deviation of one of the measurements
- x.tot: values for combined test and training data set (10299x66)
- y.tot: activities for combined test and training data set (10299x1)
- subj.tot: subjects for combined test and training data set (10299x1)
- subjects: unique list of subjects, numbered 1-30 (30x1)
- activities: the indicies for the activities used in "y" variables (6x1)
- actlen: length of "activities"" (6x1)
- subjlen: length of "subjects" (30x1)
- results: array to store average mean and std for each subject and activity (180x66)
- ind: temporary index used to identify rows of X.tot with a certain subject and activity level
- subjfin: final subject column (180x1)
- actfin: final activity indices (180x1)
- lblfin: final labels for activities for tidy data set (180x1)
- varnames: tidy variable names
- df: data frame containing final table to be written to tidy data file
