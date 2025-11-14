# Day 19: Student Performance Factors Analysis

## Dataset

[Dataset Link - https://www.kaggle.com/datasets/rabieelkharoua/students-performance-dataset]

## Summary

Exploratory data analysis of student performance factors dataset containing 6,607 records with 20 features including academic, demographic, and environmental variables affecting exam scores.

## Key Analyses

**Data Overview**
- Dataset structure with 7 numeric and 13 categorical features
- Exam scores ranging from 55 to 101 with mean of 67.24

**Univariate Analysis**
- Distribution of exam scores showing normal distribution
- Gender distribution with slight male majority (3,814 males vs 2,793 females)

**Bivariate Analysis**
- Exam scores by gender showing similar distributions
- Exam scores by parental education level indicating slight advantage for postgraduate-educated parents

**Correlation Analysis**
- Strong positive correlations between attendance (0.58) and hours studied (0.45) with exam scores
- Moderate correlations with previous scores (0.18) and tutoring sessions (0.16)

## Insights

1. Attendance and study hours are the strongest predictors of exam performance
2. Parental education shows a positive association with student achievement
3. Gender differences in performance are minimal
4. Tutoring and previous academic performance contribute moderately to current scores

## Visualizations

- Distribution of exam scores histogram
- Gender distribution bar chart
- Exam scores by gender box plot
- Exam scores by parental education level box plot
- Correlation matrix heatmap

## Files

- `data/StudentPerformanceFactors.csv` - Raw dataset
- `notebooks/eda.ipynb` - Exploratory data analysis notebook