# Day 10: Goodreads Books Dataset - Analysis & Rating Prediction

## Dataset
Kaggle:<br>
[Goodreads Books Dataset](https://www.kaggle.com/datasets/jealousleopard/goodreadsbooks)

## Project Summary

Comprehensive analysis of Goodreads books dataset with machine learning-based rating prediction. AdaBoost Regressor was trained to predict book ratings based on title characteristics, author information, book metadata, and popularity metrics. The model achieved strong performance metrics with accurate rating predictions.

## Key Findings

- **Rating Distribution**: Books are concentrated in the higher rating ranges, reflecting Goodreads' community bias toward well-reviewed titles
- **Subtitle Impact**: Books with subtitles show measurable differences in average ratings
- **Series vs Standalone**: Series books demonstrate distinct rating patterns compared to standalone publications
- **Author Influence**: Single-author and multi-author books show varying average ratings
- **Title Complexity**: Varying levels of title complexity correlate with different rating outcomes
- **High-Rated Books**: Significant percentage of books in dataset are classified as high-rated

## Book Characteristics Analysis

1. **Title Metrics**: Title length, word count, and complexity significantly influence discoverability and ratings
2. **Author Patterns**: Author count, name length, and middle name presence are predictive factors
3. **Series Dynamics**: Series books, particularly those with explicit series markers, show distinct characteristics
4. **Metadata Relationships**: Rating tiers and categories provide hierarchical classification of book quality
5. **Popularity Correlation**: Estimated popularity serves as proxy for reader engagement and rating prediction

## Rating Prediction Model

Built an AdaBoost Regressor to predict Goodreads book ratings with high accuracy based on 12 features including title characteristics, author information, and book metadata.

### Model Performance

- **Algorithm**: AdaBoost Regressor (200 estimators, learning_rate=0.05)
- **Training Samples**: 2,436
- **Testing Samples**: 609
- **Test MAE**: Low mean absolute error in rating points
- **Test RMSE**: Low root mean squared error
- **Test R² Score**: Strong predictive capability

### Key Features for Rating Prediction

- **Title Length**: Number of characters in book title
- **Word Count**: Number of words in title
- **Author Count**: Number of co-authors
- **Author Name Length**: Length of author name(s)
- **Title Complexity**: Categorical complexity level (Simple, Moderate, Complex, Very Complex)
- **Title Type**: Book classification (Standard, Subtitle, Series)
- **Has Subtitle**: Boolean indicator for subtitle presence
- **Has Series Info**: Boolean indicator for series membership
- **Has Middle Name**: Boolean indicator for author middle name
- **Series Number**: Position in series (if applicable)
- **Percentile Rank**: Ranking percentile of the book
- **Estimated Popularity**: Categorical popularity level (Low, Medium, High)

## Visualizations

### Books & Ratings Analysis
- **Rating Distribution**: Histogram showing frequency distribution of all book ratings
- **Rating by Category**: Bar chart of average ratings across rating categories
- **Rating Tier Distribution**: Count of books in each rating tier
- **Title Length vs Rating**: Scatter plot correlating title length with ratings (colored by high-rated status)
- **Word Count vs Rating**: Scatter plot showing word count relationship with ratings
- **Author Count Impact**: Box plot displaying rating distribution by number of authors
- **Subtitle Effect**: Bar chart comparing ratings for books with and without subtitles
- **Series vs Standalone**: Bar chart comparing average ratings by book type
- **Title Type Comparison**: Bar chart showing average ratings by title type
- **Title Complexity Analysis**: Bar chart displaying rating patterns by complexity level

### Model Evaluation
- **Actual vs Predicted Ratings**: Scatter plot showing model predictions vs actual ratings with error percentage color-coding
- **Feature Importance**: Horizontal bar chart identifying top predictive features

## Files

- `notebooks/goodread.ipynb` - Complete EDA, analysis pipeline, and AdaBoost rating prediction model
- `data/goodreads_books_dataset.csv` - Raw dataset with 3,045 books and 20 features
- `models/goodreads_adaboost_rating_model.joblib` - Trained AdaBoost rating prediction model
- `models/goodreads_rating_scaler.joblib` - Feature scaler for data normalization
- `models/goodreads_complexity_encoder.joblib` - Title complexity label encoder
- `models/goodreads_title_type_encoder.joblib` - Title type label encoder
- `models/goodreads_popularity_encoder.joblib` - Popularity level label encoder
- `models/goodreads_feature_columns.joblib` - Feature column names for model input

## Model Usage

The notebook includes a reusable `predict_book_rating()` function for predicting ratings on new books:

```python
predicted_rating = predict_book_rating(
    title_length=39,
    word_count=7,
    author_count=1,
    author_name_length=12,
    title_complexity="Moderate",
    title_type="Series",
    has_subtitle=False,
    has_series_info=True,
    has_middle_name=False,
    series_number=1,
    percentile_rank=99.0,
    estimated_popularity="High"
)
```

## Key Takeaways

- Book ratings can be effectively predicted using title and author characteristics
- Title complexity and length are significant predictors of book ratings
- Series books show distinct rating patterns compared to standalone publications
- Author information (count, name characteristics) influences rating outcomes
- The AdaBoost model provides reliable rating predictions for book recommendation systems
- Metadata patterns reveal underlying factors that contribute to book success on Goodreads