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

![image](https://user-images.githubusercontent.com/88283525/176159858-3e62c31a-5b86-4a7a-94d3-1939ebc58978.png)
![image](https://user-images.githubusercontent.com/88283525/176159972-812d4e0c-6aa4-4ad6-81e2-44d2011acbdd.png)

4) Evaluate Algorithms

Train Control

A 5-fold cross validation will be used to estimate accuracy.
![image](https://user-images.githubusercontent.com/88283525/176160314-5a203d2a-f109-41d3-87d3-1eb0bbd0b873.png)

![image](https://user-images.githubusercontent.com/88283525/176160394-4644b6cb-196f-477b-a527-cdfd88012b04.png)

![image](https://user-images.githubusercontent.com/88283525/176160462-42b0f736-a7c0-4ab5-9900-b838194b3bbb.png)

![image](https://user-images.githubusercontent.com/88283525/176160551-1b9c71ea-2a91-42e9-b042-cd0ff412148d.png)
![image](https://user-images.githubusercontent.com/88283525/176160672-b89328f1-d28c-4ed2-9b40-d3f1d0758c56.png)
![image](https://user-images.githubusercontent.com/88283525/176160976-87b0729f-fd1c-414f-a112-93d652db4b7c.png)
![image](https://user-images.githubusercontent.com/88283525/176161068-32de5a5b-57f8-4eab-a85b-99b1d9ddc7cb.png)

![image](https://user-images.githubusercontent.com/88283525/176161162-2a4647e3-5ccb-44d7-9968-d7055dce02d2.png)
![image](https://user-images.githubusercontent.com/88283525/176161261-2867f079-c71d-4203-906b-937d74f903cb.png)
![image](https://user-images.githubusercontent.com/88283525/176161385-29a128c4-32cc-4ab4-b3fd-ce4624747bd9.png)

