# Day 23: Spotify Track Data Analysis

## Overview
This day focuses on extensive exploratory data analysis (EDA) and classification modeling using Spotify track datasets. We analyze track popularity, artist metrics, and other features to understand patterns in music data.



## Dataset

[Dataset Link - https://www.kaggle.com/datasets/wardabilal/spotify-global-music-dataset-20092025]

- `track_data_final.csv`: Contains track-level information including popularity, duration, artist details, and genres.
- `spotify_data_clean.csv`: Cleaned Spotify data with additional metadata like album info and release dates.

## Key Findings from EDA
- Track popularity distributions and correlations with artist metrics.
- Genre analysis and top artists by popularity.
- Visualizations including histograms, scatter plots, box plots, and heatmaps.

## Models
- Logistic Regression and Random Forest classifiers trained to predict track popularity categories.
- Models evaluated using accuracy, precision, recall, and confusion matrices.
- Saved models: `spotify_lr_model.joblib` and `spotify_rf_model.joblib`.

## Files
- `notebooks/spotify_eda_classification.ipynb`: Main analysis notebook.
- `models/`: Trained classification models.
- `viz/`: Visualization.