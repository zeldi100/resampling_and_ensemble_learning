# Resampling and Ensemble Learning - for predicting credit risk

Apply various Resampling and Ensemble Learning techniques, by using imbalanced-learn and Scikit-learn libraries, to build and evaluate machine learning models to predict credit risk. 

## Background

Credit and loan service offerings online has increased a lot in the past few years, e.g. mortgages, student loans and these services are offered without using a bank. To mitigate the risk, machine learning techniques have been applied through models that can be used to predict credit risk.</br>

Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans), so different techniques have been employed for training and evaluating models with imbalanced classes. The imbalanced-learn and Scikit-learn libraries are used to build and evaluate models as part of this exercise, using the two techniques Resampling and Ensemble Learning.

## Resampling

For resampling, the imbalanced learn library was used to resample the data and then using the resampled data to build and evaluate logistic regression classifiers.
The following models were compared:
1. Simple Logistic Regression model
2. Oversampling using the naive random oversampler and SMOTE algorithms
3. Undersampling using the Cluster Centroids algorithm
4. Over- and under-sampling using a combination SMOTEENN algorithm

The balanced accuracy score, confusion matrix and imbalanced classification report was generated and compared for each model

### Findings when comparing the different resampling models:

Diagram summarising Balanced Accuracy Score (BAC), Recall and Geometric Mean of various models:

| Resampling Model | BAC | Recall | Geo
| ---- | --- | --- | ---
| **Simple Logistic Regression** | 0.95432 | 0.99 | 0.95
| High Risk |   | 0.91 | 0.95
| Low Risk |  | 1.0 | 0.95         
| **Oversampling (Native random sampler)** | 0.994775 | 0.99 | 0.99
| High Risk |   | 1.0 | 0.99
| Low Risk |  | 0.99 | 0.99  
| **Oversampling (SMOTE)** | 0.994828 | 0.99 | 0.99
| High Risk |   | 1.0 | 0.99
| Low Risk |  | 0.99 | 0.99  
| **Undersampling** | 0.983681 | 0.99 | 0.98
| High Risk |   | 0.97 | 0.98
| Low Risk |  | 0.99 | 0.98 
| **Over- and under-samping (SMOTEENN)** | 0.994748 | 0.99 | 0.99
| High Risk |   | 1.0 | 0.99
| Low Risk |  | 0.99 | 0.98 
</br>


* Model with the best balanced accuracy score: </br>
   The Smote oversampling model has the highest balance score of 0.994828
* Model with the best recall score: </br>
   Best High Risk recall score was Oversampling (Native Random Sampler), SMOTE and SMOTEENN models
   The cost of incorrectly predicting a customer as low risk (that is actually high-risk) is high as you might be taking on a customer that could default and not repay their loan. Thus the recall for High-risk was a more important consideration.
* Model with the best geometric mean score:</br>
   Oversampling, SMOTE and SMOTEENN sampling models all had a geometrical mean score of 0.99 
   
## Ensemble Learning

Two different ensemble classifiers was used to predict loan risk and evaluate each model:
1. Balanced Random Forest Classifier
2. Easy Ensemble Classifier.

The balanced accuracy score, confusion matrix and imbalanced classification report was generated and compared for each model

### Findings when comparing the different ensembling models:

Diagram summarising Balanced Accuracy Score (BAC), Recall and Geometric Mean of various models:

| Ensemble Model | BAC | Recall | Geo
| ---- | --- | --- | ---
| **Balanced Random Forest Classifier** | 0.9922617 | 0.99 | 0.99
| High Risk |   | 1.00 | 0.99
| Low Risk |  | 0.99 | 0.99         
| **Easy Ensemble Classifier** | 0.993758 | 0.99 | 0.99
| High Risk |   | 1.00 | 0.99
| Low Risk |  | 0.99 | 0.99  
</br>


* Model with the best balanced accuracy score: </br>
   Easy Ensemble Classifier was slightly better with a BAC of 99.4%

* Model with the best recall score: </br>
   Both models had the same recall of 1.0 for high risk indicating a good prediction of high risk

* Model with the best geometric mean score: </br>
   Both models had the same geometric mean score of 0.99

* Top three features identified were as follows :
   1. Borrower Income (22.76%)
   2. Interest rate (19.66%)
   3. Debt to Income (17.42%)
</br>
</br>


## Files used for the purposes of this modeling exercise.

[Resampling Jupyter Notebook](credit_risk_resampling.ipynb)

[Ensemble Jupyter Notebook](credit_risk_ensemble.ipynb)

[Lending Club Loans Data](Resources/LoanStats_2019Q1.csv.zip)