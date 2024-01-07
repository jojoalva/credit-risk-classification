# Module 20 Report

## Challenge files

The files to access the challenge jupyter notebook and its associated data are in the "Credit_Risk" folder within this repository.

## Overview of the Analysis

In the first section of this supervised learning challenge, I used a logistic regression model with the original data, from the csv file.
The data in this file references loan sizes, compares the borrowers' data for those loans, and classifies them as a high risk or low risk loan status. In this supervised learning model I have used, I split the data into a training set, having removed the "actual" loan risk already, to see if the model can correctly classify the loans as high or low risk. Then, the training set is compared to the actual loan risk, and an accuracy score formulated.

The variables I am trying to predict are:
    1. loan status
    This has been done by counting the total number of loan statuses, where 0 is low risk and 1 is high risk.
   
Once the initial logistic regression model was used, a further logistic regression model was used on resampled training data/
This dataset had used the RandomOverSampler module from the imbalanced-learn library to resample the data, thereby allowing us to compare the original data with oversampled data.

The results were then compared.

## Results

The balanced accuracy scores and the precision and recall scores of all machine learning models are as below:

* Machine Learning Model 1 (Original Data):
  * Balanced accuracy score: 0.9520479254722232
  * Classification Report

            precision    recall  f1-score   support
           0       1.00      0.99      1.00     18765
           1       0.85      0.91      0.88       619



* Machine Learning Model 2 (Resampled Data):
  * Balanced accurary score: 0.9936781215845847
  * Classification Report

            precision    recall  f1-score   support
           0       1.00      0.99      1.00     18765
           1       0.84      0.99      0.91       619

## Summary

* Which one seems to perform best? How do you know it performs best?

  The RandomOverSampler method actually predicts and has less margin of error for the misclassified loans, particularly if they are deemed to be higher risk. In comparison to the original data, the over sampled data also has a higher accuracy score of 99.3% compared to the 95.2% of the original data. Thus, the resampled data model works much better at predicting someone's loan risk. As a credit / lending agency or bank, this is the model I would choose to classify my customers.

* Does performance depend on the problem we are trying to solve?
  The problem we are trying to solve, is to create a machine learning model which correctly solves the issue of classifying loans as high or low risk, without the added human element of having to manually do it ourselves for each loan application. For example, in the RandomOverSampler method, the precision score for those with healthy loans, is 100%, meaning it classifies these people correctly all of the time. However, those with high-risk loans are only classifed correctly 84% of the time. This means the remaining 16% of people are misclassified. This is quite a large number, resulting in potentially a big risk to the bank, as misclassified customers mean they are potentially putting their capital at risk OR that the bank is avoiding giving loans to false high risk customers, resulting in fewer profits. I would say the highest risk to the bank is those which the model classifies as "0 - low risk", but actually are high risk. Luckily, in both the original data and the resampled data, precision is 100% for the low risk classifier meaning that none of these customers are truly high risk and will risk this particular bank's capital.
