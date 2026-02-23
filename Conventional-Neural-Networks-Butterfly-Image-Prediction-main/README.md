## 🦋 Butterfly Image Classification using CNN

A deep learning web application built with Convolutional Neural Networks (CNN) and Streamlit, which classifies butterfly species based on uploaded images.

## 🚀 Project Overview

This project demonstrates how a CNN model can classify butterfly images into multiple species.
The model is trained using TensorFlow/Keras, and the web interface is developed with Streamlit.

The app allows users to:

Upload a butterfly image 🦋

Predict its species using a pre-trained model (butterfly_cnn_model.h5)

View confidence percentage for each class

See performance metrics (Accuracy, Precision, Recall, F1-score)

## Streamlit app :  http://10.242.224.15:8501

## 🧠 Model Architecture

The CNN model consists of:

Convolutional Layers

MaxPooling Layers

Dropout (to prevent overfitting)

Fully Connected Dense Layers

Softmax output layer for multi-class classification

Framework: TensorFlow / Keras
Optimizer: Adam
Loss Function: Categorical Crossentropy
Metrics: Accuracy, Precision, Recall, F1-score

## 🗂️ Project Structure
📁 butterfly_cnn_project/
│
├── train/                     # Training dataset (subfolders by class)
├── test/                      # Testing dataset
├── butterfly_cnn_model.h5     # Trained CNN model
├── app.py                     # Streamlit web app
├── requirements.txt           # Dependencies
├── README.md                  # Project documentation
└── utils.py                   # Optional (preprocessing, metrics)

## ⚙️ Installation & Setup
### 1️⃣ Clone the repository
git clone https://github.com/<your-username>/butterfly-cnn-classifier.git
cd butterfly-cnn-classifier

### 2️⃣ Create a virtual environment (optional)
python -m venv env
env\Scripts\activate       # For Windows
source env/bin/activate    # For Mac/Linux

### 3️⃣ Install dependencies
pip install -r requirements.txt

### 4️⃣ Run the Streamlit app
streamlit run app.py

⚠️ Common Issue

Error:

❌ Model file not found! Please ensure butterfly_cnn_model.h5 is in this folder.


Solution:
Place the trained model file butterfly_cnn_model.h5 in the same directory as app.py.
You can generate this model by training the CNN on your dataset or download the provided model file (if shared).

## 📊 Model Evaluation

You can evaluate your model using the following metrics:

from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score

accuracy  = accuracy_score(y_true, y_pred)
precision = precision_score(y_true, y_pred, average='weighted')
recall    = recall_score(y_true, y_pred, average='weighted')
f1        = f1_score(y_true, y_pred, average='weighted')

print(f"Accuracy: {accuracy:.4f}")
print(f"Precision: {precision:.4f}")
print(f"Recall: {recall:.4f}")
print(f"F1 Score: {f1:.4f}")


## ✅ Example Output:

Accuracy: 0.9125
Precision: 0.9054
Recall: 0.9125
F1 Score: 0.9089

## 🐛 Known Limitation

If you upload a non-butterfly image (like a cat 🐱 or car 🚗),
the model will still classify it as a butterfly species with high confidence.

👉 Reason: The model was trained only on butterfly images.
You can fix this by adding an “Other” class or applying a confidence threshold in the Streamlit app.

## 💡 Future Improvements

Add a “Non-butterfly” category

Deploy model on Hugging Face or Streamlit Cloud

Use pretrained networks (e.g., MobileNetV2, EfficientNet)

Improve dataset balance


