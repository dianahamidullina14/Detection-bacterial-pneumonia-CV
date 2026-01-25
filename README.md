# Detection of Bacterial Pneumonia from Chest X-Rays

## Overview
This project develops a **Convolutional Neural Network (CNN)** model for the **automatic detection of bacterial pneumonia** in pediatric chest X-rays. The model performs **binary classification**, distinguishing bacterial pneumonia from healthy lungs and viral pneumonia.

---

## Dataset
- Pediatric Chest X-ray images (Train & Test)
- Classes:
  - **Bacterial Pneumonia**
  - **Viral/Normal**
- Total images used: ~5k (train + test)
- Data preprocessing includes grayscale conversion, resizing, normalization, and augmentation.

---

## Model Architecture
- Based on **LeNet-5 CNN architecture** (improved):
  - 3 convolutional layers with BatchNorm and MaxPool
  - Fully connected layers with Dropout
  - Binary output using **BCEWithLogitsLoss**
- Input: 128×128 grayscale images
- Trained on GPU using **Adam optimizer**

---

## Training
- Loss: Binary Cross-Entropy
- Epochs: 30 (can be increased for better performance)
- Batch size: 16
- Data augmentation includes:
  - Random horizontal flip
  - Random rotation
  - Random affine transformation

---

## Performance Metrics on Validation
| Metric      | Value |
|------------|-------|
| Train Loss | 0.421 |
| Accuracy   | 0.845 |
| Precision  | 0.805 |
| Recall     | 0.898 |
| F1-score   | 0.849 |
| ROC-AUC    | 0.907 |
| Confusion Matrix | `[[321, 83], [39, 342]]` |

---

## Test Set Metrics
| Metric      | Value |
|------------|-------|
| Test Loss  | 0.360 |
| Accuracy   | 0.867 |
| Precision  | 0.756 |
| Recall     | 0.971 |
| F1-score   | 0.850 |
| ROC-AUC    | 0.958 |
| Confusion Matrix | `[[306, 76], [11, 406]]` |

> The model achieves high recall, meaning almost all bacterial cases are correctly detected. Some viral cases are misclassified as bacterial, affecting precision.

---

## Usage
1. Clone the repository:

```bash
git clone https://github.com/dianahamidullina/Detection-bacterial-pneumonia-CV.git
cd Detection-bacterial-pneumonia-CV
