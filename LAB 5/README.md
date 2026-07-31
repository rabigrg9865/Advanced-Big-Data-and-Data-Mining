# MSCS 634 Lab 5: Clustering Techniques

This lab compares Agglomerative Hierarchical Clustering and DBSCAN using the Wine dataset from scikit-learn.

## Files

- `MSCS_634_Lab_5.ipynb`: Jupyter Notebook with data exploration, standardization, clustering, visualizations, metrics, and written analysis.

## Key Insights

Hierarchical clustering worked best with three clusters, which fits the known structure of the Wine dataset. DBSCAN was more sensitive to `eps` and `min_samples`, and several settings produced many noise points. This showed that DBSCAN can be helpful for finding dense regions and outliers with careful parameter tuning.

## Challenges

The main challenge was choosing fair DBSCAN parameters. I tested several `eps` values so the results would show how parameter choices change the clusters and noise points.
