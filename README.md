# 🌿 GREENAID - Plant Disease Detection & Cure Recommendation System

[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.9+-blue.svg)]()
[![Kaggle](https://img.shields.io/badge/dataset-Kaggle-green.svg)](https://www.kaggle.com/datasets/emmarex/plantdisease)

---

## 🌱 Overview

This project is an **end-to-end plant disease detection and treatment recommendation system** built with deep learning and computer vision.  

✅ **Key Features:**
- Detects the plant type
- Checks if the plant is healthy or diseased
- Identifies the disease (if present)
- Draws bounding boxes around infected leaf areas
- Checks if the disease is curable
- Recommends treatments (organic or chemical) using a language model

---

## 🪴 Pipeline

The solution is designed in modular stages as shown below:

```
Dataset Collection (Kaggle)
│
└──► Data Cleaning + Augmentation
│
┌──────────────────────────────────────────────┐
│ │
│ Model 1: Neural Network │
│ Model 2: CNN for Plant Type │
│ Model 3: CNN for Disease Type │
│ Model 4: Bounding Boxes (YOLO) │
│ Model 5: Cure Recommendation │
└──────────────────────────────────────────────┘
│
└──► Final Combined Model
│
└──► Output: Plant Type, Disease, Bounding Boxes, Treatment
```


```
## 📁 Folder Structure

├── data/
│ └── raw/ (from Kaggle)
│ └── processed/
│
├── notebooks/
│ ├── 01_neural_network.ipynb
│ ├── 02_cnn_plant_type.ipynb
│ ├── 03_cnn_disease_type.ipynb
│ ├── 04_bounding_boxes.ipynb
│ ├── 05_cure_recommendation.ipynb
│ └── 06_final_model.ipynb
│
├── pipeline.png
├── requirements.txt
├── README.md
└── LICENSE

```
## 🚀 How It Works

**Training Phase**
- Load and preprocess the PlantVillage dataset from Kaggle
- Resize images, normalize pixel values
- Encode disease classes (38 total)
- Perform data augmentation (rotation, flips, zoom)
- Train:
  - CNN for plant type classification
  - CNN for disease type classification
  - YOLO for bounding boxes
  - Recommendation model for treatment suggestions
- Combine all in a final pipeline

**Inference Phase**
- User uploads or shows a leaf via webcam
- Preprocessing: resize + normalize
- Predict:
  - Plant type
  - Health status
  - Disease name
- Draw bounding boxes around infected areas
- Check disease curability
- Query LLM for treatment suggestions (organic/chemical)
- Generate and display a complete final report

---

## 📊 Sample Output

✅ Plant: **Tomato**  
✅ Health: **Diseased**  
✅ Disease: **Late blight**  
✅ Bounding Boxes drawn  
✅ Curability: **Curable**  
✅ Treatment Recommendation based on region and treatment-type:  
> Use copper-based organic fungicides, remove infected leaves


---

## 🛠 Tech Stack

- Python
- Kaggle
- Roboflow for making the training bounding boxes dataset 
- TensorFlow / Keras
- YOLOv8 for bounding boxes
- Custom LLM for cure recommendations
- Streamlit (optional for a simple UI)

---

## ⚡ Getting Started

1. **Clone the repository**

```bash
git clone https://github.com/yourusername/plant-disease-detection.git
cd plant-disease-detection
