# ML Classification Project for Megaline (part of the Tripleten DA course)  

### Table of Contents:

- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools](#tools)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Classification](#classification)
- [Summary and recommendations](#summary-and-recommendations)

### Project Overview:

The aim of this project is to develop a model for Megaline Mobile Carrier that will classify it's customers into the right carrier plans. The two classification options are Ultra and or Smart, depending on the customers usage and behaivor. I used 3 different classifiction models (Decision Tree, Random Forest and Logistic Regression) to find the best fitted model. The cutoff that was requested by the customer was 75% accuracy. 

### Data Source:

The data source for this project is in 'user_behavior.csv' file in this repo. 
it contains a data frame where every observation contains monthly behavior information about one user. The information given is as follows: 

- сalls — number of calls,
- minutes — total call duration in minutes,
- messages — number of text messages,
- mb_used — Internet traffic used in MB,
- is_ultra — plan for the current month (Ultra - 1, Smart - 0).

The df was preproccessed to filter out null values and duplicates, so the removal of these values is not shown in the notebook. 

### Tools:

- Jupyter Notebook - Exploratory data analysis

### Exploratory Data Analysis:

The purpose of the EDA is to understand the general outlook of the data while prepering it for training the models. These are the steps I took: 
1. Describing the data when grouped by is_ultra column to see diffrences in descriptive values such as mean, median and count. 
2. Checking for extreme values and removeing them, in order to train the models on the best represntive data.
3. Checking for correlations between coloumns, and remove correlated coloumns.
     
### Classification: 

This consisted of several steps:
1. Spliting the data into train, validation and testing set in a 3:1:1 ratio, respectively.
2. Spliting each set into target (is_ultra column) and features (all the other columns)
3. Creating a loop to fit the hyperparameters in the most accurate way
4. Repeat 2 and 3 with each of the different models (decision tree, random forest and logistic regression)
5. Santiy checking the best fitting model for precision and recall

### Summary and recommendations:

The highest accuaracy score model was Random Forest (classifier) However, the model is of pretty low quality. It is possible the features in our data are not good predictors of whether the customer should be classified to the Ultra or Smart plan, and we should consider adding other predictors, prehaps regarding the cost of the plan, first connections to the customer who already have the same plan, or even field of work. It seems the useage alone is not a good predictor for recommending a specific plan.


