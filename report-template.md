# Module 20
## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

## Purpose
You’ll use various techniques to train and evaluate a model based on loan risk. You’ll use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

## Process
The Loan Lending data set contained the following columns:
        - Loan Size
        - Interest Rate
        - Borrower Income
        - Debt to income
        - Number of Accounts
        - Derogatory Marks
        - Total Debt
        - Loan Status

Data was split into training and testing sets by separating the data into labels and features for the column 'Loan Status'.
 * Labels represent an output value
 * Feature is an input value that describes the characteristics of such labels in datasets

<img width="399" alt="Screenshot 2024-02-08 at 8 44 43 PM" src="https://github.com/lleiva25/Credit_Risk_Classification/assets/140974405/8b99e619-fbe5-41ea-b30a-ea14f724a78f">

The balance of our target values shows the number of entries in the 'Loan Status' column.
 * value_counts() returns an object containing counts of unique values

Next, a Logistic Regression Model was utilized with the original data set by using training data. From this Logistic Regression Model, predictions were saved using test data labels.
 * The Logistic Regression Model is a supervised machine learning algorithm that accomplishes binary classification tasks by predicting the probability of an outcome, event, or observation.

From the predictions, we can generate the accuracy score, confusion matrix, and classification report of the first model.
* balanced_accuracy_score() in binary and multiclass classification problems to deal with imbalanced datasets. It is defined as the average of recall obtained in each class.
* confusion_matrix() is a table that is used to define the performance of a classification algorithm. A confusion matrix visualizes and summarizes the performance of a classification algorithm
* classification report is used to measure the quality of predictions from a classification algorithm. It details how many predictions are true and how many are false
  
<img width="645" alt="Screenshot 2024-02-08 at 8 55 40 PM" src="https://github.com/lleiva25/Credit_Risk_Classification/assets/140974405/cb74cbc8-bb2b-4824-8fc6-242517a6e085">

For the second model, another Logistic Regression Model was fitted with resampled Training Data. Predictions, accuracy scores, confusion matric, and classification reports were generated using the same functions as the first model. 

<img width="630" alt="Screenshot 2024-02-08 at 9 00 50 PM" src="https://github.com/lleiva25/Credit_Risk_Classification/assets/140974405/5d359d9c-acf9-4d78-8eee-3ae50d23630b">


## Results

* Machine Learning Model 1:
  * Balanced Accuracy Score: 95.20%
  * Confusion Matrix
           * True Negatives [18663]
           * True Positives [563]
           * False Negatives [56]
           * False Positives [102]
  * Classification Report
            * Accuracy: 0.99
            * Precision: Low Risk 100%, High Risk 85% 
            * Recall scores: Low Risk 0.99, High Risk 0.88



* Machine Learning Model 2:
  * Balanced Accuracy Score: 99.36%
  * Confusion Matrix
           * True Negatives [18649]
           * True Positives [615]
           * False Negatives [04]
           * False Positives [116]
  * Classification Report
            * Accuracy: 0.99
            * Precision: Low Risk 100%, High Risk 84% 
            * Recall scores: Low Risk 0.99, High Risk 0.99

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
  
* Machine Learning Model 2 has the highest balanced accuracy score meaning that it is a more sensitive model able to identify positives present in the classifier. However, this model does contain more false positives and less false negatives.
  
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )
  
* When it comes to machine learning, the combination of precision and recall provides insight into which model is better for predictions, however, it isn't more important to focus on one class over the other since (0,1) are indicators of the model.
  
If you do not recommend any of the models, please justify your reasoning.

*Both models have precision scores under 90% for High-Risk loans, but according to the confusion matrix, we can see that Model 1 has a total number of 158 False results while Model 2 has 120. We would want to recommend Model 2 since it has the lowest number of False results.
