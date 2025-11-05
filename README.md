The compressed tweet_data.csv file may be downloaded at https://drive.google.com/file/d/1x2IR6PC0h7HgWAg3Y_3UueQKzZLNG_WI/view?usp=sharing

## Overview

The goal of the lab was to use **financial tweets** to explore the predictive power of social media for stock markets. The tasks included text preprocessing, sentiment analysis, and the creation of a firm-level measure of media attention that could serve as a potential financial factor.

## Objectives

The main objectives of the lab were to:

1. **Manipulate and describe financial tweets**
2. **Clean and preprocess textual data**
3. **Perform sentiment analysis using machine learning models**
4. **Construct and analyze a measure of media attention**
5. (Optional) **Explore the relationship between media attention and stock returns**


## Methodology

### 1. Data Import and Exploration

I imported the dataset `Data_PCLab3_Twitter_Stock_Sentiment.csv`, which contained financial tweets with sentiment labels.  
I began by performing **descriptive statistics** on the data:
- Number of tweets in the sample  
- Average number of words per tweet and its distribution  
- Average sentiment score  
- Visualizations of tweet length and sentiment distribution  

This provided an overview of the dataset structure and basic characteristics.

### 2. Data Cleaning and Text Preprocessing

To prepare the tweets for analysis, I applied several cleaning steps:
- Removal of URLs, mentions, hashtags, punctuation, and emojis  
- Tokenization and lemmatization  
- Stopword removal  
- Normalization using *Ekphrasis* (to handle hashtags, emoticons, and elongated words)

I then created **word clouds** for positive and negative tweets separately to visualize the most frequent terms used in each sentiment category and calculated the number of unique words.

### 3. Sentiment Analysis

The dataset included a binary sentiment variable (1 = positive, 0 = negative).  
To evaluate its reliability, I built an **independent sentiment model** using pretrained transformers such as **FinBERT** and **Twitter-RoBERTa**.  
I compared the model predictions against the original sentiment labels to assess consistency and model performance.  
This helped verify whether the provided sentiment classification could be trusted.

### 4. Measuring Media Attention

Using the list of stock tickers from the previous lab session, I calculated **media attention** for each stock as the total number of tweets mentioning it.  
I also broke down attention into positive and negative components and computed measures of **disagreement** (sentiment dispersion).  
The stocks were ranked according to their total media attention, and results were visualized through bar charts and summary tables.

### 5. Linking Media Attention to Returns

Finally, I created **decile portfolios** based on the media attention measure and analyzed whether higher attention correlated with stock returns.  
The analysis was extended to check whether Twitter-based attention might represent a **potential factor** in asset pricing.  
Optionally, the residuals from a **Fama–French 5-factor regression** were used to control for traditional risk factors, exploring whether the media attention effect remained significant.


## Results and Insights

- The tweet dataset displayed clear sentiment patterns, with noticeable variation in text length and vocabulary.  
- The sentiment analysis using FinBERT improved accuracy compared to the provided labels.  
- Stocks with higher Twitter attention showed distinct return behaviors, suggesting that **social media attention may contain predictive information**.  
- The optional Fama–French adjustment indicated that part of this relationship persisted beyond standard risk factors.


## Repository Contents

- `PCLab#3.ipynb` – Jupyter Notebook containing the full analysis, code, and results  
- `FBD_Week4_PCLab3_2025.pdf` – Slide deck describing the assignment and tasks  


## Requirements

Key Python packages used in the notebook include:
- `pandas`, `numpy`, `matplotlib`, `seaborn`
- `nltk`, `gensim`, `wordcloud`
- `ekphrasis`
- `transformers`, `torch`, `sklearn`


## Acknowledgements

This project was developed as part of the **Finance with Big Data (20598)** course at **Bocconi University**, instructed by **Clément Mazet-Sonilhac**.  
All data and assignment materials were provided for educational purposes.
