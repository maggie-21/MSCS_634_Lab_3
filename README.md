# MSCS_634_Lab_3
# Clustering Analysis Lab

## Purpose

This lab explores clustering techniques on the Wine dataset from the `sklearn` library. Specifically, it:

* Implements **K-Means** and **K-Medoids** (with k = 3) to segment the data into clusters.
* Applies **z-score normalization** for consistent feature scaling.
* Uses **Silhouette Score** and **Adjusted Rand Index (ARI)** to evaluate cluster quality.
* Visualizes clustering results via **PCA**-projected scatter plots.

## Key Insights

* **K-Means Performance**:

  * Silhouette Score: 0.2849 (moderate separation)
  * ARI: 0.8975 (strong agreement with true labels)
  * Produces tight, spherical clusters with centroids at the heart of each group.

* **K-Medoids Performance**:

  * Silhouette Score: 0.1548 (less well-defined clusters)
  * ARI: 0.3413 (weaker alignment with class labels)
  * Generates irregular, elongated clusters; medoids (actual data points) often lie toward cluster edges.

* **Visualization**:

  * K-Means clusters appear more compact and separated in PCA space.
  * K-Medoids clusters overlap more and show greater shape variation.

* **Algorithm Preference**:

  * **K-Means** is preferable for spherical clusters, large datasets, and when scalability is key.
  * **K-Medoids** is preferable when robustness to outliers is needed, when using non-Euclidean distances, or when cluster centers must be actual data points.

## Challenges & Decisions

* The `sklearn-extra` package was not available, so a **custom K-Medoids** implementation using pairwise distances was developed.
* A **PCA** projection was applied to reduce high-dimensional data to 2D for clear visualization.
* Choice of **Silhouette** and **ARI** metrics balanced internal cluster cohesion (Silhouette) with external ground-truth comparison (ARI).
* Ensured reproducibility by setting random seeds for both algorithms.
