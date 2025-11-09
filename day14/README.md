# Day 14: Global Mobile Prices Analysis and Trend Forecasting

## Dataset

- Local CSV: `data/Global_Mobile_Prices_2025_Extended.csv`
- Source (original): https://www.kaggle.com/datasets/shahzadi786/world-smartphone-market-2025

## Project Summary

This project performs a professional exploratory data analysis of global mobile phone listings and attempts short-term trend forecasting when multi-year information is available. The notebook uses Plotly for interactive visualizations, applies careful cleaning and type conversion, and includes two modeling paths:

- Annual trend forecasting on median prices when year information is present. The trend model uses a regularized Ridge regression on a small polynomial basis and produces a three-year median price forecast.
- A supervised baseline pipeline (scaler + Ridge) trained on numerical features and a compact brand encoding when sufficient records exist. The pipeline and trend artifacts are saved for reproducibility.

All analysis is performed in `notebooks/GlobalMobilePhonesDataSales.ipynb` and artifacts are written to `models/`.

## Key Findings (summary)

- Price distribution is right-skewed with most listings in the lower price bands.
- Standard specification values cluster at common points (RAM, storage, battery capacities and charging speeds).
- Cross-sectional correlations between basic specs and price are weak, suggesting brand, software, supply-side factors, or omitted variables drive much of the price variation.
- When multi-year or release-date data is present, the annual median price provides a stable signal for short-term trend forecasting.

## Files

- `notebooks/GlobalMobilePhonesDataSales.ipynb` — EDA and trend forecasting notebook (Plotly visualizations).
- `data/Global_Mobile_Prices_2025_Extended.csv` — Dataset (attached to this project).
- `models/mobile_price_trend_model.joblib` — Saved trend model and metadata (created when multi-year data is available).
- `models/mobile_price_trend_annual.csv` — Annual median price used for trend modeling.
- `models/mobile_price_baseline_pipeline.joblib` — Supervised baseline pipeline (scaler + Ridge) when trained.

## How to run

1. Open `notebooks/GlobalMobilePhonesDataSales.ipynb` in Jupyter or VS Code and run cells top to bottom.
2. If you want to reproduce forecasts, ensure `data/Global_Mobile_Prices_2025_Extended.csv` is present and run the annual trend cell. The notebook will write models to `models/`.

## Notes

- Visualizations use Plotly for interactivity; export the notebook as HTML for shareable reports.
- The supervised baseline is intentionally conservative. For production-grade price prediction, incorporate demand-side variables, market region, and supply timing.