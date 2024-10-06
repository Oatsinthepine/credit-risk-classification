# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any other algorithm).

The the purpose of the analysis is to see if using logistic regression model can accuratly predict the loan status. The dataset contains features of loan_size, interest_rate, borrower_income, debt_to_income, num_of_accounts, derogatory_marks, and total_debt. The goal is to use these features to predict if a sample loan is healthy or high risk. The target is the loan_status column, which contains healthy & high risk (2 different category). 

Stage for this ML process is listed as the notebook. First import the data into dataframe. Sepereate it into featrues(X) and target(y). Then use the Scikit-learn model train_test_split into training and testing segments. Then create model and fitted with training data. finally make predictions and generate confusion matrix and classfication report to see the score.

The model used here is LogisticRegression() as the built-in model from scikit-learn library. 
All the data evaluation is also used the sklearn model of the built-in confusion matrix and classification report.


## Results

Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1: (LogisticRegression)
    * Description of Model 1 Accuracy, Precision, and Recall scores.

    - Accuracy: 0.99 
    - Precision for target class 0 (healthy): 1.00; Prcision for target class 1(high-risk): 0.84
    - Recall for target class 0 (healthy):0.99; Recall for target class 1(high-risk): 0.94

## Summary

Summarise the results of the machine learning models, and include a recommendation on the model to use, if any. For example:

* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.

The results of model evaluation is written in the the notebook Step 4. 
However, I don't recommand using the model at current stage. The reasons are listed below.
The issues reside here before jumpping into model recommandation is that throughout this model training, there are no scaling of the data. Which I think may impact the actual results, as the logistic regression model is sensitive to unscaled data. Moreover, cross validation should be implemented to further test the model before giving conclusion. Due to the task indication. There are no room for comparing the accuracy score between training and testing data. If there are evident differneces that might indicate overfitting issue. Besides, when training the model, to mitigate the effect caused by unbalanced target from the dataset, parameters like class_weight='balanced' or stratify=y should be used. 
Therefore, I think need to implement more test and incooperating the methods mentioned abvoe to acive more robust testing before the usage.

