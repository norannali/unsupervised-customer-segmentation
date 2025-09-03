# Customer Segmentation using K-Means and DBSCAN

This repository explores **customer segmentation** using two clustering techniques:
- **K-Means** (centroid-based)
- **DBSCAN** (density-based)

The goal is to compare how these algorithms perform on the same dataset (Bank Marketing data), evaluate the quality of clusters using different metrics, and interpret customer segments for potential business insights.

---

## 🚀 Project Overview
- **K-Means**: Produces 2 large clusters, balanced but very similar (differences mainly in campaign and pdays).  
- **DBSCAN**: Produces 3 smaller, well-defined clusters + Noise (outliers), capturing unique customer groups such as:
  - **Cluster 1**: Young customers, low balance, high campaign → “Hard-to-convert customers”.
  - **Cluster 2**: Older, wealthy, married customers → “VIP customers”.
  - **Noise**: Outliers with very high balance / long calls.

---

## 📊 Evaluation Metrics
- **Silhouette Score** (excl. noise for DBSCAN)  
- **Davies-Bouldin Index**  
- **Calinski-Harabasz Index**  

| Algorithm | Silhouette | Davies-Bouldin ↓ | Calinski-Harabasz ↑ |
|-----------|------------|------------------|----------------------|
| K-Means   | ~0.3 (better, due to spherical assumption) | ~1.5 | ~120 |
| DBSCAN    | -0.46 (not ideal for non-spherical) | 1.13 | 3.40 |

> DBSCAN scores are lower on standard metrics, but visually and business-wise, it finds meaningful smaller clusters and isolates noise.

---

## 🛠️ Installation
```bash
git clone https://github.com/your-username/customer-segmentation-kmeans-dbscan.git
cd customer-segmentation-kmeans-dbscan
````

## 📈 Visualizations

* **K-Means**: PCA 2D scatter plot with centroids
* **DBSCAN**: PCA 2D scatter plot with noise (-1) shown in black
* **Cluster Profiles**: Summary statistics (numeric + categorical)

---

## 🔮 Insights

* **K-Means** is simple, produces balanced clusters but may miss niche customer groups.
* **DBSCAN** identifies meaningful smaller groups and isolates outliers → better for marketing segmentation when **noise detection** is important.

---

## 🤝 Contributing

Feel free to fork this repo, open issues, or submit PRs with improvements.

---

## 📜 License

This project is licensed under the MIT License.

