# CIFAR-10 Image Classification using Baseline and Custom CNN Models

## 📚 Dataset
- **Dataset:** CIFAR-10  
- **Description:** 60,000 32x32 color images in 10 classes, with 6,000 images per class.
- **Preprocessing:** 
  - Normalized pixel values to [0, 1]
  - One-hot encoded labels

---

## 🔧 Baseline Model (Fully Connected Neural Network)

### Model Architecture
- Input: Flatten (32x32x3)
- Dense (512 units) → BatchNorm → ReLU → Dropout(0.4)
- Dense (256 units) → BatchNorm → ReLU → Dropout(0.3)
- Dense (128 units, ReLU)
- Output: Dense (10 units, softmax)

### Training
- **Optimizer:** Adam  
- **Loss Function:** Categorical Crossentropy  
- **Epochs:** 10  
- **Batch Size:** 64  
- **Validation Split:** 20%

### Evaluation
- **Test Accuracy:** `48.80%`

---

## 🧠 Custom CNN Model

### Model Architecture
Conv2D (32 filters, 3x3, ReLU, padding='same')
→ BatchNorm → MaxPooling2D
Conv2D (64 filters, 3x3, ReLU, padding='same')
→ BatchNorm → MaxPooling2D
Conv2D (128 filters, 3x3, ReLU, padding='same')
→ BatchNorm → MaxPooling2D
→ Flatten
→ Dense (128, ReLU) → Dropout(0.5)
→ Dense (10, softmax)
---

### Training
- **Epochs:** 15  
- **Batch Size:** 64  
- **Validation Split:** 20%  
- **Optimizer:** Adam

### Evaluation
- **Test Accuracy:** `73.21%`

---

## 📊 Performance Comparison

| Model           | Test Accuracy |
|----------------|---------------|
| Baseline Model | 48.80%        |
| Custom CNN     | **73.21%**    |

---

## 🔥 Confusion Matrix (Heatmap)

![image](https://github.com/user-attachments/assets/eb3dffe1-3404-4939-8b85-36501af0e985)
