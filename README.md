# K_Means-clustering
K-means clustering is an unsupervised machine learning algorithm that groups unlabeled data points into a pre-determined number (k) of clusters. It works by iteratively assigning data points to the nearest cluster centroid and then recalculating the centroid based on the new assignments until the clusters converge. 

This repository contains a Jupyter Notebook tutorial demonstrating the K-Means clustering algorithm using Scikit-learn. The project walks through loading data, visualizing it, and applying clustering. It critically highlights the importance of feature scaling (using MinMaxScaler) for distance-based algorithms and demonstrates how to find the optimal number of clusters (k) using the Elbow Method.

## Dataset

The project uses a simple dataset named `income.csv`. This file contains the following columns:
* Name
* Age
* Income($)

# Project Workflow

1.  Data Loading and Initial Plot: The dataset is loaded into a pandas DataFrame. An initial scatter plot of `Age` vs. `Income($)` is created to visualize the data distribution.

2.  Clustering (Without Scaling): A K-Means model with 3 clusters (`n_clusters=3`) is applied directly to the unscaled `Age` and `Income($)` data. The resulting clusters and their centroids are plotted. This step illustrates a common pitfall, as the varying scales of the features lead to suboptimal cluster assignments.

3.  Feature Scaling:MinMaxScaler is used to scale both the Age and Income($) columns. This is a crucial preprocessing step for K-Means to ensure features with different scales (like age vs. income) are weighted appropriately during distance calculations.

4.  Clustering (With Scaling): The K-Means algorithm (n_clusters=3) is run again, this time on the scaled data. The resulting plot shows more logical and well-defined clusters, demonstrating the effectiveness of scaling.

5.  **Elbow Method:** To determine the optimal value for `k`, the Sum of Squared Errors (SSE, or `km.inertia_`) is calculated for `k` values from 1 to 9. This is then plotted on a line graph (the "Elbow Plot") to find the "elbow" point, which indicates the optimal number of clusters for the data.

## Requirements

* `pandas`
* `scikit-learn` (specifically `KMeans` and `MinMaxScaler`)
* `matplotlib`
* `jupyter` (to run the notebook)

## How to Run

1.  Clone this repository to your local machine.
2.  Ensure you have the required Python libraries installed:
    ```bash
    pip install pandas scikit-learn matplotlib jupyter
    ```
3.  Launch Jupyter Notebook from your terminal:
    ```bash
    jupyter notebook
    ```
4.  Open the `kmeans_cluster.ipynb` file and run the cells sequentially.
