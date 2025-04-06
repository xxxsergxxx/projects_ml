# 🧠 ML Classifier Comparison Project

This project focuses on comparing three machine learning classification techniques:
- **Bagging** using Random Forest
- **Boosting** using XGBoost and LightGBM
- **Stacking** using multiple base learners and a meta-learner

---

## 📂 Dataset

The dataset contains information about auction processes and verification outcomes.  
**Target variable:** `verification_result` (binary: 0 or 1)

**Key characteristics:**
- No missing values
- Unbalanced target class
- Mostly numerical features
- Some correlated features

---

## 🔧 Project Workflow

### 1. 📊 Exploratory Data Analysis (EDA)
- All features are numerical or boolean
- Target class (`verification_result`) is unbalanced
- Clear patterns in some features (e.g., `property_price`)

### 2. 🧱 Feature Engineering
Created two new features:
- `sum_capacity`: sum of all process capacities
- `price_to_cap`: ratio of price to total capacity

### 3. ⚙️ Preprocessing
- Standard scaling applied
- Target variable converted to integers
- Split into train (64%), validation (16%), and test (20%)

---

## 📈 Models and Results

### 🔁 Random Forest (Bagging)
- **CV Accuracy:** ~0.97
- Handles unbalanced classes relatively well

### 🚀 XGBoost (Boosting)
- **CV Accuracy:** ~0.99
- Strong performance, especially with class imbalance

### ⚡ LightGBM (Boosting)
- **CV Accuracy:** ~0.99
- Comparable to XGBoost with very fast training

### 🧠 Stacking Classifier
Base models: SGD, KNN, SVC, Decision Tree, XGBoost, RF, LightGBM  
Meta-learner: LightGBM  
- **CV Accuracy:** **~0.9916**
- **Test Accuracy:** 0.99
- **Validation Accuracy:** 1.00  
> Performance improved significantly after including stronger models like XGBoost and RF.

---

## 📊 Final Scores

| Model              | CV Score |
|-------------------|----------|
| Random Forest      | ~0.974   |
| XGBoost            | ~0.988   |
| LightGBM           | ~0.991   |
| Stacking Classifier| **~0.9916** |

---

## ✅ Conclusion

- Tree-based models (Random Forest, XGBoost, LightGBM) perform best due to their ability to handle unbalanced datasets.
- Stacking provided the highest overall accuracy, especially after combining powerful base learners.
- Feature engineering and hyperparameter tuning were critical to boosting performance.

---

## 📌 Possible Improvements

- Apply class balancing techniques (e.g., SMOTE, class weights)
- Perform feature selection to reduce overfitting
- Experiment with different meta-learners or ensemble voting

---

## 💻 Requirements

- Python 3.10+
- `scikit-learn`, `xgboost`, `lightgbm`, `matplotlib`, `seaborn`, `pandas`, `numpy`

---

## 🧑‍💻 Author

Serhii Kolotukhin

📍 www.linkedin.com/in/serhii-kolotuhkin-25648a166 | GitHub
