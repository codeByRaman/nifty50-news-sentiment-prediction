# One-Page Project Summary

## Financial News Sentiment vs NIFTY50 Analysis

### Objective
This project investigates whether financial-news sentiment, together with recent NIFTY50 market information, can help explain and predict market direction. The implementation contains rule-based same-day analysis and machine-learning-based next-day prediction. 

### Data & Preprocessing
The project loads `news.csv` and `nifty50.csv`, removes unnecessary news fields, handles missing values and duplicates, converts dates and numeric market columns, sorts the market data chronologically, and merges news with NIFTY50 records by date. 

### Sentiment Analysis
A rule-based financial vocabulary contains positive and negative terms. The system counts positive terms as positive evidence and negative terms as negative evidence to create a daily `sentiment_score`. Scores above zero are classified as UP, below zero as DOWN, and zero as NEUTRAL.

### Machine Learning
For next-day prediction, the project creates sentiment moving averages, sentiment volatility, lagged market movements, volume change, and the high-low spread. The target is the next trading day's market direction. An 80/20 chronological split is used so that future observations are not placed in the training set. 

### Models & Evaluation
The models include Majority Baseline, Logistic Regression, Random Forest, and XGBoost. Random Forest is further tuned using `TimeSeriesSplit` and `GridSearchCV`. The tuned model is evaluated with test accuracy and a confusion matrix. 
### Visualizations & Backtest
The project visualizes sentiment distribution, average sentiment by market direction, sentiment versus market movement, confusion matrix, strategy versus Buy-and-Hold performance, and feature importance. The backtest compares cumulative strategy growth with Buy-and-Hold NIFTY50. 

### Conclusion
The project demonstrates an end-to-end data-science workflow combining financial text sentiment, market features, time-series-aware ML, model tuning, evaluation, and backtesting. Its main limitations are the rule-based sentiment vocabulary, dataset size, and simplified backtest assumptions. 
