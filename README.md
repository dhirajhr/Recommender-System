# Table of Contents
1. [Overview](README.md#overview)
2. [Dataset](README.md#dataset)
3. [Performance](README.md#performance)
4. [Output](README.md#output)
5. [Execution](README.md#execution)


# Overview

1. This project implements a Model-based Collaborating Filtering(CF) recommendation system using Spark MLlib and an Item-based CF system
without using a library. 
2. The dataset used is the [Yelp challenge dataset](https://www.yelp.com/dataset/challenge).
## Types of Recommender Systems
![alt text](https://cdn-images-1.medium.com/max/1600/1*SoQdGU3Xefd0bXbqkkI06w.gif "Types of Recommender Systems")
## Collaborative Filtering!
![alt text](https://cdn-images-1.medium.com/max/1600/0*o0zVW2O6Rv-LI5Mu.png "Collaborative Filtering!")

# Dataset 

* I extracted the subset of the whole dataset contains 452353 reviews between 30,000 user and 30,000 business and split them to train data (90%) and test data (10%). 
* There are two files *train review.csv* and *test review.csv*, each file contains three conlumns: *user id, business id, and
stars*. 
* And we will use these two files to finish and test our recommendation system.

# Performance

* I computed the RMSE (Root Mean Squared Error).
* Baseline for Model-Based CF Recommendation System: RMSE = 1.08 and for Item-based: RMSE = 1.11
* I tried to sample the data and even selected only ten most similar users (nearest neighbors) and thus, improved Item-based CF System to RMSE = 1.06

# Output

* user_1, business_2, prediction_12
* user_1, business_3, prediction_13
* . . .
* user_n, business_k, prediction_nk


# Execution

* *JAR Folder* contains a jar file to execute both CF Alforithms.
* Spark-submit --class ModelBasedCF Recommender_System.jar <rating file path><testing file path>
* Spark-submit --class ItemBasedCF Recommender_System.jar <rating file path><testing file path>
    
# USEFUL LINKS

* [Recommendation-AS-A-Service](https://cloud.google.com/solutions/recommendations-using-machine-learning-on-compute-engine)
* [Scaling Recommendation Engines from thousands to million users](https://www.retentionscience.com/blog/scalingrecommendations/)

## Repo directory structure

* The *scala* folder under *main* contains *ItemBased.scala* and *ModelBased.scala* files which employ the respective Collaborative Filtering Algorithms to generate recommendations. 
* The output is written in *output* folder. 
* Also, the *resources* folder contains test and train files.

        ├───src
        │   ├───main
        │   │   ├───output
        │   │   ├───resources
        │   │   └───scala
        │   └───test
        │       └───scala

Email: dramnani@usc.edu
