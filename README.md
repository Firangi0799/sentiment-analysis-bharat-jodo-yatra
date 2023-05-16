# Bharat Jodo Yatra Sentiment Analysis

This project aims to analyze the sentiment of news articles regarding the Bharat Jodo Yatra, an ambitious project by the Indian National Congress (INC) to regain popularity and prepare for the upcoming 2024 general elections. The objective is to determine if the yatra was successful in changing people's perspective towards the party or its leader, Rahul Gandhi.

For a more detailed overview of the project, including the analysis results and insights, please visit the following link: [Bharat Jodo Yatra: What Media is Saying - A Sentiment Analysis Study](https://medium.com/@abhi.kumar0799/bharat-jodo-yatra-what-media-is-saying-a-sentiment-analysis-study-60c57b82a5e1)

## Approach

The sentiment analysis is conducted using the VADER (Valence Aware Dictionary and sEntiment Reasoner) tool. The analysis is performed on two different subsets of data: one representing the sentiment before the yatra and the other during the yatra. News articles are chosen as the dataset for analysis due to the significant influence of news sources in shaping public opinion in India.

## Workflow

### Extracting Text

The news article links are extracted using webscrape.io since free news APIs do not provide access to articles from one year ago without paid plans. Beautiful Soup and requests libraries are used to extract the text content from each link, and the extracted content is stored in an Excel file.

### Pre-processing

Text preprocessing is performed on the dataset of news articles. The dataset is loaded and subjected to various text cleaning operations, including removing punctuation, special characters, and email addresses, as well as converting all words to lowercase. Stop words, such as common words like "the" and "and," are also removed. The cleaned text is saved in a new file for further analysis.

### VADER Sentiment Analysis

The necessary libraries are imported, and the dataset of news articles in Excel format is loaded using Pandas. After dropping any missing values, the SentimentIntensityAnalyzer class from the NLTK library is utilized to perform sentiment analysis on the news articles.

A function called `vader_sentiment_analysis` is defined, which applies the VADER sentiment analysis algorithm to each row of the dataset. The function calculates the positive, negative, neutral, and compound sentiment scores for each row and adds them as new columns to the dataset.

The `vader_sentiment_analysis` function is then applied to the dataset using the apply method in Pandas, which applies the function to each row. Finally, the resulting dataset with the sentiment scores is saved in a new Excel file for further analysis.

## Usage

1. Clone the repository:

   ```
   git clone https://github.com/Firangi0799/sentiment-analysis-bharat-jodo-yatra.git
   ```

2. Install the required dependencies:

   ```
   pip install beautifulsoup4 requests pandas nltk
   ```

3. Prepare the dataset by extracting the news article text and performing pre-processing as described in the workflow section.

4. Run the sentiment analysis using VADER by executing the relevant code with the prepared dataset.

5. Analyze the sentiment scores obtained and draw conclusions regarding the impact of the Bharat Jodo Yatra on people's perspective towards the INC and Rahul Gandhi.

## Contributing

Contributions are welcome! If you have any suggestions or improvements for the sentiment analysis workflow, please feel free to submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
