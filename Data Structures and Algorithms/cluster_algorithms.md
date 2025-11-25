# Clustering Algorithms

Clustering is a fundamental technique in **unsupervised machine learning** and data mining. The goal is to group a set of objects in such a way that objects in the same group (called a **cluster**) are more similar to each other than to those in other groups. Unlike supervised learning, clustering works with unlabeled data, making it a powerful tool for discovering hidden patterns and structures.

This guide explores the main families of clustering algorithms, their underlying principles, advantages, disadvantages, common use cases, and practical implementations in Python.

## 1. Partitioning Clustering

<img width="167" height="122" alt="partitioning" src="https://github.com/user-attachments/assets/37b1b08e-3beb-486f-8fd5-10d7dd55420c" />

Partitioning algorithms divide the dataset into a pre-determined number of non-overlapping groups (clusters). The core idea is to iteratively optimize a criterion, typically by minimizing the distance between data points and the center of their assigned cluster.

### How It Works
These methods start with an initial, often random, partitioning and refine it through an iterative process until the cluster assignments stabilize. The most common objective is to minimize the **Sum of Squared Errors (SSE)**, which represents the total intra-cluster variance.

### Key Algorithms
*   **k-Means:** The most famous and widely used clustering algorithm. It aims to partition `n` observations into `k` clusters in which each observation belongs to the cluster with the nearest mean (cluster center or **centroid**).
*   **k-Medoids (PAM, CLARA):** Similar to k-Means, but it uses actual data points (**medoids**) as cluster centers instead of calculated centroids. This makes it more robust to outliers and noise, as a medoid must be a representative, existing point in the cluster.

### Pros and Cons
| Pros | Cons |
| :--- | :--- |
| Fast and computationally efficient, especially for large datasets (k-Means). | Requires the number of clusters, `k`, to be specified beforehand. |
| Simple to understand and implement. | Sensitive to the initial placement of centroids/medoids. |
| Tends to produce tight, spherical clusters. | Struggles with clusters of non-spherical shapes or varying sizes and densities. |
| K-Medoids is robust to outliers. | K-Means is highly sensitive to outliers, which can skew the centroids. |

### Use Cases
*   **Customer Segmentation:** Grouping customers based on purchasing behavior, demographics, or website engagement to create targeted marketing campaigns.
*   **Document Clustering:** Organizing a collection of documents (e.g., news articles, scientific papers) into topics.
*   **Image Compression:** Reducing the number of colors in an image to the `k` most common ones.

### k-Means in Python
Here's how to implement k-Means using `scikit-learn`.

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
from sklearn.datasets import make_blobs

# Generate sample data with 4 distinct clusters
X, y_true = make_blobs(n_samples=300, centers=4, cluster_std=0.70, random_state=0)

# Initialize and fit the k-Means model
kmeans = KMeans(n_clusters=4, random_state=0, n_init=10) # n_init is important for stability
kmeans.fit(X)

# Get the cluster assignments and centroids
y_kmeans = kmeans.predict(X)
centroids = kmeans.cluster_centers_

# Visualize the results
plt.figure(figsize=(8, 6))
plt.scatter(X[:, 0], X[:, 1], c=y_kmeans, s=50, cmap='viridis')
plt.scatter(centroids[:, 0], centroids[:, 1], c='red', s=200, alpha=0.75, marker='X')
plt.title('K-Means Clustering')
plt.xlabel('Feature 1')
plt.ylabel('Feature 2')
plt.show()
```

## 2. Hierarchical Clustering

<img width="146" height="124" alt="hierarchical" src="https://github.com/user-attachments/assets/8d5b0945-694a-467a-8dde-12648ebe3baa" />

Hierarchical clustering creates a tree-like structure of clusters, known as a **dendrogram**. This approach does not require the number of clusters to be specified in advance.

### How It Works
*   **Agglomerative (Bottom-Up):** Starts with each data point as its own cluster. In each step, it merges the two closest clusters until only one cluster remains.
*   **Divisive (Top-Down):** Starts with all data points in a single cluster. In each step, it splits a cluster into two until each data point is its own cluster.

The decision of which clusters to merge or split is determined by a **linkage criterion** (e.g., Ward, Complete, Average, Single), which measures the distance between clusters.

### Pros and Cons
| Pros | Cons |
| :--- | :--- |
| Does not require specifying the number of clusters. | Computationally expensive, typically O(n³) for agglomerative methods. |
| The resulting dendrogram is insightful and allows for visualization of the data's structure. | Once a merge or split is done, it cannot be undone (greedy approach). |
| Can work with any distance metric. | Can be difficult to interpret the dendrogram for large datasets. |

### Use Cases
*   **Biological Sciences:** Creating taxonomies of species (phylogenetic trees) based on genetic or physical similarities.
*   **Social Network Analysis:** Identifying communities and hierarchies within a social network.
*   **Organizational Charts:** Automatically generating potential hierarchical structures for a company based on employee interactions.

### Agglomerative Clustering in Python

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import AgglomerativeClustering
from sklearn.datasets import make_blobs
from scipy.cluster.hierarchy import dendrogram, linkage

# Generate sample data
X, y_true = make_blobs(n_samples=50, centers=3, cluster_std=1.0, random_state=42)

# Perform hierarchical clustering to generate the linkage matrix
linked = linkage(X, method='ward')

# Plot the dendrogram
plt.figure(figsize=(10, 7))
dendrogram(linked,
            orientation='top',
            labels=np.arange(1, 51),
            distance_sort='descending',
            show_leaf_counts=True)
plt.title('Hierarchical Clustering Dendrogram')
plt.xlabel('Data Point Index')
plt.ylabel('Distance (Ward)')
plt.show()

# To get cluster labels for a specific number of clusters (e.g., 3)
cluster = AgglomerativeClustering(n_clusters=3, affinity='euclidean', linkage='ward')
labels = cluster.fit_predict(X)
print(\"Cluster labels:\", labels)
```

