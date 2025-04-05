# 📈 BTC/USDT Volatility Forecasting (Binance, 1-minute data)

This project demonstrates a complete machine learning pipeline to forecast short-term (5-minute) realized volatility for BTC/USDT using high-frequency (1-minute) historical OHLCV data from Binance.

---

## 🎯 Goal

To predict future 5-minute realized volatility using engineered features from past price, volume, and return data, and evaluate performance of baseline and ML models.

---

## 🛠️ Technologies

- Python 3.x
- Pandas, NumPy
- Scikit-learn
- XGBoost
- LightGBM (CPU & GPU experiments)
- Matplotlib, Seaborn
- Jupyter Notebook / Google Colab

---

## 📦 Workflow

1. Load and preprocess Binance OHLCV data
2. Calculate log returns and 5-minute forward volatility (target)
3. Engineer lag-based and rolling features
4. Train & evaluate models:
   - Naive Baseline (lag-1)
   - XGBoost (default and reduced features)
   - LightGBM (default, tuned, CPU)
5. Visualize results and analyze prediction errors

---

## 🔍 Key Findings

- Baseline model using previous volatility outperformed all ML models
- LightGBM and XGBoost had very similar performance
- GridSearch-based tuning yielded minimal gains
- GPU-based training was unstable in Google Colab (fallback to CPU)

---

## 📊 Results

| Model                   | MAE        | RMSE       |
|------------------------|------------|------------|
| Baseline (lag-1)       | 0.000097   | 0.000192   |
| XGBoost (all)          | 0.000233   | 0.000361   |
| XGBoost (reduced)      | 0.000236   | 0.000364   |
| LightGBM (default)     | 0.000236   | 0.000363   |
| LightGBM (tuned, CPU)  | 0.000250   | 0.000376   |

---


## 🚀 Next Steps

- Explore LSTM or TCN models for sequential learning
- Try volatility classification (low/medium/high) instead of regression
- Aggregate volatility to higher timeframes (15m–1h)

---

## 📂 Files

- `btc_volatility_forecast.ipynb` – full notebook with code, visualizations, and explanations
- `data/` – not included (Binance OHLCV 1-minute)
- `README.md` – this file

---

## 🧑‍💻 Author

**Serhii Kolotukhin**, Feedmill engineer & Data Scientist  
📍 Focus: ML in finance, process optimization, time series  
🔗 www.linkedin.com/in/serhii-kolotuhkin-25648a166

