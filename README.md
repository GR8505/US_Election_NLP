# Twitter and US Election Results
-------------------------------------------------------------------------------------
### A study using Natural Language Processing (NLP)

![](https://github.com/GR8505/US_Election_NLP/blob/main/Images/fo_us_elex_dashboard_main.jpg)

## Executive Overview
-------------------------------------------------------------------------------------

Based on the results, there is no concrete evidence that justifies Twitter is a good proxy for determining US Election outcomes.
This project focused on **Sentiment/Emotion Analysis** and **Twitter Engagement** to determine whether this form of Social Media
is effective in predicting US election results.

### Sentiment Analysis
![](https://github.com/GR8505/US_Election_NLP/blob/main/Images/D3.png)
Dashboard Link:
https://app.powerbi.com/reportEmbed?reportId=6cb7ce27-d1d7-4a87-9bbc-d93ed5962dc7&autoAuth=true&ctid=26a3e96a-449c-4586-88e2-f15b7d132cd5&config=eyJjbHVzdGVyVXJsIjoiaHR0cHM6Ly93YWJpLXVzLWVhc3QtYS1wcmltYXJ5LXJlZGlyZWN0LmFuYWx5c2lzLndpbmRvd3MubmV0LyJ9

**Sentiment Score** => The Average Sentiment Score for each candidate in which 1 is the most Positive Sentiment, -1 is the most
                       Negative Sentiment and 0 is Neutral Sentiment.

**Sentiment Analysis** => Looks at the percentage of tweets for each candidate that are Positive Sentiment, Negative 
                          Sentiment and Neutral Sentiment.
                          
**Emotion Analysis** => This will analyze the list of words used in the tweets and link them to a particular emotion.  Refer to
                        https://github.com/GR8505/US_Election_NLP/blob/main/emotions.txt for list of words and their linked emotions.

---------------------------------------------------------------------------------------
### Twitter Engagement
![](https://github.com/GR8505/US_Election_NLP/blob/main/Images/D4.png)
Dashboard Link: 
https://app.powerbi.com/reportEmbed?reportId=6cb7ce27-d1d7-4a87-9bbc-d93ed5962dc7&autoAuth=true&ctid=26a3e96a-449c-4586-88e2-f15b7d132cd5&config=eyJjbHVzdGVyVXJsIjoiaHR0cHM6Ly93YWJpLXVzLWVhc3QtYS1wcmltYXJ5LXJlZGlyZWN0LmFuYWx5c2lzLndpbmRvd3MubmV0LyJ9

This analysis gauges whether some of the popular Twitter metrics like **Likes**, **Replies** and **Retweets** are reliable
indicators for determining who wins the race to the White House.  The **Tweet Length** feature was created during the Transformation
process.

---------------------------------------------------------------------------------------
### Key Insights

1) All winners recorded higher **Average Sentiment** scores than their opponents
2) All winners registered a larger percentage of positive tweets compared to their rivals, with 2012 being the only exception.
3) Each winning candidate had a lower percentage of tweets with negative sentiment than their opponents.
4) 


The results of the **Emotional Analysis** is inconclusive to say the least.  In 2008, the top two emotions for Obama were **happy**
and **sad** in that order.  However, that order flipped in 2012 with sad being the highest expressed emotion.  In fact, tweets 
about the Republican representative, Romney, had more __'happy'__ words than sad, but he did not prevail as the winner that year.
In 2016, **sad**, **happy** and **fearful** were the three top emotions expressed for both Hillary Clinton and Donald J. Trump. 
For the recently concluded 2020 elections, **happy** was the top emotion for Trump while **sad** was the number one emotion 
expressed in tweets for Joe Biden.

The **Twitter Engagement** results provided further insights but left me with more questions than answers.  




## Resources
-------------------------------------------------------------------------------------
* Twint
* Python
* MongoDB
* Power BI


## Data Acquisition
-------------------------------------------------------------------------------------
* Scraped Twitter using Twint via Anaconda Environment
* Used the first and last names of each US Presidential candidate as the key search words
  Eg. twint -s "Joe Biden" --since "2020-10-15 17:00:00" --until "2020-10-16 17:00:00" --lang en -o biden3_2020.csv --csv
      twint -s "Donald Trump" --since "2020-10-15 17:00:00" --until "2020-10-16 17:00:00" --lang en -o trump3_2020.csv --csv
* Scraped data on the day following each of the three mandatory Presidential debates for consistency
* Scraped for tweets in the English language


## Data Storage
-------------------------------------------------------------------------------------
* Datasets were stored in MongoDB database
* Created a MongoDB connection using Python to call on each dataset
  See the following link to see how this was executed https://github.com/GR8505/US_Election_NLP/blob/main/NLP.ipynb
  

## Data Preprocessing
--------------------------------------------------------------------------------------
* Kept the following features
  - tweet
  - likes_count
  - retweets_count
  - replies_count
* Cleaned tweets using Regular Expressions (Regex)
* Created tweet_length feature (which measures the number of words in each tweet)
  See the following link to see how this was executed https://github.com/GR8505/US_Election_NLP/blob/main/NLP.ipynb
  

## Machine Learning - Natural Language Processing (NLP)
--------------------------------------------------------------------------------------
* Used the TextBlob library to perform Sentiment Analysis
  - Sentiment and Subjectivity scores were obtained for each tweet
  - Each tweet was ranked as Positive, Negative or Neutral Sentiment based on Sentiment scores
* Used the NLTK library to perform Emotion Analysis
  - Please refer to jupyter notebook for further details on how this was executed https://github.com/GR8505/US_Election_NLP/blob/main/Emotion_Test.ipynb


