# Lecture: Matrix Factorization and Related Concepts

## 1. Introduction to Matrix Factorization

Matrix Factorization is a core concept in machine learning and data analysis.  
It means breaking a large and complex matrix into the product of smaller, simpler matrices.

This idea is extremely useful because:
- Large matrices are hard to analyze directly
- Smaller matrices reveal hidden patterns
- Computation becomes faster and more efficient

Matrix factorization is widely used in:
- Recommender Systems
- Image Processing
- Dimensionality Reduction
- Clustering Algorithms

---

## 2. Matrix Factorization: Big Picture

In general form:

A ≈ P × Q

Where:
- **A** is the original data matrix
- **P** and **Q** are smaller matrices
- The product of P and Q approximates A

The goal is **not exact reconstruction**, but a **good approximation** that captures essential information.

---

## 3. Singular Value Decomposition (SVD)

### 3.1 What is SVD?

Singular Value Decomposition (SVD) is one of the most famous matrix factorization techniques.

It decomposes a matrix as:

A = U × Σ × Vᵀ

Where:
- **U** → Represents how each data point uses the hidden patterns
- **Σ (Sigma)** → Diagonal matrix containing singular values (importance of each pattern)
- **Vᵀ** → Represents the actual hidden patterns

---

### 3.2 Intuition Behind SVD (Teacher Explanation)

Think of a song made using:
- Drums
- Guitar
- Flute

To our ears, it sounds like one song.  
But technically, it is a combination of different instruments.

SVD does the same:
- Separates complex data into basic underlying components
- Each component has a strength (Sigma)

---

### 3.3 Applications of SVD

- Image compression (remove less important components)
- Noise reduction
- Topic modeling in NLP
- Dimensionality reduction

---

## 4. K-Means Clustering and Matrix Factorization

### 4.1 K-Means Overview

K-Means is a clustering algorithm that:
- Divides data into **K clusters**
- Each point belongs to exactly **one cluster**

This is called **hard clustering**.

---

### 4.2 K-Means as Matrix Factorization

K-Means can be viewed as factorizing data into:
- A **cluster assignment matrix** (0 or 1 values)
- A **centroid matrix**

The objective is to minimize the distance between:
- Data points
- Their assigned cluster centroids

---

### 4.3 Constraint in K-Means

- Each row has exactly **one 1**
- All other values are **0**
- A data point cannot belong to multiple clusters

---

## 5. Gaussian Mixture Model (GMM)

### 5.1 GMM Overview

GMM is similar to K-Means but more flexible.

Key difference:
- GMM performs **soft clustering**

This means:
- A data point can belong to multiple clusters
- Each cluster assignment has a probability between 0 and 1

---

### 5.2 GMM and Matrix Factorization

Just like K-Means, GMM can be represented using matrix factorization:
- Instead of binary assignments
- Probabilistic values are used

This makes GMM more realistic for real-world data.

---

## 6. Principal Component Analysis (PCA)

### 6.1 PCA Overview

PCA is a dimensionality reduction technique based on matrix factorization.

It converts:
- High-dimensional data
- Into fewer uncorrelated components

These components are called **principal components**.

---

### 6.2 PCA and Matrix Factorization

PCA relies on:
- Eigenvectors → directions
- Eigenvalues → importance

Conceptually, PCA is closely related to SVD.

Purpose of PCA:
- Reduce noise
- Reduce computation
- Preserve maximum variance

---

## 7. Non-Negative Matrix Factorization (NMF)

### 7.1 What is NMF?

NMF is a matrix factorization method where:
- All values must be **non-negative**

This is useful when:
- Negative values have no real meaning

---

### 7.2 Why NMF is Useful

Examples:
- Image pixels (cannot be negative)
- Frequency counts
- Probabilities

NMF improves interpretability because:
- Components combine additively
- No cancellation using negative values

---

## 8. Matrix Factorization in Recommender Systems

### 8.1 Core Representation

In recommender systems:

A = P × Q

Where:
- **A** → User–Item interaction matrix
- **P** → User latent matrix
- **Q** → Item latent matrix
- **D** → Number of latent dimensions

---

### 8.2 Meaning of Latent Dimension (D)

Latent dimension represents hidden features such as:
- Movie genres
- User taste patterns

Important point:
- **D has no direct real-world meaning**
- It is a mathematical construct

---

## 9. Choosing the Latent Dimension (D)

### 9.1 Elbow Curve Method

- Plot loss vs D
- Choose point where improvement slows down
- Prevents overfitting

---

### 9.2 Train–Validation Split

- Train on 80% known ratings
- Validate on 20%
- Choose D that performs best on validation data

This is more reliable than elbow method.

---

## 10. Summary and Conclusion

Matrix factorization is a unifying concept behind:
- SVD
- PCA
- K-Means
- GMM
- Recommender Systems

Key takeaways:
- Simplifies complex data
- Reveals hidden patterns
- Handles sparsity efficiently
- Forms backbone of modern ML systems

For strong understanding:
- Practice coding implementations
- Experiment with different dimensions
- Observe trade-offs between accuracy and complexity
