# Project 2 - Ames Housing Data
_____________________________

1. datasets - folder with csv files
2. Ames_Housing_Regression_Kaggel.ipynb - Linear Regression modeling for Kaggle submission (many features (~300))
3. Ames_Housing_Regression_Submission.ipynb - Linear Regression modeling for Kaggle submission (few features (~30))

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

### Aim Of The Project

1. Predict price based on feature provided (in dollars).
2. Select features which influence the price of the property.
3. Provide recommendations for stakeholders.

#### Answer the following questions:

1. With an increase of Overall Quality of property does price increase?
2. Does the price vary with different House Style?
3. Does older property cost less than newer ones?


## Data Sets (CSV files):
 - [train](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_2_Housing_Price/datasets/train.csv)
 - [test](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_2_Housing_Price/datasets/test.csv)
 - [sample_submission](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_2_Housing_Price/datasets/sample_sub_reg.csv)
 
## Data [Dictionary](https://github.com/April-DS/General_Assembly_Projects/blob/master/project_2_Housing_Price/datasets/README.md)
______________________________________________

## Three type of modeling will be deploied: Lasso Linear Regression, Multilinear regression and Ridge Linear Regression.


Linear Regression evaluation.

The R2 score is a bit higher (0.8965824658431704) than Lasso (0.8961671756077313).

        --- Baseline model scores ---
        Root mean squared error RMSE: 79309.30582989656
        R2: 0.0
        
        --- Lasso model scores ---
        Root mean squared error RMSE: 25555.91779216108
        R2: 0.8961671756077313
        
        --- LR model scores ---
        Root mean squared error RMSE: 25504.75980561859
        R2: 0.8965824658431704
        
        --- Ridge model scores ---
        Root mean squared error RMSE: 25596.84391872191
        R2: 0.8958343463996501


R2 scores are consistent what can be interpreted that the model is not overfitting.

The scores are high enough to say that the model is not underfitting.

The RMSE is a bit smaller than Lasso, that means that LR model fits the data better.

It can be seen that residuals distributed homoscedastic, but not really random due to outliers.

#### All models gave very similar results, but the LR model perform slightly better. The decision is to keep the first model of Linear Regression due to best R2 and RMSE score.¶

__________________________________________

## Conclusion

Answering question of our project:
    
 1. With an increase of Overall Quality of property does price increase?
**Yes, the price of the property increase**
 - The overall quality of property highly correlated with a sale price (0.804683). The coefficient is positive what means that with an increase in overall quality the sale price also increases.
 - overall quality one of the most influencing features. With an increase in 1 grade of quality the price increase on $ 13986.

 2. Does the price vary with different House Style?
 **Yes, price differ**
 - From the scatterplot above we could see that the median and distribution of sale price vary regarding different house style.
 - 'One story' House style is cost more than other styles.

 3. Does older property cost less than newer ones?
**Yes, the older property cost less**
 - The positive correlation coefficient for year_built (0.573751) demonstrates that newer properties cost higher than older ones.
 - With an increase in one year the property rise in price in $ 5069.
 
 ## Recommendations
 
 **To House Owners, Landlords, Real Estate Agents:**

Features which increase the price of your property:
1. Basement and the overall area of the property.
2. Overall material and finish quality.
3. A number of fireplaces.
4. 'One story' house style.


**To House Buyers:**
1. Houses which were built earlier cost less.
2. Kitchen quality influence on sale price. The cost of renovation of the kitchen should be considered. With an increase in kitchen quality on 1 point, the price rise in $ 6183.

3. Exterior material quality increase price not so drastically, on $ 3879 with better quality. It means that the exterior can be misleading.

## Further research suggestions

The built model of the prediction sale price of property of Ames should be explored on other datasets. It is possible that the model will show worse prediction in other locations.

Further research should consider:
- To evaluate the generalizability of the model more data required.
- Prices higher than $ 500,000 should be explored separately. The model shows worse predictions for such a high price. More data should be collected for high price property separately.
- Features with a negative slope. Additional models should be built to evaluate the influence of the features on price.
- Use more complicated models for prediction.
____________________________________

### Late submission scores:
Public Score now: 28980.29521
    
Public Score for Kaggle: 25888.84521
    
Private Score now: 33462.61116

Private Score for Kaggle: 34211.28292 
