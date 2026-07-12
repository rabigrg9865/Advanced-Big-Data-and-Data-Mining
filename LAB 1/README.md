# MSCS 634 Lab 1: Data Visualization, Data Preprocessing, and Statistical Analysis

## Purpose

This lab applies data visualization, preprocessing, and statistical analysis techniques in Python using an open-data dataset downloaded from Data.gov. The dataset used is Washington State's Electric Vehicle Population Data, which contains Battery Electric Vehicle (BEV) and Plug-in Hybrid Electric Vehicle (PHEV) registration records.

## Dataset Source

- Source platform: Data.gov
- Dataset title: Electric Vehicle Population Data
- Publisher: data.wa.gov / State of Washington
- Dataset page: https://catalog.data.gov/dataset/electric-vehicle-population-data
- CSV endpoint used for this lab: `https://data.wa.gov/resource/f6w7-q2d2.csv?$limit=20000`
- Local raw dataset file: `wa_ev_population_data.csv`

A 20,000-record CSV download was used so the notebook remains easy to run and review while still using actual public data from the required type of open-data platform.

## Repository Contents

- `Lab_1_Data_Visualization_Preprocessing_Statistical_Analysis.ipynb`: completed Jupyter Notebook with code, outputs, explanations, visualizations, preprocessing, and statistical analysis.
- `wa_ev_population_data.csv`: raw downloaded dataset from Data.gov/data.wa.gov.
- `wa_ev_population_data_cleaned.csv`: cleaned, reduced, scaled, and discretized dataset produced during preprocessing.
- `screenshots/`: PNG screenshots required by the lab instructions.

## Key Insights

- Battery Electric Vehicles make up the majority of the EV records in the downloaded sample.
- Tesla appears as one of the most common EV makes, indicating strong representation in Washington State EV registrations.
- Vehicle counts are concentrated in recent model years, showing the dataset is heavily weighted toward newer EV registrations.
- Electric range has many zero values because the dataset includes newer vehicles whose range has not been researched yet.
- IQR did not identify electric-range outliers among non-zero range values, so the allowed standard-deviation method was used to identify unusually high range records.
- Correlation analysis provides a quick view of relationships among numeric fields such as model year, electric range, ZIP code, district, vehicle ID, and census tract.

## Preprocessing Decisions

- Missing categorical location/geography values were filled with `Unknown`.
- Missing numeric geography values were filled with the median because these fields are identifiers or district-style values, not continuous performance measurements.
- IQR was calculated for non-zero electric range values, but because it found no outliers, two-standard-deviation outlier detection was used for actual outlier handling.
- Data reduction used a 20% random sample and dropped high-cardinality identifier/geocoding columns: `vin_1_10`, `dol_vehicle_id`, `geocoded_column`, and `_2020_census_tract`.
- Min-Max scaling was applied to electric range, Z-score standardization was applied to model year, and electric range was discretized into Unknown/Not Researched, Short, Medium, and Long categories.

## Challenges

The main challenge was choosing a real public dataset that supports every required task. The EV dataset is appropriate because it includes categorical variables, numeric variables, missing values, enough records for sampling, and numeric values suitable for statistical analysis. Another decision was treating zero electric range carefully because the dataset uses it for many vehicles whose range has not yet been researched.
