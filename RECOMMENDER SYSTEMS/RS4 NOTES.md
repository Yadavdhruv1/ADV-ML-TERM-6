# Lecture 12: Matrix Factorization in Recommender Systems

## 1. Introduction

Matrix Factorization is one of the most important techniques used in **modern recommender systems**.  
It became famous after being successfully used in the **Netflix Prize Competition**, where it significantly improved recommendation accuracy.

The core idea is simple:
> Break a large, sparse user–item matrix into smaller, meaningful matrices that capture hidden patterns.

---

## 2. Why Matrix Factorization is Needed

### 2.1 Sparsity Problem

In real-world systems:
- Users rate or interact with only a few items
- Most entries in the user–item matrix are **missing**

This creates a **sparse matrix**, making similarity-based methods less effective.

Matrix factorization solves this by learning from the **available ratings** and generalizing patterns.

---

## 3. Basic Idea of Matrix Factorization

Given a user–item matrix **R**:

- Rows → Users  
- Columns → Items  
- Values → Ratings / interactions  

Matrix factorization decomposes **R** into two smaller matrices:

- **P** → User latent factor matrix  
- **Q** → Item latent factor matrix  

So,

R ≈ P × Qᵀ

This approximation helps us **predict missing ratings**.

---

## 4. Latent Factors (Core Intuition)

Latent factors are **hidden features** that are not explicitly present in the data.

### Example (Netflix Movies)

Instead of describing a movie directly as:
- Action
- Romance
- Comedy

The model **learns these properties automatically**.

Example:
- Avengers → High Action, Low Romance
- Titanic → High Romance, Medium Drama

Similarly, users also get latent factors representing their preferences.

This allows the system to predict:
> “Will this user like this movie?”

---

## 5. Optimization Objective (Loss Function)

The goal of matrix factorization is to **minimize prediction error**.

The loss function is:

min ∑ ( rᵢⱼ − Pᵢ · Qⱼᵀ )² + λ ( ||P||² + ||Q||² )

Where:
- rᵢⱼ = actual rating
- Pᵢ = latent vector of user i
- Qⱼ = latent vector of item j
- λ = regularization parameter

### Why Regularization?
- Prevents overfitting
- Keeps values from becoming too large

---

## 6. Stochastic Gradient Descent (SGD)

### 6.1 What is SGD?

SGD is an optimization technique that updates parameters **one rating at a time**.

It is commonly used when:
- Dataset is moderate in size
- Online learning is required

---

### 6.2 Steps in SGD

1. Initialize user matrix **P** and item matrix **Q** randomly
2. For each known rating:
   - Predict rating using dot product (P × Q)
   - Calculate error (actual − predicted)
   - Update P and Q using gradients
3. Repeat until convergence

### Key Point:
SGD is flexible but can be **slow** for very large datasets.

---

## 7. Alternating Least Squares (ALS)

### 7.1 What is ALS?

ALS is another optimization method where:
- One matrix is fixed
- The other matrix is solved using least squares
- Then roles are swapped

---

### 7.2 Steps in ALS

1. Fix item matrix **Q**, solve for user matrix **P**
2. Fix user matrix **P**, solve for item matrix **Q**
3. Repeat until loss stabilizes

### Why ALS is Popular:
- Faster convergence
- Easy to parallelize
- Works well with large-scale systems (Spark)

---

## 8. SGD vs ALS (Exam-Friendly Comparison)

| Aspect | SGD | ALS |
|------|-----|-----|
| Update style | One rating at a time | Matrix-wise |
| Speed | Slower | Faster |
| Scalability | Limited | High |
| Parallelization | Difficult | Easy |
| Use case | Small datasets | Large datasets |

---

## 9. Advantages of Matrix Factorization

- Handles sparse data effectively
- Captures hidden user preferences
- Produces highly personalized recommendations
- Scales to millions of users and items

---

## 10. Applications in Recommender Systems

### Netflix
- Movie recommendations based on latent preferences

### Amazon
- Product recommendations using user-item patterns

### Spotify
- Music recommendations using listening behavior

Matrix factorization forms the **core engine** behind these systems.

---

## 11. Limitations

- Cold start problem (new users/items)
- Requires sufficient interaction data
- Computationally expensive without optimization

---

## 12. Conclusion

Matrix factorization is a **cornerstone technique** in recommender systems.

Key takeaways:
- Converts sparse data into meaningful patterns
- Learns latent user and item features
- Optimized using SGD or ALS
- Essential for large-scale personalization systems

Understanding matrix factorization is crucial for building **industrial-grade recommender systems**.
