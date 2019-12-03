# DSND Capstone Data Analysis with Spark

Applying machine learning on a large dataset using PySpark

##  Project Overview

I worked with a medium sized (240MB) of the full dataset (12GB) using IBM Cloud.

### What is Sparkify

It is a fake popular digital music service similar to Spotify or Panadora, millions of users stream their favorite songs to this service every day either using the free tier that place advertisments between the songs, or using premium subscription model where they stream music as free  but pay a monthly flat rate, users can upgrade, downgrade, or cancel their service at any time, so it's crusial to make sure the users love the sevice.

## Problem Statement
The data contains the key insights for keeping users happy and helping the business thrive, so me as a data scientist, my rule is helping the business growing and growing, so I can predict which users at risk to churn either downgrading from premium to free tier or cancelling their service alltogether, predicting these users before they leave accurately the business can offer them discounts and incentives, potentially saving this business millions in revenue. 

### Project steps

* Load data into Spark
* Explore and clean data
* create Features
* Build models and compare between them 
* predict the churn according to the best model

## Evaluation Metrics

My main purpose of this project is to predict if the user will churn or not, the best metric to evaluate my prediction is by using F1 score, that Accuracy is used when the True Positives and True negatives are more important while F1-score is used when the False Negatives and False Positives are crucial, and in this prediction the False Negatives and False Positives are crucial, so using f1 score will be more helpful, also Accuracy can be used when the class distribution is similar while F1-score is a better metric when there are imbalanced classes. in my case I have imbalanced class that the churned users are much more than the stayed users (as in the define churn part), In most real-life classification problems, imbalanced class distribution exists and thus F1-score is a better metric to evaluate our model on.

## Justification 
In this machine learning journey, I build a machine learning pipeline by creating indexers for categorical variables(giving each value an index), then  maps a column of category indices to a column of binary vectors using one hot encoders, then combine features into vectors, then normalizing the numeric features, then I used three estimators to choose between them the best one based on the metrics used in evaluation.

The main purpose is to predict if the customer will churn or not, the random frest classifier was chosen in this prediction because it gave us the best performance based on the f1 score. the best model was chosen with the best hyperparameters because I used the cross validation approach in tuning the hyperparameters.

The f1 score on train dataset is 92%, and on test dataset is 80%, but with tuning the hyperparameters the best model gives us 87% on test dataset, so I used it on validation dataset and the f1 score is 81% .

## Files

* Sparkify.ipynb: it is a python 3 notebook which contains the data analysis of medium datasetand machine learning techniques to build the best model. 

## Conclusion

### Reflection

Millions of users stream their favourite songs in this sparkify service, and our purpose in this project to predict if the customer will churn or not, so the PySpark and SparkML were used to analyze data and make predictions, the steps of working on this project followed from doing exploratory data nalysis to build intuition about the data, then feature engineering, then build machine learning pipelines on multiple estimators, and then choose the best one according to f1 score.

Extracting the features from the datset to build machine learning models was the most interesting step, that you can be creative in this part.

### Improvement

That we built a very good model that 81% f1 score was achieved, but there are more ways to improve our result:

1. perform more fine tuning on hyperparameters
2. Using the largest dataset, that will improve the performace of the model because we will have more train dataset
3. Using other classifiers.
4. extracting more features.


## External Libraries
1. [PySpark](https://spark.apache.org/docs/2.2.1/api/python/index.htm), SparkML
