 Bitcoin Crash Risk Detection Using Market Sentiment

Project Overview

This project explores whether market sentiment can help identify periods of higher crash risk in Bitcoin.

The idea came from my interest in both finance and data science. Bitcoin is highly volatile and does not have traditional fundamentals like earnings, dividends, or book value, so I wanted to understand whether investor psychology could provide useful signals about future risk.

To investigate this, I combined Bitcoin daily price data with the Crypto Fear & Greed Index and applied machine learning models to study whether sentiment-based features could help detect Bitcoin crash days.

Objective

The main goal of this project was to answer:

**Can market psychology, specifically the Crypto Fear & Greed Index, help detect Bitcoin price crash risk?**

Instead of only trying to predict Bitcoin’s exact next-day return, I also reframed the problem as a classification task: identifying whether the next day could be a high-risk crash day.

Dataset

The project uses daily data from June 2019 to April 2026, covering approximately 2,497 observations.

Data Sources

* Bitcoin daily price data from Yahoo Finance using `yfinance`
* Crypto Fear & Greed Index data from alternative.me API

Key Variables

* Bitcoin open, high, low, close, and volume
* Daily returns
* Fear & Greed sentiment score
* Sentiment labels such as Fear, Greed, Extreme Fear, and Extreme Greed

Feature Engineering

Several financial and sentiment-based features were created, including:

* Daily Bitcoin returns
* Lagged returns
* Moving averages
* Rolling volatility
* Volume change
* Fear & Greed lag features
* Fear & Greed momentum indicators
* Extreme fear and extreme greed flags
* Crash indicator

A crash day was defined as a daily Bitcoin price drop of more than 5%.

Machine Learning Approach

I tested two main approaches:

 1. Regression

The regression models were used to predict Bitcoin’s exact next-day return.

Models used:

* Ridge Regression
* Random Forest Regressor

 2. Classification

The classification models were used to detect whether the next day had a higher risk of being a crash day.

Models used:

* Logistic Regression
* XGBoost Classifier

 Key Results

The regression models showed that predicting exact short-term Bitcoin returns is extremely difficult due to the noisy and volatile nature of the market.

The classification approach was more useful for risk detection. Logistic Regression achieved an AUC of 0.663 and detected 6 out of 11 crash days in the test period.

Key Takeaway

This project showed that while predicting Bitcoin’s exact price movement is very difficult, market sentiment can still provide useful signals for identifying periods of higher crash risk.

The main lesson was that data science may not always give perfect predictions, especially in financial markets, but it can help convert uncertainty into measurable insights and support better decision-making.

 Tools and Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* yfinance
* Requests
* Matplotlib
* Seaborn
* Jupyter Notebook

Project Structure


bitcoin-crash-risk-detection/
│
├── bitcoin_crash_detection.ipynb
├── README.md
├── reports/
│   └── project_report.pdf
└── presentation/
    └── project_presentation.pdf

 Disclaimer
This project is for educational and analytical purposes only. It is not financial advice or an investment recommendation.
