# Credit Scoring Model using Machine Learning

## Project Overview

This project develops a **Credit Scoring Model** to predict whether a customer is likely to default on a loan. The model helps financial institutions assess credit risk and make informed lending decisions.

The project uses the **Give Me Some Credit** dataset and compares the performance of three machine learning algorithms:

* Logistic Regression
* Decision Tree
* Random Forest

---

## Business Problem

Financial institutions face significant losses when borrowers fail to repay loans.

The objective of this project is to:

* Identify high-risk customers
* Predict loan default probability
* Support data-driven credit approval decisions
* Reduce financial risk

---

## Dataset

**Dataset:** Give Me Some Credit

### Target Variable

`SeriousDlqin2yrs`

### Target Meaning

* **0** → No Default
* **1** → Default

### Key Features

* RevolvingUtilizationOfUnsecuredLines
* DebtRatio
* MonthlyIncome
* Age
* NumberOfTimes90DaysLate
* NumberOfOpenCreditLinesAndLoans
* NumberOfDependents

---

## Data Preprocessing

### Missing Value Treatment

Missing values were found in:

* MonthlyIncome
* NumberOfDependents

Median imputation was used to handle missing data.

### Feature Engineering

Two additional features were created:

#### DebtIncomeRatio

```text
DebtRatio / MonthlyIncome
```

#### IncomePerDependent

```text
MonthlyIncome / (NumberOfDependents + 1)
```

These engineered features became important predictors in the final model.

---

## Exploratory Data Analysis (EDA)

Performed:

* Class Distribution Analysis
* Correlation Heatmap
* Feature Importance Analysis
* Confusion Matrix
* ROC Curve Analysis

### Key Findings

* Credit utilization is the strongest predictor of default.
* Debt-related features strongly influence credit risk.
* The dataset is highly imbalanced.

---

## Machine Learning Models

### Logistic Regression

| Metric    | Score  |
| --------- | ------ |
| Accuracy  | 93.42% |
| Precision | 58.38% |
| Recall    | 5.39%  |
| F1 Score  | 9.86%  |
| ROC-AUC   | 0.714  |

---

### Decision Tree

| Metric    | Score  |
| --------- | ------ |
| Accuracy  | 89.86% |
| Precision | 25.84% |
| Recall    | 27.68% |
| F1 Score  | 26.73% |
| ROC-AUC   | 0.611  |

---

### Random Forest

| Metric    | Score  |
| --------- | ------ |
| Accuracy  | 93.66% |
| Precision | 57.92% |
| Recall    | 18.60% |
| F1 Score  | 28.16% |
| ROC-AUC   | 0.847  |

---

## Model Comparison

| Model               | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
| ------------------- | -------- | --------- | ------ | -------- | ------- |
| Logistic Regression | 93.42%   | 58.38%    | 5.39%  | 9.86%    | 0.714   |
| Decision Tree       | 89.86%   | 25.84%    | 27.68% | 26.73%   | 0.611   |
| Random Forest       | 93.66%   | 57.92%    | 18.60% | 28.16%   | 0.847   |

---

## Best Model

### Random Forest

Random Forest was selected as the final model because it achieved:

* Highest Accuracy
* Highest F1 Score
* Highest ROC-AUC Score

**Final ROC-AUC Score:** `0.847`

---

## Feature Importance

Top predictors influencing credit risk:

1. RevolvingUtilizationOfUnsecuredLines
2. DebtRatio
3. DebtIncomeRatio
4. Age
5. IncomePerDependent
6. MonthlyIncome

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Joblib
* Jupyter Notebook

---

## Project Structure

```text
CREDIT_SCORING_MODEL/
│
├── credit_scoring.ipynb
├── requirements.txt
├── README.md
├── .gitignore
└── credit_scoring_model.pkl
```

---

## Future Improvements

* Handle class imbalance using SMOTE
* Hyperparameter tuning
* Streamlit deployment
* Real-time credit risk prediction dashboard

---

## Conclusion

This project demonstrates how machine learning can be used to assess borrower creditworthiness and support lending decisions. Among the evaluated models, Random Forest provided the best balance between predictive performance and risk identification, making it the preferred model for credit risk assessment.
