# Day 12: Heart Disease Prediction

This project analyzes the heart disease dataset to uncover insights and build a machine learning model to predict the presence of heart disease in patients.

## Dataset
Kaggle:<br>
[Housing Price Dataset](https://www.kaggle.com/datasets/tan5577/heart-failure-dataset)

## The analysis is broken into two main parts:
1.  **Exploratory Data Analysis (EDA):** Visualizing data distributions and relationships using Plotly.
2.  **Machine Learning:** Building a predictive classification model using `scikit-learn`.

## Key Features

* **EDA Dashboard:** A 2x2 dashboard visualizing patient age, cholesterol, resting blood pressure, and the relationship between age and cholesterol.
* **Preprocessing Pipeline:** A robust `sklearn` pipeline that automatically standardizes numerical features and one-hot-encodes categorical features.
* **Predictive Model:** A trained Logistic Regression model for binary classification (Heart Disease: 1 or 0).
* **Model Evaluation:** A visual confusion matrix and a full `classification_report` (Accuracy, Precision, Recall, F1-Score) to assess performance.
* **Prediction Function:** A simple, ready-to-use function to predict on new, single-patient data.

## How to Use the Model for Prediction

The notebook trains and saves a complete `Pipeline`. You can use the included helper function to make predictions on new data samples easily.

```python
import pandas as pd
# Assume 'full_pipeline' is the trained Pipeline from the notebook

def predict_heart_disease(input_data):
    """
    Predict heart disease based on input data.
    
    Parameters:
    input_data (dict): A dictionary containing feature values.
    
    Returns:
    int: Predicted class (0 or 1).
    """
    input_df = pd.DataFrame([input_data])
    prediction = full_pipeline.predict(input_df)
    return prediction[0]

# Example usage:
sample_input = {
    'Age': 55,
    'Sex': 'M',
    'ChestPainType': 'ATA',
    'RestingBP': 140,
    'Cholesterol': 250,
    'FastingBS': 0,
    'RestingECG': 'Normal',
    'MaxHR': 150,
    'ExerciseAngina': 'N',
    'Oldpeak': 1.0,
    'ST_Slope': 'Up'
}

predicted_class = predict_heart_disease(sample_input)
heart_diagnosis = 'Heart Disease' if predicted_class == 1 else 'No Heart Disease'

print(f"Input sample: {sample_input}")
print(f"Predicted diagnosis: {heart_diagnosis} (Class: {predicted_class})")