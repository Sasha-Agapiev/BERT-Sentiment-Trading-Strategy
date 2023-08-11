# BERT-Sentiment-Trading-Strategy
Final Project for FRE-7773: Machine Learning for Financial Engineering with Professor Sandeep Jain. 
Built a Twitter sentiment analysis trading strategy using a a fine-tuned BERT model with 110 million parameters. Backtested the strategy on 2017 SPY and DJIA returns using 6M+ tweets for sentiment signals. 

Instructions:
1.   The first step is to import the BERT model and fine-tune its weights using tagged Twitter data. The tagged data I used is found in stock_tweets.csv. After fine-tuning, save the weights to disk so they can be accessed in the main trading strategy notebook.
2.   The main trading strategy is defined in TradingStrategy.ipynb. The methodology is to read through all stock-related tweets in a given lookback period (e.g: 1 day, 4 days, 1 week, etc...) and gauge whether these tweets are more positive or negative than usual. If the positivity score is above a certain threshold, we long an ETF such as SPY or DJIA. If the positivity score is below a certain threshold, we go short. If there is no noticeably positive or negative sentiment, we hold the current position. 
3.    For my backtesting, I used DJIA_price_data.csv and SPY_price_data.csv. The actual tweet dataset I used for my backtesting is far too large for Github uploads. Refer to the Cassandra project (Cresci et al., 2018) for similar datasets. A more practical idea would be to use recent tweet data to build an actual trading model rather than simply backtesting.
4.   The final section of the notebook is devoted to comparing backtesting results to other benchmarks and ML trading strategies. 
