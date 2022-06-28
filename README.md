# ML-WEEK-4
Executive Summary

This report is for the Coursera Practical Machine Learning Course Project.

Data from the accelerometers on the belt, forearm, arm, and dumbbell of 6 participants were used to predict the the manner in which they did the exercise. This report will describe how I built my model, how I used cross validation, what I think the expected out of sample error is.

Three models were evaluated: a) Classification Tree, b) Random Forest, and c) Gradient Boosting Machines using a 5-fold cross validation on a training set. The evaluation showed that random forest was the most accurate model with 99% in-sample accuracy. Using a validation set, the out of sample error was 0.7%. The random forest model was used to predict the 20 test cases provided.

Background

Using devices such as Jawbone Up, Nike FuelBand, and Fitbit it is now possible to collect a large amount of data about personal activity relatively inexpensively. These type of devices are part of the quantified self movement – a group of enthusiasts who take measurements about themselves regularly to improve their health, to find patterns in their behavior, or because they are tech geeks. One thing that people regularly do is quantify how much of a particular activity they do, but they rarely quantify how well they do it. In this project, your goal will be to use data from accelerometers on the belt, forearm, arm, and dumbbell of 6 participants. They were asked to perform barbell lifts correctly and incorrectly in 5 different ways. More information is available from the website here: http://groupware.les.inf.puc-rio.br/har (see the section on the Weight Lifting Exercise Dataset).

Data

The training data for this project are available here:

https://d396qusza40orc.cloudfront.net/predmachlearn/pml-training.csv

The test data are available here:

https://d396qusza40orc.cloudfront.net/predmachlearn/pml-testing.csv

The data for this project come from this source: http://groupware.les.inf.puc-rio.br/har. If you use the document you create for this class for any purpose please cite them as they have been very generous in allowing their data to be used for this kind of assignment.

Report is divided into:

Load Data

Explore Data

Prepare Data

Evaluate Algorithms

Predict Test Set

1) Load Data

Load libraries

library(lattice)

library(ggplot2)

library(caret)

Load dataset
![image](https://user-images.githubusercontent.com/88283525/176158958-1b81168d-f694-4fea-b1a8-5142f4fe3797.png)

Split training set into sub-training/test sets
![image](https://user-images.githubusercontent.com/88283525/176159029-1c2d511c-5425-45ef-b852-d159368385a7.png)

2) Explore Data

Descriptive statistics
![image](https://user-images.githubusercontent.com/88283525/176159176-fd047753-1838-4add-8fee-7da5d9b2c967.png)

Visualization

The "classe" variable is plotted out to visualize the spead of the types of exercise.
![image](https://user-images.githubusercontent.com/88283525/176159368-177b5a67-9c17-46f5-9843-298b7e8d0e5b.png)

3) Prepare Data

Clean data

Remove metadata (rows 1-7)

subTrain <- subTrain[,-c(1:7)]
Remove variables that contains mostly missing values

# Check number of NAs in each column
table(colSums(is.na(subTrain)))
## 
##     0 14419 14420 14421 14423 14424 14429 14446 14473 14474 14475 14476 14477 
##    53    67     1     1     2     8     2     2     1     1     1     6     2 
## 14718 
##     6
100 variables contains 98% or more missing values (14409/14718*100) and will be removed from the analysis.

subTrain<- subTrain[,colSums(is.na(subTrain))<14409]
Next, the variables with near-zero variance will be removed.

nearZeroVar(subTrain)
## integer(0)
After removing the variables with missing values, the remaining 53 variables do not have near-zero variance.
