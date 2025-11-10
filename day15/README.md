# Day 15: Loan Eligibility Prediction

## Dataset

### Kaggle
[Loan Eligibility Prediction](https://www.kaggle.com/datasets/avineshprabhakaran/loan-eligibility-prediction)

- Local CSV: `data/Loan_Eligibility_Prediction.csv`
- Typical features: Applicant income, coapplicant income, credit history, gender, marital status, education, property area, and loan status.

## Project Summary

This project builds a supervised classification pipeline to predict loan approval. The workflow includes data validation, preprocessing and encoding of categorical features, feature engineering (total income), model training and comparison, and final model export.

## Models and Performance

- Logistic Regression: baseline model with standard scaling.
- Decision Tree Classifier: tuned depth for balance between bias and variance.
- Random Forest Classifier: selected as the final model for stability and performance.

Performance metrics reported: precision, recall, and F1 score for the approval class. See `notebooks/LoanEligibillity.ipynb` for detailed scores and comparisons.

## Key Findings

- Approval strongly correlates with credit history and verified income.
- Married applicants and applicants from semiurban areas show higher approval rates in this dataset.
- Gender differences in approval partly reflect application volume and demographic composition rather than model bias in this analysis.

## Files

- `notebooks/LoanEligibillity.ipynb` — notebook with full pipeline, visualizations, and model export.
- `data/Loan_Eligibility_Prediction.csv` — dataset used for modeling.
- `models/` — saved model artifacts (if exported).

## How to run

1. Open `notebooks/LoanEligibillity.ipynb` and execute cells sequentially.
2. To use the exported model, load the joblib artifact and call the provided prediction helper.
# Day 15