# Day 29: Mental Health Social Media Analysis

## Overview
This day focuses on analyzing the relationship between social media usage patterns and mental health states using machine learning. We explore a comprehensive dataset containing demographic information, social media usage metrics, and mental health indicators to build a predictive model.

## Dataset
- **Source**: Mental Health Social Media Dataset
- **Size**: 5,000 records
- **Features**: Age, gender, platform usage, screen time, social interactions, sleep patterns, physical activity, anxiety/stress/mood levels
- **Target**: Mental health state (At_Risk, Healthy, Stressed)

## Dataset Source
[Social Media Mental Health Indicators Dataset](https://www.kaggle.com/datasets/sonalshinde123/social-media-mental-health-indicators-dataset)

## Analysis Components

### Exploratory Data Analysis (EDA)
- **Mental State Distribution**: Pie chart showing the proportion of different mental health states
- **Age vs Anxiety**: Scatter plot examining the relationship between age and anxiety levels
- **Screen Time Impact**: Box plot analysis of screen time across different mental health states
- **Platform Usage**: Bar chart of social media platform preferences
- **Correlation Analysis**: Heatmap showing relationships between numerical features

### Machine Learning Pipeline
- **Preprocessing**: Label encoding for categorical variables, standard scaling for numerical features
- **Model**: Random Forest Classifier
- **Performance**: Perfect accuracy on test set (100%)
- **Feature Importance**: Analysis of which features contribute most to predictions


## Key Findings
- Screen time shows significant correlation with mental health states
- Age and anxiety levels have notable relationships
- Platform usage patterns differ across mental health categories
- The Random Forest model achieves perfect classification accuracy

## Usage
Load the saved pipeline for making predictions:
```python
from joblib import load
from sklearn.preprocessing import LabelEncoder
import pandas as pd

# Load the pipeline
pipeline = load('../models/mental_health_pipeline.joblib')

# Create label encoders (fit on same categories as training)
le_gender = LabelEncoder()
le_platform = LabelEncoder()
le_gender.fit(['Male', 'Female'])
le_platform.fit(['Instagram', 'Facebook', 'Twitter', 'Snapchat', 'LinkedIn'])

# Prepare data with encoded categorical features
sample_data = pd.DataFrame({
    'age': [25],
    'gender_encoded': [le_gender.transform(['Female'])[0]],
    'platform_encoded': [le_platform.transform(['Instagram'])[0]],
    'daily_screen_time_min': [400],
    'social_media_time_min': [200],
    'negative_interactions_count': [5],
    'positive_interactions_count': [10],
    'sleep_hours': [7.5],
    'physical_activity_min': [30]
})

prediction = pipeline.predict(sample_data)
print(f'Predicted Mental State: {prediction[0]}')
```