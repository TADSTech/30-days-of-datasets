# Day 16 & 17: Ensemble-Powered Loan Payback Prediction

## Dataset

- Source: Kaggle Playground Series S5E11 (Loan Default Prediction)
- Features: Demographic and financial data including education level, grade, gender, loan purpose, employment status, etc.
- Target: Binary classification for loan payback (1 = paid back, 0 = default)

## Project Summary

This project implements an ensemble-powered machine learning pipeline for predicting loan payback likelihood. The workflow includes data preprocessing with ordinal and one-hot encoding, cross-validation training of multiple models (XGBoost, LightGBM, CatBoost), and an ensemble combining CatBoost and LightGBM for improved performance. Additional visualizations provide insights into model comparisons, feature importance, and prediction distributions.

## Models and Ensemble

- **Individual Models**: XGBoost, LightGBM, CatBoost trained with Stratified K-Fold CV.
- **Ensemble**: VotingClassifier combining CatBoost and LightGBM with soft voting.
- **Evaluation**: Metrics include accuracy, precision, recall, F1-score, and ROC AUC. CatBoost typically performs best, with ensemble providing robustness.

## Key Findings

- CatBoost and LightGBM are top performers; ensemble improves stability.
- Feature importance highlights education level, grade, and employment status as key predictors.
- ROC curves show strong discriminative ability across models.

## Visualizations

- Model performance comparison bar chart.

## Kaggle

To get the full experience, check out the kaggle set
[Ensemble(Voting) Powered Loan Payback Prediction](https://www.kaggle.com/code/miclenzy/ensemble-powered-loan-payback-prediction)