## Overview of the Analysis

Purpose of this analysis is to identify the creditworthiness of borrowers by using various machine learning techniques to train and evaluate a model based on loan risk. We used  a dataset of historical lending activity from a peer-to-peer lending services company.

 
The  matrix X contains the input features that the model will use to make predictions
consisted on key variables like loan size, interest rate, borrower's income, debt-to-income ratio, account count, derogatory marks, and total debt.These factors influence in predicting the loan status, categorizing it as either a healthy loan  0 or a 'high-risk loan 1'.

The stages of the machine learning process we went through as part of this analysis are as follows:
Firstly we fit the Logistic Regression Model on the original data set.

-We  loaded the data in a dataframe and Separate the data into labels (y) and features (X).
-Split the data using train_test_split module from sklearn.
- we created the Logistic Regression Model with the original data by instantiating the regression model and fit this model using traing data that consisted on X-train and Y_train that has already been obtained by using the train test learn module of sklearn.
- we made predictions by using the .predict function on the feature data X_test.
- we calculated the balanced accuracy score and confusion matrix by using y test data and predictions.

Secondly, We repeated the process of fitting and predicting a logistic Regression Model with another machine learning technique 'Resampled traing set' that is used to remove the imbalannce in dataset.
we imported the RandomOverSampler from imblearn
we over sample our minority data set (high risk loan). After oversampling we counted the values of our dependent variable y which is now equally didvided between healthy loans 56277
and high risk loan 56277.




## Machine Learning Model 1:

To analyse, we can see the model did a good job with an accuracy score of 94%. 

* Although, We note that the recall for healthy loans is 100% but for 'high risk loans 1' it is 89%, which is not a good, It means the model is falsely approving the 11 high risk loans out of 100 applications. There is a chance that in real life those people won't be able to return the loan. so we need to minimise this FP(false positive ie 67 in this case) numbers in the model so we can have a more higher recall for high risk loans. 

* The Precision and f1-score are 100% for the 'healthy loan 0' wheras  for the 'high_risk loan 1' class, the precision is 87%, indicating that 87% of the predicted instances for this class are true positives, while 13% are false positives. 

* The F1-score, which considers both precision and recall, is 88%, reflecting a balanced performance between precision and recall for this class.

## Machine Learning Model 2:
With oversampled data, we can see a huge difference in the confusion matrix where False Positive numbers have decreased from 67 in the original dataset to 2 in the oversampled dataset, which is a big improvement.
* The accuracy score has improved from 94% to nearly 100% (0.9959744975744975) in the oversampled data.
* Recall for healthy loan and high risk loan has improved to 100%. 
* f1 score for high risk loan has improved from 88% to 93%.


## Summary
To sum up, oversampling has addressed the issue of imbalance in the dataset and contributed to improve model performance, especially for the minority class high risk loan. It helped the model to learn the features of the high risk loan more effectively, leading to better precision, recall, and F1-score.
Which Model is best fit depends on a careful consideration of business goals, resources , and the specific objectives of the machine learning project.




