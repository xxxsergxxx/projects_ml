# 🍽️ Entree Recommendation System – Session-Based Modeling with KNN

This project explores the construction of a **recommendation system** using user session data from the Entree Chicago restaurant dataset. It includes end-to-end processing: data parsing, cleaning, transformation, visualization, modeling, and evaluation.

---

## 📦 Dataset Description

The dataset contains session logs from users browsing a restaurant recommendation system. Each row corresponds to a session containing a sequence of user interactions and a final selected restaurant (target).

- **Sessions** contain multiple steps with navigation and preference cues (e.g., more creative, cheaper, change cuisine).
- **Target** is the restaurant the user selected at the end of the session.
- Additional info includes restaurant metadata (decor, service, cost, etc.).

---

## 🔍 Objectives

- Load and clean complex tab-separated session files
- Analyze the structure and characteristics of the sessions
- Visualize patterns and explore distributions
- Engineer features for modeling
- Train a recommendation model using KNN
- Evaluate model performance and generate recommendations

---

## 🛠️ Tools & Libraries

- `Python`  
- `Pandas`, `NumPy` – for data manipulation  
- `Matplotlib`, `Seaborn` – for visualization  
- `scikit-learn` – for modeling and preprocessing  
- `TSNE` – for dimensionality reduction and clustering  
- `TargetEncoder` – for categorical transformation  

---

## 📊 Exploratory Data Analysis

### General Analysis

- Session data varies in length, requiring dynamic parsing.
- Many entries use symbolic suffixes (`L`, `N`, etc.), requiring interpretation via dictionaries.

### Visualization Insights

- **Session Length**:
  - Median number of steps ≈ 4.
  - Most sessions have between 3 to 9 entries.
- **Target Frequency**:
  - Many restaurants appear fewer than 50 times, skewing class balance.
- **IP Distribution**:
  - Users tend to revisit ~40 times on average.

### Clustering

- Applied **t-SNE** to Chicago restaurant features.
- Resulting projection suggests ~12 potential clusters.

---

## 🧹 Data Cleaning & Feature Engineering

- Removed sessions with unknown targets (`-1`) and underrepresented labels (<50 appearances).
- Filtered out long sessions (more than 9 steps).
- Extracted target column from variable-length rows.
- Encoded categorical features using `TargetEncoder`.

---

## 🤖 Modeling

### Algorithm
- Used `KNeighborsClassifier` with a pipeline:
  - `StandardScaler` for normalization
  - `KNN` for multi-class classification

### Training
- Dataset split into 80% train, 20% test (on 20,000 samples).
- Target variable was restaurant ID (as categorical class).

### Evaluation
- Measured with **ROC AUC score** using multiclass OVO strategy.

```python
roc_auc_score = 0.674
```

🎯 Recommendation Strategy

Using the trained KNN model, it's possible to recommend a restaurant based on the latest sequence of a user's session, encoded into numerical format. Model learns patterns such as:

   * Navigation styles (more traditional, cheaper, etc.)

   * Restaurant traits (service, decor, pricing)

   * Repeated user behavior

📌 Highlights

   * Custom functions were created to extract targets from sessions and to convert symbolic navigation and entry codes into meaningful numeric values.

   * Sessions were dynamically parsed from multiple inconsistent-length files using max column detection.

   * Model handles categorical noise and sparsity with robust preprocessing.

📎 Author

Serhii Kolotukhin
