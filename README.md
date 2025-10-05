# SPY Direction Prediction: Decision Tree Classifier

## Overview

This project applies a **Decision Tree Classifier** to predict the **next-day direction of SPY (S&P 500 ETF)** — whether tomorrow’s close will be higher or lower than today’s. It explores the predictive value of standard technical indicators using 10+ years of daily OHLCV data.

---

## Methodology

* **Data Source:** SPY historical data from Yahoo Finance (2010–2024)
* **Target:** 1 if next day’s close > today’s, else 0
* **Features:** Returns, moving averages, RSI, MACD, ATR, stochastic oscillators, and volume indicators
* **Validation:** Temporal train/validation/test split (70/15/15) to prevent data leakage
* **Model:** Scikit-learn Decision Tree optimized via grid search with time-series cross-validation

---

## Results

* **Train Accuracy:** ~91% (expected overfit)
* **Validation Accuracy:** ~51%
* **Test Accuracy:** ~49%
* **ROC-AUC (Test):** 0.49
* Model did **not outperform** naive baselines (e.g., “always up”), reflecting the difficulty of short-term market prediction.

**Top predictive features:**
`StochD`, `ret_5d`, `ret_1d`, `ATR_14`, `SMA_diff`

---

## Insights

* Simple decision trees struggle in efficient markets.
* Technical indicators show limited standalone predictive power.
* Proper temporal validation and baseline comparison are critical for financial ML tasks.
* The project emphasizes **education and transparency**, not trading advice.

---

## Future Work

* Test ensemble models (Random Forest, Gradient Boosting).
* Incorporate macro, sentiment, and alternative data sources.
* Analyze cross-asset generalization and rolling retraining.

---

## Requirements

```
pandas
numpy
yfinance
matplotlib
seaborn
scikit-learn
```

---

## Disclaimer

This project is for **educational purposes only** and **not financial advice**.
Past performance does not guarantee future results.

