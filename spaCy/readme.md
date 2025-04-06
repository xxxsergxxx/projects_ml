# IMDB Sentiment Classification

This project focuses on classifying IMDB movie reviews as **positive** or **negative** using machine learning techniques. The core model is based on **LightGBM**, and performance is further enhanced through a **stacking ensemble** with KNN and SVC as base/meta learners.

## 📌 Features

- Text preprocessing with `spaCy` (lemmatization, stopword removal)
- TF-IDF feature extraction
- LightGBM model with hyperparameter tuning
- Stacking classifier with KNN, LightGBM, and SVC
- Evaluation with accuracy, precision, recall, F1-score, confusion matrix, and ROC-AUC

## 📂 Dataset

- **Source**: [IMDB Dataset](https://ai.stanford.edu/~amaas/data/sentiment/)
- **Size**: 50,000 labeled reviews (balanced)
- **Classes**: `positive`, `negative`

## ⚙️ Model Pipeline

1. Clean and preprocess text
2. Transform using `TfidfVectorizer`
3. Train LightGBM (tuned with `GridSearchCV`)
4. Optionally, stack with KNN and SVC for improved performance

## 🧪 Results

| Model           | Accuracy | ROC AUC |
|----------------|----------|---------|
| LightGBM       | 0.84     | –       |
| Stacking Model | 0.88     | 0.95    |

## 🛠 Tech Stack

- Python
- scikit-learn
- LightGBM
- spaCy
- seaborn & matplotlib

## 🚀 How to Run

```bash
# Install dependencies
pip install -r requirements.txt

# Run preprocessing and training
python sentiment_classification.py
```

> Note: This project was developed in Google Colab using Jupyter notebooks.

## 📈 Example Confusion Matrix

```
[[2190  344]
 [ 261 2205]]
```

## 🧑‍💻 Author

Serhii Kolotukhin

📍 www.linkedin.com/in/serhii-kolotuhkin-25648a166 | GitHub

