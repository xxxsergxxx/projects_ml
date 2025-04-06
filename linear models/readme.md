# 🍷 Wine Quality Prediction  

## 🔍 Overview

This project aims to build machine learning models to predict the quality of wine based on its physicochemical properties. Two datasets are used — **red wine** and **white wine** — with most analysis focused on white wine due to its larger size.

---

## 📋 Agenda

1. **Primary Data Analysis**
   - Checked for missing values
   - Inspected data types
   - Visualized correlations using heatmaps
   - Detected outliers via boxplots

2. **Feature Engineering**
   Created three new features to improve predictive power:
   - `sulfur_ratio` = total sulfur dioxide / free sulfur dioxide  
   - `acid_ratio` = volatile acidity / fixed acidity  
   - `total_acid` = sum of all acid-related features

3. **Feature Scaling**
   - Standardized features using `StandardScaler`

4. **Dataset Splitting**
   - Train/Test split: 80% / 20%
   - Red wine dataset was initially considered as validation but later discarded due to feature distribution mismatch

5. **Model Training (Default)**
   - Trained models with default hyperparameters
   - Used pipelines with cross-validation

6. **Hyperparameter Tuning**
   - Tuned parameters for SGD models using `GridSearchCV`

7. **Evaluation & Comparison**
   - Stored model performance in a `score_store` dictionary
   - Compared models using R², accuracy, and MAE

---

## 🤖 Models & Results

| Model                        | Evaluation Metric | Score      |
|-----------------------------|-------------------|------------|
| Linear Regression           | R² (Test)         | 0.3248     |
| Logistic Regression         | Accuracy (CV)     | 0.5429     |
| OLS Regression (Statsmodels)| MAE               | **0.5768** |
| Poisson Regression          | R² (CV)           | 0.2756     |
| SGD Regressor (Tuned)       | R² (CV)           | 0.2839     |
| SGD Regressor (Default)     | R² (Test)         | 0.3225     |
| SGD Classifier (Tuned)      | Accuracy (CV)     | 0.4449     |
| SGD Classifier (Default)    | Accuracy (Test)   | 0.4408     |

✅ **OLS regression provided the best MAE performance.**

---

## 💡 Key Insights

- Feature engineering significantly improved model interpretability
- Red and white wine datasets are not interchangeable for model validation
- Default SGDClassifier outperformed the tuned version
- Simple linear models provide a solid baseline, but more complex models could improve performance

---

## 🛠️ Technologies Used

- Python 3.10  
- Google Colab / Jupyter Notebooks  
- Pandas, NumPy, Matplotlib, Seaborn  
- Scikit-learn  
- Statsmodels  

---

## 🚀 Next Steps

- Test ensemble methods like Random Forest, XGBoost  
- Try PCA or other dimensionality reduction techniques  
- Build a unified red + white model with a `wine_type` feature  
- Use classification thresholds for quality groups (e.g., low, medium, high)

---

## 📬 Contact

If you have questions or would like to collaborate, feel free to reach out!

**Serhii Kolotukhin**  

🇺🇦 Ukraine  
