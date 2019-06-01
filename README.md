# Table of Contents
1. [Dependencies](README.md#dependencies)
1. [Data Structure Used](README.md#datastructure)
1. [Approach](README.md#approach)


# Overview

1. This project implements a Model-based Collaborating Filtering(CF) recommendation system using Spark MLlib and an Item-based CF system
without using a library. 
2. The dataset used is the [Yelp challenge dataset](https://www.yelp.com/dataset/challenge).
![alt text](https://cdn-images-1.medium.com/max/1600/1*SoQdGU3Xefd0bXbqkkI06w.gif "Types of Recommender Systems")


# Dependencies

1. The source code is written in Java 8 and is called Main.java and resides the src folder.
2. src also contain Prescriber.java which is a POJO class that converts each csv line into an object.
3. The compilation instructions are specified in the run.sh file.
4. The following imports are required: import java.io.*;import java.nio.file.*; import java.util.*; import java.util.function.Function; import java.util.stream.Collectors;

# Data Structure Used
* The idea behind my solution is to use Functional Programming. I have used Java Streams to process the data.
* Streams seem to ideal choice while processing millions of records!
![alt text](https://www.logicbig.com/tutorials/core-java-tutorial/java-util-stream/images/java-streams.png "Java Streams")


# Approach

* To start with, entire data was read as stream and each line of input was converted into an object.
* The input stream was mapped to (Drug_Name,Cost) and aggregation was performed to get total cost for each drug.
* Also, the stream was mapped to (Drug_Name,First_Name,Last_Name) and all three entities were combined as key.
* Finally, we had two maps: (Drug_Name, Cost) and (Drug_Name, Unique_Count). The results were written using PrintWriter. 


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
