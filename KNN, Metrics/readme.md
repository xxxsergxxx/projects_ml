# 🐚 Abalone Age & Sex Prediction

This project focuses on applying machine learning techniques to the **Abalone dataset** to predict:

- The **age** of abalones (regression task based on the number of rings).
- The **sex** of abalones (classification task based on physical features).

---

## 📂 Dataset

Source: [UCI Machine Learning Repository – Abalone Dataset](https://archive.ics.uci.edu/ml/datasets/Abalone)

Each row represents physical measurements of an abalone. The dataset includes:

- `Sex`: Categorical (M, F, I)
- `Length`, `Diameter`, `Height`: Physical size
- `Whole weight`, `Shucked weight`, `Viscera weight`, `Shell weight`: Various weight measurements
- `Rings`: Target for regression. Age = Rings + 1.5

---

## 🧠 Project Pipeline

### 1. 📊 Exploratory Data Analysis (EDA)
- No missing values.
- One categorical feature: `Sex`.
- Visualizations:
  - Boxplots by `Sex` and by `Rings`
  - Pairplots
- Detected and removed anomalies:
  - `Height > 0.4`
  - `Length < Diameter`
  - `Height < 0.04` with `Length > 0.2`

### 2. 🏗️ Feature Engineering
Two new features were added:
- `Diff_weight = Whole_weight - (Shucked + Viscera + Shell)`
- `Shell_area = Length * Height`

### 3. ⚖️ Feature Scaling
Used `StandardScaler` for numeric features.

### 4. 🔀 Dataset Splitting
Split into:
- Train: 80%
- Test: 10%
- Validation: 10%

---

## 🔢 Regression Task – Predicting Age (`Rings`)

### Models:
- **Baseline K-Nearest Neighbors (KNN)**
- **Tuned KNN (with GridSearchCV)**
- **Linear Regression**

### Evaluation Metrics:

| Model              | R² (CV) | R² (Validation) | MAE (Validation) | MSE (Validation) |
|-------------------|---------|------------------|------------------|------------------|
| Baseline KNN       | 0.48    | –                | 1.61             | –                |
| Tuned KNN          | 0.49    | 0.56             | 1.51             | –                |
| Linear Regression  | 0.54    | 0.60             | –                | 4.47             |

### 🔍 Observations:
- Linear regression slightly outperformed KNN on the validation set.
- Model performance decreases on examples with extremely high/low `Rings`.

---

## 🎯 Classification Task – Predicting Sex

Target: `Sex_encoded` (0 = F, 1 = I, 2 = M)  
Input: All numeric + engineered features

### Models:
- **Baseline KNN**
- **Tuned KNN (GridSearchCV)**

### Evaluation:

| Model         | CV Accuracy | ROC AUC (OVR) |
|---------------|-------------|---------------|
| Baseline KNN  | 0.53        | –             |
| Tuned KNN     | 0.53        | 0.72          |

### 🔍 Observations:
- Classification performance is limited due to overlap in feature distribution across classes.
- Additional feature engineering or data balancing could help.

---

## 📈 Visualization

Predicted vs actual values were visualized for both regression and classification tasks.

---

## ✅ Conclusion

- Feature engineering and data cleaning significantly improved model performance.
- Linear regression outperformed KNN in age prediction.
- Sex classification with KNN achieved moderate results (ROC AUC ≈ 0.72).
- Further improvements could include:
  - Testing other models (RandomForest, XGBoost, etc.)
  - Using PCA or feature selection
  - Balancing class distribution in classification

---

## 🛠️ Tools & Libraries

- Python 3.10
- pandas, numpy, seaborn, matplotlib
- scikit-learn (KNN, LinearRegression, GridSearchCV, pipelines)
- Google Colab

---

## 📌 Author

Serhii Kolotukhin 
Project created as part of Hillel Machine Learning Course
