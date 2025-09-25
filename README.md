# 🐾 Animals-10 Image Classification

This project was developed as part of the **Akbank Deep Learning Bootcamp (2025)**.  
The goal is to build and evaluate models for classifying images from the **Animals-10 dataset**, containing 10 different animal categories.

---

## 📊 Dataset

- **Source:** [Animals-10 (Kaggle)](https://www.kaggle.com/datasets/alessiocorrado99/animals10)  
- **Classes (10):** dog (*cane*), horse (*cavallo*), elephant (*elefante*), butterfly (*farfalla*), chicken (*gallina*), cat (*gatto*), cow (*mucca*), sheep (*pecora*), spider (*ragno*), squirrel (*scoiattolo*)  
- **Size:** ~28,000 images  
- **Split:** 80% training, 10% validation, 10% test  

---

## 🏗️ Methodology

### 1. Baseline CNN
- Custom CNN built from scratch.  
- Included data augmentation and class weighting.  
- **Result:** ~46% test accuracy, showing limited generalization.

### 2. Transfer Learning – ResNet-50
- Pretrained on ImageNet, backbone frozen initially.  
- Added Global Average Pooling + Dropout + Dense (10 classes).  
- Stage 1: Train head (frozen base).  
- Stage 2: Fine-tune last convolutional blocks at low learning rate.  
- **Result:** ~97% test accuracy, strong improvement over baseline.

### 3. Model Interpretability
- Applied **Grad-CAM** to visualize model attention.  
- Confirmed that ResNet-50 attends to meaningful animal features (e.g., head, wings, legs).  
- Baseline CNN often misfocused on backgrounds.

---

## 📈 Results

| Model        | Test Accuracy |
|--------------|---------------|
| Baseline CNN | 0.4595        |
| ResNet-50 TL | 0.9668        |

- Transfer Learning improved accuracy by **+51 percentage points** compared to the baseline.  
- Confusion matrices and classification reports show ResNet-50 performs consistently well across all 10 classes.  

---

## 🖼️ Sample Outputs

- **Training Curves:** Accuracy and loss plots for both models.  
- **Confusion Matrices:** Visualizing per-class predictions.  
- **Grad-CAM:** Example attention heatmaps demonstrating model interpretability.  

---

## 🚀 How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/animals10-classification.git
   cd animals10-classification
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the Jupyter Notebook:
   ```bash
   jupyter notebook notebooks/animal_classification.ipynb
   ```

## 📌 Acknowledgements  

- **Akbank Deep Learning Bootcamp 2025** for guidance and mentorship.  
- **Kaggle dataset** by *alessiocorrado99*.  
- **TensorFlow/Keras** for model implementation.  

## Kaggle Link:
- https://www.kaggle.com/code/korayercan/animaldetection-baselinecnn-resnet50