## 3. Density-Based Clustering

<img width="301" height="135" alt="density_based" src="https://github.com/user-attachments/assets/b7b9f45d-ee55-41be-9c8a-479ab5434472" />

Density-based algorithms define clusters as dense regions of data points separated by sparser regions. This approach is excellent for finding clusters of arbitrary shapes and identifying noise.

### How It Works
The core idea is to grow clusters by connecting points that are closely packed together. A point is a **core point** if it has a minimum number of other points (`MinPts`) within a given radius (`epsilon` or `eps`). Clusters are formed by connecting core points and any points that are reachable from them (**border points**). Points that are not part of any cluster are labeled as **noise**.

### Key Algorithms
*   **DBSCAN (Density-Based Spatial Clustering of Applications with Noise):** The foundational density-based algorithm. It's effective but can struggle with clusters of varying densities.
*   **OPTICS (Ordering Points To Identify the Clustering Structure):** An extension of DBSCAN that addresses the varying density problem by creating a reachability plot, effectively producing a density-based clustering structure for a range of `epsilon` values.
*   **HDBSCAN:** A more recent evolution that is robust, requires minimal parameter tuning, and can find clusters of varying densities automatically.

### Pros and Cons
| Pros | Cons |
| :--- | :--- |
| Does not require specifying the number of clusters. | Performance can degrade in high-dimensional spaces (curse of dimensionality). |
| Can find arbitrarily shaped clusters (e.g., non-spherical). | Sensitive to the `eps` and `MinPts` parameters (DBSCAN). |
| Robust to outliers, which are identified as noise. | Cannot handle clusters of varying densities well (DBSCAN). |

### Use Cases
*   **Geospatial Data Analysis:** Identifying areas of interest or hotspots on a map, like crime clusters in a city or the habitat of a species.
*   **Anomaly Detection:** Finding fraudulent transactions in a financial dataset, which often appear as noise points far from dense clusters of legitimate transactions.
*   **Bioinformatics:** Clustering protein structures that share a common dense core.

### DBSCAN in Python

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import DBSCAN
from sklearn.datasets import make_moons

# Generate non-spherical sample data
X, y = make_moons(n_samples=200, noise=0.05, random_state=0)

# Initialize and fit the DBSCAN model
# eps: The maximum distance between two samples for one to be considered as in the neighborhood of the other.
# min_samples: The number of samples in a neighborhood for a point to be considered as a core point.
dbscan = DBSCAN(eps=0.3, min_samples=5)
y_dbscan = dbscan.fit_predict(X) # -1 indicates noise

