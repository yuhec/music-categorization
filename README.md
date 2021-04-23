# music-categorization
## Bordeaux Ynov Campus - Music Categorization Project
**Creation date :** 23/04/2021

**Authors :**  
- Laëtitia CONSTANTIN
- Mouna DAHMANI

**Elective** : Machine Learning   
**Professeur** : Théophile Ravillion   
**Date** : Friday 23 Avril 2021

## **Context**
You work at Deezer, Data Science department, congratulations.
Some clever music engineers have developed a dataset containing information about pieces of music. 
With a few Fourier transforms and other tricks of their trade, they have developed two datasets containing many indicators describing a piece of music.
They are counting on you to develop an algorithm that can identify the musical genre of a piece of music based on the different indicators they have developed.
You are apprehensive about asking them for information about these variables, but you realize that they are away on a company retreat and you are left alone with a labeled practice set, a test set, and a mocking post-it note from your boss asking you to make accurate predictions about the test set by 4pm.


## Challenge :
Model the problem, build a model and make a prediction of which category each item in the test.csv file belongs to using a model that is as simple and efficient as possible.

## Report
A github project containing notebooks (in the model_builder folder) + a predictions.csv file containing the predictions made on the test set.

In header the name of the columns (music_id and prediction) and for each song the predicted category.
Please use the comma as separator.

## How to launch the project?

- 1 - Launch 00.Get Data
- 2 - Launch 02.Preprocessing
- 3 - Launch 03.Models
- 4 - Launch 04.Test prediction


## Models performances Validation Data

The best performing model is the SVC (with a Lasso feature selection) with a score of 0.78 and 0.78 accuracy.


|  PCA |  Feature selection  |     Normalization        |  Model                    | Parameters                                                   |  Metrics       | Score           | Comments       |
| ---  | :-:                 | :-:                      | :-:                       | :-:                                                          | :-:            | :-:             | :-:            |
|  10  | Correlation Matrix  |     RobustScaler         |    LogisticRegression     | {'class_weight': None, 'max_iter': 100, 'penalty': 'none'}   | acc <br> f1    |  0.58 <br> 0.56 | Overfit (0.08) |
|  10  | Correlation Matrix  |     RobustScaler         |    RandomForestClassifier | {'max_depth': 4, 'n_estimators': 750}                        | acc <br> f1    |  0.69 <br> 0.68 | Overfit (0.2)  |
|  10  | Correlation Matrix  |     RobustScaler         |    SVC                    | {'degree': 2, 'kernel': 'rbf'}                               | acc <br> f1    |  0.69 <br> 0.67 | Overfit (0.12) |
|  10  | Correlation Matrix  |     RobustScaler         |    KNeighborsClassifier   | {'leaf_size': 30, 'n_neighbors': 5, 'p': 2}                  | acc <br> f1    |  0.58 <br> 0.56 | Overfit (0.13) |
|  10  | Correlation Matrix  |     StandardScaler       |    LogisticRegression     | {'class_weight': balanced, 'max_iter': 100, 'penalty': 'l2'} | acc <br> f1    |  0.56 <br> 0.55 | Overfit (0.07) |
|  10  | Correlation Matrix  |     StandardScaler       |    RandomForestClassifier | {'max_depth': 4, 'n_estimators': 750}                        | acc <br> f1    |  0.64 <br> 0.62 | Overfit (0.24) |
|  10  | Correlation Matrix  |     StandardScaler       |    SVC                    | {'degree': 2, 'kernel': 'rbf'}                               | acc <br> f1    |  0.69 <br> 0.68 | Overfit (0.11) |
|  10  | Correlation Matrix  |     StandardScaler       |    KNeighborsClassifier   | {'leaf_size': 30, 'n_neighbors': 5, 'p': 2}                  | acc <br> f1    |  0.58 <br> 0.56 | Overfit (0.12) |
|  10  | Correlation Matrix  |     MinMaxScaler         |    LogisticRegression     | {'class_weight': balanced, 'max_iter': 100, 'penalty': 'l2'} | acc <br> f1    |  0.53 <br> 0.52 | Overfit (0.09) |
|  10  | Correlation Matrix  |     MinMaxScaler         |    RandomForestClassifier | {'max_depth': 4, 'n_estimators': 750}                        | acc <br> f1    |  0.59 <br> 0.58 | Overfit (0.21) |
|  10  | Correlation Matrix  |     MinMaxScaler         |    SVC                    | {'degree': 2, 'kernel': 'rbf'}                               | acc <br> f1    |  0.63 <br> 0.61 | Overfit (0.18) |
|  10  | Correlation Matrix  |     MinMaxScaler         |    KNeighborsClassifier   | {'leaf_size': 30, 'n_neighbors': 4, 'p': 2}                  | acc <br> f1    |  0.55 <br> 0.54 | Overfit (0.19) |
|  5   | Lasso               |     MinMaxScaler         |    LogisticRegression     | {'class_weight': balanced, 'max_iter': 100, 'penalty': 'l2'} | acc <br> f1    |  0.69 <br> 0.68 | Overfit (-0.01)|
|  5   | Lasso               |     MinMaxScaler         |    RandomForestClassifier | {'max_depth': 4, 'n_estimators': 750}                        | acc <br> f1    |  0.72 <br> 0.72 | Overfit (0.11) |
|  5   | Lasso               |     MinMaxScaler         |    **SVC**                | {'degree': 2, 'kernel': 'rbf'}                               | acc <br> f1    |  0.78 <br> 0.78 | Overfit (-0.01)|
|  5   | Lasso               |     MinMaxScaler         |    KNeighborsClassifier   | {'leaf_size': 30, 'n_neighbors': 4, 'p': 2}                  | acc <br> f1    |  0.64 <br> 0.60 | Overfit (0.08) |


## Copyright Members
- [Mouna DAHMANI](https://gitlab.com/MounaDahmani) 
- [Laëtitia CONSTANTIN](https://gitlab.com/yuhec) 

**License**
Ynov Bordeaux.