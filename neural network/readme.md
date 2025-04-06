# 🧠 MNIST Digit Classification using Feedforward Neural Network (Non-CNN)



## 📌 Overview

This project implements a neural network to classify handwritten digits from the popular [MNIST dataset](http://yann.lecun.com/exdb/mnist/), **without using convolutional layers (CNN)**. Instead, a **fully connected (dense) neural network** is used, built with `tf.keras`.

While CNNs are the standard for image recognition tasks, this project explores the capabilities and limitations of dense layers in image classification.

---

## 🛠️ Technologies Used

- Python 3.10  
- TensorFlow / Keras 3.6  
- NumPy, Matplotlib, Seaborn  
- Scikit-learn  

---

## 📚 Dataset

**MNIST**: The dataset consists of 70,000 grayscale images (28x28 pixels) of handwritten digits from 0 to 9.

- Training set: 60,000 images  
- Test set: 10,000 images

Each image is accompanied by a label indicating the digit (0–9).

---

## 🚀 Project Workflow

### 1. **Data Loading & Visualization**

- MNIST dataset is loaded directly via `keras.datasets`.
- The first 64 digits are plotted to visually inspect the data.

### 2. **Preprocessing**

- Images reshaped from `(28, 28)` to `(28, 28, 1)` to simulate a single-channel format.
- Normalized pixel values from `[0, 255]` to `[0.0, 1.0]`.
- Labels one-hot encoded using `to_categorical()`.

### 3. **Model Architecture**

A simple `Sequential` model with the following layers:
- Input layer `(28, 28, 1)`
- Dense layer with 256 units and ReLU activation  
- BatchNormalization
- Flatten layer
- Dense layer with 128 units and ReLU activation  
- Output layer with 10 units and softmax activation

**Loss Function**: `categorical_crossentropy`  
**Optimizer**: `Adam` with learning rate `0.003`  
**Epochs**: 5  
**Batch size**: 32  

### 4. **Training Performance**

Model is trained for 5 epochs, and performance is evaluated on both training and test sets.

Example Output:
Train accuracy: 95.44% Test accuracy: 94.85%


---

## 📊 Results & Evaluation

### 📈 Accuracy & Loss over Epochs

- Training and validation accuracy/loss are visualized
- Loss decreased by **~32%**, indicating successful training

### 🔍 Confusion Matrix

A confusion matrix is plotted to show model accuracy across different digit classes. Most values are concentrated on the diagonal, showing strong classification performance.

### 🖼️ Prediction Visualization

120 test images are displayed with their predicted labels, giving a qualitative sense of performance.

---

## 📦 Model Summary

| Layer | Output Shape | Parameters |
|-------|--------------|------------|
| Dense (256 units) | (28, 28, 256) | 512 |
| BatchNorm | (28, 28, 256) | 1024 |
| Flatten | (None, 200704) | 0 |
| Dense (128 units) | (None, 128) | 25M+ |
| Dense (10 units) | (None, 10) | 1290 |

🧠 **Total Parameters**: ~25.6M

---

## ✅ Final Evaluation

| Metric        | Training Set | Test Set |
|---------------|--------------|----------|
| Accuracy      | 95.44%       | 94.85%   |
| Final Loss    | 0.1625       | 0.2017   |

Although this model performs well, **CNNs would typically outperform this architecture** on the MNIST dataset. This project serves as a baseline or learning tool for understanding dense networks in image tasks.

---

## 💾 Future Improvements

- Implement a CNN-based model for performance comparison  
- Add dropout for regularization  
- Try other optimizers like RMSProp or Nadam  
- Tune hyperparameters with `GridSearch` or `KerasTuner`

---


## 🧑‍💻 Author

Serhii Kolotukhin

📍 www.linkedin.com/in/serhii-kolotuhkin-25648a166 | GitHub
