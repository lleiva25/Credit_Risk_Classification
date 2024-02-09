# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

## Purpose

##

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

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
Both models have precision scores under 90% for High-Risk loans, but according to the confusion matrix, we can see that Model 1 has a total number of 158 False results while Model 2 has 120. We would want to recommend Model 2 since it has the lowest number of False results.
