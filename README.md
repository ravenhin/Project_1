# Ames, IA Housing Data for Predicting Home Sale Price

### Executive Summary

In a Kaggle challenge, we were given data from Ames, IA to create a model that would predict the sale price of a house. In order to create a model, it is best to explore the data to understand the different variables as well as make clean the data. After exploring the data, I created different kinds of linear regression models, and evaluated their r-squared values. Some of the models were created from exploratory data analysis that was done, and other models were created from research I had done on variables that can determine the price of a house.

### Description of Data

Size: 81 features and 2051 samples

Source: [Kaggle Data Dictionary](https://www.kaggle.com/c/dsi-us-10-project-2-regression-challenge/data)

Target: Regression

### Exploratory Data Analysis (EDA)

In order to understand the data set, it is best to look through and understand what the data types are of the different features as well as look at the amount of missing data that is in the set. I concluded that there was not much data missing, so then I created a correlation graph of all the numerical data. Below is a graph of the correlations I cared about exploring because of their relationship to sale price.

Sale Price Correlation Plot from EDA
![Correlations](Sale%20Price%20Correlations.png)

Once I looked at correlations, I decided to create a model based solely on the features that had a positive correlation of .5 or more thinking that this would give me a high performing model because of the initial relationship. After creating this model, I explored the data further and created pairplots of all the numeric data in relation to sale price to get a better understanding of the shape of the data. It was in looking at the graphs that I found there were outliers that could have been hindering the performance of the model. So I decided to drop a couple of samples that had outliers in multiple features. Once I did this I also included all of the features that were numerical in order to work on the bias-variance trade-off and ultimately improve the model. After creating this model, I found that the scores for this model did improve from the first model I had created.

After doing EDA on the data, I decided to research what determines the price of a house, and found research that lead me to create models with features that supported the research. Then I created another model based on further research I did where certain features were discussed as not adding value or no having any affect on the price of a house, and drop these features from the previous model. Ultimately, I found that having more features in a model in this case was more helpful.

In order to make improvements to the model I created based on research, I decided to create a lasso model of the initially researched features. This improved my model, but only to perform as well as the model that had all the numerical features. Then I wanted to compare my lasso model to a ridge model to see which would perform better, in this case the Lasso Model performed better than the Ridge Model. Below are the cross validation scores, train scores, and test scores for the model where appropriate.

|Model | Mean Cross Validation Score | Train Score | Test Score |
|------|------------------------|-------------|------------|
|Linear Regression: Positive Correlation values above .5|0.75|0.75|0.85|
|Linear Regression: All Positive Correlations| 0.85| 0.86| 0.88|
|Linear Regression: Researched Variables| 0.84| 0.85| 0.83|
|Linear Regression: Further Researched Model| 0.83| 0.85| 0.81|
|Lasso Model| N/A | 0.91| 0.87|
|Ridge Model| N/A | 0.94| 0.85|

### Primary Findings/Conclusions:

In creating the different models, I found that researching what is important in a real world instance may not be the best at truly deciding what would be best for determining the sale price of a house. In this case the more information you have about different features on a house the better off your model will be. Creating a model with more features and perhaps including even more features such as information about nearest grocery stores, nearest schools, etc. could improve the model even more.  

Also when investigating my lasso model coefficients to see what features had the most effect on the model. The engineered feature, above grade (ground) living area square feet times total square feet of basement area had the biggest effect on the model because practically this makes sense. If you are able to understand how much space is in a house and on each level it can only make the house that much more valuable.
