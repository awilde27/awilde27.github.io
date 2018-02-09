---
layout: post
title: User Analysis on Yelp Reviews
subtitle: A Simple Approach to Sentiment Analysis
comments: true
gh-repo: awilde27/Info-Class-Projects
image: /imgs/yelp_logo.png
---


1. [Intro](#intro) 
2. [Setup](#setup)
3. [Hypotheses](#hypotheses)
4. [Data Processing](#data-processing)
5. [Method](#method)
6. [Results](#results)
7. [Conclusions](#conclusions)


# Intro

This post is inspired by an assignment I was given in my Data Mining and Analytics class, where we were given a dataset containging Yelp reviews and had to complete some analysis on it. In the process, I decided to ask my own "research" question about the dataset in hopes of possibly finding insight beyond what was found in the class assignment. 

# Setup

The Yelp reviews dataset contains the features business ID, user ID, stars, review text, review date, number of cool votes, number of funny votes, and number of cool votes. For those unfamiliar with the Yelp app, a user has the ability to vote on another user's review in one of those three categories.  

# Hypotheses

### Hypothesis 1

One of the questions I set out to answer is whether or not there is a pattern between review length and rating (in stars) given. It is pretty intuitive to think that a person who did not like the experience at the place they visited would have much more to say than a person who did enjoy his or her experience. 

The counterpoint to this idea is that there are people out there who write long reviews on places they did enjoy. Although I don't believe the data will be able to answer this question, my intuition tells me that this has more to do with the reviewer's personality rather than an overall trend.

### Hypothesis 2

I also want to delve into the votes given to user's reviews. The reason behind this is to see if there is any pattern with the length of the review and the type and quantity of votes given to that review. I believe that there will be a strong relationship between a user's average ratings and the number of useful votes given to the review. For example, really positive reviews may be on average shorter under the first hypothesis, and this may correspond to less useful reviews since there may not be as much useful information about the location of interest.

Ultimately, if these hypotheses are correct, there will be some interesting conclusions to make about the nature of reviews, ones that can use pretty simplistic data analysis instead of expensive and complex algorithms such as textual sentiment analysis among others.

# Data Processing

In the assignment, we engineered many new features based on the original. The notable features that I ended up choosing for this analysis were: 

> 1. Average review text length (non-space characters)
2. Average number of stars given
3. Average "terseness" rating for someone's reviews (Useful votes / length of review) * 100
4. Most frequently used star rating for each reviewer

These features are perfect for performing the clustering I am interested in.

# Method

The primary goal of this analysis is to cluster the data in a way that will provide insight on the aformentioned relationships. As a result, I used K-Means clustering with SKLearn after preprocessing with an aggregation on the User ID. Aggregating by User ID beforehand is useful because it greatly reduces the size of the data without losing much information with respect to the objectives. In other words, the dataset goes from over 550,000 rows to just over 100,000. 

Regarding the number of clusters, I chose k=4 and k=8 for the cluster sizes. These were picked to see if there would be any difference in the clustering algorithm with a relatively small cluster size and a relatively large cluster size. 

# Results

These are the results of using K-Means for the first hypothesis. 

![Cluster 4](/imgs/yelp_cluster4_table.png)

![Cluster 8](/imgs/yelp_cluster8_table.png)


# Conclusions

Conclusions go here.





