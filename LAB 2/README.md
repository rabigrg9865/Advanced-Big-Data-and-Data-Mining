# Lab 2 — KNN and Radius Neighbors

## Purpose

This lab compares two instance-based classifiers on the sklearn Wine dataset: K-Nearest Neighbors (KNN), which classifies from a fixed number of nearby samples, and Radius Neighbors (RNN), which classifies from samples inside a fixed distance. The notebook explores the dataset, uses the required stratified 80/20 train/test split with random_state=42, evaluates the assigned parameter values, and visualizes each model's test-accuracy trend.

## Results and observations

The notebook creates one line plot for KNN accuracy by k and a second line plot for Radius Neighbors accuracy by radius. On the 36-item test set, the results were:

| Model | Parameter | Test accuracy |
| --- | ---: | ---: |
| KNN | k=1 | 77.78% |
| KNN | k=5, 11, 15, or 21 | 80.56% |
| RNN | radius=350 | 72.22% |
| RNN | radius=400, 450, or 500 | 69.44% |
| RNN | radius=550 or 600 | 66.67% |

KNN was more accurate for every assigned setting. Moving from k=1 to k=5 improved accuracy, then the result remained stable through k=21; this indicates that a modestly broader neighborhood reduced sensitivity to individual local points. RNN's accuracy decreased as the radius increased because progressively broader neighborhoods mixed examples from different wine classes. The feature values have substantially different raw scales—especially proline—so raw Euclidean radii are strongly influenced by that feature.

KNN is preferable here when a fixed neighbor count and stronger measured accuracy are the priority. RNN can be preferable when a meaningful distance threshold is known and the density of the data matters; it can adapt the number of neighbors per prediction. In a future RNN experiment, standardizing features before selecting radii would make each feature contribute more evenly to the distance calculation.

## Decisions and challenges

- The prescribed radius values were evaluated on the raw feature units, as required. The most-frequent-class fallback prevents a test observation with no neighbors from causing an unhandled prediction error.
- The split is stratified so each wine class remains proportionally represented in training and testing.
- The notebook was executed successfully with the displayed tables and figures saved in the notebook output.



