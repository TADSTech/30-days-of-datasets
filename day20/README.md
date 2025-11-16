# Day 20: GPU Evolution Analysis

## Dataset

[Dataset Link - https://www.kaggle.com/datasets/alanjo/gpu-data]

## Summary

Exploratory data analysis of GPU specifications from 1986 to 2026, including brand distribution, temporal trends in memory and clock speeds, and correlations between key metrics.

## Key Analyses

**Data Overview**
- Dataset with 1,745 GPUs across 40 years
- Extracted release year from date strings
- Cleaned memory sizes and clock speeds for analysis

**Temporal Trends**
- GPU releases peaked at 147 in 2016
- Memory sizes grew exponentially from <1 MB to >10,000 MB
- Clock speeds increased steadily to ~1,200 MHz before stabilizing

**Brand Analysis**
- NVIDIA dominates with 837 GPUs (48%)
- ATI/AMD combined 781 GPUs (45%)
- Other brands have minimal presence

**Correlations**
- Strong correlation between release year and memory (0.62)
- Moderate correlation with clock speed (0.35)
- Weak correlation between memory and clock speed (0.22)

## Insights

1. GPU industry growth accelerated dramatically after 2010
2. Memory capacity has been the primary driver of performance improvements
3. NVIDIA's market dominance reflects successful product strategy
4. Linear models struggle to capture exponential technological progress

## Visualizations

- GPU releases per year bar chart
- Top 10 brands distribution
- Memory size evolution line chart
- Clock speed evolution line chart
- Correlation matrix heatmap
- Memory prediction scatter plot with regression line

## Lightweight ML

- Linear regression to predict memory size from release year
- MSE: 8,945,632 on test set
- Demonstrates challenges of modeling exponential growth with linear methods

## Files

- `data/gpu_1986-2026.csv` - Raw GPU dataset
- `notebooks/gpueda.ipynb` - EDA and ML notebook