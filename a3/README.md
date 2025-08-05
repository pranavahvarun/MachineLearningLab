# Experiment 3: Email Spam or Ham Classification

## 🎯 Objective
Classify emails as spam or ham using Naive Bayes, KNN, and SVM classifiers and evaluate using accuracy, ROC curves, confusion matrices, and 5-fold cross-validation.

## 🧰 Tools & Libraries
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn

## 📂 Folder Structure
- `experiment3.ipynb` – Full classification logic
- `datasets/` – spambase_csv.csv (UCI dataset)
- `screenshots/` – Confusion matrices and ROC plots
- `requirements.txt`

## 🧠 Models Compared
- Naive Bayes (Gaussian, Multinomial, Bernoulli)
- KNN (k=3, 5, 7; KDTree, BallTree)
- SVM (Linear, Polynomial, RBF, Sigmoid)

## 📈 Performance Summary
| Model        | Accuracy | F1 Score |
|--------------|----------|----------|
| MultinomialNB| 0.871    | 0.88     |
| SVM (RBF)    | 0.903    | 0.90     |
| KNN (k=3)    | 0.865    | 0.86     |

## 🔁 Cross-Validation (K=5)
- SVM (RBF): 0.900
- KNN: 0.858
- Naive Bayes: 0.861

## 🧪 How to Run
pip install -r requirements.txt
jupyter notebook experiment3.ipynb
