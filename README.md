# Glass Classification
As a warm up and exercise I picked this small real life data set to deal with minumum data cleaning while making EDA and apply some classification models.

The purpose of this project is to define the type of a glass depending on the given features. 

The motivation behind the glass classification is given by the contributor as;
>The study of classification of types of glass was motivated by
criminological investigation. At the scene of the crime, the glass left
can be used as evidence…if it is correctly identified!

The data set used in this work is obtained from;
- https://archive.ics.uci.edu/ml/datasets/Glass+Identification

![](/images/image.png)

## Code and Resources Used 
**Python Version:** 3.9  
**Packages:** pandas(1.4.4), numpy(1.21.5), seaborn(0.11.2), matplotlib(3.5.2), scipy(1.9.1), sklearn(1.0.2), mlxtend, xgboost(1.7.2)

## Data Cleaning & Feature Engineering
* A duplicated row detected and dropped from the data set.
* The oxide contents have been scaled to set between 0-1 instead of 0-100.
* MinMax scaling has been applied to RI

## EDA
* Features RI, Mg, K, Ca, Ba, and Fe were highly; Al and Si were moderately skewed, these features have been normalised.
* There is a highly positive correlation between RI and Ca. The cause is revealed as Ca is required to make the glass insoluble, but the higher amounts makes a glass prone to devitrification, hence increases the RI levels.

![alt text](https://github.com/ildeniz/ML-2022-001-Glass_classification/blob/master/oxide%20content%20boxplot.png "The oxide contents BoxPlot")

![alt text](https://github.com/ildeniz/ML-2022-001-Glass_classification/blob/master/RI%20and%20Ca%20correlation%20plot.png "RI and Ca Correlation by type of glass")

## Model Building
I applied various classification models to several altered data sets and evaluated the results by accuracy score.

I split the data into train and tests sets with a test size of 20% and applied 10 fold cross-validation on the selected models.

Models applied:
* Random Forest Classifier
* Ada Boost Classifier
* K-Neighbors Classifier
* Extra Trees Classifier
* GradientBoostingClassifier
* Support Vector Classifier
* Gaussian Naive Bayes

## Model performance
* Extra Trees Classifier accuracy score: 0.82 (mean values), only oxide content have been scaled.
* Random Forest Classifier accuracy score: 0.81 (mean values), all fetures have been scaled.
