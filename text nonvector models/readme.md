# 🎬 IMDB Sentiment Classification

This project demonstrates sentiment classification on the IMDB movie reviews dataset using traditional NLP techniques such as **Bag-of-Words (BoW)** and **TF-IDF**, paired with **LightGBM** for classification.

---

## 🧠 Goal

Classify reviews as either **positive** or **negative** using:
- Text preprocessing (cleaning, stopword removal, lemmatization)
- Feature extraction via BoW and TF-IDF
- Supervised learning with LightGBM

---

## 📦 Used Tools

- **scikit-learn** (vectorization, pipelines, evaluation)
- **LightGBM** (model training)
- **NLTK** (stopwords, lemmatization)
- **WordCloud**, **matplotlib**, **seaborn** (visualization)

---

## 📁 Dataset

- **Name**: IMDB Movie Reviews
- **Size used**: 10,000 reviews
- **Labels**: `positive` (1), `negative` (0)

---

## 🔄 Preprocessing Steps

- Lowercasing
- Removing HTML tags, links, punctuation, and numbers
- Stopword removal (`nltk`)
- Lemmatization (`WordNetLemmatizer`)

---

## 📊 Feature Extraction

Two vectorization methods were tested:

1. **Bag of Words (CountVectorizer)**
2. **TF-IDF (TfidfVectorizer)**

Both used `max_features=10000`.

---

## 🚀 Modeling

A **LightGBMClassifier** was trained using scikit-learn pipelines and evaluated with:

- 5-fold Cross-validation
- Accuracy, Precision, Recall, F1-score

### CountVectorizer Results:
- **CV Score**: `0.8448`
- **Test Accuracy**: `0.86`

### TfidfVectorizer Results:
- **CV Score**: `0.8402`
- **Test Accuracy**: `0.86`

---

## 📈 Evaluation Metrics

Example classification report (TF-IDF):

```
              precision    recall  f1-score   support

           0       0.87      0.84      0.86       996
           1       0.85      0.88      0.86      1004

    accuracy                           0.86      2000
```

---

## ☁️ Word Clouds

Word clouds were generated for both positive and negative reviews to visualize common words after preprocessing.

---

## 🧪 How to Run

```bash
pip install -r requirements.txt
python run_sentiment.py
```

> Make sure to mount your Google Drive if running in Colab.

---

## 📝 Notes

- All processing is done using standard `sklearn` and `nltk`.
- LightGBM is used directly with pipelines.
- No deep learning libraries involved.

---

🧑‍💻 Author

Serhii Kolotukhin

📍 www.linkedin.com/in/serhii-kolotuhkin-25648a166 | GitHub
