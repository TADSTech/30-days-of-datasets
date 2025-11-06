# Day 11: Housing Price Analysis & Prediction

## Dataset
Kaggle:<br>
[Housing Price Dataset](https://www.kaggle.com/datasets/wardabilal/real-estate-price-insights)

## Project Summary

Comprehensive analysis of housing prices with focus on identifying key market drivers and building a predictive model. The project explores relationships between property features (area, bedrooms, amenities) and pricing, followed by an AdaBoost Regressor model for accurate price prediction.

## Key Findings

### Market Drivers Priority

| Factor | Impact | Priority |
|--------|--------|----------|
| **Area (Size)** | Strongest predictor - direct positive correlation | Critical |
| **Air Conditioning** | ~₹2M price premium (50% premium) | High |
| **Furnishing Status** | Furnished adds 30-40% premium vs unfurnished | High |
| **Parking Availability** | 3+ spots add significant premium | Medium-High |
| **Bedrooms** | Correlates with both area and price | Medium |

### Price Insights

- **Price Range**: ₹2M to ₹14M across the dataset
- **Area Range**: Properties from 1,500 to 16,500 square units
- **Market Concentration**: Most properties cluster between 4,000-8,000 square units with prices of ₹4M-7M
- **AC Premium**: Properties with air conditioning command ~₹2M higher prices on average
- **Furnishing Impact**: Furnished properties achieve highest average prices (~₹25M total value), followed by semi-furnished (~₹20M) and unfurnished (~₹18M)

## Visualization Insights

### 1. Price vs Area by Furnishing Status

**Key Observations**:
- Strong positive correlation between area and price across all furnishing categories
- **Furnished** (Blue): Mid-to-high price range with premium positioning
- **Semi-Furnished** (Red): Mid-range pricing with moderate spread
- **Unfurnished** (Green): Widest distribution, generally lower prices for equivalent area
- Bedroom count (bubble size) shows larger homes tend to be furnished

### 2. Effect of Air Conditioning on House Prices

**Key Observations**:
- **With AC**: Median price ~₹6M, range ₹2M-₹10M+ with outliers to ₹13M
- **Without AC**: Median price ~₹4M, range ₹1.5M-₹8M
- **Price Difference**: ~₹2M premium (50% increase) for AC-equipped properties
- Air conditioning is a significant value-added feature in the market

### 3. Average House Price by Furnishing Status and Parking

**Market Segments**:
- **Furnished + High Parking**: Premium segment (~₹10M-12M)
- **Semi-Furnished + Medium Parking**: Mid-market segment (~₹8M-10M)
- **Unfurnished + Low Parking**: Entry-level segment (~₹4M-6M)

**Parking Impact**:
- 3+ parking spots command highest premium (yellow segments)
- 1-2 spots add mid-level value (orange segments)
- 0-1 spots represent base value (purple/blue segments)

## Price Prediction Model

Built an AdaBoost Regressor with Decision Tree base estimator to predict housing prices based on property features.

### Model Architecture

- **Algorithm**: AdaBoost Regressor
- **Base Estimator**: Decision Tree Regressor (max_depth=4)
- **Number of Estimators**: 200
- **Learning Rate**: 0.05
- **Feature Scaling**: StandardScaler normalization

### Features Used

1. **Area**: Property size (primary predictor)
2. **Bedrooms**: Number of bedrooms
3. **Bathrooms**: Number of bathrooms
4. **Stories**: Number of floors
5. **Mainroad**: Access to main road (binary)
6. **Guestroom**: Presence of guest room (binary)
7. **Basement**: Basement availability (binary)
8. **Hot Water Heating**: Heating system (binary)
9. **Air Conditioning**: AC availability (binary)
10. **Parking**: Number of parking spaces
11. **Preferred Area**: Location preference (binary)
12. **Furnishing Status**: Encoded (0=unfurnished, 1=semi-furnished, 2=furnished)

### Model Performance

- **Test Set Size**: 20% of data
- **Training Set**: 80% of data
- **Evaluation Metrics**: MAE, MSE, R² Score
- Strong predictive performance for real estate valuation

## Market Recommendations

### For Buyers
- Area is the primary value driver; focus on location and size
- AC presence is highly valued; consider maintenance costs
- Parking availability should influence location choice
- Unfurnished properties offer better value for customization

### For Sellers
- Improving furnishing status can increase appeal by 30-40%
- Adding parking facilities provides good ROI
- Air conditioning upgrade justified by 50% price premium
- Properties near main roads command higher prices

### For Investors
- Unfurnished properties in high-demand areas offer best ROI potential
- Focus on properties with expansion/renovation opportunities
- Market shows strong demand for both luxury and value segments
- AC and parking upgrades provide measurable value addition

## Visualizations

- **Price vs Area Scatter Plot**: Relationship between property size and price by furnishing status
- **Air Conditioning Box Plot**: Price distribution comparison for AC vs non-AC properties
- **Furnishing & Parking Bar Chart**: Average prices by furnishing status and parking availability

## Files

- `notebooks/housing.ipynb` - Complete EDA and AdaBoost price prediction model
- `data/Housing_Price_Data.csv` - Raw dataset with property features and prices

## Key Takeaways

1. **Area is King**: Property size remains the strongest predictor of housing prices
2. **Amenities Matter**: AC, parking, and furnishing significantly impact valuation
3. **Premium Justification**: Higher-end features command measurable price premiums
4. **Market Segmentation**: Clear price tiers exist based on feature combinations
5. **Predictive Accuracy**: AdaBoost model provides reliable price predictions for real estate valuation
6. **Investment Strategy**: Strategic improvements (AC, parking, furnishing) offer quantifiable ROI
