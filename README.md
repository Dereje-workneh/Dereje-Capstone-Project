
# Analyzing Stock Market Price Based on Historical data and twitter sentiment Analysis: Excutive summamry

  Dereje Workneh  June 09, 2020

  Data Science Immersive Student @ General Assembly


### Introduction
In this project, we would like to create a system that predicts stock market movements on a given day, based on time series data and market sentiment analysis. We will use Twitter data on that day to predict the price sentiment to perform analysis on historical data.

Sentiment analysis is a discipline of text classification. Sentiment analysis refers to the practice of applying NLP and text analysis techniques to identify and extract subjective information from a piece of text. Sentiment analysis works better on text that has a subjective context than it does on text with only an objective context. This is due to the fact that if a body of text has an objective context or perspective to it, the text usually depicts some normal statements or facts without expressing any emotion, feelings, or mood. Subjective text contains text that is usually expressed by a human having typical moods, emotions, and feelings.

It is also to build sentiment analysis model on Apple products that allowing us to categorize words of comments based on their sentiments such as whether they are positive, negative and also the magnitude of it.

## Objective
Given the time series data and Twitter data from January 2015-01-01 to June 2020-06-06, we will construct a system to predict stock market price (up, same, down) on a given day, based on the key attributes computed from the historical data from the past five years and market sentiment. Given these inputs, the model will be expected to output a prediction of apple for a given time.
## Statement of the Problem:
I would like to train the system on three models and compare the performances of these three models. Furthermore, I would like to determine whether the addition of a public sentiment attribute is beneficial in the prediction of price movement. To help me examine these problems, we would like to raise three questions:

- Which classification method is the most accurate in predicting market movement on a given day? arima model?
- Does the addition of public sentiment, in this case from Twitter, help in the prediction of market movement



## Procedure:
1. Data collection
2. Data cleaning and Explatory data analysis (EDA)
3. Preprocessing and modeling(tuning)
4. Validation of models
5. Conclusion and recommendation


### Data collection:
- For time series data analysis from Yahoo! Finance into csv and for sentiment analysis from the Twitter.

### Data Cleaning and EDA
During data cleaning of comments, I removed hyperlinks, html, punctuation, the same words with two or more letters, duplicate messages, whitespace, non standard characters.  Stop words were removed and some of the words in the commnents were lemmatized. The EDA result showed tha more than 20 most frequent words were unique classes in both physics and chemistry.


### Preprocessing, Modeling and Evaluation
#### Stock Data Preprocessing
The data we collected from Yahoo! Finance had to be
preprocessed in order to become suitable for further reliable analysis. The main problem we faced was that while
the Twitter data were available for each day of the week, including weekends, the stock values were absent for weekends
and other holidays when the market is closed. In order to
fill the missing values, we overcame this problem by using a
simple statistical function. If the value that is missing is y,
the previous known value is xprevious and the next known
value is xnext, then the value y will be:
y = (xprevious + xnext)/2.
This approximation works most of the time very well except in cases of unexpected rapidly rise and fall
#### Twitter Data Preprocessing
For the process of collecting tweets, Twitter provides two
possible ways to gather Tweets: the Streaming API or the
Search API. The Streaming API allows users to obtain realtime access to tweets from an input query. The user first
requests a connection to a stream of tweets from the server.
Then, the server opens a streaming connection and tweets
are streamed in as they occur, to the user. However, there
are a few limitations of the Streaming API. First, language is
not specificable, resulting in a stream that contains Tweets
of all languages, including a few non-Latin based alphabets,
that complicates further analysis.
Because of these issues, we decided to go with the Twitter
Search API instead. The Search API is a REST API which
allows users to request specific queries of recent tweets. The
Search API allows filtering based on language, region, geolocation and time. There is a rate limit associated with the
query, but we handle it in the code.

#### Sentiment Analysis
The text of each tweet includes a lot of words that are
irrelevant to its sentiment. For example, some tweets contain URLS, tags to other users, or symbols that have no
meaning. In order to better determine a tweet’s sentiment
score, before anything else we had to exclude the “noise”
that occurred because of these words. For this to happen,
we relied on a variety of techniques using the Natural Language ToolKit (NLTK) for Python. 

#### Models
To predict an outcome based on time series data, we  use used a time series model which is called Auto Regressive Integrated Moving Average (ARIMA) is used as the machine learning technique to analyze and predict future stock prices based on historical prices.
Accurate classification continues to be an engaging problem in machine learning and data mining. It is more than
often that we need to create a classifier with a set of training data and labels. In our case, we want to build a classifier that is trained on our “positive” and “negative” labelled
tweet corpus.This way, the classifier will be able to label future tweets as either ”positive” or ”negative”, according to
each tweet’s characteristics and features. In this project,
we examine two classifiers used for text classification: Naive
Bayes Bernoulli and Support Vector Machines (SVM).

![Alt text](https://github.com/Dereje-workneh/Dereje-Capstone-Project/blob/master/Correlation%20between%20tweet%20and%20stock%20prices.png)

### Conclusions and Recommendation
Stock price forecasting is an important and thriving topic in financial engineering especially since new techniques and approaches on this matter are gaining ground constantly. In the contemporary era, the ceaseless use of social media has reached unprecedented levels, which has led to the belief that the expressed public sentiment could be correlated with the behavior of stock prices. The idea is to recognize patterns which confirm this correlation and use them to predict the future behavior of the various stock prices. With no doubt, though uninteresting individually, tweets can provide a satisfactory reflection of public sentiment when taken in aggregate. In this paper, we develop a system which collects past tweets, processes them further, and examines the effectiveness of various machine learning techniques such as Naive Bayes Bernoulli classification and Support Vector Machine (SVM), for providing a positive or negative sentiment on the tweet corpus. Subsequently, we employ the same machine learning algorithms to analyze how tweets correlate with stock market price behavior. Finally, we examine our prediction's error by comparing our algorithm's outcome with next day's actual close price. Overall, the ultimate goal of this project is to forecast how the market will behave in the future via sentiment analysis on a set of tweets over the past few days, as well as to examine if the theory of contrarian investing is applicable. The final results seem to be promising as we found correlation between sentiment of tweets and stock prices. Thus, further research could
also analyze a wider of basket of stocks, ideally not highly correlated to broader markets,
to verify and improve on our findings. Future
work on this topic could also involve testing
recurrent neural networks on the data, which
would be particularly suitable for time series
prediction problems like this one.









