# Lecture 3: Dimensionality Reduction – PCA and t-SNE
**Course:** Advanced Machine Learning  

---

## 1. Introduction

In this lecture, we studied two main dimensionality reduction techniques:

- **Principal Component Analysis (PCA)**  
- **t-distributed Stochastic Neighbor Embedding (t-SNE)**

**Key difference:**  
- PCA → used for **preprocessing and model building**  
- t-SNE → used for **visualizing high-dimensional data**

---

## 2. Why Dimensionality Reduction?

High-dimensional datasets can cause:

- Increased computation time
- Overfitting
- Difficult visualization
- Redundant or correlated features

**Benefits of dimensionality reduction:**

- Removes unnecessary features
- Keeps important information
- Makes data easier to analyze and visualize

---

# PART A: PRINCIPAL COMPONENT ANALYSIS (PCA)

---

## 3. What is PCA?

PCA is a **linear dimensionality reduction technique** that:

- Projects data into a **new coordinate system**
- Orders axes by **variance captured**
- First axis → maximum variance, second → next, and so on

**Deterministic:** Running PCA on the same data always gives the same result.

---

## 4. Purpose of PCA

- Reduce the number of features
- Preserve maximum variance
- Remove correlations between features
- Improve model generalization

---

## 5. Principal Components

- New features formed as **linear combinations of original features**
- Each component represents **one independent direction**
- Components are ordered by variance

**Example:**

`PC1 = a1·X1 + a2·X2 + a3·X3`  
`PC2 = b1·X1 + b2·X2 + b3·X3`

> Each PC = one degree of freedom

---

## 6. Eigenvectors and Eigenvalues

- **Eigenvectors** → directions of maximum variance (become PCs)  
- **Eigenvalues** → magnitude of variance along that direction  

> Larger eigenvalue → more important component

---

## 7. Explained Variance Ratio

- Shows how much variance each component captures
- Helps decide **how many PCs to keep**
- Common practice: retain **90–95% cumulative variance**

---

## 8. Degree of Freedom (DoF) in PCA

- Degree of Freedom = number of independent directions in data  
- Original dataset: n features → n DoF  
- After PCA with k components → k DoF  

**Example:**  
- Original features = 8 → DoF = 8  
- After PCA (keep 3 PCs) → DoF = 3  

**Intuition:**  
If data lies along a line in 3D space, true DoF ≈ 1, PCA discovers this.

---

## 9. Standardization Before PCA

- Standardize data: mean = 0, standard deviation = 1  
- Reason: PCA is sensitive to scale; large-valued features dominate variance

---

## 10. PCA in Practice

- First 2–3 PCs often capture most variance  
- PCA is **not always ideal for 2D visualization**  
- Important relationships may be lost if too few PCs are used

---

## 11. Limitations of PCA

- Linear method only
- Sensitive to outliers
- Reduced interpretability
- Information loss if too many PCs are discarded

---

# PART B: t-DISTRIBUTED STOCHASTIC NEIGHBOR EMBEDDING (t-SNE)

---

## 12. What is t-SNE?

- Non-linear dimensionality reduction technique
- Mainly for **visualizing high-dimensional data**  
- Typically reduces data to **2D** (sometimes 3D)

---

## 13. Purpose of t-SNE

- Reveal hidden clusters
- Preserve **local neighborhood structure**
- Make complex data visually understandable  

> t-SNE is **not used for model training**

---

## 14. Local Structure Preservation

- Nearby points in high-dimensional space stay close in 2D
- Distant points can move freely  
- Makes clusters visually clear

---

## 15. Probabilistic Nature

- t-SNE converts distances into **probabilities**
- Measures **similarity between points** instead of raw distance  
- Helps solve the **crowding problem** in low dimensions

---

## 16. KL Divergence

- t-SNE minimizes **Kullback–Leibler divergence**  
- Goal: low-dimensional embedding reflects high-dimensional relationships

---

## 17. Perplexity

- Controls size of **local neighborhood**
- Low perplexity → focus on very local structure  
- High perplexity → considers broader context  
- Typical values: **5–50**

---

## 18. Stochastic Nature

- t-SNE is **not deterministic**
- Different runs can give slightly different results
- Random initialization affects output

---

## 19. PCA vs t-SNE

| Feature | PCA | t-SNE |
|---------|-----|-------|
| Type | Linear | Non-linear |
| Deterministic | Yes | No |
| Use | Preprocessing | Visualization |
| Preserves | Global variance | Local structure |
| Output dimensions | Any | Usually 2D |
| Interpretability | Moderate | Low |

---

## 20. Practical Tips

- Always standardize before PCA
- PCA before t-SNE can reduce noise
- Tune perplexity carefully
- t-SNE is **not suitable for prediction**
- Visualize multiple runs for consistency

---

## 21. Conclusion

- **PCA** → for dimensionality reduction and modeling  
- **t-SNE** → for visualization and exploring local clusters  
- Both techniques complement each other  
- Knowing **when to use which** is crucial in machine learning
