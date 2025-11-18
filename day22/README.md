# Day 22: Iris Flower Classification

## Dataset

[Dataset Link - https://www.kaggle.com/datasets/nalisha/machine-learning-practice-dataset-iris-flowers]

## Summary

Exploratory data analysis and classification modeling of the classic Iris flower dataset using Random Forest.

## Key Analyses

**Data Overview**
- 150 samples with sepal and petal measurements
- Three species: setosa, versicolor, virginica
- Balanced dataset with 50 samples per species

**Feature Analysis**
- Petal dimensions provide better species separation
- Sepal measurements show more overlap between species
- Clear linear relationships visible in scatter plots

**Model Performance**
- Random Forest classifier trained on measurement features
- High accuracy achieved on test set
- Confusion matrix shows strong predictive performance

## Insights

1. Petal measurements are key differentiators between Iris species
2. Machine learning models can achieve near-perfect classification
3. Feature relationships provide clear visual separation

## Visualizations

- Scatter matrix showing feature relationships by species
- Confusion matrix heatmap

## Model

- Random Forest classifier saved for species prediction
- Features: sepal length/width, petal length/width
- Target: species classification

## Files

- `data/iris.csv` - Iris flower measurements dataset
- `notebooks/iris_classification.ipynb` - EDA and modeling notebook
- `models/iris_classifier.joblib` - Trained classification model