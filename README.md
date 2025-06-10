![image](https://github.com/user-attachments/assets/35995544-6526-4154-9d48-707fb2613628)

# 🌿 Plant-Seedlings-Classification

## 🔍 Overview

- **Task**: Image classification – predict plant species from seedling images
- **Dataset**: 5,475 training images across 12 categories (e.g. Sugar beet, Maize, Loose Silky-bent), plus 794 unlabeled test images
- **Framework**: TensorFlow / Keras
- **Model**: Simple CNN with 3 convolutional blocks + BatchNorm + Dropout
- **Augmentation**: Rotation, zoom, shift, brightness, flip
- **Performance**:  
  - Validation Accuracy: **73.5%**  
  - Final Kaggle Score: **0.76826**

---

## 🚀 Project Steps

### 1. Exploratory Data Analysis
- Visualized class imbalance in `train/`
- Sample image preview per class

### 2. Image Preprocessing
- Resized images to `224x224`
- Normalized pixel values to `[0, 1]`
- Applied strong data augmentation with `ImageDataGenerator`

### 3. Model Architecture
- `Conv2D + BatchNorm + MaxPooling` × 3 blocks
- Fully connected layer with `Dropout(0.5)`
- Output layer: `Dense(12, softmax)`
- Compiled with `Adam` optimizer + `categorical_crossentropy`

### 4. Training
- Used `EarlyStopping` and `ModelCheckpoint`
- Trained for up to 20 epochs on 80% training data
- Saved the best model as `best_cnn_model.keras`

### 5. Evaluation
- Plotted accuracy/loss curves
- Validation accuracy improved steadily to 73.5%
- No major overfitting observed

### 6. Prediction & Submission
- Loaded test images from `test/`
- Predicted class labels using the best model
- Exported `submission.csv` (Kaggle format)
