# Predicting U.S. Permanent Labor Certification Application Result through Machine Learning Classification
Jon Yu

## Abstract
The goal of this project was to construct and compare various machine learning classification models and select the optimal one to interpret/predict the result of a U.S. Permanent Labor Certification application. U.S. employers can utilize this model to gauge if their skilled foreign workers are at risk of being declined and interpret the feature contribution to the result to improve changes of the worker receiving the certification.

## Data
The processed application data for 2020 and 2021 are available from the U.S. Department of Labor (https://www.dol.gov/agencies/eta/foreign-labor/performance). This serves as the primary data set and is supplemented by three additional indicators of a nation's technical and educational prowess provided from the World Bank (https://www.dol.gov/agencies/eta/foreign-labor/performance).

1) Number of R&D researchers per one million citizens 
2) Spending on education as % of GDP
3) National literacy rate

The above indicators were imported separately to be merged onto the primary data frame on the country of origin column.

## Algorithms/Tools

Tools for the project included -

1) Python to ingest and aggregate the raw data

2) Pandas for exploratory data analysis and cleaning

3) Seaborn and SHAP to visualize feature interaction with target variable

4) SKLearn to perform analyses/comparison of logistic regression, k-nearest neighbors, decision tree, random forest, Gaussian Naive Bayes, Bernoulli Naive Bayes, and XGBoost models, then further tune the best subset

## Findings

In this pursuit, the parameters are defined as follows :

+ True positive (TP) = actually declined application is predicted as being declined
+ True negative (TN) = actually approved application is predicted as being approved
+ False positive (FP) = actually approved application is predicted as being declined
+ False negative (FN) = actually declined application is predicted as being approved


With these in mind, my emphasis is on minimizing false negatives (incorrectly predicting applications as being approved when in reality they will be rejected) and maximizing Recall score which equates to TP / (TP + FN). XGBoost, random forest, and logistic regression models offer the best metrics at first glance of the ROC curve. Upon further tuning of hyperparameters, XGBoost reigns supreme with improvements in AUC (0.87=>0.93), F1 (0.39=> 0.48), and recall (0.79=>0.85) over baseline logistic regression model. 

Biggest contributing features to minizing the chances of application being declined that are also within the employer's/employee's control would be:

1) Higher salary
2) Larger company size in terms of number of employees
3) Higher skill level 
4) Possessing a Bachelor's degree
5) Listing a specific skill set in application

## Communication

The entirety of my Python code is available in the same GitHub repository as this file. A model learning model will be deployed through Streamlit which allows for user input of feature variables to provide a binary output result of the U.S. Permanent Labor Certification application.
