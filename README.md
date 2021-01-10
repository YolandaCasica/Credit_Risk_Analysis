# Credit_Risk_Analysis
Applying machine learning algorithms to determine a person's credit card risk.

## Project Overview

The purpose of this analysis was to create a machine learning models that could be used to predict credit risk. Machine learning uses statistical algorithms to learn from data patterns and make predictions. There are different ways to build a machine learning, but for this project a supervised machine learning model was built. Supervised machine learning is able to handle labeled data, which was useful since categorical data needed to be trained and tested. The following analysis will describe the process taken to create our prediction model.

## Analysis Results

### Resampling Models

After splitting our dataset into training and testing, resampling models were used to predict credit risk. The first algorithm used was the RandomOverSampler,

![RandomOverSampler](https://github.com/YolandaCasica/Credit_Risk_Analysis/blob/main/Images/RandomOverSampler.png)

Our next algorithm to try was SMOTE:

![SMOTEOversampling](https://github.com/YolandaCasica/Credit_Risk_Analysis/blob/main/Images/SMOTEOversampling.png)

The next algorithm used was the ClusterCentroids:

![ClusterCentroids](https://github.com/YolandaCasica/Credit_Risk_Analysis/blob/main/Images/ClusterCentroids.png)

The SMOTEENN algorithm used a combinatorial appraoch of over- and undersampling:

![SMOTEENN](https://github.com/YolandaCasica/Credit_Risk_Analysis/blob/main/Images/SMOTEENN.png)

* Oversampling, both naive and with SMOTE, did not yield a useable model for the prediction of bad loans. Naive oversampling resulted in a precision score of 0.01 and recall of 0.62. The F1 score of 0.02 reflected athe low precision score. SMOTE oversampling similarly resulted in a precision score of 0.01 and recall of 0.61, and a F1 score of 0.02.
* A model with undersampling yielded similarly poor results, with a precision score of 0.01, recall of 0.65, and F1 score of 0.01.
* Combination sampling resulted in a precision score of 0.01 and recall of 0.70, and a F1 score of 0.02. While the recall score is marginally better than that of the other models, the overall performance of the model is still poor.

### Ensemble Classifier Models

Then, BalancedRandomForestClassifier and EasyEnsembleClassifier were used to try and predict credit risk.

![BalancedRandomForestClassifier](https://github.com/YolandaCasica/Credit_Risk_Analysis/blob/main/Images/BalancedRandomForestClassifier.png)

![AdaBoostClassifier](https://github.com/YolandaCasica/Credit_Risk_Analysis/blob/main/Images/AdaBoostClassifier.png)

* The random forest classifier, with and without AdaBoost, failed to achieve useable performance. The balanced random forest classifier's precision is 0.04, meaning that in 100 loan applications that were flagged to be bad, only 4 were actually bad loan applications. The model's recall/sensitivity is 0.67, meaning that it detected 67% of bad loan applications. The F1 score is low at 0.07, since either a low precision or recall will result in a lower F1 score.
* The random forest classifier with AdaBoost, while achieving better results, still suffered from inadequate predictive power. Its precision score is 0.09 and its recall 0.92. The F1 score, again, is skewed low at 0.16 by the low precision score.

## Project Summary

Based on the analysis points during this project, it was clear that none of the models used here would have a high enough accuracy score to be used for credit risk evaluation since there was only little improvement in accuracy and the overall performances were too unsatisfactory to be reputably used.
