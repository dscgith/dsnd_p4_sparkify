---
# Sparkify - Customer Churn Prediction
This is the final capstone project as part of the Data Science Nanodegree, using PySpark for distributed big data wrangling.
The project was executed in the Udacity workspace, which is why only a small dataset could be used for computation time reasons.

Sparkify is a fictional music streaming service, which has to deal with some percentage of users leaving the service due to unknown reasons. This is why logs containing the activity history of the users come in as a valuable asset to analyse user behaviour. Based on such data the goal is to predict which users will churn, so Sparkify can react to this, for example offering special discounts to keep users with the service.

---

#### Content
+ [Libraries used](#libraries-used)  
+ [Motivation](#motivation)  
+ [Data](#data)  
+ [What has been done?](#what-has-been-done)  
+ [Possible future Improvements](#possible-future-improvements)  
+ [Acknowledgements](#acknowledgements) 

---

### Libraries used
+ PySpark
+ Pandas
+ Numpy
+ Matplotlib
+ Seaborn
+ datetime
+ re
+ IPython

Python Version 3.6.3 was used for this project

---

### Motivation
For this project the goal was to get a better understanding of big data handling, using PySpark, and get some experience with the common ML topic of customer churn prediction on a big dataset. 

---

### Data

| filename | file description |
| :-- | :-- |
| mini_sparkify_event_data.7z | A zipped JSON file containing a list of user interactions with the music streaming service, e.g. sub sites visited, listened songs, registration date etc. |
| Sparkify_Data.ipynb | This notebook contains the data exploration, data preparation, feature engineering and exporting the feature dataset |
| Sparkify_Data.html | HTML export of Sparkify_Data.ipynb |
| Sparkify_Modeling.ipynb | This notebook contains the training and evaluation of different algorithms to predict customer churn |
| Sparkify_Modeling.html | HTML export of Sparkify_Modeling.ipynb |
| mini_sparkify_feature_data.parquet | Dataset which contains the features selected and created in Sparkify_Data.ipynb and used for modeling in Sparkify_Modeling.ipynb |
| best_model | Folder containing the export of the best model found for predicting churn |

The used dataset *mini_sparkify_event_data.json* contains a small subset of a larger dataset mimicking the usage log of a fictional music streaming service called Sparkify. This subset contains 128 MB of data.  
The dataset was provided by Udacity.

---

### What has been done?
+ Sparkify_Data.ipynb  
    + Data cleaning
    + Exploratory Data Analysis
    + Feature Engineering  
    
*The dataset was thoroughly explored by plotting statistical and visualisations to get an understanding of the data and collect ideas of interesting features.  
In the end a feature dataset with 27 features was created for all 225 users of the small dataset by aggregating the data of the users.*
    
+ Sparkify_Modeling.ipynb  
    + Training different models for predicting user churn
    + Grid search and cross-validation
    + Model result comparison  
    
*The feature dataset of the previous notebook was used to train several models like Logistic Regression, DecisionTreeClassifier, RandomForestClassifier, LinearSVC, NaiveBayes and MultilayerPerceptronClassifier. For those models a grid search was done to find optimized parameters by evaluating with F1-Score and cross-validation.  
The MultilayerPerceptronClassifier was found to be best performing, showing a F1-Score of 0.7 using the following parameters found with grid search: maxIter: 20 / layers: [27, 10, 2] / solver: l-bfgs / stepSize: 0.005*
    
---

### Possible future Improvements
+ Use the bigger dataset to get more information and less bias for model training
+ Even out the bias by dropping or duplication data
+ Engineer more features, that improve churn prediction
+ Evaluate downgrade events as indicator for future subscription cancellation
+ Train models on bigger parameter range with grid search

---
### Acknowledgements
The dataset and some starter code were provided by Udacity as part of the Data Science Nanodegree project.

---
