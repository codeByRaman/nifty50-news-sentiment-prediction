# Financial News Sentiment vs NIFTY50 Analysis

## Overview
This project analyzes the relationship between financial-news sentiment and NIFTY50 market direction. It has two parts: rule-based same-day sentiment analysis and machine-learning prediction of the next trading day's direction.

## Dataset
Place these files in `Data/`:
- `news.csv`
- `nifty50.csv`

The code cleans, groups, and merges the datasets by date. It generates `final_project_dataset.csv`.

## Technologies
Python, Pandas, NumPy, Matplotlib, Scikit-learn, and optionally XGBoost.

## Workflow
1. Load and clean financial news data.
2. Load and clean NIFTY50 OHLC and market data.
3. Group news headlines by date and merge with NIFTY50 data.
4. Calculate a rule-based financial sentiment score using positive and negative financial vocabularies.
5. Perform EDA using sentiment distribution, average sentiment by market direction, and sentiment-vs-market-movement plots.
6. Create next-day prediction features:
   - `sentiment_score`
   - `sentiment_ma3`
   - `sentiment_ma7`
   - `sentiment_std3`
   - `movement_lag1`
   - `movement_lag2`
   - `volume_change`
   - `high_low_spread`
7. Use an 80/20 chronological train-test split.
8. Compare Majority Baseline, Logistic Regression, Random Forest, and XGBoost.
9. Tune Random Forest using `TimeSeriesSplit` and `GridSearchCV`.
10. Evaluate with accuracy, classification reports, and a confusion matrix.
11. Compare a simple model strategy against Buy-and-Hold NIFTY50.
12. Visualize tuned Random Forest feature importance.

## How to Run
```bash
pip install pandas numpy matplotlib scikit-learn xgboost
```

Then run the notebook/script with the `Data/` folder in the expected location.

If XGBoost is not installed, the code continues without it.

## Outputs
- `final_project_dataset.csv`
- Sentiment EDA plots
- Model evaluation results
- Confusion matrix
- Strategy vs Buy-and-Hold chart
- Feature-importance chart

## Limitations
- Part A measures same-day co-movement, not future prediction.
- Part B predicts the next trading day's direction.
- Sentiment depends on the predefined financial vocabulary.
- The simple backtest ignores transaction costs, slippage, and taxes.
- A small financial dataset can produce unstable model performance.
- Accuracy alone does not establish trading profitability.

## Conclusion
The project provides an end-to-end pipeline from financial news and market data to sentiment scoring, feature engineering, chronological ML prediction, model tuning, evaluation, and a simple backtest.
