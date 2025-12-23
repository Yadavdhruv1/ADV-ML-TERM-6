# Principal Component Analysis (PCA) – Lecture 1  
**Course:** Advanced Machine Learning  

---

## 1. Introduction to PCA

Principal Component Analysis (PCA) is a dimensionality reduction technique used to reduce the number of features while preserving maximum variance in the data.

---

## 2. Why Dimensionality Reduction is Needed

- High-dimensional data increases computational cost
- Leads to overfitting
- Makes visualization difficult
- Introduces noise and redundancy

### Real-world Analogy
A group photo taken from far away captures essential information while removing unnecessary details.

---

## 3. Principal Components

- Principal components are linear combinations of original features
- They capture maximum variance
- Components are ordered by importance

Mathematically:
PC₁ = a₁X₁ + a₂X₂ + ... + aₙXₙ

---

## 4. Orthogonality of Principal Components

- Principal components are orthogonal (uncorrelated)
- Ensures each component captures unique information

---

## 5. Variance and Eigenvalues

- PCA maximizes variance
- Eigenvectors represent directions
- Eigenvalues represent magnitude of variance

Higher eigenvalue ⇒ more important component

---

## 6. Explained Variance Ratio

Explained Variance Ratio helps determine how many components to retain.

Typically, 90–95% variance is preserved.

---

## 7. PCA Workflow

1. Standardize the data
2. Compute covariance matrix
3. Compute eigenvalues and eigenvectors
4. Sort components by eigenvalues
5. Select top k components
6. Project data onto new feature space

---

## 8. Advantages of PCA

- Reduces overfitting
- Improves computational efficiency
- Helps visualization

---

## 9. Disadvantages of PCA

- Loss of interpretability
- Linear technique
- Sensitive to scaling

---

## 10. Applications of PCA

- Image compression
- Noise reduction
- Feature extraction
- Data visualization
