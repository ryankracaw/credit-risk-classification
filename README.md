# credit-risk-classification

Using various techniques to train and evaluate a model based on loan risk this project uses a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

# Module 12 Report Template

## Overview of the Analysis

The analysis considered the following factors:

* The size of the loan
* The interest rate
* The borrower's income
* The debt-to-income ratio
* The number of accounts the borrower holds
* Any derogatory marks against the borrower
* The borrower's total debt

The dataset of 77,536 data points was split into training and testing sets. The training set was used to build an initial logistic regression model (Machine Learning Model 1) using the LogisticRegression module from scikit-learn. Machine Learning Model 1 was then applied to the testing dataset. The purpose of the model was to determine whether a loan to the borrower in the testing set would be low- or high-risk.

The initial model was biased towards low-risk loans because the training dataset had 75,036 low-risk data points and only 2,500 high-risk data points. To address this imbalance, the training set data was resampled with the RandomOverSampler module from imbalanced-learn. This generated 56,277 data points for both low-risk (0) and high-risk (1) loans, based on the original dataset.

The resampled data was used to build a new logistic regression model (Machine Learning Model 2). The purpose of Machine Learning Model 2 was to determine whether a loan to the borrower in the testing set would be low- or high-risk. The results of the two models are summarized below.


## Results

| Model                    | Accuracy | Precision                              | Recall                                  |
|--------------------------|----------|----------------------------------------|-----------------------------------------|
| Machine Learning Model 1 | 99%      | Healthy Loan: 100% High-risk Loan: 87% | Healthy Loan: 100% High-risk Loan: 89%  |
| Machine Learning Model 2 | 100%     | Healthy Loan: 100% High-risk Loan: 87% | Healthy Loan: 100% High-risk Loan: 100% |

## Summary

Machine Learning Model 2 is going to predict less false negatives. But, the confusion matrix for Machine Learning Model 2 predicted more fasle positives. If the goal for using these models was to predicted healthly loans, it would be very useful. However, since neither model gave a precision above 90% for high-risk loans, I would not use these models. If we needed to use a model for predicting high-risk loans Machine Learning Model 2 would be the best only because it had fewer false predicitions of the testing data overall and had a slightly higher accuracy.
