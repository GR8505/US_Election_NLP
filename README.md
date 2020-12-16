# Twitter and US Election Results
-------------------------------------------------------------------------------------
### A study in Natural Language Processing (NLP)

![](https://github.com/GR8505/US_Election_NLP/blob/main/Images/fo_us_elex_dashboard_main.jpg)

## Executive Overview
-------------------------------------------------------------------------------------

Based on the results, I am unable to concretely prove that Twitter is a good proxy in determining US Election outcomes.
Looking at the data for the 2008, 2012, 2016 and 2020 elections, all winners had a higher **Average Sentiment Score** than
their opponents.  The closest was in 2012, in which Barack Obama had an average score of 0.08 compared to Mitt Romney's 0.075.

In the **Sentiment Analysis** I looked at the percentage of tweets that were positive, negative and neutral for each candidate.
In each case, the eventual winner recorded a higher percentage of positive tweets except for Barack Obama against Mitt Romney 
in the 2012 election campaign.  Interestingly enough, all winning candidates registered a lower percentage of tweets with 
negative sentiment.

The results of the **Emotional Analysis** is inconclusive to say the least.  In 2008, the top two emotions for Obama were **happy**
and **sad** in that order.  However, that order flipped in 2012 with sad being the highest expressed emotion.  In fact, tweets 
about the Republican representative, Romney, had more __'happy'__ words than sad, but he did not prevail as the winner that year.
In 2016, **sad**, **happy** and **fearful** were the three top emotions expressed for both Hillary Clinton and Donald J. Trump. 
For the recently concluded 2020 elections, **happy** was the top emotion for Trump while **sad** was the number one emotion 
expressed in tweets for Joe Biden.

The **Twitter Engagement** results provided further insights but left me with more questions than answers.  

![](https://github.com/GR8505/US_Election_NLP/blob/main/Images/D3.png)

Please refer to the following link to view the above dashboard. 
https://app.powerbi.com/reportEmbed?reportId=6cb7ce27-d1d7-4a87-9bbc-d93ed5962dc7&autoAuth=true&ctid=26a3e96a-449c-4586-88e2-f15b7d132cd5&config=eyJjbHVzdGVyVXJsIjoiaHR0cHM6Ly93YWJpLXVzLWVhc3QtYS1wcmltYXJ5LXJlZGlyZWN0LmFuYWx5c2lzLndpbmRvd3MubmV0LyJ9


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


