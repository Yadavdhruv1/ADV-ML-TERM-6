# Lecture 4: K-Means Clustering and Optimization
**Course:** Advanced Machine Learning  

---

## 1. Introduction

In this lecture, we studied **K-Means clustering**, one of the most important algorithms in **unsupervised machine learning**.

We focused on:
- How K-Means works
- How to choose the **optimal number of clusters (K)**
- Problems with K-Means
- Methods to improve K-Means results

---

## 2. What is Clustering?

Clustering is an **unsupervised learning task** where:
- The data has **no labels**
- The goal is to group similar data points together

Each group is called a **cluster**.

---

## 3. What is K-Means Clustering?

K-Means is an algorithm that:
- Divides data into **K distinct clusters**
- Each data point belongs to **exactly one cluster**
- Each cluster is represented by a **centroid (mean of points)**

The objective of K-Means is to:
> Minimize the distance between data points and their cluster centroids.

---

## 4. How K-Means Works (Step-by-Step)

### Step 1: Initialization
- Choose the number of clusters **K**
- Randomly select **K initial centroids**

---

### Step 2: Assignment Step
- For each data point:
  - Compute distance to each centroid
  - Assign the point to the **nearest centroid**
- Distance used: **Euclidean distance**

---

### Step 3: Update Step
- Recalculate centroids
- New centroid = **mean of all points assigned to that cluster**

---

### Step 4: Iteration
- Repeat Assignment and Update steps
- Stop when:
  - Centroids stop changing, or
  - Maximum number of iterations is reached

This process is called **convergence**.

---

## 5. Objective Function of K-Means

K-Means tries to minimize:

**Within-Cluster Sum of Squares (WCSS)**

WCSS is:
- Sum of squared distances between each point and its cluster centroid

Lower WCSS → tighter and better clusters

---

## 6. Choosing the Optimal Number of Clusters (K)

Choosing the right value of K is **very important**.
If K is wrong:
- Clusters may be meaningless
- Model performance suffers

---

## 7. Elbow Method

### Idea
- Increase K and observe how WCSS changes
- Initially, WCSS drops sharply
- After a point, improvement slows down

That point is called the **elbow**.

---

### How Elbow Method Works
1. Run K-Means for different values of K
2. Plot:
   - X-axis → K
   - Y-axis → WCSS
3. Look for a bend (elbow) in the graph

---

### Limitation
- Elbow is sometimes **not very clear**
- Requires human judgment

---

## 8. Silhouette Score

### What is Silhouette Score?

Silhouette score measures:
> How well a data point fits within its cluster compared to other clusters.

---

### Score Range
- Range: **–1 to +1**
- +1 → very well clustered
- 0 → overlapping clusters
- –1 → wrongly assigned point

---

### Interpretation
- Higher average silhouette score → better clustering
- Useful when elbow method is unclear

---

## 9. Role of Domain Knowledge

Sometimes math alone is not enough.

Domain knowledge helps:
- Decide meaningful number of clusters
- Avoid unrealistic clustering
- Align clusters with real-world interpretation

---

## 10. Problems with K-Means

K-Means has several limitations:

- Sensitive to **initial centroid selection**
- Struggles with:
  - Non-spherical clusters
  - Different cluster sizes
  - Different cluster densities
- Affected by **outliers**
- Requires K to be specified beforehand

---

## 11. Random Initialization Problem

Because centroids are chosen randomly:
- Different runs can give different results
- Algorithm may converge to a **local minimum**
- Poor initialization → poor clustering

---

## 12. K-Means++ Initialization

K-Means++ improves centroid initialization.

### Idea
- Choose initial centroids **far apart from each other**
- Reduces chance of poor clustering

---

### Benefits
- Faster convergence
- Better cluster quality
- More stable results

---

## 13. Hierarchical Clustering with K-Means

Hierarchical clustering can be used:
- To estimate the number of clusters
- As a preprocessing step before K-Means

This combination improves clustering quality.

---

## 14. Simulation and Visual Intuition

In class, K-Means was simulated on:
- Gaussian-distributed data

Observations:
- Centroids move after each iteration
- Random initialization can fail
- Better initialization leads to better clusters

---

## 15. Important Exam Points

- K-Means is **unsupervised**
- Uses **Euclidean distance**
- Objective: minimize **WCSS**
- Elbow method uses WCSS vs K plot
- Silhouette score ∈ [–1, 1]
- K-Means++ improves initialization

---

## 16. Conclusion

- K-Means is a simple and powerful clustering algorithm
- Choosing the correct K is crucial
- Elbow method, Silhouette score, and domain knowledge should be used together
- K-Means++ significantly improves clustering performance

Understanding these concepts is essential for applying clustering in real-world machine learning problems.

---
