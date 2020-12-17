# Twitter and US Election Results
### by Dillon Hamilton, Kevin Connolly, Sebastian Lopez and Greg Bhola
-------------------------------------------------------------------------------------
### A study using Natural Language Processing (NLP)

<img src="https://github.com/GR8505/US_Election_NLP/blob/main/Images/fo_us_elex_dashboard_main.jpg" alt="drawing" width="600"/>


## Executive Overview
-------------------------------------------------------------------------------------

Based on the results, there is no concrete evidence that justifies Twitter is a good proxy for determining US Election outcomes.
This project focused on **Sentiment/Emotion Analysis** and **Twitter Engagement** to determine whether this form of Social Media
is effective in predicting US election results.

### Sentiment Analysis
<a href="https://app.powerbi.com/reportEmbed?reportId=6cb7ce27-d1d7-4a87-9bbc-d93ed5962dc7&autoAuth=true&ctid=26a3e96a-449c-4586-88e2-f15b7d132cd5&config=eyJjbHVzdGVyVXJsIjoiaHR0cHM6Ly93YWJpLXVzLWVhc3QtYS1wcmltYXJ5LXJlZGlyZWN0LmFuYWx5c2lzLndpbmRvd3MubmV0LyJ9"> <img src="https://github.com/GR8505/US_Election_NLP/blob/main/Images/D3.png" alt="drawing" width="1200"/> </a>

[![Watch the video](https://github.com/GR8505/US_Election_NLP/blob/main/Images/D3.png)](https://youtu.be/Vopsl1aOs30)
https://youtu.be/jtQU7YTS5jg

For powerBI users, click the above image to view dashboard.


**Sentiment Score** => The Average Sentiment Score for each candidate in which 1 is the most Positive Sentiment, -1 is the most
                       Negative Sentiment and 0 is Neutral Sentiment.

**Sentiment Analysis** => Looks at the percentage of tweets for each candidate that are Positive Sentiment, Negative 
                          Sentiment and Neutral Sentiment.
                          
**Emotion Analysis** => This will analyze the list of words used in the tweets and link them to a particular emotion.  Refer to
                        [emotions.txt](https://github.com/GR8505/US_Election_NLP/blob/main/emotions.txt) for list of words and 
                        their linked emotions.

---------------------------------------------------------------------------------------
### Twitter Engagement
![](https://github.com/GR8505/US_Election_NLP/blob/main/Images/D4.png)
Dashboard [Link](https://app.powerbi.com/reportEmbed?reportId=6cb7ce27-d1d7-4a87-9bbc-d93ed5962dc7&autoAuth=true&ctid=26a3e96a-449c-4586-88e2-f15b7d132cd5&config=eyJjbHVzdGVyVXJsIjoiaHR0cHM6Ly93YWJpLXVzLWVhc3QtYS1wcmltYXJ5LXJlZGlyZWN0LmFuYWx5c2lzLndpbmRvd3MubmV0LyJ9)

This analysis gauges whether some of the popular Twitter metrics such as, **Likes**, **Replies** and **Retweets** are reliable
indicators for determining who wins the race to the White House.  The **Tweet Length** feature was created during the Transformation
process.

---------------------------------------------------------------------------------------
### Key Insights

1) All winners recorded higher **Average Sentiment** scores than their opponents
2) All winners registered a larger percentage of positive tweets compared to their rivals, with 2012 being the only exception.
3) Each winning candidate had a lower percentage of tweets with negative sentiment than their opponents.
4) **Emotional Analysis** showed no clear patterns.
5) **Twitter Engagement** results was inconclusive:
   - In 2008 and 2016, the losers recorded higher Average Likes scores, however, in 2012 and 2020 the winners had higher Average 
     Likes scores.
   - In all years, the winners registered higher Average Replies scores.
   - Average Retweets scores were higher for all winners, except in 2016.
   - Average Tweet Length was higher for the winners in 2016 and 2020 but not in the other two years.

---------------------------------------------------------------------------------------

## Resources
---------------------------------------------------------------------------------------
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
  See the following [jupyter notebook](https://github.com/GR8505/US_Election_NLP/blob/main/NLP.ipynb) to see how this was executed 
  

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
* Obtained the key words (minus stop words) to obtain word cloud https://github.com/GR8505/US_Election_NLP/blob/main/Cleaned_Tweets.ipynb
  ![](https://github.com/GR8505/US_Election_NLP/blob/main/Images/D6.png)
* Used the NLTK library to perform Emotion Analysis
  - Please refer to jupyter notebook for further details on how this was executed https://github.com/GR8505/US_Election_NLP/blob/main/Emotion_Test.ipynb


## Limitations
--------------------------------------------------------------------------------------
* NLP is not 100% accurate in measuring sentiment, as it is unable to read sarcasm or wittiness.
* The location of the tweets were not revealed, so we have no idea if American citizens made these comments.
* Twitter came out in 2006, so there was a dearth of Twitter data in 2008 and 2012.  Back then, it was not the social
  media monster it is today.


## References
--------------------------------------------------------------------------------------
1)_Twint - https://github.com/twintproject/twint_
2)_Sentiment/Emotion Analysis - Attreya Bhatt - https://github.com/attreyabhatt/Sentiment-Analysis_
3)_https://stackabuse.com/python-for-nlp-sentiment-analysis-with-scikit-learn/_
4)_https://stackabuse.com/python-for-nlp-parts-of-speech-tagging-and-named-entity-recognition/_

-----------------------------------------------------------------------------------------
