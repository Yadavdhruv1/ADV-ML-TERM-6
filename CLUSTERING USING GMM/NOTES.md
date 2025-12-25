# Lecture 5: Gaussian Mixture Models (GMM) and Soft Clustering  
**Course:** Advanced Machine Learning  

---

## 1. Introduction to Clustering

Clustering is an **unsupervised learning** technique where we group data points such that:
- Points in the **same group (cluster)** are similar to each other
- Points in **different clusters** are dissimilar

Clustering is useful when:
- We do not have labels
- We want to discover hidden patterns in data

Examples:
- Grouping customers based on buying behavior  
- Segmenting images based on color intensity  
- Grouping students based on performance trends  

---

## 2. Types of Clustering

### 2.1 Hard Clustering

In **hard clustering**, each data point belongs to **exactly one cluster**.

Example:
- In **K-Means**, a data point is assigned to the nearest centroid
- There is **no uncertainty** in assignment

Once assigned, the point fully belongs to that cluster.

---

### 2.2 Soft Clustering

In **soft clustering**, a data point can belong to **multiple clusters with certain probabilities**.

Example:
- A student may belong **70%** to “average” group and **30%** to “good” group
- This reflects real-world ambiguity

**Gaussian Mixture Models (GMM)** perform **soft clustering**.

---

## 3. Limitations of K-Means Clustering

Although K-Means is simple and fast, it has several limitations:

### 3.1 Assumes Spherical Clusters
- K-Means works well only when clusters are round (globular)
- It fails when clusters are **elliptical or tilted**

### 3.2 Hard Assignment
- Each point is forced into one cluster
- No probability or uncertainty is captured

### 3.3 Similar Cluster Sizes
- K-Means tends to create clusters of similar size
- Not suitable when real clusters have different densities

Because of these limitations, we need a more flexible approach.

---

## 4. Gaussian Mixture Models (GMM)

### 4.1 What is a GMM?

A **Gaussian Mixture Model** assumes that:
- Data is generated from a mixture of **multiple Gaussian distributions**
- Each cluster corresponds to **one Gaussian**

Instead of assigning a point to one cluster, GMM assigns:
- A **probability** that the point belongs to each cluster

---

## 5. Why Use GMM Instead of K-Means?

| K-Means | GMM |
|------|------|
| Hard clustering | Soft clustering |
| Distance-based | Probability-based |
| Spherical clusters | Elliptical clusters |
| No uncertainty | Models uncertainty |

GMM is preferred when:
- Clusters overlap
- Data is not clearly separable
- Shape of clusters is not circular

---

## 6. Gaussian Distribution (Quick Revision)

A **Gaussian (Normal) Distribution** is defined by:

- **Mean (μ)** → Center of the distribution  
- **Standard Deviation (σ)** → Spread of the data  

In 1D:
- Bell-shaped curve

In 2D:
- Becomes an **ellipse**

---

## 7. Parameters in Gaussian Mixture Model

Each Gaussian in GMM has the following parameters:

### 7.1 Mean (μ)
- Represents the center of the cluster
- Shifting μ moves the cluster position

### 7.2 Variance / Standard Deviation (σ)
- Controls how spread out the data is
- Larger σ → wider cluster

### 7.3 Covariance (Σ)
- Controls:
  - Shape of the cluster
  - Orientation of the ellipse
- Allows modeling tilted and stretched clusters

This is the main reason GMM can model complex data.

---

## 8. Real-World Example (Intuition)

Consider **hair length data** in dermatology:
- Some people have medium-long hair
- Some clusters overlap

K-Means:
- Forces a strict boundary

GMM:
- Assigns probabilities
- Better represents reality

---

## 9. Steps in Gaussian Mixture Model (EM Algorithm)

GMM is trained using the **Expectation–Maximization (EM)** algorithm.

---

### Step 1: Initialization
- Choose number of Gaussians (k)
- Initialize mean, covariance, and weights randomly

---

### Step 2: Expectation Step (E-Step)
- Compute probability that each data point belongs to each Gaussian
- These probabilities are called **responsibilities**

---

### Step 3: Maximization Step (M-Step)
- Update parameters (μ, Σ) using the computed probabilities
- Maximize the likelihood of the data

---

### Step 4: Convergence
- Repeat E-Step and M-Step
- Stop when parameters stop changing significantly

---

## 10. Comparison: K-Means vs GMM (Exam Important)

| Feature | K-Means | GMM |
|------|------|------|
| Type | Hard clustering | Soft clustering |
| Shape | Circular | Elliptical |
| Assignment | Distance-based | Probability-based |
| Overlapping clusters | Poor | Excellent |

---

## 11. Key Takeaways

- GMM is a **probabilistic clustering** technique
- It overcomes major limitations of K-Means
- Uses **Gaussian distributions** to model clusters
- Works well for **overlapping and non-spherical data**
- EM algorithm is the backbone of GMM

---

## 12. Summary

Gaussian Mixture Models provide a more realistic and flexible approach to clustering.  
By assigning probabilities instead of strict labels, GMM captures uncertainty and handles complex real-world data much better than K-Means.

This makes GMM especially useful in:
- Medical data
- Customer segmentation
- Image and signal processing
