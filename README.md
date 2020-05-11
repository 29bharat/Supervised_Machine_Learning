# Supervised_Machine_Learning
  
## Objective
  
Implement machine learning models.
  
Use resampling to attempt to address class imbalance.
  
Evaluate the performance of machine learning models.
  
## Resources
  
Dataset provided: LoanStats_2019Q1.csv
  
## Steps:
  
Data from the csv file was read into a dataframe and basic cleanup was applied like dropping the na rows, filtering out Issued Loans, converting rates to numerical values and  customizing the data points to low risk and high risk based on the target column.
  
Features and Target were created and then the data was split into X_train, X_test, y_train and y_test.
  
### OverSampling: https://github.com/29bharat/Supervised_Machine_Learning/blob/master/linear_regression_salary/credit_risk_resampling.ipynb
  
#### Naive Random Oversampling
  
This model uses RamdonOverSampler method. The accuracy score is 0.66. From the confusion matrix we see a high False Positives of 7216 which brings the precision to 0.01 whereas we have a recall of 0.008 with high False Negatives(9888). The Classification report shows the precison of 0.01, recall of 0.74 and F1 score of 0.02 for high risk application . The low risk application shows the precison of 1.00, recall of 0.58 and F1 score of 0.73. The model seems inadequate to predict credist risk.
  
#### SMOTE Oversampling
  
This model uses SMOTE method. The accuracy score is 0.65. From the confusion matrix we see a high False Positives of 5410 which brings the precision to 0.012 whereas we have a recall of 0.005 with high False Negatives(11694). The Classification report shows the precison of 0.01, recall of 0.62 and F1 score of 0.02 for high risk application . The low risk application shows the precison of 1.00, recall of 0.68 and F1 score of 0.81. The model seems inadequate to predict credist risk.
  
#### Undersampling
  
This model uses RandomUnderSampler method. The accuracy score is 0.68. From the confusion matrix we see a high False Positives of 8094 which brings the precision to 0.008 whereas we have a recall of 0.007 with high False Negatives(9010). The Classification report shows the precison of 0.01, recall of 0.64 and F1 score of 0.02 for high risk application . The low risk application shows the precison of 1.00, recall of 0.53 and F1 score of 0.69. The model seems inadequate to predict credist risk.
  
#### Combination (Over and Under) Sampling
  
This model uses SMOTEENN method. The accuracy score is 0.56. From the confusion matrix we see a high False Positives of 7024 which brings the precision to 0.011 whereas we have a recall of 0.008 with high False Negatives(10080). The Classification report shows the precison of 0.01, recall of 0.77 and F1 score of 0.02 for high risk application . The low risk application shows the precison of 1.00, recall of 0.59 and F1 score of 0.74. The model seems inadequate to predict credist risk.

### Summary
  
Given the results of the above modesl, none of them is adequate enough to predict credist risk truly.
  
## Challenge Extension: https://github.com/29bharat/Supervised_Machine_Learning/blob/master/linear_regression_salary/credit_risk_ensemble.ipynb
  
### Ensembling
  
#### Balanced Ramdom Forest
  
This model uses BalancedRandomForestClassifier method. The accuracy score is 0.76. From the confusion matrix we see a high False Positives of 1749 which brings the precision to 0.037 whereas we have a recall of 0.004 with high False Negatives(15355). The Classification report shows the precison of 0.04, recall of 0.67 and F1 score of 0.07 for high risk application . The low risk application shows the precison of 1.00, recall of 0.9 and F1 score of 0.95.
  
#### Easy Ensemble AdaBoost Classifier
  
This model uses EasyEnsembleClassifier method. The accuracy score is 0.93. From the confusion matrix we see a high False Positives of 983 which brings the precision to 0.086 whereas we have a recall of 0.006 with high False Negatives(16121). The Classification report shows the precison of 0.09, recall of 0.92 and F1 score of 0.16 for high risk application . The low risk application shows the precison of 1.00, recall of 0.94 and F1 score of 0.97.
  
### Summary
  
The AdaBoost Classifer has a higher accuracy score compared to the Random Forest. The precision is low at 0.09 with a good sensitivity of 0.92. Low risk applications also have a high sensitivity of 0.97 with also a high precision. Hence, Adaboost with higher fasle negative is a good model to go with to predict low risk applications. It does not perform too well on the high risk because of low precision.
