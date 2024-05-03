# Churn-Kaggle-Challenge
This repository holds an attempt to use machine learning to predict churn at a specified bank using a bank churn dataset (link)

## Overview
The objective was to be able to predict whether a customer would leave or not based on the features given by the kaggle challenge dataset. The objective was approached through the testing of three different machine learning algorithms. The best performing algorithm would subsequently be picked and enhanced through various methods of model tuning. At its peak performance, the model achieved 87% accuracy and an ROC score of about 88.960% (0.88960). The current best performing model on Kaggle has achieved an ROC score of 90.585% (0.90585).

## Summary of Work Done

### Data Understanding

The training data was comprised of 165035 rows and about 14 columns. The test dataset had 110024 rows and 13 columns. Each row represented a customer, and the features describing the customers contained mostly information regarding their status within the bank (e.g. how long they had been with the bank, credit score, their bank balance, etc.) along with some standard demographic information.

### Data Preprocessing

The dataset contained no missing values, however there outliers that heavily skewed some of the deatures. Most of the numerical features (the ones that were not encoded) were standardized. Some of the features were dropped due to having no relevance to the algorithm (e.g. Customer ID). One-hot encoding was applied to the two remaining categorical variables (Geography and Gender).


_______________________________________________________________________


Kaggle Challenge using the Churn Dataset
