# Component 02 – Weather Impact Analysis on Tea Production

## Overview

This component focuses on analysing how weather conditions influence monthly tea production across Sri Lankan districts.

Using the processed tea production and weather datasets, exploratory and statistical analysis techniques will be applied to identify which weather variables most strongly affect tea yield, and how these effects vary across time, regions, and elevation zones.

## Objectives

- Explore the relationship between weather variables and monthly tea production.
- Identify the weather factors with the strongest influence on tea yield.
- Analyse seasonal patterns and trends in both weather and production data.
- Investigate lagged effects of weather on harvest (e.g. rainfall in previous months).
- Compare weather impact across districts and elevation zones (high-grown and low-grown regions).
- Provide evidence-based insights to support feature selection in model training.

## Methodology

1. **Data Understanding:** Review the integrated tea production and weather datasets, including variables such as rainfall, temperature, humidity, and sunshine hours.
2. **Exploratory Data Analysis (EDA):** Examine distributions, trends, seasonality, missing values, and outliers.
3. **Correlation Analysis:** Measure the strength and direction of relationships between weather variables and tea production using Pearson and Spearman correlation.
4. **Lag Analysis:** Test the effect of previous months' weather on current production to identify delayed impacts.
5. **Regional Comparison:** Compare weather–production relationships across districts and elevation zones.
6. **Feature Importance Analysis:** Rank weather variables by their influence on tea production using statistical and tree-based methods.
7. **Insight Summary:** Summarise the key findings and recommend the most relevant weather features for the prediction models.

## Expected Outputs

- Exploratory data analysis results and summary statistics.
- Correlation matrices and heatmaps of weather variables against tea production.
- Lag analysis results showing delayed weather effects.
- Seasonal and regional comparison visualisations.
- Ranked list of the most influential weather features.
- Summary of key findings and recommended features for model training.

## Technologies and Tools

- Python
- Google Colab
- Pandas and NumPy
- SciPy and Statsmodels
- Scikit-learn
- Matplotlib and Seaborn

## Integration

The findings and the recommended weather features from this component will be provided to **Component 03 – Harvest Prediction Model Training and Comparison** to guide feature selection, and to **Component 04 – Decision Support Application with Explainable AI (XAI)** to support the interpretation of weather effects within the overall Sri Lankan Tea Production Prediction System.
