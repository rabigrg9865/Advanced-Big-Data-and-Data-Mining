# Lab 3 — K-Means and K-Medoids

## Purpose

This lab compares K-Means and K-Medoids clustering on the sklearn Wine dataset. All 13 features are standardized with z-score normalization before clustering, then both methods form three clusters to match the dataset's known three wine classes. The notebook evaluates cluster quality with Silhouette Score and Adjusted Rand Index (ARI), and visualizes both results side by side on the same two-component PCA projection.

## Results and observations

| Algorithm | Silhouette Score | Adjusted Rand Index |
| --- | ---: | ---: |
| K-Means | 0.2849 | 0.8975 |
| K-Medoids | 0.1548 | 0.3413 |

K-Means produced the better-defined clusters in this run: it had the higher Silhouette Score, meaning its clusters were more cohesive and separated in the standardized feature space, and its much higher ARI matched the known Wine classes more closely. The side-by-side PCA scatter plots mark K-Means centroids with red X markers and K-Medoids medoids with red P markers. The K-Means partition appears more cleanly separated in the PCA view, while the K-Medoids partition has more overlap and differently positioned group boundaries.

K-Means is preferable for this dataset because the standardized Wine groups are reasonably compact and its mean-based centers captured the class structure effectively. K-Medoids may be preferable when outliers are a concern or when using a real observation as the cluster representative is important; medoids are less affected by extreme values but require more computation. The comparison is a single reproducible run, so the numerical result should not be treated as a universal ranking of the methods.

## Decisions and challenges

- Standardization was essential because the Wine features have very different numeric ranges; without it, large-range features would dominate the distance calculations.
- k=3, random_state=42, and n_init=20 for K-Means make the analysis reproducible.
- The environment's installed NumPy is binary-incompatible with the available scikit-learn-extra wheel. The notebook attempts to use scikit-learn-extra first and provides a deterministic compatible K-Medoids fallback so the required analysis can still execute. On a compatible installation, the primary scikit-learn-extra implementation is used.
- The notebook was executed successfully and contains its metric table and side-by-side scatter plot outputs.



