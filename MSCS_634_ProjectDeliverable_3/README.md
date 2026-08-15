# MSCS 634 Project Deliverable 3: Classification, Clustering, and Pattern Mining

## Purpose
This deliverable applies classification, clustering, and association rule mining to the cleaned UCI Red Wine Quality dataset.

## Methods
- Created a binary quality class: quality score >= 6 as higher quality.
- Built Decision Tree and k-NN classification models.
- Tuned k-NN using GridSearchCV.
- Evaluated classification using accuracy, F1 score, confusion matrix, and ROC curve.
- Built a K-Means clustering model and visualized clusters with PCA.
- Created association rules from discretized chemical properties.

## Key Insights
Higher quality wines tend to align with higher alcohol, lower volatile acidity, and favorable sulphate/density patterns. Clustering separates wines into interpretable chemical profiles.

## Files
- `Project_Deliverable_3.ipynb`
- `data/d3_classification_results.csv`
- `data/d3_cluster_summary.csv`
- `data/d3_association_rules.csv`
- `screenshots/` visualizations
