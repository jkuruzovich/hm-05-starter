## Exercises
Note this is easily viewed from the [github repository](https://github.com/techfundamentals-fall2017/hm-05-starter).

For the exercise below you should import the Iris Dataset as a dataframe called iris.df.

(1). Create a variable called sepal_width.mean that contains the mean of the sepal_width column of iris.df.

(2). Create a new column of iris.df called sepal_area that is equal to the sepal_width times sepal_length.

(3). Create a new dataframe iristrain.df that includes the first 75 rows of the iris dataframe.

(4). Create a new dataframe iristest.df that includes the last 75 rows of the iris dataframe.

(5). Create a new vector sepal_length from the sepal_length column of the iris dataframe.

For the exercise below you should import train.csv and test.csv files from the Titanic dataset.

(6). While we can submit our answer to Kaggle to see how it will perform, we can also utilize our test data to assess accuracy. Accuracy is the percentage of predictions made correctly-i.e., the percentage of people in which our prediction regarding their survival. 

a. Create columns in the training dataset PredEveryoneDies and PredGender with the same predictions from above. 

b. Create variables AccEveryoneDies and AccGender using a calculation of accuracy of predictions for the training dataset.

(7). Notice how we are utilizing the code to select out the passengerID and the Survived column and generating a submission file over and over? This is in need of a function. Create a generate_submission function that accepts a DataFrame, a target column, and a filename and writes out the submission file with just the passengerID and the Survived columns, where the survived column is equal to the target column. It should then return a DataFrame with the passengerID and the Survived columns.

Executeing the following: 

`submitdie <- generate_submission(train, "PredEveryoneDies", "submiteveryonedies.csv")`

Should return a dataframe with just passengerID and the Survived column. (You will have to execute this to pass tests.)

(8). In according to the women and children first protocol we hypothesize that our model could be improved by including whether the individual was a child in addition to gender. After coding survival based on gender, update your recommendation to prediction in the training dataset survival based on age. `train$PredGenderAge13` should be the prediction incorporating both Gender and whether Age < 13. train$PredGenderAge18 should be the prediction incorporating both Gender and whether Age < 18. AccGenderAge13 should be the accuracy of the age prediction, based on `train$PredGenderAge13`. `AccGenderAge18` should be the accuracy of the age prediction, based on `train$PredGenderAge18`. 

**Hint: You might find that you have to remove the NA's before doing operations on the Age column.**

(9). You should find that the AccGenderAge13 is better than AccGenderAge18. Create a new `column` child in the test and train DataFrames that is 1 if Age < 13 and 0 otherwise. This is a feature.

## Running Tests
- Running tests requires three files:  (1) `test.intro-r-exercises.R` has all of the tests and you should not need to change this file. (2) `run-tests.R` can be used to run the tests. (3) `intro-r-exercises.R` is where you will put all of your code.  

- It is easiest to run the tests from RStudio.  Set your working directory to the same directory that has all 3 files.  For example, `setwd("~/githubdesktop/0_class/hm-05-starter/hm")` is how you do it on mac/Linux. You can also navigate the file path in the bottom right of RStudio and click the *More* button to set the working directory. 
- You can see all of the tests in the file `test.intro-r-exercises.R`.  
- You can run the tests using the `run-tests.R` file.  Passing tests should yield output indicated below.
![Imgur](http://i.imgur.com/MaTxeLg.png)