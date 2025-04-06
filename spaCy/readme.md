# Sentiment Classification using IMDb Dataset

## 📝 Task

Binary classification of movie reviews into **positive** or **negative** sentiments using Natural Language Processing (NLP) and Machine Learning.

---

## 📁 Dataset

**Source:** IMDB Dataset of 50K Movie Reviews  
**Columns:**

- `review` — raw text of the review  
- `sentiment` — label: `"positive"` or `"negative"`

---

## 🧼 Data Cleaning & Preprocessing

- Removed:
  - HTML tags
  - URLs
  - Punctuation
  - Digits
- Converted text to lowercase
- Lemmatization via spaCy
- Removed stopwords (`spaCy.STOP_WORDS`)
- Converted target labels:  
  `"positive"` → `1`, `"negative"` → `0`

Example of preprocessing:
- Original: `"One of the other reviewers has mentioned..."`
- Cleaned: `"one reviewer mention watch oz episode hook ..."`

---

⚙️ Model Training
✅ LightGBM Classifier

LGBMClassifier(
    learning_rate=0.069,
    n_estimators=100,
    num_leaves=27,
    random_state=42
)

Best parameters (GridSearchCV):

{"num_leaves": 27}

---

📊 Evaluation (LightGBM)

Metrics:

    Accuracy: 0.84

    Precision: 0.85 (class 0), 0.83 (class 1)

    Recall: 0.83 (class 0), 0.86 (class 1)

Confusion Matrix:

[[4096  865]
 [ 701 4338]]

 🧠 Stacking Classifier

Base learners:

    KNeighborsClassifier

    LGBMClassifier

Meta-learner:

    SVC
---

📈 Stacking Classifier Results

Metrics:

    Accuracy: 0.88

    Precision: 0.89 (class 0), 0.87 (class 1)

    Recall: 0.86 (class 0), 0.89 (class 1)

    ROC AUC: 0.949
---

📊 Model Comparison
Model	Accuracy	ROC AUC	Notes
LightGBM	0.84	–	Fast, simple baseline
Stacking (KNN + LGBM → SVC)	0.88	0.949	Best performance overall
---

📚 Libraries Used

    spaCy

    scikit-learn

    lightgbm

    matplotlib, seaborn

    TfidfVectorizer, StackingClassifier
---

📌 Notes

    Data cleaned using regex and spaCy

    Text transformed with TF-IDF

    Model stacking improves results

    LightGBM is a strong baseline
