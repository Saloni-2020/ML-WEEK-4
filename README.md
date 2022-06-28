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
