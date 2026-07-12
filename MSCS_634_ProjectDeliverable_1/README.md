# MSCS 634 Project Deliverable 1: Data Collection, Cleaning, and Exploration

## Dataset Summary
This deliverable uses the UCI Red Wine Quality dataset. The dataset contains 1,599 wine samples and 12 columns, including chemical measurements and a wine quality rating.

## Major Cleaning and Exploration Steps
- Loaded and inspected the dataset structure with Pandas.
- Checked for missing values and duplicate rows.
- Removed duplicate rows.
- Identified outliers using the IQR method.
- Winsorized selected noisy chemical variables to reduce the influence of extreme values while preserving records.
- Created visualizations for quality distribution, alcohol-quality relationship, and feature correlations with quality.

## Key Insights
- Most wines are rated 5 or 6, so later classification may require grouping quality classes.
- Alcohol is positively associated with quality.
- Volatile acidity is negatively associated with quality.
- Chlorides, residual sugar, sulphates, and sulfur dioxide measures show outliers that should be monitored in later modeling.

## Challenges
The dataset does not contain missing values, so the cleaning process focused on duplicate rows and noisy outliers. Duplicate removal reduced repeated observations, and IQR-based winsorization helped prepare the dataset for modeling without discarding many records.
