# Project 2 - Ames Housing Data
___________________________

Contents:
 - [Problem Statement](#Problem-Statement)
     - [Aim Of The Project](#Aim-Of-The-Project)
 - [Data Overview](#Data-Overview)
 - [Data Cleaning](#Data-Cleaning)
     - [Encoding Ordinal Columns Into Ints](#Encoding-Ordinal-Columns-Into-Ints)
     - [Missing Data](#Missing-Data)
     - [Data Type](#Data-Type)
     - [Clean Datasets As csv](#Clean-Datasets-As-csv)
     - [Data Dictionary](#Data-Dictionary)
 - [Exploratory Data Analysis](#Exploratory-Data-Analysis)
     - [Summary Statistics](#Summary-Statistics-Of-Train-Dataset)
     - [Outliers And Anomalies](#Outliers-And-Anomalies)
     - [Exploring Columns Relationship](#Exploring-Columns-Relationship)
 - [Feature Creating](#Feature-Creating)
 - [Feature Selection](#Feature-Selection)
     - [Backward Elimination](#Backward-Elimination)
     - [Recursive Feature Elimination](#Recursive-Feature-Elimination)
 - [Preprocessing Data](#Preprocessing-Data)
 - [Modeling And Evaluation](#Modeling-And-Evaluation)
     - [Lasso](#Lasso)
     - [Linear Regression](#Linear-Regression)
     - [Ridge](#Ridge)
 - [Pridictions](#Pridictions)
 - [Inference](#Inference)
 - [Conclusion](#Conclusion)
 - [Recommendations](#Recommendations)
 - [Further research suggestions](#Further-research-suggestions)
 
 ___________________________________
 
 
 ## Problem Statement
 
 A real estate market Dataset from Kaggle was used to identify and study the features which can contribute the most into the price (in dollars) prediction of property in Ames, Iowa, USA. The Dataset comprises sales from 2006 to 2010.

The Regression models (Linear Regression, Lasso Regression and Ridge Regression) were used for price prediction based on features from provided Dataset (CSV files). The performance of the model was gauged with R2 value.

The model is essential for all market stakeholders: house owners, landlords, real estate agents, their clients etc. It gives them the possibility of short-term and long-term financial planning as well as realistic property price.
