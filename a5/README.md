# Experiment 5 – Perceptron vs Multi-Layer Perceptron

This repository contains the implementation of **Experiment 5** from the *ICS1512: Machine Learning Algorithms Laboratory*.  
The experiment compares the **Perceptron Learning Algorithm (PLA)** implemented from scratch with a tuned **Multi-Layer Perceptron (MLP)** using PyTorch, evaluated on the **English Handwritten Characters dataset**.

---

## 📌 Aim
To implement the Perceptron Learning Algorithm (PLA) and compare its performance with a Multi-Layer Perceptron (MLP) on a multiclass handwritten character recognition task.  

---

## 🛠️ Preprocessing
- Images converted to grayscale and resized to **28×28**.  
- Flattened into **784-dimensional vectors**.  
- Normalized pixel values to **[0, 1]**.  
- Encoded labels into integers for **62 classes** (0–9, A–Z, a–z).  
- Dataset split: **2463 training, 435 validation, 512 testing**.  
- Features standardized using **z-score normalization**.  

---

## 📊 Results
| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| PLA   | 0.2109   | 0.2154    | 0.2108 | 0.1980   |
| MLP   | 0.5059   | 0.5075    | 0.5083 | 0.4954   |

- PLA struggled due to linear separability limitations.  
- MLP performed significantly better (~51% accuracy) with non-linear transformations and deeper layers.  

---

## 📂 Repository Structure
├── pla.py # Implementation of Perceptron Learning Algorithm
├── mlp.py # Implementation of Multi-Layer Perceptron (PyTorch)
├── utils.py # Preprocessing and helper functions
├── requirements.txt # Python dependencies
├── report.pdf # Lab report (Experiment 5)
└── README.md # Project documentation


---

## ▶️ Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/perceptron-vs-mlp.git
   cd perceptron-vs-mlp
