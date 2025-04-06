# 🧠 Credit Risk Classification Using Decision Tree & Logistic Regression

This project focuses on building classification models to predict **credit risk** using the [UCI Credit Approval Dataset](https://archive.ics.uci.edu/ml/datasets/Credit+Approval). Two models are trained and compared:
- 🌳 `DecisionTreeClassifier`
- 📈 `LogisticRegression`

---

## 📂 Dataset Overview

- 🗂 **File**: `crx.data`
- 📏 **Rows**: 690
- 📊 **Features**: 15
- 🎯 **Target**: A16 (credit approval `+` or `-`)

---

## 📊 EDA & Data Cleaning

### 🔍 Issues Identified:
- Missing values marked with `'?'`
- Zero values and suspicious placeholders like `"00000"` in numeric features (`A14`, `A15`)
- Mixed data types — categorical features stored as `object`

### ✅ Actions Taken:
- Dropped rows with `'?'` (only 37 rows)
- Converted relevant features (`A2`, `A14`, `A15`) to numeric
- Filtered out outliers:  
  - `A14` capped at 2000  
  - `A15` capped at 22000

---

## 🛠️ Feature Engineering

- 🧮 `A14_2 = A14 / A2`
- 🧮 `A8_3 = A8 / A3`
- 🧮 `A15_sqr = A15 ** 2`

---

## 🧪 Train-Test-Validation Split

- 📚 90% used for training/testing
- ✅ 10% used for final validation
- From training data: 80% train, 20% test

---

## 🔍 Preprocessing Pipeline

- 🧼 Categorical encoding via `TargetEncoder`
- 🔢 Scaling via `StandardScaler`
- 🔄 Used `make_column_transformer` + `Pipeline`

---

## 🌳 Model 1: Decision Tree Classifier

### 🔧 Hyperparameters Tuned:
- `max_depth`: [5, 10]
- `max_leaf_nodes`: [3, 6]

### ✅ Results:

#### Test Set:
Accuracy: 91% Precision: 0.89–0.93 Recall: 0.88–0.93


#### Validation Set:
Accuracy: 83% Class 0 F1: 0.84 Class 1 F1: 0.83
## 📈 Model 2: Logistic Regression

### 🔧 Hyperparameters Tuned:
- `max_iter`: [100–900]
- `penalty`: `l2`

### ✅ Results:

#### Test Set:

Accuracy: 91% Precision: 0.90–0.91 Recall: 0.90–0.91


#### Validation Set:

Accuracy: 82% Class 0 F1: 0.82 Class 1 F1: 0.81


---

## 🔁 Comparison

| Metric           | Decision Tree | Logistic Regression |
|------------------|----------------|----------------------|
| Cross-val Score  | **0.856**      | **0.861**            |
| Test Accuracy    | **91%**        | **91%**              |
| Valid Accuracy   | **83%**        | 82%                  |
| Best Use Case    | Slightly better generalization with trees |

✅ **Conclusion**: Both models perform very similarly, with decision tree slightly outperforming on validation, potentially due to its ability to model non-linearity.

---

## 📦 Base Model (No Feature Eng.)

| Metric             | Value          |
|--------------------|----------------|
| Cross-Val (Tree)   | 0.853          |
| Test Accuracy      | 83%            |

🔎 Feature engineering **improved model accuracy** slightly from 83% ➡️ 91%

---

## 🚀 Installation

```bash
pip install scikit-learn pandas matplotlib seaborn category_encoders
```

##🧑‍💻 Author

Serhii Kolotukhin

📍 www.linkedin.com/in/serhii-kolotuhkin-25648a166 | GitHub