# Visualize the results
plt.figure(figsize=(8, 6))
plt.scatter(X[:, 0], X[:, 1], c=y_dbscan, s=50, cmap='plasma')
plt.title('DBSCAN Clustering')
plt.xlabel('Feature 1')
plt.ylabel('Feature 2')
plt.show()
```

## 4. Grid-Based Clustering

<img width="123" height="116" alt="grid_based" src="https://github.com/user-attachments/assets/d365d3e1-c55d-4ac8-a895-04804d6a7568" />

Grid-based methods quantize the data space into a finite number of cells that form a grid. All clustering operations are then performed on this grid structure, rather than on the individual data points.

### How It Works
The algorithm first divides the feature space into a grid. It then calculates the density of each grid cell. Finally, adjacent, high-density cells are grouped together to form clusters.

### Key Algorithms
*   **STING (Statistical Information Grid):** Uses a hierarchical grid structure to store statistical information (mean, standard deviation, count) about the points in each cell. Queries are answered using this pre-computed information.
*   **CLIQUE (Clustering in Quest):** A density- and grid-based algorithm that automatically finds subspaces with high-density clusters in high-dimensional data.

### Pros and Cons
| Pros | Cons |
| :--- | :--- |
| Very fast processing time, as it depends on the number of grid cells, not the number of data points. | The quality of clustering depends heavily on the grid resolution. |
| Highly scalable for massive datasets. | Can lose information due to quantization. |
| Works well for identifying clusters in spatial data. | Struggles with high-dimensional data due to the exponential growth of grid cells. |

### Use Cases
*   **Large-scale Image Analysis:** Grouping pixels in very large satellite or medical images.
*   **Spatial Data Mining:** Analyzing massive geographic datasets to find regions with similar characteristics.

## 5. Model-Based Clustering

<img width="251" height="186" alt="model_based" src="https://github.com/user-attachments/assets/52194ea2-20bf-46e3-a8ce-f4f0386055b0" />

Model-based algorithms assume that the data is generated from a mixture of underlying probability distributions. The goal is to find the best-fit model for the data and use that model to define the clusters.

### How It Works
The most common approach is the **Gaussian Mixture Model (GMM)**. GMM assumes that the data points are generated from a mixture of a finite number of Gaussian distributions with unknown parameters. The algorithm uses the **Expectation-Maximization (EM)** technique to iteratively estimate the parameters of these distributions (mean, covariance) and the probability that each data point belongs to each distribution. This results in a \"soft\" clustering, where each point has a probability of belonging to each cluster.

### Pros and Cons
| Pros | Cons |
| :--- | :--- |
| Provides a \"soft\" clustering, giving probabilities of cluster membership. | Requires the number of clusters (distributions) to be specified. |
| Can model complex, ellipsoidal cluster shapes. | Can be computationally expensive, as EM is iterative. |
| Based on a solid statistical foundation. | Assumes the data follows the specified distribution (e.g., Gaussian). |

### Use Cases
*   **Image Segmentation:** Separating a foreground object from the background in an image, where each region is modeled by a different distribution.
*   **Speaker Diarization:** Identifying \"who spoke when\" in an audio recording by modeling each speaker's voice as a distinct Gaussian mixture.
*   **Financial Modeling:** Clustering stocks based on their return and volatility patterns.

### Gaussian Mixture Models (GMM) in Python

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.mixture import GaussianMixture
from sklearn.datasets import make_blobs

# Generate anisotropic (elliptical) data
X, y_true = make_blobs(n_samples=400, centers=4, cluster_std=0.60, random_state=0)
X_stretched = np.dot(X, np.random.RandomState(0).randn(2, 2)) # Create elliptical shapes

# Initialize and fit the GMM model
gmm = GaussianMixture(n_components=4, random_state=0)
gmm.fit(X_stretched)
y_gmm = gmm.predict(X_stretched)

# Visualize the results
plt.figure(figsize=(8, 6))
plt.scatter(X_stretched[:, 0], X_stretched[:, 1], c=y_gmm, s=40, cmap='viridis', zorder=2)
plt.title('Gaussian Mixture Model Clustering')
plt.xlabel('Feature 1')
plt.ylabel('Feature 2')
plt.show()
```

## 6. Constraint-Based / Semi-Supervised Clustering

This family of algorithms incorporates prior domain knowledge into the clustering process. This knowledge is provided as constraints, such as pairs of points that **must-link** (belong to the same cluster) or **cannot-link** (belong to different clusters).

### How It Works
Standard clustering algorithms are modified to satisfy these constraints. For example, **COP-KMeans** is a modification of k-Means where the cluster assignment step is constrained: a point can only be assigned to a cluster if the assignment does not violate any \"cannot-link\" constraints with points already in that cluster. Similarly, it tries to keep \"must-link\" points together.

### Pros and Cons
| Pros | Cons |
| :--- | :--- |
| Can significantly improve clustering accuracy by leveraging expert knowledge. | Requires a source of prior knowledge, which may not always be available. |
| Guides the algorithm towards a more meaningful and relevant solution. | The quality of results depends heavily on the quality of the constraints. |

### Use Cases
*   **Image Database Organization:** A user provides feedback by marking some images as being of the same object (\"must-link\") to improve automatic grouping.
*   **Genomic Clustering:** Incorporating known biological pathways as constraints to guide the clustering of gene expression data.

COP-KMeans (Constrained k-Means)
Semi-supervised clustering with pairwise constraints
