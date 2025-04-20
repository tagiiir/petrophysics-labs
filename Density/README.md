# Density Logging Approximation via K-Means Clustering

## Description

Density logging data contains substantial amounts of continuous measurements that can often be **approximated** to simplify further **processing, interpretation, and modeling**.  
This project develops an algorithm that approximates density logging curves using **iterative partitioning** of the original dataset and **minimization of total variance** via clustering.  
The approach is based on **K-Means clustering**, which groups similar values and replaces them with representative constants (cluster centroids), reducing noise and allowing simplified analysis.

The method is validated by comparing the **Root Mean Square Error (RMSE)** of the approximated curves for different numbers of clusters.


## Example Use Case

Given well log curves such as `rhob10`, `rhob30`, and `rhob50`, the project:
- Segments each curve into a defined number of clusters;
- Replaces raw values with cluster means (centroids);
- Calculates RMSE between the original and approximated curves;
- Visualizes approximation quality across different cluster counts.


## Technologies

- `numpy` – numerical operations & clustering
- `pandas` – data handling
- `matplotlib` – plotting and visualizations
- (optional) `scikit-learn` – for KMeans implementation


## Visualization Example

- Comparison of original and approximated density curves
- RMSE vs. number of clusters ("elbow" method for optimal k)
- Step-like approximation to highlight zonal structure

