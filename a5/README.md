# 🤖 Perceptron vs Multi-Layer Perceptron on Handwritten Characters

This project compares the **Perceptron Learning Algorithm (PLA)** (implemented from scratch) with a **Multi-Layer Perceptron (MLP)** (using PyTorch) on the **English Handwritten Characters dataset** (62 classes: 0–9, A–Z, a–z).

---

## 📂 Project Structure
- **pla.py** → Perceptron implementation from scratch  
- **mlp.py** → Multi-Layer Perceptron implementation using PyTorch  
- **utils.py** → Preprocessing and helper functions  
- **report.pdf** → Lab report for Experiment 5  
- **README.md** → Documentation and usage instructions  
- **requirements.txt** → Dependencies  

---

## ⚙️ Workflow

### 1. Data Preprocessing
- Converted images to **grayscale** and resized to **28×28**  
- Flattened each image into a **784-dimensional vector**  
- Normalized pixel values to **[0, 1]**  
- Encoded labels into **62 integer classes** (0–9, A–Z, a–z)  
- Split dataset into:  
  - **Train**: 2463 samples  
  - **Validation**: 435 samples  
  - **Test**: 512 samples  
- Standardized features using **z-score normalization**  

### 2. Models Implemented
- **PLA (from scratch)**  
  - Step activation function  
  - Weight update: `w ← w + η(y − ŷ)x`  
  - 50 epochs, learning rate `η = 0.01`  

- **MLP (PyTorch)**  
  - Input: 784 units  
  - Hidden layers: [256, 128], ReLU activation  
  - Output: 62 classes with Softmax  
  - Optimizer: Adam (`lr = 0.01`)  
  - Loss: CrossEntropyLoss  

### 3. Evaluation Metrics
On **validation and test sets**:
- Accuracy  
- Precision  
- Recall  
- F1-Score  
- Confusion Matrices  
- Training vs Validation Accuracy Curves  

---

## 📊 Example Results
*(Recorded during the experiment – may vary with tuning)*  

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| PLA   | 0.2109   | 0.2154    | 0.2108 | 0.1980   |
| MLP   | 0.5059   | 0.5075    | 0.5083 | 0.4954   |

- **PLA** struggled with linear separability (~21% accuracy).  
- **MLP** significantly outperformed PLA (~51% accuracy).  

---

## ▶️ How to Run
1. Clone the repository:  
   ```bash
   git clone https://github.com/<your-username>/perceptron-vs-mlp.git
   cd perceptron-vs-mlp
2. Install dependencies:
    ```bash
   pip install -r requirements.txt
3. Run Perceptron model:
    ```bash
    python pla.py
4. Run MLP model:
    ```bash
    python mlp.py

## 🏁 Conclusion

PLA is limited to linearly separable problems and showed poor performance on high-dimensional character recognition.
MLP handled complex non-linear relationships better and achieved much higher accuracy.
Confirms the advantage of deep learning methods over simple linear models for image classification tasks.
