# Twitter-Data-Analysis-to-Identify-Urban-Issues

## Table of content

1. [Problem Statement](#problem-statement)
2. [Objective](#objective)
2. [Steps](#steps)
    * [Data Scraping and Manual Labelling](#data-scraping-and-manual-labelling)
    * [Data Preprocessing](#data-preprocessing)
    * [Complaint or Not ? || Categorizing the Complaints using Machine Learning Algorithms](#complaint-or-not---categorizing-the-complaints-using-machine-learning-algorithms)
    * [Visualization](#visualization)
    * [Understanding Results with Real Time Data](#understanding-results-with-real-time-data)
    

## Problem Statement 
  Twitter is a good source for short and real time updates (known as tweets) and there are various techniques to extract and process people’s opinions and sentiments. In our project, we used data from Twitter- social media platform- to find issues that people deal with in day-to-day life. As this generates a huge amount of data, we have restricted our project to only Urban Problems. This includes things as simple as potholes and uncleared garbage dumps to something that can cause huge disastrous consequences like weak bridges and human trafficking. These are problems that disrupt a person’s day-to-day life if not dealt with and so we plan to ensure that the problems are heard and are addressed.
  
  We chose Twitter for two main reasons. One, it uses text as the most common format of posts and two, Twitter is already the most commonly used platform for people to complain or share the problems they’re facing. This makes it a good source for us to collect data and analyze it to find data relevant to urban issues and people do not have tolearn how to use a new interface.
  
## Objective 
The objective of this project is to use tweets to find problems citizens in urban areas are
facing on a daily basis. This is to help identify issues based on their type and bring it to
the notice of the concerned authorities as well as keep the public informed of the
frequency of the issues every fortnight.

This can be summarised in 2 points:
* Identifying issues among thousands of tweets.
* Segregate and publicise the problems based on their type.

## Steps 

### Data Scraping and Manual Labelling
Gaining access to Twitter data is a simple process. First we applied for a developer account. After our request was approved,we scraped tweets with the user location 'Mumbai'. Python library Tweepy was used in the process. Tweepy is an open-sourced library, hosted on GitHub and enables Python to communicate with Twitter platform and use its API. If you need more information on how to use Tweepy you can go to http://docs.tweepy.org/en/latest/getting_started.html


After gathering tweets from Mumbai region, we concluded that we can majorly categorise them into these 17 sections:
1. Trains
1. Traffic
1. Potholes
1. Transport
1. Illegal Parking and Hawkers
1. Illegal Banners
1. Noise 
1. Violence
1. Scam / Fraud
1. Harassessment
1. Robbery
1. Garbage Mismanagement
1. High Electricity Bills
1. Drainage and Water Supply Issues
1. Missing Person
1. Electricity Related
1. Gas Related

We manually labelled almost 10,000 tweets on the basis whether the tweet can be qualified as a complaint or not. Why adopt the tedious process of manually labelling the tweets to create training data, when you can use modified sentiment analysis to do the same ? The answer is simple : Accuracy. Sentiment analysis gives much lower percentage accuracy compared to machine learning algorithms. The manual labelling also included sorting them into the predecided 17 categories. So now we have raw training data ready.

### Data Preprocessing
Data preprocessing aims to facilitate the training/testing process by appropriately transforming and scaling the entire dataset. Before we can implement the machine learning algorithms, we need to clean the tweets to get better accuracy. Cleaning includes spelling correction , removing hashtags and Twitter handles,removing stopwords,lemmatization and removing proper nouns. Various packages are available in python which help to carry out this process. The flowchart below shows the steps and the packages we used to clean the dataset.

![alt text](https://github.com/adiimated/Twitter-Data-Analysis-To-Identify-Urban-Issues/blob/master/diagrams/Data%20Preprocessing%20Steps.png)

### Complaint or Not ? || Categorizing the Complaints using Machine Learning Algorithms
The next task after data preprocessing, is to determine whether a tweet can be classified as a complaint or not. To do the same various machine learning techniques can be used, which give varying percentages of accuracy. Therefore we performed them on the training data to find the one which gave the highest accuracy. Naive Bayes, SVM, Bag of Words,Logistic Regression, K Neighbours, Decision Tree, Random Forest and SGD were implemented. Out of which SVM gave the highest percentage of accuracy. Similar results were observed while categorizing the tweets into the 17 sections. Due to thses analytics, we zeroed on SVM as the algorithm to categorize the tweets.

| ML Technique  | Complaint Detection Accuracy | Categorization Accuracy |
| ------------- | ------------- | ------------- |
| Naive Bayes  | 87.34 %  | 85.65 %  |
| SVM  | 89.08 %  | 87.17 %  |
| Bag of Words  | 85.49 %  | 71.87 %  |
| Logistic Regression  | 88.86 %  | 86.67 %  |
| K Neighbours  | 85.54 %  | 85.60 %  |
| Decision Tree  | 85.82 %  | 85.09 %  |
| Random Forest  | 85.60 %  | 85.60 %  |
| SGD  | 88.58 %  | 86.67 %  |


### Visualization

Data visualization is the act of taking data and placing it into a visual context, such as a map or graph. Data visualizations make big and small data easier for the human brain to understand, and visualization also makes it easier to detect patterns, trends, and outliers in groups of data. Visualization in context of our project helps to understand which specific issues in Mumbai people are tweeting about and which of them are the most prominent. The most prominent issue is the one which has the longest bar in the bar plot. 


### Understanding Results with Real Time Data 

![alt text](https://github.com/adiimated/Twitter-Data-Analysis-To-Identify-Urban-Issues/blob/master/screenshots/Visualization.png)

When we tested our code with real time data, the image above was one of the outcomes. From that we can say that the biggest issue mumbaikers tweeted about in february is 'Traffic', followed by potholes,illegal banners and transportation .

#### Created by Chandrakantha Sruthi P., Shaily Pandey and Pratiksha Naik
