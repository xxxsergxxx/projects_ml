# 📊 Clustering Analysis on German Credit Dataset using t-SNE, KMeans & DBSCAN

This project explores **unsupervised learning** techniques for analyzing customer credit risk using clustering algorithms. The dataset is visualized via **t-SNE** for dimensionality reduction and analyzed with **KMeans** and **DBSCAN** clustering. Evaluation is performed using **Silhouette Score** and **DBCV**.

---

## 📁 Dataset

- 📄 **File**: `SouthGermanCredit.asc`
- 💡 **Source**: German Credit Dataset
- 🧾 **Rows**: 1000
- 🔢 **Features**: 20 numerical + categorical (after preprocessing)
- 🏷️ **Target**: `credit_risk` (binary - used only for visualization)

---

## 🧰 Libraries Used

- `scikit-learn`, `matplotlib`, `seaborn`
- `clustergram` for visualizing cluster separation across K
- `DBCV` for clustering evaluation
- `t-SNE` from `sklearn.manifold` for 2D visualization

---

## 🧼 Data Preparation

- Checked for missing values (none found)
- Scaled data with `StandardScaler`
- t-SNE applied to visualize complex cluster structures in 2D

---

## 📉 t-SNE Analysis

- t-SNE was used to reduce 20D data to 2D
- Visualized different features (`credit_risk`, `foreign_worker`, `telephone`, etc.)
- Found that certain categorical features form visible clusters (e.g. `foreign_worker`, `other_debtors`)

### Example:
- 🟠 Orange = Class 1 (e.g. foreign worker present)
- 🔵 Blue = Class 2

t-SNE was especially useful in:
- Identifying hidden structures
- Understanding how features distribute across latent space

---

## 📦 Clustering Models

### 1️⃣ **KMeans**

- Chose `k=4` based on `Clustergram` visualization
- Evaluated with:
  - **Silhouette Score**: `~0.071`
  - **DBCV Score**: `~ -0.59`

### 2️⃣ **DBSCAN**

- Estimated optimal `eps` via k-distance plot
- Used `MinPts = 42`, `eps ≈ 3.82`
- Clustered into 2 main clusters + noise points (`-1`)
- Evaluated with:
  - **Silhouette Score**: `~0.15`
  - **DBCV Score**: `~ -0.28`

---

## 📊 Evaluation Summary

| Metric            | KMeans      | DBSCAN     |
|-------------------|-------------|------------|
| Silhouette Score  | 0.071       | **0.151**  |
| DBCV Score        | -0.60       | **-0.28**  |
| Clusters Found    | 4           | 2 (+ noise)|

✅ **DBSCAN outperformed KMeans** on both evaluation metrics, indicating a better ability to capture the dataset's inherent structure.

---

## 📈 Visualizations

- t-SNE Plots colored by key categorical features
- Clustergram (KMeans separation overview)
- DBSCAN decision boundary visualization
- k-distance plot for DBSCAN eps estimation

---

## 🚀 Installation

```bash
pip install clustergram
pip install "git+https://github.com/christopherjenness/DBCV"
pip install scikit-learn matplotlib seaborn
```

## ✍️ Author

Serhii — Feedmill Engineer & Data Scientist
