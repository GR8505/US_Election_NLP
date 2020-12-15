# Twitter and US Election Results
-------------------------------------------------------------------------------------
### A study in Natural Language Processing (NLP)

![](https://github.com/GR8505/US_Election_NLP/blob/main/Images/fo_us_elex_dashboard_main.jpg)

## Executive Overview
-------------------------------------------------------------------------------------
https://app.powerbi.com/reportEmbed?reportId=6cb7ce27-d1d7-4a87-9bbc-d93ed5962dc7&autoAuth=true&ctid=26a3e96a-449c-4586-88e2-f15b7d132cd5&config=eyJjbHVzdGVyVXJsIjoiaHR0cHM6Ly93YWJpLXVzLWVhc3QtYS1wcmltYXJ5LXJlZGlyZWN0LmFuYWx5c2lzLndpbmRvd3MubmV0LyJ9

![](https://github.com/GR8505/US_Election_NLP/blob/main/Images/D3.png)

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


