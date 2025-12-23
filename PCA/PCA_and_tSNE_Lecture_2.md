# Dimensionality Reduction Techniques – PCA and t-SNE  
**Lecture 2**  
**Course:** Advanced Machine Learning  

---

## 1. Overview

In this lecture, we studied dimensionality reduction techniques with a focus on:

- Principal Component Analysis (PCA)
- t-distributed Stochastic Neighbor Embedding (t-SNE)

The objective was to understand how these techniques help visualize high-dimensional data efficiently while minimizing information loss.

---

## 2. Principal Component Analysis (PCA)

### 2.1 What is PCA?

Principal Component Analysis (PCA) is a linear dimensionality reduction technique that transforms data into a new coordinate system such that:

- The first principal component captures the maximum variance
- Each subsequent component captures the next highest variance
- All components are orthogonal (uncorrelated)

PCA focuses on capturing global variance patterns in the data.

---

### 2.2 Eigenvectors and Eigenvalues

- PCA computes eigenvectors and eigenvalues of the covariance matrix
- Eigenvectors define the directions of the new axes (principal components)
- Eigenvalues represent the amount of variance captured by each component

Higher eigenvalue implies a more important principal component.

---

### 2.3 Orthogonal Transformation

- PCA performs an orthogonal transformation
- Principal components are at right angles to each other
- This removes multicollinearity among features
- Ensures each component captures unique information

---

### 2.4 Limitations of PCA

Despite its usefulness, PCA has several limitations:

- **Information Loss:** Dimensionality reduction may discard useful variance  
- **Sensitivity to Outliers:** Outliers can distort principal components  
- **Interpretability:** Components are linear combinations of features  
- **Linearity Assumption:** PCA assumes linear relationships  

---

### 2.5 Standardization and PCA

Before applying PCA, data must be standardized:

- Mean = 0
- Standard deviation = 1

Without standardization:
- Features with larger scales dominate variance
- Explained variance becomes misleading

---

### 2.6 PCA Example (Conceptual)

In class, PCA was applied after standardizing the dataset.  
It was demonstrated that applying PCA on unscaled data leads to biased explained variance, highlighting the importance of preprocessing.

---

## 3. t-Distributed Stochastic Neighbor Embedding (t-SNE)

### 3.1 Introduction to t-SNE

t-SNE is a non-linear dimensionality reduction algorithm primarily used for:

- Data visualization
- Discovering clusters in high-dimensional data

Unlike PCA, t-SNE focuses on preserving local relationships.

---

### 3.2 Preserving Local Structure

- Points close in high-dimensional space remain close in low-dimensional space
- Emphasizes neighborhood preservation
- Global distances may be distorted

---

### 3.3 Probabilistic Nature of t-SNE

- Distances are converted into probability distributions
- t-SNE minimizes Kullback–Leibler (KL) divergence between:
  - High-dimensional similarities
  - Low-dimensional embeddings

This leads to clearer cluster separation.

---

### 3.4 Crowding Problem

- High-dimensional data cannot be perfectly represented in low dimensions
- Many points compete for limited space
- This results in the crowding problem

t-SNE mitigates this using heavy-tailed distributions.

---

### 3.5 Intuitive Analogy

An analogy used in class was a party scenario:

- Friends (similar points) stay close
- Strangers (dissimilar points) remain far apart

t-SNE replicates this behavior in reduced dimensions.

---

### 3.6 PCA vs t-SNE

| Aspect | PCA | t-SNE |
|------|-----|------|
| Type | Linear | Non-linear |
| Focus | Global variance | Local structure |
| Interpretability | Moderate | Low |
| Visualization | Limited | Excellent |
| Scalability | High | Computationally expensive |

---

### 3.7 Example with Code (Conceptual)

Using the digits dataset:
- PCA produced overlapping clusters
- t-SNE clearly separated digit classes

This demonstrated the effectiveness of t-SNE for visualization tasks.

---

## 4. Conclusion

- PCA is suitable for feature reduction and preprocessing
- t-SNE is ideal for visualization and cluster discovery
- Both techniques serve different purposes
- The choice depends on the problem being solved

---

## 5. Key Takeaways

- PCA preserves variance
- t-SNE preserves local neighborhoods
- Always standardize data before PCA
- Use t-SNE for visualization, not for model training
