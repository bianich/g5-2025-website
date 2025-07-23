---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: "Data Analysis"
header_title: "Clustering"
vega: true

header_type: hero #base, post, hero,image, splash
---

# Clustering Analysis Report

The dataset contains structured information on items listed for sale, with attributes ranging from geographical coordinates (`lat`, `long`), pricing dynamics (`initial_price`, `price_change`, `total_fees`), interaction features (`likes`, `reviews_count`), to categorical descriptors (`size_macro`, `item_condition`, `business` flag).
- **Removed label (brand)**:
Due to high cardinality and sparsity, the `label` (brand) column was dropped to improve clustering quality.
- **Clustering target isolation**:
The column `sold` were excluded from the clustering input to avoid target leakage. They were retained for post-hoc evaluation.
- **Normalization**:
- `StandardScaler` was applied for **KMeans** and **Hierarchical** clustering.
---
 
### Hierarchical Clustering
A random sample of **100,000 samples** was selected to compute the pairwise distance matrix. Three linkage methods were tested: `single`, `complete`, and `ward`.

![ Dendrogram Comparison](assets/images/image-analysis/ 3_dendograms.png)
 

![Dendrogram Comparison](assets/images/clustering/3_dendograms.png)
- **Single Linkage**: suffers from the chaining effect, resulting in poorly separated, elongated clusters.
- **Complete Linkage**: promotes compact clusters but can be biased toward spherical shapes.
- **Ward Linkage**: minimizes intra-cluster variance, yielding well-balanced and interpretable clusters.
**Ward linkage** was selected for further analysis due to its superior structure and alignment with our interpretability goals.
---
### Optimal Cluster Selection (Ward Method)
To determine the ideal number of clusters, we tested multiple cut-off distances (`t`) on the Ward dendrogram and calculated the **Davies-Bouldin (DB) score** for each:
![DB vs cut-off](assets/images/clustering/Cluster_Gerarchico_scelta_taglio.png)
- The **lowest DB score** (~0.78) was observed at **t = 250**, which corresponds to **13 clusters**.
- This value balances compactness (low intra-cluster variance) and separation.
---
### Cluster Visualization using t-SNE
To validate the cluster structure in a 2D space, we performed **t-SNE dimensionality reduction** on the same sample used in hierarchical clustering:
![t-SNE ](assets/images/clustering/TSNEGerarchico.png)

- Most clusters are **visually distinct**, confirming the effectiveness of Ward linkage.
- Minor overlaps suggest soft boundaries between some behavioral groups, which is expected in real-world data.
---
### Cluster-Level Behavior Analysis
The `sold` rates were then aggregated by cluster to understand how sale probability varies across groups:
![Sell Rate per Cluster](assets/images/clustering/labels_sold_ger.png)
- The **global sell rate** is **58.34%** (red dashed line).
- Several clusters (e.g., **Clusters 5, 10, 11**) perform significantly **above average**, suggesting these segments represent highly sellable items.
- Clusters **4 and 7** have lower conversion rates and may represent cold inventory.
---
##  KMeans Clustering: Evaluation & Select
The **Davies-Bouldin Index (DBI)** combined to elbow method was used to evaluate clustering compactness and separation. The index was computed for different values of K from 2 to 19. Lower values are better.
![Davies-Bouldin evaluation](assets/images/clustering/Boldrini_Kmeans.png)

- **Observation**: The curve stabilizes and shows a local minimum around **K = 10**.
- **Decision**: We selected **K = 10** as the optimal number of clusters for further analysis.
---
##  Cluster Visualization: t-SNE Projection
To visually assess the KMeans clustering, **t-SNE** was applied to a random sample (100,000 records) from the dataset and the 2D embedding was colored by cluster membership.
![t-SNE] (assets/images/image-analysis/t-SNE_Kmeans.png)
- **Interpretation**:
- Clusters show good spatial separation in 2D.
- Minor overlaps exist, but structure is preserved.
- This confirms that the 10 clusters learned by KMeans capture meaningful patterns in the data.
---
##  Cluster-Level Business Insight: Sell Rate Analysis
Each cluster’s average `sold` rate was compared to the global average (≈ 58.15%).
![Sell Rate] (assets/images/image-analysis/clustering_num_sold_k10.png)
- **Key findings**:
- Clusters **4** and **7** show the **highest conversion rates**, approaching 70%.
- Cluster **0** performs significantly worse (≈ 37%), possibly pointing to poor listings or irrelevant products.
- These insights can guide **business strategy**, such as emulating successful cluster features for underperforming items.
## Method Comparison & Final Choice
| Method              | Clusters | DBI     | Silhouette |
|---------------------|----------|---------|------------|
| **KMeans**          | 10       | 0.832  | **0.4583** |
| Hierarchical (Ward) | 13       | **0.78**| 0.4089     |
- While Ward had a slightly better DBI, the **Silhouette Score for KMeans was higher** and with fewer clusters (10 vs 13).
- Visual inspection via t-SNE showed better-defined and more compact clusters for KMeans.
- **KMeans** was therefore chosen for downstream analysis due to its interpretability, compactness, and better silhouette performance.
### Cluster-Level Descriptions – KMeans
![Combined cluster grid](assets/images/clustering/combined_cluster_grid_image.jpg)
The following table summarizes each of the 10 KMeans clusters based on dominant item characteristics and behavioral traits:
| Cluster | Description                                                                                                                                                                                                     |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0       | This cluster mainly consists of items in "Very good" condition and is predominantly adult-sized. The items in this group are rarely sold. They are sold by users with fewer reviews and lower reputation.        |
| 1       | This cluster mainly consists of items in "Good" condition and is predominantly adult-sized. The items in this group are frequently sold.                                                                         |
| 2       | This cluster mainly consists of items in "Very good" condition and is predominantly adult-sized. The items in this group are frequently sold.                                                                   |
| 3       | This cluster mainly consists of items in "Very good" condition and is predominantly unknown-sized. The items in this group are frequently sold. They tend to have a higher initial price.                        |
| **4**   | **This cluster mainly consists of items in "New with tags" condition and is predominantly adult-sized. The items in this group are frequently sold. They tend to have a higher initial price**.                  |
| 5       | This cluster mainly consists of items in "New without tags" condition and is predominantly adult-sized. The items in this group are frequently sold.                                                            |
| 6       | This cluster mainly consists of items in "Very good" condition and is predominantly child-sized. The items in this group are frequently sold. They tend to be cheaper than average.                              |
| **7**   | **This cluster mainly consists of items in "New with tags" condition and is predominantly adult-sized. The items in this group are frequently sold. They are sold by users with more reviews**.                 |
| 8       | This cluster mainly consists of items in "Satisfactory" condition and is predominantly adult-sized. The items in this group are rarely sold. They receive fewer likes than average.                             |
| 9       | This cluster mainly consists of items in "Very good" condition and is predominantly adult-sized. The items in this group are rarely sold. They tend to have a higher initial price and fewer likes than average. |