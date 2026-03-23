# Predict-Bitcoin-Price-Direction
Using Machine Learning methods to Predict Stock Market Price.  

🚀 Project Overview
The notebook implements a full machine learning pipeline, including:

Data Acquisition: Automated fetching of market data via yfinance and on-chain data via CoinMetrics API.

Feature Engineering: Generation of over 35 technical indicators including RSI, MACD, Bollinger Bands, and MVRV Z-scores.

Modeling: Implementation and comparison of five different models:

Linear Regression (OLS)

Logistic Regression (Classification)

Lasso Regression (with TimeSeriesSplit Cross-Validation)

Random Forest Regressor (Hyperparameter tuned)

XGBoost Regressor (Gradient Boosting)

📊 Dataset & Features
The model uses daily Bitcoin data starting from early 2012. Key features include:

Price Action: Log returns, lags (1d, 3d, 7d), and candlestick body/range ratios.

Technical Analysis: SMAs (7, 14, 21, 50), EMA, Relative Strength Index (RSI), and Average True Range (ATR).

On-Chain Data: MVRV (Market Value to Realized Value) ratio, including its 7-day change and 90-day Z-score to capture market over/undervaluation.

Target: Cumulative percentage return over the next 3 days, filtered by a ±1% threshold to reduce noise.

🛠️ Installation
To run this notebook, you will need Python 3.x and the following libraries:

Bash
!pip install numpy pandas matplotlib scikit-learn xgboost yfinance requests
📈 Model Performance
The models are evaluated based on Directional Accuracy (the ability to correctly predict if the price will go up or down).

Results from the current implementation:

Lasso & XGBoost: Generally show the highest directional accuracy (>53%).

TimeSeriesSplit: Used throughout to ensure no data leakage (respecting the chronological order of financial data).

🔍 Key Findings
Feature Selection: Lasso regression helps identify the most impactful features, often highlighting MVRV Z-scores and volatility measures as key predictors.

Non-linearity: Gradient Boosting (XGBoost) tends to capture the complex relationships in crypto markets better than standard linear models.

🛡️ Disclaimer
This project is for educational purposes only. Cryptocurrency trading involves significant risk. This model is not financial advice.

