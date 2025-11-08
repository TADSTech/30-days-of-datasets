# Day 13: Car Price Prediction 2025

## Dataset
Kaggle:<br>
[Car Price Prediction Dataset](https://www.kaggle.com/datasets/aliiihussain/car-price-prediction)

## Project Summary

Comprehensive analysis of car pricing with machine learning-based price prediction. Multiple models (Lasso Regression, Random Forest, Gradient Boosting, XGBoost) were trained and evaluated to predict car prices based on brand, year, mileage, fuel type, and transmission. XGBoost emerged as the best performer with superior R² scores.

## Key Findings

- **Brand Distribution**: Varied representation across automotive brands with distinct pricing patterns
- **Average Prices by Brand**: Significant price variations based on brand positioning and market segment
- **Feature Engineering**: Car age and mileage per year are strong predictors of depreciation
- **Luxury Premium**: Luxury brands (Tesla, BMW, Audi, Mercedes) command significant price premiums
- **Fuel Type Impact**: Electric and hybrid vehicles show different pricing compared to traditional fuel
- **Transmission Effect**: Automatic transmission generally correlates with higher prices

## Market Insights

### Feature Importance Analysis

1. **Car Age**: Direct negative correlation with price; older cars depreciate
2. **Mileage Per Year**: Usage intensity strongly impacts valuation
3. **Brand Positioning**: Luxury vs standard brands show 50%+ price differences
4. **Fuel Type Evolution**: Electric/Hybrid gaining market share with premium positioning
5. **Transmission Type**: Automatic preferred in luxury segment, manual in budget segment
6. **Mileage**: Total accumulated kilometers critical for used car valuation

## Model Comparison

| Model | MAE | MSE | R² Score | Recommendation |
|-------|-----|-----|----------|-----------------|
| **Lasso Regression** | Low | Moderate | ~0.85 | Baseline |
| **Random Forest** | Low | Low | ~0.87 | Good |
| **Gradient Boosting** | Low | Low | ~0.88 | Very Good |
| **XGBoost** | Low | Low | ~0.90+ | ⭐ **BEST** |

### Best Model: XGBoost

- **Algorithm**: XGBoost Regressor
- **Number of Estimators**: 100
- **Learning Rate**: 0.1
- **Objective**: Squared error regression
- **Performance**: Highest R² score, best generalization
- **Advantage**: Superior handling of complex feature interactions

## Features & Engineering

### Original Features
- **Year**: Manufacturing year
- **Brand**: Car manufacturer
- **Fuel Type**: Petrol, Diesel, Hybrid, Electric
- **Transmission**: Manual or Automatic
- **Mileage**: Total kilometers driven

### Engineered Features
- **Car Age**: 2025 - Year (depreciation indicator)
- **Mileage Per Year**: Mileage / (Car Age + 1) (usage intensity)
- **Is Luxury**: Binary indicator (1 for Tesla/BMW/Audi/Mercedes, 0 otherwise)
- **Fuel Group**: Categorical grouping (Traditional: Petrol/Diesel, Eco: Hybrid/Electric)

## Data Processing

### Encoding & Scaling
- **Numerical Features**: StandardScaler normalization
  - Year, Mileage, Car_Age, Mileage_per_Year, Is_Luxury
- **Categorical Features**: OneHotEncoder
  - Brand, Fuel Type, Transmission, Fuel_Group

### Train-Test Split
- Training Set: 80% (1,248 samples)
- Testing Set: 20% (312 samples)
- Random State: 69 (reproducibility)

## Model Usage

### Simple Prediction Function

```python
from car_predictions import predict_car_price

price = predict_car_price(
    year=2023,
    brand="Toyota",
    fuel_type="Petrol",
    transmission="Automatic",
    mileage=15000
)
print(f"Predicted Price: ₹{price:,.2f}")
```

### Robust Predictor Class

```python
from car_predictions import CarPricePredictor

predictor = CarPricePredictor(
    model_path='../models/car_price_xgboost_model.joblib',
    preprocessor_path='../models/car_price_preprocessor.joblib',
    feature_info_path='../models/car_price_feature_info.joblib'
)

result = predictor.predict(
    year=2023,
    brand="BMW",
    fuel_type="Diesel",
    transmission="Automatic",
    mileage=45000
)

if result["status"] == "success":
    print(f"Price: ₹{result['predicted_price']:,.2f}")
else:
    print(f"Errors: {result['errors']}")
```

## Visualizations

### Brand Analysis
- **Distribution of Car Brands**: Histogram showing frequency of each brand
- **Average Price by Brand**: Bar chart comparing average prices across brands

### Model Performance
- **Model Comparison Chart**: Normalized comparison of MAE, MSE, and R² across all models

## Files

- `notebooks/car_predictions.ipynb` - Complete EDA, feature engineering, model training, and evaluation
- `data/car_price_prediction_.csv` - Raw dataset with 1,560 car records and 5 base features
- `models/car_price_xgboost_model.joblib` - Trained XGBoost price prediction model
- `models/car_price_preprocessor.joblib` - ColumnTransformer for encoding and scaling
- `models/car_price_feature_info.joblib` - Feature names and structure information

## Supported Brands

The predictor supports the following brands:
- **Luxury**: Tesla, BMW, Audi, Mercedes
- **Standard**: Toyota, Honda, Maruti, Hyundai, Ford, Mahindra

## Supported Parameters

- **Year**: 1990 to 2025
- **Fuel Types**: Petrol, Diesel, Hybrid, Electric
- **Transmission**: Manual, Automatic

## Key Takeaways

1. **XGBoost Superiority**: XGBoost outperforms all other models with highest R² and best generalization
2. **Feature Engineering Matters**: Derived features (Car Age, Mileage Per Year) significantly improve predictions
3. **Brand Positioning**: Luxury brands command predictable premiums reflected in model coefficients
4. **Market Trends**: Electric and hybrid vehicles are reshaping automotive pricing landscape
5. **Depreciation Patterns**: Clear correlation between age, mileage, and price depreciation
6. **Production Ready**: Robust prediction system with input validation and error handling
7. **Scalability**: Model easily adaptable to new brands and vehicle types with retraining
