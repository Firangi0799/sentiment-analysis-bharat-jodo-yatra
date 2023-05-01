Context:
The Bharat Jodo Yatra was a very ambitious project by the Indian National Congress to recover its lost popularity among people and prepare for the upcoming 2024 general elections.

According to the Indian National Congress the yatra aimed to address rampant unemployment & inflation, the politics of hate and division and the over-centralization of our political system, but, deep down we know it was just a gamble to revive the INC.

Problem Statement:
Find out if the yatra was really able to change people’s perspective towards the party or the party leader Rahul Gandhi.

Approach:
I will do sentiment analysis of my dataset using VADER. The analysis will be of two different data subsets to compare the sentiment before and during the yatra.

I chose to go with news articles as my base dataset because twitter has limited the use of it’s API and snscrape wasn’t working with twitter. In India news sources influence people very much, so I’m going ahead with news articles.

Work flow:
Extracting Text:
I extracted the news article links using webscrape.io as I am using news articles for the analysis. There are various free news APIs but they do not provide the feature to extract news articles from one year ago without getting their paid plans, therefore I had only one option left.

I then used Beautifulsoup and resquests to extract all the text content from each link and stored all of it in a excel file.

Pre-processing:
I performed text preprocessing on a dataset of news articles. First, I loaded the dataset and then applied a series of text cleaning operations, such as removing punctuation, special characters, and email addresses, and converting all words to lowercase. I also removed stop words, which are common words like “the” and “and” that are unlikely to contribute to the meaning of the text. Finally, I saved the cleaned text to a new file for further analysis.

VADAR:
I imported the necessary libraries and loaded a dataset of news articles in Excel format using Pandas. After dropping any missing values from the dataset, I created an instance of the SentimentIntensityAnalyzer class from the NLTK library to perform sentiment analysis on the news articles.

Next, I defined a function called vader_sentiment_analysis that applies the VADER sentiment analysis algorithm to each row of the dataset. The function calculates the positive, negative, neutral, and compound sentiment scores for each row and adds them as new columns to the dataset.

I then applied the vader_sentiment_analysis function to the dataset using the apply method in Pandas, which applies a function to each row of the dataset. Finally, I saved the resulting dataset with the sentiment scores to a new Excel file for further analysis.


