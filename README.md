REPORT: Predicting House Prices in Philadelphia
Tamara Estrada-Martinez
**Data ** from: https://www.phila.gov/property/data/


This project employs multiple techniques, including feature scaling, dimensionality reduction, and model selection, to optimize prediction accuracy. The process is well organized, starting from preprocessing to model training and evaluation, providing insights into the performance of each technique.

**Data Collection**
I found a dataset on the website of The City of Philadelphia. The dataset is called, OPA Property Assessments. It contains 582942 rows of information and 82 columns of attributes.
All I needed to do to be able to use this dataset was download the csv and read in the csv using pandas. The environment I used for this project was Google Colab. 
This dataset contains all the relevant attributes for accurately predicting a house's market price.

**Data Preprocessing**
Data Preprocessing took up about 60% of the time to complete this project. There were many NaN values so in order to most effectively deal with them I compared each attribute to the 'market value' to see how much they affected/meant in relation to each other. The main removal came from dropping all other building types that weren't houses(e.g., apartments and hotels). All other attributes included a lot of handling missing values and removing various outliers. This often was a challenge because many of the attributes were not clearly defined. The latitude and longitude attributes had missing values but the best approach to this was to fill the missing values with the mean of the corresponding attribute. I also took the absolute value of longitude based on how longitude was going to be used as a feature in the machine learning model. 

**Feature Engineering**
Once my data was preprocessed, I began employing feature engineering techniques. For my categorical attributes I used Binary Encoding, for encoding simple non-numeric values I used one-hot encoding, and my numeric data stayed the same. I then standardized the categorical attributes and checked for outliers using z-score detection. Once the outliers were known I then dropped them from the dataframe. I used the threshold of -3 to 3 to determine if a value is an outlier or not. This was all done to help the models performance and accuracy.

**Model Development**
Overview:
I developed various machine learning models for predicting ‘market_value’. Techniques include: Decision Tree Regression, Principal Component Analysis(PCA), and Linear Regression with feature selection through SelectKBest. 
The decision tree model achieved a root mean square error of 2213.08 and a R^2 value of 0.9996. Which indicates that this model has a high level of accuracy. 
The PCA model was tested with different numbers of components (20, 30, 40, 50) in efforts to reduce dimensionality before my regression models transformed the data. All component cases demonstrated a trend where the increasing number of components lead to a significant improvement in the models performance. The RMSR decreased and the R^2 increased as the number of components increased, indicating very good predictions. 
The linear regression with feature selection model did make it difficult to to suggest if  the RMSE or R^2 were better predictors. Other models(PCA OR Decision Trees) were better fit to predict this relationship. 

Discussion:
The Decision Tree Regressor had really high accuracy which may indicate that the model is overfitting. Depending on the application this model may be interpreted differently.
PCA showed to be the best performing model, even as the number of components increased. The extreme improvement from RMSE and R^2 means that a lot of the features prior to data preprocessing were redundant. The values show that the data preprocessing was completed as accurately and efficiently as possible. The dataset was split into training and testing parts, as an 80-20 split, making sure that there's a set to evaluate the model's performance on unseen/unused data. 
Within the PCA model was included a step-by-step approach that shows that the model gets better as more components are added, eventually leading to almost perfect predictions with 50 number components.
The feature selection using SelectKBest with regression selected the top 30 features for the model. This identifies the features with the strongest relationship, eliminating noise. 

**Potential Improvements**
The data preprocessing step could have been a lot more intuative if their were more documentation helping the user understand the dataset. 
Detailed documentation can help users make informed decisions during data cleaning and feature engineering which will improve model accuracy.
Further regularization techniques could provide better models and in hopes prevent overfitting. 
Futher feature engineering techniques could have also been applied to facilitate the analysis and help prevent noise.

**Construction of Test Dataset and Evaluation of Your Model**
Did not have enough time to complete my data set/analysis. Many apologies. 
