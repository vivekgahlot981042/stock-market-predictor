# 📈 Stock Market Predictor

> A Machine Learning system that predicts stock price trends with 85% accuracy using Random Forest and 4 other ML models.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)
![Accuracy](https://img.shields.io/badge/Accuracy-85%25-blue?style=flat-square)

---

## 📌 Overview

This project builds a stock market prediction system that forecasts whether a stock price will go **up or down** on the next trading day. Five different ML models were trained and compared to find the best performer. **Random Forest achieved 85% accuracy** with a 20% reduction in error after hyperparameter tuning.

---

## ✨ Features

- 📊 **5 ML Models Compared** — Linear Regression, Decision Tree, Random Forest, SVM, Neural Network
- 🧹 **Feature Engineering** — Moving averages, RSI, volume trends, lag features
- 📉 **Real Data** — Historical stock data fetched from Yahoo Finance (yfinance)
- ⚙️ **Hyperparameter Tuning** — GridSearchCV used for Random Forest optimization
- 📈 **Visualisation** — Matplotlib & Seaborn plots for trends and predictions

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Language | Python |
| ML Library | Scikit-learn |
| Data Source | Yahoo Finance (yfinance) |
| Data Processing | Pandas, NumPy |
| Visualisation | Matplotlib, Seaborn |
| Environment | Google Colab |

---

## 📊 Model Comparison

| Model | Accuracy | Notes |
|---|---|---|
| Linear Regression | ~68% | Baseline |
| Decision Tree | ~72% | Prone to overfitting |
| **Random Forest** | **85%** | **Best performer** |
| SVM | ~75% | Good but slower |
| Neural Network | ~78% | Better with more data |

---

## 🔧 Feature Engineering

Raw stock price data alone is not enough. The following features were engineered to improve model performance:

```python
# Moving Averages
df['MA_7']  = df['Close'].rolling(window=7).mean()
df['MA_21'] = df['Close'].rolling(window=21).mean()

# RSI (Relative Strength Index)
df['RSI'] = compute_rsi(df['Close'], period=14)

# Volume Trend
df['Volume_Change'] = df['Volume'].pct_change()

# Lag Features
df['Lag_1'] = df['Close'].shift(1)
df['Lag_3'] = df['Close'].shift(3)
```

---

## 📂 Project Structure

```
stock-market-predictor/
│
├── data/
│   └── fetch_data.py              # Yahoo Finance data fetcher
│
├── features/
│   └── feature_engineering.py    # MA, RSI, lag features
│
├── models/
│   ├── train_models.py            # Train all 5 models
│   └── evaluate_models.py        # Compare performance
│
├── notebooks/
│   └── stock_prediction.ipynb    # Full Colab notebook
│
├── visualisations/
│   └── plots.py                  # Matplotlib/Seaborn plots
│
├── requirements.txt
└── README.md
```

---

## 🚀 How to Run

```bash
# 1. Clone the repo
git clone https://github.com/comedivek/stock-market-predictor.git
cd stock-market-predictor

# 2. Install dependencies
pip install -r requirements.txt

# 3. Fetch data and train models
python models/train_models.py

# 4. See results
python models/evaluate_models.py
```

---

## 📈 Sample Results

```
Model Evaluation on Test Set:
------------------------------
Linear Regression   → Accuracy: 68.2%
Decision Tree       → Accuracy: 72.5%
Random Forest       → Accuracy: 85.1%  ✅ Best
SVM                 → Accuracy: 75.3%
Neural Network      → Accuracy: 78.4%

Best Model: Random Forest
Error Reduction after tuning: -20%
```

---

## 🔮 Future Improvements

- Add real-time stock data streaming
- Build a web dashboard using Flask/Streamlit
- Include sentiment analysis from financial news
- Try LSTM for time-series based prediction

---

## 👨‍💻 Author

**Vivek Gahlot**
[LinkedIn](https://www.linkedin.com/in/vivek-gahlot-371970256) • [GitHub](https://github.com/comedivek) • [Email](mailto:vt981042@gmail.com)
