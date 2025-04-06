# 🧪 Classification with Imbalanced Data: SMOTE vs One-vs-Rest

This project explores how to handle imbalanced datasets using techniques like **SMOTE (Synthetic Minority Oversampling Technique)** and **One-vs-Rest Classification**, using the well-known **Glass Identification dataset**. The main goal is to analyze how these methods influence classification performance.

---

## 📁 Dataset

- Dataset: `glass.data` (from UCI ML Repository)
- 214 samples, 9 features, 6 classes in target column `TYPE`
- Some classes are heavily underrepresented

---

## ⚙️ Libraries Used

- `pandas`, `numpy`
- `scikit-learn`
- `matplotlib`, `seaborn`
- `imblearn` (for SMOTE)

---

## 🧼 Data Preprocessing

- Dropped ID column
- Checked for missing values
- Visualized class imbalance
- Used `pairplot()` to analyze feature distributions by class

---

## 🧠 Baseline Model: KNN Classifier

- Built a pipeline with `StandardScaler` + `KNeighborsClassifier`
- Used **5-fold cross-validation** with `roc_auc_ovr` scoring
- Accuracy: **~70%**
- Cross-validation ROC AUC score: **~0.835**

### 🔎 Baseline Issues:
- Poor performance on rare classes (e.g. class 3 and 5)
- Confusion matrix shows frequent misclassification between classes 1, 2, 3

---

## ⚖️ SMOTE (Synthetic Minority Oversampling)

SMOTE was applied to the dataset to balance all class distributions.

### 🧪 Post-SMOTE Evaluation

- Balanced dataset size: 456 samples
- Accuracy improved to **85%**
- Cross-validation ROC AUC score: **~0.951**
- All classes had reasonable precision & recall, but **1-2-3** were still close in feature space

---

## 🧪 Feature Transformation + SMOTE

To improve separability:
- Features for class **1** were squared
- Features for class **3** were cubed
- SMOTE was reapplied

### 📈 Results:

- Accuracy: **93%**
- ROC AUC: **~0.98**
- All classes showed strong f1-scores

---

## 🎯 OneVsRest Classifier

An alternative multiclass approach where:
- One binary classifier is trained per class (vs. rest)

### ⚠️ Results:

- Accuracy: **86%**
- ROC AUC: **~0.969**
- Weaker performance on minority classes compared to SMOTE
- Classes 5 and 6 suffered most

---

## 📊 Visualization

- Class distribution before and after SMOTE
- ROC AUC curves for each class (One-vs-Rest)
- Confusion matrices for each model
- Histograms of prediction probabilities

---

## 📌 Key Conclusions

- Baseline KNN fails on minority classes
- **SMOTE** improves performance significantly, especially after feature transformations
- **OneVsRest** is interpretable but may underperform on overlapping classes
- Proper balancing + feature engineering is key to improving multi-class models

---

## 📦 Installation

```bash
pip install pandas numpy seaborn matplotlib scikit-learn imbalanced-learn


✍️ Author

Serhii Kolotukhin
