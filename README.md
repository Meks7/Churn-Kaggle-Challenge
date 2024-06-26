# Churn-Kaggle-Challenge
This repository holds an attempt to use machine learning to predict churn at a specified bank using a bank churn dataset (link)

## Overview
The objective was to be able to predict whether a customer would leave or not based on the features given by the kaggle challenge dataset. The objective was approached through the testing of three different machine learning algorithms. The best performing algorithm would subsequently be picked and enhanced through various methods of model tuning. At its peak performance, the model achieved 87% accuracy and an ROC score of about 88.960% (0.88960). The current best performing model on Kaggle has achieved an ROC score of 90.585% (0.90585).

## Summary of Work Done

### Data Understanding

The training data was comprised of 165035 rows and about 14 columns. The test dataset had 110024 rows and 13 columns. Each row represented a customer, and the features describing the customers contained mostly information regarding their status within the bank (e.g. how long they had been with the bank, credit score, their bank balance, etc.) along with some standard demographic information.

### Data Preprocessing

The dataset contained no missing values, however there outliers that heavily skewed some of the deatures. Most of the numerical features (the ones that were not encoded) were standardized. Some of the features were dropped due to having no relevance to the algorithm (e.g. Customer ID). One-hot encoding was applied to the two remaining categorical variables (Geography and Gender).

#### Visualization
![credit score ss](https://github.com/Meks7/Churn-Kaggle-Challenge/assets/144177911/bdb02a7d-bca0-4177-b245-269e6bc8161f)

Much of the data was skewed slightly left or slightly right

![balance ss](https://github.com/Meks7/Churn-Kaggle-Challenge/assets/144177911/ea07a6dc-a7a2-4f96-a4ad-e92bdbe93acf)

While other data contained outliers.

![Corr Heatmap](https://github.com/Meks7/Churn-Kaggle-Challenge/assets/144177911/4fbdeede-efbe-46e4-bc92-0ff773f2a129)

Of all the features, age seemed to have the most impact on the target variable

### Data Formulation

The goal was to use machine learning to predict whether a customer would leave (churn) or stay in this particular bank, basing it's predictions on prior recorded data in the form of a dataset. The input contained features that were used to predict the classes withing the target variable, e.g. estimated salary, geography, how long the customer stayed with the bank (tenure), etc. XGB was primarily used and tuned, however Random Forest and Decision Tree were also initially compared. Decision Tree was initially picked under the guise of ease of use and amateur-friendly properties. Random Forest was picked due to its robustness and overall higher complexity in relation to decision tree. XGB in part for this same reason, as well as its reputation for effective predictive ability. After evaluation of all three models, XGB was ultimately used and its hyperparameters fine-tuned through gridsearch. 

### Training
Hardware was of no concern, however some freezing and long execution times were experienced, though that was partly expected.

### Performance Comparison

The three best performing models included XGB with gridsearch hyperparameter tuning, XGB with SMOTE and hyperparameter tuning, and XGB with bayesian optimization hyperparameter tuning. XGB with bayesian hyperparameter tuning proved to be the most effective, even if only slightly. It performed slightly better in accuracy, and slightly better overall in recall for the positive and negative class. ROC stayed largely the same throughout however took a slight dip when SMOTE was implemented.

![table](https://github.com/Meks7/Churn-Kaggle-Challenge/assets/144177911/85128333-1e15-478f-8caa-0d097921351f)


![R curve](https://github.com/Meks7/Churn-Kaggle-Challenge/assets/144177911/27b1bd23-a64d-4e37-9f7e-4cfd19c0e1fd)

R-Curve of best Model

### Conclusions

XGB, though can be quite complicated, is efficient at predictive modeling and can be easily interpreted depending on what it is being used for. Overall, SMOTE seemed to not have a very good overall effect on the model, but may be useful when it comes to positive class recall (churn).

_______________________________________________________________________


Kaggle Challenge using the Churn Dataset
