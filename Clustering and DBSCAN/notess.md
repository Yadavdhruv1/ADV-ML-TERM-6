# Lecture 6: Density-Based Clustering – DBSCAN  
**Course:** Advanced Machine Learning  

---

## 1. Overview of the Lecture

In this lecture, we studied **density-based clustering**, with a primary focus on **DBSCAN (Density-Based Spatial Clustering of Applications with Noise)**.

Before introducing DBSCAN, we revised earlier clustering techniques like **K-Means** and **Gaussian Mixture Models (GMM)** and discussed why they fail in certain real-world scenarios, especially when:
- Data contains **outliers**
- Clusters have **arbitrary (irregular) shapes**
- Cluster densities are not uniform

---

## 2. Quick Revision: Existing Clustering Methods

### 2.1 K-Means Clustering

**Concept:**
K-Means divides data into **K clusters** by minimizing the distance between data points and their assigned cluster centroid.

**Limitations of K-Means:**
- Produces only **spherical clusters**
- Performs **hard clustering** (one point → one cluster)
- Sensitive to **initial centroid selection**
- Cannot handle **noise or outliers**
- Performs poorly when cluster densities differ

---

### 2.2 Gaussian Mixture Models (GMM)

**Concept:**
GMM is a **probabilistic clustering** approach where data is assumed to come from a mixture of Gaussian distributions.

**Key Properties:**
- Uses **Expectation–Maximization (EM)** algorithm
- Supports **soft clustering** (probability-based membership)
- Can model **elliptical clusters** using covariance matrices

**Limitations of GMM:**
- Sensitive to initialization
- Requires specifying number of clusters in advance
- Struggles with heavy noise and outliers

---

## 3. Motivation for DBSCAN

Both K-Means and GMM:
- Require the number of clusters beforehand
- Do not naturally detect noise
- Fail when clusters have arbitrary shapes

**DBSCAN solves these problems by using density instead of distance alone.**

---

## 4. Introduction to DBSCAN

**DBSCAN** stands for  
**Density-Based Spatial Clustering of Applications with Noise**

DBSCAN groups together points that are **closely packed** and labels points in low-density regions as **noise**.

Key idea:
> Clusters are regions of **high point density**, separated by regions of **low density**.

---

## 5. Key Parameters in DBSCAN

DBSCAN uses **two main parameters**, which are extremely important for exams.

### 5.1 EPS (Epsilon)

- Defines the **radius** around a point
- Points within this radius are considered **neighbors**

Smaller EPS:
- More strict clustering
- More points may become noise

Larger EPS:
- Clusters may merge incorrectly

---

### 5.2 MinPoints (MinPts)

- Minimum number of points required within EPS to form a **dense region**
- Common rule of thumb:
  - MinPts ≥ dimensions + 1

---

## 6. Types of Points in DBSCAN

DBSCAN classifies points into **three categories**.

### 6.1 Core Points

- A point is a **core point** if:
  - It has at least **MinPoints** within its EPS radius

Core points form the **heart of clusters**.

---

### 6.2 Border Points

- Border points:
  - Lie within EPS of a **core point**
  - But do not themselves satisfy MinPoints

They belong to clusters but are not dense enough to expand them.

---

### 6.3 Noise Points (Outliers)

- Points that are:
  - Not core points
  - Not reachable from any core point

These are labeled as **noise**.

This is one of DBSCAN’s biggest advantages.

---

## 7. DBSCAN Algorithm – Step by Step

### Step 1: Pick an Unvisited Point
- Randomly select a point
- Find all neighbors within EPS

---

### Step 2: Check Core Condition
- If neighbors ≥ MinPoints → mark as **core point**
- Else → temporarily label as noise

---

### Step 3: Cluster Expansion
- For each core point:
  - Add all reachable points to the cluster
  - Expand until no more points can be added

---

### Step 4: Repeat
- Continue until all points are visited and classified

---

## 8. Intuition Using a Real-Life Analogy

**Friend Circle Analogy:**

- EPS → How close someone must be to be considered your friend
- MinPoints → Minimum friends needed to form a group

If a person has enough close friends → **core point**  
Friends of friends → **border points**  
Loners → **noise points**

---

## 9. Advantages of DBSCAN

- Automatically detects **outliers**
- No need to specify number of clusters beforehand
- Can find clusters of **arbitrary shapes**
- Works well when clusters are irregular

---

## 10. Limitations of DBSCAN

- Highly sensitive to **EPS and MinPoints**
- Difficult to tune parameters for **high-dimensional data**
- Struggles when cluster densities vary significantly

---

## 11. Comparison: K-Means vs GMM vs DBSCAN

| Feature | K-Means | GMM | DBSCAN |
|------|------|------|------|
| Cluster shape | Spherical | Elliptical | Arbitrary |
| Noise handling | No | Poor | Excellent |
| Hard / Soft | Hard | Soft | Density-based |
| K required | Yes | Yes | No |
| Outlier detection | No | No | Yes |

---

## 12. Key Takeaways (Exam Focused)

- DBSCAN is a **density-based clustering algorithm**
- Uses **EPS** and **MinPoints**
- Identifies **core, border, and noise points**
- Excellent for **outlier detection**
- Best suited when cluster shapes are irregular

---

## 13. Conclusion

DBSCAN is a powerful alternative to traditional clustering methods when dealing with real-world data that contains noise, irregular shapes, and unknown cluster counts.

In upcoming lectures, DBSCAN will be used for:
- **Anomaly detection**
- **Practical clustering applications**
- **Project-based learning**
