# 📧 Email Spam Classification (ML Lab Assignment 3)

This project implements **Email Spam or Ham Classification** using three machine learning algorithms:  
- Naïve Bayes  
- K-Nearest Neighbors (KNN)  
- Support Vector Machine (SVM)  

Dataset used: [`spambase_csv.csv`](https://archive.ics.uci.edu/ml/datasets/spambase)  

---

## 📂 Project Structure
- **mllaba3.py** → Main script with preprocessing, training, validation, hyperparameter tuning, and evaluation.  
- **spambase_csv.csv** → Dataset (must be stored in Google Drive if using Colab).  
- **README.md** → This documentation.  

---

## ⚙️ Workflow

### 1. Data Preprocessing
- Missing values removed.  
- Target column `class` converted to categorical (0 = Ham, 1 = Spam).  
- Features normalized with `StandardScaler` for KNN and SVM.  

### 2. Train / Validation / Test Split
The dataset is divided as:
- **Train (60%)** → Used for model training  
- **Validation (20%)** → Used for hyperparameter tuning  
- **Test (20%)** → Used only once for final unbiased evaluation  

Splits used in the code:
- Raw features (for Naïve Bayes `MultinomialNB`):
  - `X_raw_train`, `y_raw_train`  
  - `X_raw_valid`, `y_raw_valid`  
  - `X_raw_test`, `y_raw_test`  

- Scaled features (for KNN, SVM, GaussianNB, BernoulliNB):
  - `X_scaled_train`, `y_scaled_train`  
  - `X_scaled_valid`, `y_scaled_valid`  
  - `X_scaled_test`, `y_scaled_test`  

### 3. Models Implemented
- **Naïve Bayes**
  - GaussianNB
  - MultinomialNB
  - BernoulliNB  

- **KNN**
  - k = 3, 5, 7 (different tree algorithms)  

- **SVM**
  - Linear  
  - Polynomial  
  - RBF  
  - Sigmoid  

### 4. Hyperparameter Tuning
- Grid Search applied to:
  - KNN (`n_neighbors`, `algorithm`)  
  - SVM (`kernel`, `C`, `gamma`)  
- Performed on **training set**, best parameters selected using **validation set**.  

### 5. Evaluation
Each model is evaluated on:
- **Validation set** → To choose the best hyperparameters  
- **Test set** → Final accuracy, F1-score, confusion matrix, ROC curve  

Metrics used:
- Accuracy, Precision, Recall, F1-Score  
- Confusion Matrix  
- ROC Curve + AUC Score  

---

## 📊 Results (Example)
*(Actual results will vary when running code)*  

| Model              | Validation Accuracy | Test Accuracy |
|---------------------|---------------------|---------------|
| GaussianNB          | 82%                 | 80%           |
| MultinomialNB       | 88%                 | 85%           |
| KNN (Best Tuned)    | 90%                 | 88%           |
| SVM (Best Tuned)    | 93%                 | 92%           |

---

## ▶️ How to Run
1. Open **Google Colab**  
2. Mount Google Drive and ensure dataset is available at: content/drive/MyDrive/spambase_csv.csv
3. Run all cells in `mllaba3.py` or copy into a Colab notebook.  

---

## 📌 Notes
- `MultinomialNB` requires **raw (non-scaled) features**.  
- KNN and SVM work better with **scaled features**.  
- Test set is used only once at the end to report unbiased performance.  

---

✍️ **Author**: Pranavah Varun (Reg No. 3122237001039)  
