# Sentiment Classification on IMDB Dataset using RNN, LSTM, and GRU

This project demonstrates how to perform sentiment classification (positive/negative) on the IMDB movie reviews dataset using Recurrent Neural Network architectures including **Simple RNN**, **LSTM**, and **GRU** implemented in TensorFlow/Keras.

## 📂 Project Structure

- Data preprocessing and cleaning
- Stopword removal and lemmatization
- Text vectorization with `TextVectorization`
- Model building with:
  - Simple RNN
  - Stacked Bidirectional LSTM
  - GRU
- Model training and evaluation
- Visualization of accuracy and loss curves

---

## 🧠 Models Overview

### ✅ 1. **Simple RNN**
- **Activation**: `softmax` *(not optimal for binary)*
- **Result**: Poor performance (Accuracy ~ 50%)
- **Note**: Softmax on single neuron is incorrect → should use `sigmoid`.

### ✅ 2. **Bidirectional LSTM**
- **Architecture**: Stacked Bi-LSTM layers + Dense layers
- **Activation**: `sigmoid`
- **Callbacks**: EarlyStopping, ModelCheckpoint
- **Val Accuracy**: ~87.4%
- **Loss**: ~0.30

### ✅ 3. **GRU**
- **Activation**: `softmax` *(again, should be sigmoid)*
- **Result**: Accuracy stuck at ~48%
- **Note**: Same activation mistake as RNN

---

## 📊 Training Performance (LSTM)

```text
Epoch 1: val_accuracy = 0.8273
Epoch 5: val_accuracy = 0.8683
Best accuracy (epoch 8): 87.4%


📦 Requirements

pip install numpy pandas nltk matplotlib tensorflow keras scikit-learn

Make sure to also download the required NLTK resources:

import nltk
nltk.download('stopwords')
nltk.download('wordnet')

🧪 Example Prediction (LSTM)

sample_text = "The movie was not cool. But the visuals were amazing."
prediction = model.predict([sample_text])
print(prediction)


📁 Dataset

    IMDB Dataset (IMDB Dataset.csv)

    Used first 15,000 rows for processing speed

⚠️ Common Issues

    Softmax used on single output neuron → always outputs 1.0. Fix: use sigmoid.

    Unbuilt model warning → resolved after .fit() or proper input shape handling.

✍️ Author

Serhii Kolotukhin
