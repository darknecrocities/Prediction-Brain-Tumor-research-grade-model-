# 📘 Brain Tumor MRI Classification Model – Documentation

## 🧠 Overview
This project trains a **deep learning model** using **EfficientNetB0** to classify MRI images into:
- **YES** → Tumor detected  
- **NO** → No tumor detected  

Dataset used: *Brain MRI Images for Brain Tumor Detection (Kaggle)*

---

## ⚙️ Tech Stack
- TensorFlow / Keras  
- EfficientNetB0  
- Google Colab  
- Kaggle API  
- OpenCV  
- Split-Folders  
- Matplotlib  
- Scikit-learn  

---

## 📂 Project Workflow

### **1️⃣ Environment Setup**
- Install required libraries  
- Configure Kaggle API  
- Download and extract dataset  
- Organize data using `splitfolders` into:
  - Train (70%)
  - Validation (20%)
  - Test (10%)

---

## 🧪 Data Preprocessing
- Images resized to **224 × 224**
- Data normalization (`rescale=1./255`)
- Augmentations:
  - Rotation  
  - Shifting  
  - Shear  
  - Zoom  
  - Horizontal flip  

---

## 🏗️ Model Architecture (EfficientNetB0)
- Pre-trained EfficientNetB0 (ImageNet weights)
- GlobalAveragePooling2D
- Dense(128, ReLU)
- Dropout layers for regularization
- Final Dense(1, sigmoid) for binary output

---

## 🚀 Training Phases

### **🔹 Phase 1 – Initial Training (Frozen Base Model)**
- Base model frozen  
- Train dense layers  
- Optimizer: Adam (1e-4)  
- Epochs: 50  
- Callback:
  - ReduceLROnPlateau

### **🔹 Phase 2 – Fine‑Tuning**
- Unfreeze layers from layer 150 onward  
- Optimizer reduced to (1e-5)  
- Train for another 50 epochs  

---

## 📊 Evaluation Metrics
Metrics calculated from test dataset:
- **Accuracy**
- **Precision**
- **Recall**
- **F1-score**
- **AUC (ROC-AUC)**
- **Confusion Matrix**
- **Classification Report**

---

## 🖼️ Inference (Image Prediction)
- User uploads MRI image  
- Image resized → preprocessed → predicted  
- Threshold: **0.6**
- Output displayed:
  - Image  
  - Predicted class  
  - Raw model output  

---

## 💾 Saving the Model
Model exported as:  
`brain_tumor_model.h5`

---

## 📎 Important Notes
- EfficientNetB0 provides strong accuracy with minimal parameters  
- Learning rate scheduling helps stabilize training  
- Freezing → unfreezing model improves performance  
- Dataset quality strongly affects results  

---

## 🏁 Final Takeaway
This project demonstrates a **full end‑to‑end deep learning pipeline**:  
✔ Dataset handling  
✔ Preprocessing  
✔ Transfer learning  
✔ Fine‑tuning  
✔ Evaluation  
✔ Real‑image prediction  

Perfect for medical imaging research and ML experimentation.  

---

Created by: **Arron Kian M. Parejas | World Top Dev**
