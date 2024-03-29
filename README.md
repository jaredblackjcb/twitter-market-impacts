# Impact of Presidential Tweets on Market Volatility

## Project Overview
The goal of my project is to determine whether President Trump's Twitter
account could be influencing market volatility.
Twitter has rapidly increased the speed of information flow in recent years. 
This project aims to discover how that impacts securities markets. Specifically, 
I will be investigating whether there is a correlation between tweets from the 
president of the United States and market volatility.

## Data
I used the tweepy package to access the Twitter API and acquire a data set 
that contains President Trump's tweets. I cleaned that data and extracted the 
relevant information including the date, text, character count, and number of 
re-tweets. I used the textblob package to perform a sentiment analysis on the
text of each tweet and return a sentiment score between -1 and 1. This data is
stored in a MongoDB database on my local machine.

My second data set is a csv file containing daily prices of the VIX market 
volatility index. The price of this financial instrument reflects the amount of
volatility in the market. The higher the price, the more volatility there is.

## Analysis
The next step in the project will be to pull all the data together into a
Jupyter notebook and perform a regression analysis. I will plot the tweet
frequency and VIX prices side by side to see how much correlation exists 
between them. I plan to quantify the amount of influence each variable has over
market volatility and compute its significance level. That will allow me to draw
a conclusion and determine whether the president's twitter account has a
significant impact on market volatility.

## Unforseen Challenges
The ISOdate data type in MongoDB prevented me from pulling data from the database,
so I ended up just using the dataframe returned by my query of the Twitter API 
without storing it in MongoDB first.

Twitter imposes limits on the amount of data that can be retrieved from a user's
timeline. The tweepy module only allows 200 tweets per query, but using a cursor
with pagination, I was able to get almost 3,000 data points. I originally planned
 to use all of the president's tweets, which would have been over 30,000 data
 points, but that was impossible because of Twitter's developer restrictions.