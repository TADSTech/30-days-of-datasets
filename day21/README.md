# Day 21: UK Job Market Analysis 2025

## Dataset

[Dataset Link - https://www.kaggle.com/datasets/jakupymeraj/jobs-a-2025-dataset]

## Summary

Exploratory data analysis of 4,000 UK job postings from 2025, focusing on salary distributions and category trends. Includes a predictive model for salary estimation.

## Key Analyses

**Data Overview**
- Dataset with job titles, companies, categories, and salary information
- Salary data available for approximately 38% of postings
- Wide salary range reflecting diverse job market

**Category Analysis**
- Teaching and healthcare jobs most common
- Energy and legal sectors show highest average salaries
- Hospitality and retail at lower end of salary spectrum

**Salary Insights**
- Most salaries concentrated between £30,000-£50,000
- Significant variation across job categories
- Long tail of high-paying positions

**Predictive Modeling**
- Random Forest regression model for salary prediction
- Features: job category and location
- Model provides baseline salary estimates for job market analysis

## Insights

1. Job market shows strong demand in education and healthcare sectors
2. Salary premiums exist for specialized technical and professional roles
3. Geographic location influences salary expectations
4. Predictive models can help benchmark compensation across categories

## Visualizations

- Job category distribution bar chart
- Salary distribution histogram
- Average salary by category bar chart

## Model

- Random Forest regressor saved for salary predictions
- Encoders for categorical features included
- Suitable for estimating salary ranges in UK job market

## Files

- `data/jobs25.csv` - Raw job postings dataset
- `notebooks/jobseda.ipynb` - EDA and modeling notebook
- `models/salary_predictor.joblib` - Trained prediction model
- `models/category_encoder.joblib` - Category label encoder
- `models/location_encoder.joblib` - Location label encoder