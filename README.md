#  Dumbell Biceps Curl Exercise Prediction Model

The goal of this project is to predict the manner in which participants conducted an exercise, Unilateral Dumbell Biceps Curl, using data from accelerometers on the belt, forearm, arm, and dumbell of 6 participants. I used testing and training data sets provided from an exercise study (Velloso et al. 2013) to test and select a model. 

## Getting Started

The following libraries are used to develop the prediction model model. 

```
library(caret)
library(randomForest)
library(splines)
library(rpart)
library(rattle)
library(rpart.plot)
```

## Data

We are using data from a weight lifting excercises study in which participants were asked to perform barbell lifts correctly and incorrectly in 5 different ways. Read more: http://groupware.les.inf.puc-rio.br/har#ixzz4M3W3G2zV

The testing and training data can be found at the following urls:

* Training Data: "http://d396qusza40orc.cloudfront.net/predmachlearn/pml-training.csv"
* Testing Data: "http://d396qusza40orc.cloudfront.net/predmachlearn/pml-testing.csv"


## Model
We built two different models, decision tree and random forest, on our training set and evaluate them on the test set.

* Decision Tree
```
modFit_DT <- rpart(classe ~ ., data = myTraining, method="class")
```
* Random Forest Model
```
modFit_RF <- randomForest(classe ~ ., data = myTraining, ntree = 1000)
```

## Author
* Megan Neisler

## Acknowledgements
* This was completed as part of Coursera's Johns Hopkins Data Science Specialization.
* Data Source: Velloso, E.; Bulling, A.; Gellersen, H.; Ugulino, W.; Fuks, H. Qualitative Activity Recognition of Weight Lifting Exercises. Proceedings of 4th International Conference in Cooperation with SIGCHI (Augmented Human '13) . Stuttgart, Germany: ACM SIGCHI, 2013.
