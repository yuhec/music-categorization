# music-categorization
## Bordeaux Ynov Campus - Music Categorization Project
**Creation date :** 23/04/2021

**Authors :**  
- Laëtitia CONSTANTIN
- Mouna DAHMANI

# TD de machine Learning : Catégorisation musicale

**Elective** : Machine Learning   
**Professeur** : Théophile Ravillion   
**Date** : Vendredi 23 Avril 2021

## **Contexte**
Vous travaillez chez Deezer, département Data Science, félicitations.
D'habiles ingénieurs musicologues ont mis au point un jeu de données contenant des informations sur des morceaux de musique. 
Avec quelques transformées de Fourier et autres joyeusetés propres à leur art, ils ont mis au point deux jeux de données contenant de nombreux indicateurs décrivant un morceau de musique.
Ils comptent sur vous pour mettre au point un algorithme capable d'identifier le genre musical d'un morceau sur la base des différents indicateurs qu'ils ont mis au point.
Vous vous apprétiez à leur demander des informations concernant ces variables mais vous constatez qu'ils sont partis en séminaire d'entreprise et que vous vous retrouvez tout seul avec un jeu d'entrainement étiqueté, un jeu de test et un post-it goguenard de votre chef qui vous demande de faire des prédictions précises sur le jeu de test d'ici 16h.

## Défi :
Modéliser le problème, construire un modèle et faire une prédiction de la catégorie à laquelle appartient chaque élément du fichier test.csv à l'aide d'un modèle aussi simple et performant que possible.

## Livrable
Un projet github contenant des notebooks (dans le dossier model_builder) + un fichier prédictions.csv contenant les prédictions faites sur le jeu de test

En header le nom des colonnes (music_id et prediction) et pour chacun des morceaux la catégorie prédite.
Merci d'utiliser la virgule comme séparateur 

## Comment lancer le projet ?

- 1 - Lancer 00.Get Data
- 2 - Lancer 02.Preprocessing
- 3 - Lancer 03.Models
- 4 - Lancer 04.Test prediction


## Models performances Validation Data

Le modèle le plus performant est le SVC (avec une feature selection Lasso) avec un score de 0.78 et 0.78 d'accuracy.


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