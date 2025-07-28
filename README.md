# Fraud Detection in a Financial Firm

## 📌 Objective
Build a machine learning model to detect fraudulent transactions in a large financial dataset and recommend preventive actions.

## Dataset
📥 [ Download Dataset (CSV) ](https://drive.usercontent.google.com/download?id=1VNpyNkGxHdskfdTNRSjjyNa5qC9u0JyV&export=download&authuser=0)


## ⚙️ Tools & Technologies
- **Language:** Python  
- **Libraries:** Pandas, NumPy, scikit-learn, Matplotlib, Seaborn  
- **Models Used:** Logistic Regression, Naive Bayes


## Business Goals


## 1. Data Cleaning (Missing Values, Outliers, Multicollinearity)

- **Missing Values:** Checked using `data.isna().sum()` — no missing values found.
- **Outliers:** Reviewed distributions and applied `StandardScaler` to reduce the effect of transaction amount outliers.
- **Multicollinearity:** Removed highly correlated or redundant features like `nameOrig`, `nameDest` to ensure model interpretability.

---

## 2. Fraud Detection Model Description

Implemented two models:

- **Naive Bayes Classifier:** A probabilistic model assuming independence among predictors.
- **Logistic Regression:** A linear model estimating the probability of fraud.

- Encoded `type` column using `LabelEncoder`.
- Scaled numerical features for better model performance.
- Data split into 60% training and 40% testing.

---

## 3. Variable Selection

Included features:
- `step`, `amount`, `oldbalanceOrg`, `newbalanceOrig`, `oldbalanceDest`, `newbalanceDest`, and encoded `type`.

Removed:
- `nameOrig` and `nameDest` (non-predictive and may cause overfitting).

---

## 4. Model Performance

- **Naive Bayes Accuracy:** ~97.17%
- **Logistic Regression Accuracy:** ~99.90%

Additional Metrics (Logistic Regression):
- Evaluated with `confusion_matrix` and `classification_report`.
- Showed strong balance between false positives and false negatives.

---

## 5. Key Factors That Predict Fraudulent Transactions

- **Transaction Type:** `TRANSFER` and `CASH_OUT` linked to most frauds.
- **Amount:** Larger transactions more likely to be fraudulent.
- **Balance Fields:** Fraud often involves zero or irregular balances.
- **Step:** Time patterns may indicate fraudulent behavior.

---

## 6. Do These Factors Make Sense?

Yes:

- `TRANSFER` and `CASH_OUT` are common channels for moving stolen funds.
- Zero balances before/after transactions are strong red flags.
- Large, sudden balance shifts are unusual and often fraudulent.

---

## 7. Prevention Recommendations

- **Real-Time Monitoring:** Flag large or suspicious transactions.
- **MFA:** Require identity verification for risky operations.
- **User Behavior Profiling:** Detect unusual user actions.
- **Limit High-Risk Transactions:** Apply stricter rules for `TRANSFER` and `CASH_OUT`.

---

## 8. Measuring Success

- **Fraud Rate Reduction:** Compare pre- and post-implementation fraud counts.
- **False Positive Rate:** Monitor wrongly flagged legitimate transactions.
- **Customer Feedback:** Track complaints related to false alerts.
- **Precision/Recall:** Reassess model metrics after implementation.

