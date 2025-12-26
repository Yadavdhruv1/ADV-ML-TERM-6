# Lecture 8: Visualization, Clustering, and Anomaly Detection – Consolidated Overview

## 1. Overview of the Lecture

In this lecture, we revised and connected multiple machine learning techniques that are commonly used in real-world data science projects.  
The focus was not only on algorithms but also on **when and why** to use them.

The topics covered included:
- Dimensionality reduction for visualization
- Clustering techniques for grouping data
- Anomaly detection for identifying unusual behavior
- Practical project-oriented thinking, especially for customer segmentation problems

---

## 2. Dimensionality Reduction Techniques

### 2.1 Principal Component Analysis (PCA)

PCA is a dimensionality reduction technique used to reduce the number of features while retaining as much information as possible.

Teacher’s intuition:  
If you have many features, PCA helps you summarize them into fewer meaningful directions.

Key points:
- PCA creates new features called **principal components**
- These components are **orthogonal** (independent of each other)
- Each component captures a certain amount of variance from the data

### Explained Variance Ratio

The explained variance ratio tells us how much information each principal component carries.

Example:
- PC1 → 33%
- PC2 → 26%
- PC3 → 23%
- PC4 → 16%

This helps decide how many components are enough.

Important note:
PCA is good for **feature reduction**, but not always reliable for visualization, especially when the data has non-linear patterns.

---

## 3. t-Distributed Stochastic Neighbor Embedding (t-SNE)

### 3.1 Purpose of t-SNE

t-SNE is mainly used for **data visualization**, not feature reduction.

Teacher’s intuition:  
t-SNE tries to keep similar points close together when projecting data from high dimensions to 2D.

Key characteristics:
- Preserves **local relationships**
- Very effective for visualizing clusters
- Computationally expensive for large datasets

---

### 3.2 Important Parameters in t-SNE

Perplexity:
- Controls how many neighbors are considered
- Low perplexity → focus on very local structure
- High perplexity → slightly more global view

Iterations:
- Number of optimization steps
- More iterations usually lead to better visualization

Comparison with PCA:
- PCA preserves variance
- t-SNE preserves neighborhood similarity
- For visualization, t-SNE usually performs better

---

## 4. Clustering Techniques

### 4.1 Objective of Clustering

Clustering groups data points based on similarity without using labels.

Common use case:
- Customer segmentation
- Grouping users based on behavior

---

### 4.2 K-Means Clustering

K-Means is a hard clustering algorithm.

Key ideas:
- You must choose the number of clusters (K)
- Each data point belongs to exactly one cluster

Elbow Method:
- Used to find optimal K
- Plot WCSS vs K
- The point where improvement slows down is the “elbow”

Limitation:
- Assumes spherical clusters
- Struggles with overlapping or irregular clusters

---

### 4.3 Gaussian Mixture Models (GMM)

GMM is a **soft clustering** technique.

Teacher’s intuition:  
Instead of forcing a point into one cluster, GMM assigns probabilities.

Key advantages:
- Handles overlapping clusters
- Can model elliptical shapes
- More flexible than K-Means

---

## 5. Anomaly Detection

### 5.1 Purpose of Anomaly Detection

Anomaly detection identifies unusual or rare data points.

Applications:
- Fraud detection
- System monitoring
- Identifying abnormal customer behavior

---

### 5.2 General Techniques Discussed

Key ideas:
- Mostly unsupervised
- Requires tuning parameters like contamination
- Often combined with clustering for better insights

Anomaly detection helps answer:
“Which points do not behave like the rest?”

---

## 6. Project-Oriented Learning

The instructor emphasized that:
- Algorithms alone are not enough
- Understanding the business problem is critical
- Parameter tuning and interpretation matter more than code

Example:
In customer segmentation:
- Clustering helps group customers
- Anomaly detection highlights unusual spenders
- Together, they help design better marketing strategies

---

## 7. Key Takeaways from the Lecture

- PCA reduces dimensions but may fail for visualization
- t-SNE is powerful for visual exploration
- K-Means is simple but rigid
- GMM provides flexibility using probabilities
- Anomaly detection identifies rare but important cases
- Business insight is the final goal of any ML project

---

## 8. What Comes Next

The next set of lectures will focus on:
- Recommender Systems
- Time Series Analysis
- More business-driven ML applications

These topics will expand ML usage from analysis to prediction.
