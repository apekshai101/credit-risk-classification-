## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This include:

* Explain the purpose of the analysis.
The purpose of this analysis is to predict the loan risk (healthy loans vs high risk loans) by using Logistic Regression machine learning model on a dataset of historical lending activity from a peer-to-peer lending services company.

* Explain what financial information the data was on, and what you needed to predict.
The dataset consists of 8 columns for  loan_size, interest_rate, borrower_income, debt_to_income, number_of_accounts, derogatory_marks, total_debt, and loan_status. Our target column for this analysis is "loan-status" to predict healthy and high risk loans.


* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
DataFrame y variable has 1 column "loan_status" which contains two unique values: 0 and 1.There are 75,036 count of the value 0 and  2,500 count of the value 1.
DataFrame X variable has 7 columns loan_size, interest_rate, borrower_income, debt_to_income, num_of_accounts, derogatory_marks, and total_debt.There are unique combination of values for these columns.


* Describe the stages of the machine learning process you went through as part of this analysis.
1)First read the lending_data.csv data into a Pandas DataFrame(credit_df)
2)Create the labels set (y) from the “loan_status” column, and then create the features (X) DataFrame from the remaining columns.
3)Split the data into training and testing datasets by using train_test_split function.
4)Fit a logistic regression model by using the training data (X_train and y_train).
5)Save the predictions for the testing data labels by using the testing feature data (X_test) and the fitted model.
6)Evaluate the model’s performance by generating a confusion matrix and printing the classification report.


* Briefly touch on any methods you used (e.g., `LogisticRegression`).
For this analysis Logistic regression machine learning method was used. 
Imported the LogisticRegression module from SKLearn.
Other libraries that were used are 
- from sklearn.metrics import confusion_matrix, classification_report, 
- from sklearn.model_selection import train_test_split.


## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
* Description of Model 1 Accuracy, Precision, and Recall scores.
Accuracy score: 0.99
Precision score: Class 0: 1.00   Class 1: 0.85
Recall score:    Class 0: 0.99   Class 1: 0.91


## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any.
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )
 If you do not recommend any of the models, please justify your reasoning.

The Logistic Regression model performed well for this dataset.Overall accuracy was 0.99 or 99% which is very high. 
The model was perfect in predicting Class 0 (healthy loans). For the 0 class(healthy loans), the precision was 1.00 or 100% and the recall was 0.99 or 99% which are very high and does a great job with no false positive as precision is 100% and 1% false negative as recall is 99%.

However for class 1 (high-risk loans), the model was less satisfactory in predicting this class compared to class 0.For class 1 (high-risk loans), precision is 0.85 or 85% with 15% chances of false positives and the recall is 0.91 or 91% with 9% chance of false negative.The fact that the model has more false positives than false negatives for high-risk loans suggests that while it is good at identifying most of the actual high-risk loans (high recall), it also tends to misclassify some good loans as high-risk (lower precision). This could be an indication that the model might be too sensitive or that it needs further refinement to reduce false positives.

From above we can conclude that the Logistic Regression model is great at predicting healthy loans compared to high-risk loans.

The logistic regression model performs well for this dataset but we need to test different machine learning models like random forest,SVM,KNN,gradient boosting etc for this dataset to compare the results in order to remove any bias or imbalance in data before putting the Logistic Regression model in use for predicting loans as healthy or high risk. 















