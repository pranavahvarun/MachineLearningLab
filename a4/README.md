# 🧬 Ensemble Prediction on Breast Cancer Dataset

This project applies **ensemble learning methods** and decision tree models to classify breast cancer tumors as **malignant** or **benign** using the [WDBC dataset](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic)).

---

## 📂 Project Structure
- **ensemble_prediction.py** → Main experiment script (exported from Colab)  
- **wdbc.data** → Dataset file (must be in Google Drive for Colab)  
- **README.md** → Documentation and usage instructions  
- **requirements.txt** → Dependencies  

---

## ⚙️ Workflow

### 1. Data Preprocessing
- Dataset: Wisconsin Diagnostic Breast Cancer (WDBC)  
- Dropped `ID` column  
- Encoded target labels (`M=1 malignant`, `B=0 benign`)  
- Missing values handled using **mean imputation**  
- Features standardized with `StandardScaler`  

### 2. Train / Validation / Test Split
- **Train (60%)** → Model training  
- **Validation (20%)** → Hyperparameter tuning with GridSearchCV  
- **Test (20%)** → Final unbiased evaluation  

Variables used:
- `X_train`, `y_train` → Training set  
- `X_valid`, `y_valid` → Validation set  
- `X_test`, `y_test` → Test set  

### 3. Models Implemented
- **Decision Tree**  
- **AdaBoost**  
- **Gradient Boosting**  
- **XGBoost**  
- **Random Forest**  
- **Stacking Classifier** (base: SVM, Naïve Bayes, Decision Tree; meta: Logistic Regression or Random Forest)  

### 4. Hyperparameter Tuning
- Done with `GridSearchCV`  
- Specific grids for each model (e.g., depth, estimators, learning rate, etc.)  
- Cross-validation: **5-Fold CV**  

### 5. Evaluation Metrics
On **test set**:
- Accuracy  
- F1-Score  
- ROC-AUC Score  
- Confusion Matrix  
- ROC Curves plotted for all models  

---

## 📊 Example Results
*(Numbers will vary depending on hyperparameter tuning)*  

| Model             | Accuracy | F1-Score | AUC  |
|-------------------|----------|----------|------|
| Decision Tree     | 0.93     | 0.92     | 0.95 |
| AdaBoost          | 0.96     | 0.95     | 0.98 |
| Gradient Boosting | 0.97     | 0.96     | 0.99 |
| XGBoost           | 0.97     | 0.96     | 0.99 |
| Random Forest     | 0.96     | 0.95     | 0.98 |
| Stacking          | 0.98     | 0.97     | 0.99 |

---

## ▶️ How to Run
1. Upload dataset `wdbc.data` to your Google Drive  
2. In **Google Colab**, mount your drive:  
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   /content/drive/MyDrive/wdbc.data
   ```
3. Run ensemble_prediction.py (or copy into a Colab notebook).
