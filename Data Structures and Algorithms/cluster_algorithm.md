# Cluster Algorithm

## Partitioning

<img width="167" height="122" alt="partitioning" src="https://github.com/user-attachments/assets/37b1b08e-3beb-486f-8fd5-10d7dd55420c" />

Divide the dataset into k groups (clusters), usually by optimizing some criterion (e.g., minimizing intra-cluster distance).

* k-Means
* k-Medoids (PAM, CLARA)

## Hierarchical

<img width="146" height="124" alt="hierarchical" src="https://github.com/user-attachments/assets/8d5b0945-694a-467a-8dde-12648ebe3baa" />

Create a tree-like structure (dendrogram) of clusters either by agglomeration (bottom-up) or division (top-down).

* Agglomerative Hierarchical Clustering
* Divisive Hierarchical Clustering

## Density-Based

density_based

<img width="301" height="135" alt="density_based" src="https://github.com/user-attachments/assets/b7b9f45d-ee55-41be-9c8a-479ab5434472" />

Identify clusters as dense regions of points separated by sparse areas (good for arbitrary shapes and noise).

* DBSCAN
* OPTICS
* HDBSCAN

## Grid-Based

<img width="123" height="116" alt="grid_based" src="https://github.com/user-attachments/assets/d365d3e1-c55d-4ac8-a895-04804d6a7568" />

Divide the data space into a finite number of grid cells, then group dense cells together.

* STING (Statistical Information Grid)
* CLIQUE

## Model-Based

<img width="251" height="186" alt="model_based" src="https://github.com/user-attachments/assets/52194ea2-20bf-46e3-a8ce-f4f0386055b0" />

Assume the data is generated from a mixture of underlying probability distributions, then fit a model to estimate cluster structure.

* Gaussian Mixture Models (GMM)
* Expectation-Maximization (EM) clustering

## Constraint-Based / Semi-Supervised Clustering

Incorporate prior knowledge (constraints or labels) into clustering.

COP-KMeans (Constrained k-Means)
Semi-supervised clustering with pairwise constraints
