# Anomaly Detection – Isolation Forest and Local Outlier Factor (LOF)

---

## 1. Isolation Forest

### 1.1 Overview (Teacher Explanation)

Isolation Forest is an anomaly detection algorithm based on a very simple idea:

> **Anomalies are rare and different, so they are easier to isolate.**

Instead of measuring distance or density, Isolation Forest randomly splits the data.
Normal points require many splits to isolate, while anomalies get isolated very quickly.

This makes Isolation Forest:
- Fast
- Scalable
- Very effective for high-dimensional data

---

### 1.2 Isolation Trees (iTrees)

Isolation Forest builds many **isolation trees**.

Each tree:
- Randomly selects a feature
- Randomly selects a split value
- Keeps splitting until a point is isolated

Important idea:
- **Fewer splits → higher chance of anomaly**

---

### 1.3 Path Length Intuition (Very Important for Exams)

- **Path length** = number of splits needed to isolate a point
- Anomalies → short path length
- Normal points → long path length

This is the core logic behind the anomaly score.

---

### 1.4 Anomaly Score Formula

The anomaly score is defined as:

S(x, M) = 2 ^ ( - E(H(x)) / C(M) )

Where:
- **E(H(x))** is the average path length needed to isolate point `x`
- **C(M)** is the average path length for a dataset of size `M`

---

### 1.5 Interpretation of Anomaly Score

- Score close to **1** → anomaly
- Score close to **0** → normal point

---

### 1.6 Contamination Parameter

The **contamination** parameter represents the expected fraction of anomalies in the data.

Example:
- `contamination = 0.05`
- Means **5% of the data** is assumed to be anomalous

This helps the model decide the **cutoff threshold** for labeling anomalies.

---

### 1.7 Advantages of Isolation Forest

- Works very well on **high-dimensional data**
- Computationally **fast and scalable**
- Does **not depend on distance or density**
- Best suited for **global anomaly detection**

---

## 2. Local Outlier Factor (LOF)

---

### 2.1 Overview

Local Outlier Factor (LOF) is a **density-based anomaly detection algorithm**.

Instead of looking at the whole dataset, LOF focuses on **local neighborhoods**.

A point is an outlier if:
- Its local density is much **lower than its neighbors**

---

### 2.2 Teacher’s Intuition for LOF

Imagine people standing in a field:

- A person standing far away from a group looks suspicious
- A person standing inside a crowd looks normal

LOF works exactly like this by comparing **local density**.

---

### 2.3 Role of K-Nearest Neighbors (KNN)

LOF uses **K-nearest neighbors** to define locality.

Steps:
1. Find the `K` nearest neighbors of a point
2. Measure how dense the neighborhood is
3. Compare it with the point’s own density

---

### 2.4 LOF Score Formula

LOF score is calculated as:

LOF(A) = Average Density of Neighbors of A / Density of A

---

### 2.5 Interpretation of LOF Values

- LOF = 1 → point is similar to neighbors
- LOF < 1 → point is denser than neighbors
- LOF > 1 → point is less dense (possible outlier)

More interpretation:
- Slightly > 1 → weak outlier
- Much > 1 → strong outlier

LOF is very good at detecting **local anomalies**.

---

## 3. Isolation Forest vs LOF (Exam Table)

| Aspect | Isolation Forest | LOF |
|------|------------------|-----|
| Approach | Random isolation | Density comparison |
| Type of anomaly | Global | Local |
| High-dimensional data | Works well | Not very effective |
| Core intuition | Easy isolation | Density deviation |

---

## 4. Practical Implementation Notes

Both algorithms can be implemented using:
- scikit-learn
- NumPy
- matplotlib

In class, students were advised to practice using **Google Colab** to:
- Tune parameters
- Visualize anomalies
- Understand real-world behavior

---

## 5. Final Conclusion

- Use **Isolation Forest** for large or high-dimensional datasets
- Use **LOF** when local density differences matter

Both techniques are extremely important for **exams and real-world anomaly detection problems**.
