# Day 6: Student Data Analysis & Multi‑Output Score Predictor

## Dataset
Students Academic Performance Dataset  
Source: https://www.kaggle.com/datasets/sadiajavedd/students-academic-performance-dataset

## Project summary
Comprehensive analysis and prediction of three student exam scores (Math, Reading, Writing) from demographic and preparatory features. Includes extensive EDA, feature engineering, and comparison of multiple ML models.

## Key EDA findings
- Gender: males tended to score higher on Math; females tended to score higher on Reading and Writing.  
- Test preparation: completing the test preparation course correlates with substantially higher scores.  
- Lunch: students with standard lunch showed higher average scores than those with free/reduced lunch.  
- Race/Ethnicity: Group E had the highest average performance across subjects.
- Strong correlations between reading and writing scores, moderate correlation with math.

## Model & implementation
- Goal: multi‑output regression to predict [Math, Reading, Writing].  
- Models compared: Random Forest, Gradient Boosting, Linear Regression
- Feature engineering: parental education encoding, binary indicators for test prep and lunch
- Pipeline: OneHotEncoder for categorical features → Best performing regressor
- Artifact: trained pipeline saved as `students_performance_best_model.joblib`.

## Performance
- Best model performance improved with feature engineering
- R² scores typically 0.15-0.25 across subjects (limitations due to available features)
- Gradient Boosting generally performed best among tested models

## Next steps
- Collect additional features (study habits, attendance, socioeconomic indicators)
- Try advanced models (XGBoost, neural networks)
- Implement hyperparameter tuning with cross-validation
- Consider separate models per subject for specialized prediction

## How to reproduce
1. Place the dataset in the `data/` directory.  
2. Run the comprehensive notebook: `notebooks/students_performance_comprehensive.ipynb`
3. The trained pipeline will be saved as `models/students_performance_best_model.joblib`.
