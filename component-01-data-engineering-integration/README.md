# Component 01 – Data Engineering and Integration

## Overview

This component collects, cleans and combines the tea production and weather datasets. The result is one reliable dataset for weather analysis (Component 02) and harvest prediction (Component 03).

The work is in [`DSGP_Data_preprocessing.ipynb`](../DSGP_Data_preprocessing.ipynb), mainly the data loading, preprocessing and **"Final data set preparation"** sections.

## Objectives

- Load and inspect all tea production and weather datasets.
- Clean the data and check its quality: missing values, duplicates, invalid values and inconsistent formats.
- Convert the raw files into a consistent monthly structure.
- Match tea districts with the weather locations.
- Merge tea production and weather data into one final dataset.

## Datasets Used

| Dataset | Description |
|---|---|
| Tea production by elevation and region | Monthly production by elevation (High, Medium, Low grown), by 38 districts and by regional group, 2015–2025 |
| Monthly tea production by process type | Monthly Orthodox, CTC and Green Tea production, 2015–2026 |
| ALL FACTORIES 2023–2026 | Monthly green leaf quantity for five factories (ACU, T Valley, T View, New Panawenna, New Nawalakanda) |
| Manual Entry | Daily production records entered manually, 2023–2026 |
| Sri Lanka Tea Areas Weather 2015–2026 | Monthly weather for 38 tea sub-districts (rainfall, temperature, humidity, solar radiation, wind, ET0, sunshine, soil moisture) |

## Methodology

1. **Data loading and inspection:** Load every dataset and check its shape, columns, data types and first rows.
2. **Tea production data (elevation, district, region):**
   - Convert dates to monthly datetime.
   - Check for missing values, duplicates and negative values.
   - Confirm that the kg and tonne columns match.
3. **Process type data:**
   - Check that the Orthodox, CTC and Green shares add up to 1.
   - Find months with data-quality notes, such as repeated or mismatched figures, and flag them with `quality_flag`.
4. **Factory data:**
   - Remove the extra header rows and rename the columns.
   - Fill in the missing year values.
   - Convert month names to numbers.
   - Reshape the table into long format: one row per factory per month.
5. **Manual entry data:**
   - Reshape the yearly columns into a daily time series.
   - Remove the empty days.
   - Note that 29 February 2024 is missing from the template.
6. **Weather data:**
   - Check for missing values and duplicate month and sub-district rows.
   - Confirm the date coverage: 141 months for every sub-district.
7. **Matching and merging:**
   - Standardise the date and location names.
   - Confirm that all 38 tea districts and all 6 regional groups match the weather data.
   - Average the weather data by month and regional group, then merge it with district production.
8. **Validation and export:**
   - Check that the final dataset has no missing values and no duplicates.
   - Check that the record count matches the original tea data (5,016 rows).
   - Export the final dataset.

## Final Dataset

**`final_tea_weather_merged_dataset.csv`**

- **Records:** 5,016 (38 districts × 132 months)
- **Period:** January 2015 – December 2025
- **Columns:** date, district, regional group, production (kg and tonnes), data-quality flags and 10 weather variables
- **Quality checks:** no missing values, no duplicate month and district rows, record count matches the original tea data

## Technologies and Tools

- Python, Google Colab
- Pandas, NumPy
- Matplotlib, Seaborn (for inspection and EDA)

## Integration

The final merged dataset is used by:

- **Component 02 – Weather Impact Analysis:** to study how weather relates to tea production.
- **Component 03 – Harvest Prediction Model:** as the input to feature engineering and model training ([`DSGP_FeatureEnginnering.ipynb`](../DSGP_FeatureEnginnering.ipynb)).
