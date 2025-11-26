# Day 30: Global Health Dataset - Comprehensive EDA & Ensemble ML

## Final Day Special: Maximum Extensive Analysis

This is the grand finale of the 30-days-of-datasets challenge! Day 30 features an extensive analysis of the Unified Global Health Dataset - a comprehensive collection of health metrics from 195 countries spanning 30 years (1990-2021).

## Dataset Overview
- **Records**: 22,050 health observations
- **Time Period**: 1990-2021 (32 years)
- **Features**: 150+ health, economic, and demographic indicators
- **Scope**: Global health data including mortality rates, life expectancy, healthcare metrics, and economic indicators

## Dataset Source
[Global Health, Nutrition, Mortality, Economic Data
](https://www.kaggle.com/datasets/miguelroca/global-health-nutrition-mortality-economic-data)

## Analysis Components

### 1. Exploratory Data Analysis (EDA)
Comprehensive visualizations using Plotly (dark theme) to understand global health patterns:

- **Life Expectancy Distribution**: Shows worldwide life expectancy spread with median-based categorization
- **Infant Mortality vs Life Expectancy**: Scatter plot analysis over time showing strong inverse correlation
- **GDP vs Life Expectancy by Gender**: Economic impact on health outcomes across genders
- **Healthcare Impact Analysis**: Box plot showing healthcare coverage influence
- **Temporal Trends**: Global average life expectancy improvement from 1990-2021
- **Correlation Heatmap**: Key health indicators and their relationships

### 2. Data Processing Pipeline
- Handled missing values using median imputation
- Removed duplicates (0 found)
- Created balanced binary target: High/Low Life Expectancy
- Feature engineering and encoding for categorical variables
- Feature scaling with StandardScaler

### 3. Ensemble Machine Learning Model

#### Individual Models Trained:
1. **Random Forest Classifier** (n_estimators=100)
   - Accuracy: 90.50%
   - F1-Score: 90.59%

2. **Gradient Boosting Classifier** (n_estimators=100)
   - Accuracy: 89.73%
   - F1-Score: 89.87%

3. **Logistic Regression**
   - Accuracy: 84.72%
   - F1-Score: 84.91%

4. **K-Nearest Neighbors** (n_neighbors=5)
   - Accuracy: 88.00%
   - F1-Score: 88.24%

#### Voting Classifier Ensemble (Soft Voting):
- **Accuracy**: 89.93%
- **F1-Score**: 90.14%
- **Precision**: 90% (both classes)
- **Recall**: 90% (both classes)

### 4. Top Feature Importance
1. Infant Mortality Rate (23.2%)
2. Under 5 Mortality Rate (21.3%)
3. Birth Rate (14.2%)
4. GDP per Capita (12.0%)
5. Gender (9.6%)
6. Death Rate (7.9%)

## Model Evaluation Results

### Confusion Matrix (Voting Ensemble)
```
                 Predicted Low    Predicted High
Actual Low          1,936            269
Actual High           175           2,030
```

### Key Metrics
- **True Positives**: 2,030 (High Life Expectancy correctly identified)
- **True Negatives**: 1,936 (Low Life Expectancy correctly identified)
- **False Positives**: 269 (Type I Error)
- **False Negatives**: 175 (Type II Error)
- **Overall Accuracy**: 89.93%

## Visualizations Generated
1. `life_expectancy_distribution.html` - Distribution of global life expectancy
2. `mortality_vs_life_expectancy.html` - Mortality trends over decades
3. `gdp_vs_life_expectancy.html` - Economic impact analysis
4. `healthcare_impact.html` - Healthcare coverage effectiveness
5. `life_expectancy_trend.html` - Temporal progression (1990-2021)
6. `correlation_heatmap.html` - Key indicator relationships
7. `confusion_matrix_ensemble.html` - Model performance matrix
8. `model_comparison.html` - All models performance comparison
9. `feature_importance.html` - Top 12 predictive features

## Pipeline & Deployment

### Saved Artifacts
- `health_prediction_ensemble_pipeline.joblib` - Complete ML pipeline
- `health_prediction_scaler.joblib` - Feature scaler
- `health_prediction_gender_encoder.joblib` - Categorical encoder
- `health_prediction_feature_names.txt` - Feature column names

### Example Predictions

#### Example 1: Developed Country (2020)
- Infant Mortality: 3.0, Under-5 Mortality: 4.0
- GDP per Capita: $45,000
- **Prediction**: High Life Expectancy (98.94% confidence)

#### Example 2: Developing Country (2020)
- Infant Mortality: 35.0, Under-5 Mortality: 45.0
- GDP per Capita: $3,000
- **Prediction**: Low Life Expectancy (98.60% confidence)

#### Example 3: Emerging Market (2020)
- Infant Mortality: 15.0, Under-5 Mortality: 18.0
- GDP per Capita: $10,000
- **Prediction**: High Life Expectancy (94.70% confidence)

## Key Findings

1. **Strong Mortality-Life Expectancy Link**: Infant and child mortality rates are the most predictive features (45% combined importance)

2. **Economic Impact**: GDP per Capita significantly influences health outcomes - wealthier nations consistently show higher life expectancy

3. **Global Progress**: Average global life expectancy increased from ~65 years (1990) to ~72 years (2021)

4. **Balanced Performance**: Voting ensemble effectively combines strengths of individual models for robust predictions

5. **High Confidence Predictions**: Model achieves 95-98% confidence on clear country scenarios

## Files Structure
```
day30/
├── README.md (this file)
├── data/
│   └── UnifiedDataset.csv (22,050 records)
├── notebooks/
│   └── day30_unified_eda_ensemble.ipynb (Complete analysis)
├── viz/
│   ├── life_expectancy_distribution.html
│   ├── mortality_vs_life_expectancy.html
│   ├── gdp_vs_life_expectancy.html
│   ├── healthcare_impact.html
│   ├── life_expectancy_trend.html
│   ├── correlation_heatmap.html
│   ├── confusion_matrix_ensemble.html
│   ├── model_comparison.html
│   └── feature_importance.html
└── models/
    ├── health_prediction_ensemble_pipeline.joblib
    ├── health_prediction_scaler.joblib
    ├── health_prediction_gender_encoder.joblib
    └── health_prediction_feature_names.txt
```

## Technologies Used

### Data Processing
- Python 3, pandas, numpy

### Visualization
- Plotly (dark theme for all interactive plots)

### Machine Learning
- Scikit-learn: Random Forest, Gradient Boosting, Logistic Regression, KNN, Pipeline, VotingClassifier
- StandardScaler for feature normalization
- LabelEncoder for categorical variables

### Deployment
- joblib for model serialization
- Complete pipeline for production-ready predictions

## Usage

### Loading the Pipeline
```python
from joblib import load
import pandas as pd

# Load pipeline and supporting artifacts
pipeline = load('models/health_prediction_ensemble_pipeline.joblib')

# Prepare sample data (must match feature order)
sample = pd.DataFrame({
    'Year': [2020],
    'Infant Mortality Rate': [10.0],
    'Under 5 Mortality Rate': [12.0],
    'Suicides Rate': [8.0],
    'Birth Rate': [15.0],
    'Death Rate': [8.0],
    'GDP per Capita': [15000.0],
    'Total Population': [50000000.0],
    'Doctors': [200.0],
    'Nurses and Midwifes': [500.0],
    'Road Traffic Deaths': [15.0],
    'Gender_encoded': [1]  # 0=Male, 1=Female
})

# Make predictions
prediction = pipeline.predict(sample)
probabilities = pipeline.predict_proba(sample)

print(f"Prediction: {prediction[0]}")  # 0=Low, 1=High
print(f"Confidence: {max(probabilities[0])*100:.2f}%")
```

## Summary

Day 30 represents the culmination of 30 days of data science exploration. This final analysis demonstrates:
- **Comprehensive EDA**: 9 interactive visualizations revealing global health patterns
- **Powerful Ensemble ML**: 4 models combined for robust 89.93% accuracy predictions
- **Production-Ready Pipeline**: Serialized and deployable for real-world applications
- **Actionable Insights**: Clear factors driving life expectancy across nations

The ensemble approach successfully balances model strengths, achieving excellent performance without GPU acceleration, making it practical for standard computational resources.

## Lessons Learned

1. Ensemble methods effectively combine diverse model perspectives
2. Mortality indicators are universal predictors of life expectancy
3. Economic metrics (GDP) strongly correlate with health outcomes
4. Balanced datasets (50-50 split) enable fair model evaluation
5. Feature scaling is crucial for models like Logistic Regression and KNN

---

**Challenge Completion**: 30/30 Days ✅