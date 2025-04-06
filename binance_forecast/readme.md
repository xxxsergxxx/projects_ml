# 📈 BTC/USDT Volatility Forecasting (Binance, 1-minute data)

This project demonstrates a complete machine learning pipeline to forecast short-term (5-minute) realized volatility for BTC/USDT using high-frequency (1-minute) historical OHLCV data from Binance.

---

## 🎯 Goal

To predict future 5-minute realized volatility using engineered features from past price, volume, and return data, and evaluate the performance of baseline, ML, and deep learning models.

---

## 🛠️ Technologies

- Python 3.x
- Pandas, NumPy
- Scikit-learn
- XGBoost
- LightGBM
- TensorFlow / Keras (MLP, 1D-CNN)
- Matplotlib, Seaborn
- Jupyter Notebook / Google Colab

---

## 📦 Workflow

1. Load and preprocess Binance OHLCV data
2. Calculate log returns and 5-minute forward volatility as target
3. Engineer predictive features:
   - Lagged returns, rolling stats
   - Price action and volume-based features
   - Time-of-day signals
4. Train & evaluate models:
   - Naive Baseline (lag-1)
   - XGBoost (full and reduced)
   - LightGBM (default and tuned)
   - MLP (fully connected neural network)
   - 1D-CNN (temporal feature extraction)
5. Combine models using linear **stacking** and weighted **ensembling**
6. Visualize predictions and analyze errors

---

## 🔍 Key Findings

- Volatility is highly autocorrelated — lag-based baseline is very strong
- Tree-based models (XGBoost, LightGBM) provide limited gain over naive forecasts
- Deep learning models (MLP, 1D-CNN) capture non-linear patterns but require scaling
- Stacking and ensembling improves generalization and outperforms individual models

---

## 📊 Results

| Model                 | MAE        | RMSE       |
|----------------------|------------|------------|
| Baseline (lag-1)     | 0.000097   | 0.000192   |
| XGBoost (full)       | 0.000233   | 0.000361   |
| XGBoost (reduced)    | 0.000236   | 0.000364   |
| LightGBM (default)   | 0.000236   | 0.000363   |
| LightGBM (tuned)     | 0.000250   | 0.000376   |
| MLP (dense)          | 0.000308   | 0.000379   |
| 1D-CNN               | 0.000329   | 0.000438   |
| **Stacked Ensemble** | **0.000213** | **0.000355** |
| **Weighted Ensemble**| **0.000184** | **0.000271** |

✅ Ensemble model achieved the best results across both MAE and RMSE.

---

## 🧪 Model Types

| Type           | Model      | Notes                                       |
|----------------|------------|---------------------------------------------|
| Baseline       | Lag-1      | Simple and surprisingly strong              |
| Tree-based     | XGBoost    | Fast, robust, interpretable                 |
| Tree-based     | LightGBM   | Similar performance to XGBoost              |
| Neural Network | MLP        | Sensitive to scaling, moderate performance  |
| CNN            | 1D-CNN     | Captures short-term patterns from sequences |
| Ensemble       | Stacking   | Linear regression over model outputs        |
| Ensemble       | Weighted   | Tuned weights for smoother blending         |

---

## 🚀 Next Steps

- 📚 Explore LSTM / Transformer-based models for better temporal memory
- 📊 Reformulate as classification task (volatility regime detection)
- ⏱️ Aggregate volatility over longer timeframes (15min–1h)
- 📈 Add multi-asset data (ETH, SPX, DXY) or macro indicators
- 💡 Deploy as streaming model for real-time inference

---

## 📂 Files

- `btc_volatility_forecast.ipynb` – full notebook with code, models, and plots
- `data/` – (not included) 1-minute OHLCV data from Binance
- `README.md` – this file

---

## 🧑‍💻 Author

**Serhii Kolotukhin**  
 Data Scientist  

🔍 Focus: ML in finance, time series forecasting, process automation  
📍 LinkedIn: [serhii-kolotuhkin-25648a166](https://www.linkedin.com/in/serhii-kolotuhkin-25648a166)

---

## 📝 License

Open-source under the [MIT License](LICENSE)
