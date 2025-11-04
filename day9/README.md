# Day 9: BMW Sales Data Analysis & Price Prediction

## Dataset
Kaggle:<br>
[BMW Sales Data (2010-2024)](https://www.kaggle.com/datasets/ahmadrazakashif/bmw-worldwide-sales-records-20102024)

## Project Summary

Comprehensive analysis of BMW sales trends from 2010-2024 with a predictive model for BMW pricing. AdaBoost Regressor achieved strong performance in predicting vehicle prices based on features like model, year, mileage, fuel type, transmission, and engine size.

## Key Findings

- **Fuel Type Dominance**: Petrol vehicles lead market share, with growing hybrid adoption
- **Top Models**: 5 Series, 3 Series, and X3 are the best-selling models
- **Regional Leader**: Highest concentration of sales in specific regions with distinct preferences
- **Transmission Preference**: Automatic transmission significantly outpaces manual
- **Color Trends**: Specific colors show stronger sales correlations
- **Price Range**: BMW prices span from budget-friendly to luxury segments

## Sales Insights

1. **Year-over-Year Growth**: Recent years (2022-2024) show different sales patterns compared to early years (2010-2015)
2. **Mileage Impact**: Vehicle mileage categories show distinct sales distributions indicating depreciation patterns
3. **Model & Fuel Combinations**: Premium models paired with petrol engines maintain strong market presence
4. **Regional Fuel Preferences**: Different regions show varying preferences for fuel types

## Price Prediction Model

Built an AdaBoost Regressor to predict BMW prices with high accuracy, achieving strong R² scores and low prediction errors.

### Key Features for Price Prediction

- Mileage (KM): Historical usage indicator
- Year: Vehicle age and model generation
- Engine Size (L): Performance and category indicator
- Model: Brand positioning and market segment
- Fuel Type: Engine technology and efficiency
- Transmission: Manual vs Automatic transmission

## Visualizations

### Sales & Trends Analysis
- BMW sales trends over 15 years (line chart)
- Top 10 models by sales volume (bar chart)
- Regional sales distribution (pie chart)
- Fuel type preferences evolution over time (line chart with markers)
- Engine size vs sales volume correlation (bubble chart)
- Price vs sales volume by model (scatter plot)
- Transmission type distribution (bar chart)
- Color popularity analysis (bar chart)
- Region vs fuel type heatmap
- Sales classification distribution (High vs Low)
- Average price by model and fuel type (grouped bar chart)
- Year-over-year regional performance (stacked bar chart)
- Mileage category impact on sales (bar chart)

## Files

- `notebooks/trends.ipynb` - Complete EDA, analysis pipeline, and predictive modeling
- `data/BMW_sales_data(2010-2024).csv` - Raw dataset with 15 years of sales data
- `models/bmw_adaboost_price_model.joblib` - Trained AdaBoost price prediction model

## Model Usage

The notebook includes a reusable `predict_bmw_price()` function for making predictions on new vehicles:

```python
predicted_price = predict_bmw_price(
    model_name="3 Series",
    year=2023,
    mileage_km=45000,
    fuel_type="Petrol",
    transmission="Automatic",
    engine_size_l=2.0
)
```

## Key Takeaways

- BMW maintains strong market presence across multiple vehicle segments
- Price prediction can be accurately modeled using vehicle characteristics
- Regional and temporal variations significantly impact sales patterns
- Fuel type preferences are shifting with market trends
- The AdaBoost model provides reliable pricing predictions for inventory valuation and market analysis
