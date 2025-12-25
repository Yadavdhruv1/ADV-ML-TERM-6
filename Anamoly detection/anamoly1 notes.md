# Lecture 7: Clustering and Anomaly Detection

## 1. Overview of the Lecture

In this lecture, we studied clustering and anomaly detection together.  
The main idea was to understand how clustering algorithms help us identify normal patterns in data, and how points that do not follow these patterns can be treated as anomalies or outliers.

We revised earlier clustering methods and then focused on DBSCAN and different anomaly detection techniques.

---

## 2. What is Clustering?

Clustering is the process of grouping data points such that:
- Data points inside the same cluster are similar to each other
- Data points from different clusters are dissimilar

Clustering is an unsupervised learning task, meaning no output labels are given beforehand.

---

## 3. Clustering Algorithms Discussed

### 3.1 DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

DBSCAN forms clusters based on the density of data points instead of distance from a center.

#### Important Parameters

**EPS (Epsilon)**  
This defines the maximum distance within which two points are considered neighbors.

**Minimum Samples (MinPts)**  
This is the minimum number of points required inside the EPS radius to form a dense region.

---

#### Advantages of DBSCAN

- Automatically detects noise and outliers
- Can find clusters of any shape
- No need to specify number of clusters beforehand

---

#### Limitations of DBSCAN

- Very sensitive to the choice of EPS and MinPts
- Does not work well in high-dimensional datasets

---

### 3.2 K-Means Clustering

- Requires specifying the number of clusters (n_clusters)
- Uses hard clustering
- Each point belongs to exactly one cluster
- Sensitive to initialization
- Poor at handling noise and outliers

---

### 3.3 Gaussian Mixture Models (GMM)

- Uses n_components instead of n_clusters
- Performs soft clustering
- Assigns probabilities of belonging to clusters
- Can handle overlapping clusters
- Still sensitive to noise

---

## 4. Hyperparameter Tuning in Clustering

Hyperparameter tuning is especially important for DBSCAN.

- Changing EPS changes cluster compactness
- Changing MinPts affects how much noise is detected

Incorrect tuning may:
- Merge different clusters
- Split one cluster into many
- Mark many points as noise

---

## 5. What is Anomaly Detection?

Anomaly detection is the process of identifying data points that significantly deviate from normal patterns in data.

Such points are also called outliers.

---

## 6. Anomaly vs Novelty (Important Exam Concept)

**Anomaly**
- Abnormal or incorrect data
- Usually undesirable
- Example: Fraudulent transaction

**Novelty**
- Rare but meaningful data
- Represents new behavior
- Example: New customer trend

---

## 7. Statistical Anomaly Detection Methods

### 7.1 IQR (Interquartile Range) Method

Uses quartiles to detect outliers.

- Q1 = 25th percentile
- Q3 = 75th percentile
- IQR = Q3 − Q1

A point is an outlier if:
value < Q1 − 1.5 × IQR  
or  
value > Q3 + 1.5 × IQR

Best suited for univariate data.

---

### 7.2 Z-Score Method

Measures how far a data point is from the mean.

Formula:
Z = (x − μ) / σ

If |Z| > 2 or 3, the point is considered an anomaly.

Limitations:
- Assumes normal distribution
- Sensitive to extreme values

---

## 8. Machine Learning Based Anomaly Detection

### 8.1 Isolation Forest

Core idea:
Anomalies are easier to isolate than normal points.

- Uses random splits
- Fewer splits required → more likely anomaly

Advantages:
- Works well in high dimensions
- Scalable and efficient

---

### 8.2 Local Outlier Factor (LOF)

- Measures local density of a point
- Compares density with neighbors
- Lower density → possible anomaly

Mentioned as a future topic.

---

## 9. Case Study: Make Moons Dataset

The make_moons dataset is:
- Non-linear
- Non-spherical

Observations:
- K-Means fails due to spherical assumption
- GMM partially works
- DBSCAN performs best by detecting clusters and noise automatically

---

## 10. Practical Implementation Notes

Common tools used:
- Python
- NumPy
- Matplotlib
- Scikit-learn

Typical workflow:
1. Load data
2. Visualize
3. Apply algorithm
4. Tune parameters
5. Analyze results

---

## 11. Key Exam Takeaways

- DBSCAN handles noise and irregular clusters
- K-Means performs hard clustering
- GMM performs soft clustering
- IQR and Z-score are statistical methods
- Isolation Forest is effective for complex anomaly detection
- Always distinguish anomaly vs novelty

---

## 12. Conclusion

This lecture showed how clustering and anomaly detection work together to analyze real-world data. Understanding these techniques is crucial for fraud detection, monitoring systems, and data preprocessing.
