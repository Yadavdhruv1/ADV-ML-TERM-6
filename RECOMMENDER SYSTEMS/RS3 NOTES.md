# Lecture 11: Recommender Systems – Collaborative Filtering

## 1. Overview of Recommender Systems

In this class, we studied **Recommender Systems**, which are systems designed to predict and suggest items that a user is likely to prefer.

These systems are heavily used in real-world platforms such as:
- Netflix
- Amazon
- Spotify
- YouTube

The main goal of a recommender system is to:
- Increase user engagement
- Improve user experience
- Keep users active on the platform for longer durations

---

## 2. What is a Recommender System?

A recommender system is a machine learning system that suggests items to users based on:
- Past user behavior
- Preferences
- Similar users or items

Examples:
- Netflix recommending movies
- Amazon suggesting products
- Spotify suggesting songs or playlists

---

## 3. Matrix Representation in Recommender Systems

### 3.1 User–Item Interaction Matrix (Matrix A)

Recommender systems commonly use a matrix representation.

Structure of the matrix:
- Rows represent **users**
- Columns represent **items**
- Cell value (Aᵢⱼ) represents interaction between user *i* and item *j*

Types of values:
- Binary (0 or 1): viewed / not viewed, bought / not bought
- Numerical: ratings (1–5), time spent, number of clicks

This matrix is the foundation of collaborative filtering.

---

## 4. Similarity Measures

To recommend items, we need to measure **similarity**.

### 4.1 Cosine Similarity

Cosine similarity measures how similar two vectors are by calculating the cosine of the angle between them.

Key points:
- Used for comparing users or items
- Value ranges between -1 and 1
- Higher value means higher similarity

Cosine similarity is widely used because:
- It works well with sparse data
- It focuses on direction rather than magnitude

---

## 5. Collaborative Filtering

Collaborative filtering is based on the idea that:
> Users with similar behavior will like similar items.

There are two major types of collaborative filtering.

---

### 5.1 User–User Collaborative Filtering

Concept:
- Find users similar to a target user
- Recommend items liked by similar users

Example:
If User A and User B like similar movies, then movies liked by User B can be recommended to User A.

Steps:
1. Compute similarity between users
2. Identify nearest neighbors
3. Recommend items based on neighbors’ preferences

Limitation:
- Does not scale well with large number of users

---

### 5.2 Item–Item Collaborative Filtering

Concept:
- Find items similar to the item a user interacted with
- Recommend similar items

Example:
If users who bought item A also bought item B, then B is recommended to someone who bought A.

Key points:
- Introduced by Amazon in 1998
- More scalable than user-user filtering
- Item similarities change less frequently than user preferences

This method is widely used in production systems.

---

## 6. Cold Start Problem

The cold start problem occurs when the system has insufficient data.

### 6.1 New User Problem
- No interaction history
- System cannot infer preferences

### 6.2 New Item Problem
- No user interactions available
- Difficult to recommend the item

Common solutions:
- Recommend popular items
- Use demographic data (age, location)
- Ask users for initial preferences

---

## 7. Sparse Matrix Problem

Most user-item matrices are **sparse**.

Meaning:
- Most entries are zero
- Users interact with only a small subset of items

Problems caused by sparsity:
- Poor similarity computation
- Increased computational cost
- Reduced recommendation quality

Handling sparsity is a major challenge in recommender systems.

---

## 8. Evolution of Recommender Systems

### 8.1 Pre-2007
- Similarity-based methods
- User-user and item-item filtering

---

### 8.2 2007–2015
- Matrix factorization techniques
- Popularized by the Netflix Prize competition
- Reduced sparsity and improved accuracy

---

### 8.3 Post-2015
- Deep learning-based recommender systems
- Neural networks model complex user-item interactions
- Better personalization at scale

---

## 9. Practical Applications

### Netflix
- Recommends movies and shows based on viewing history
- Uses collaborative filtering and advanced ML models

### Amazon
- Recommends products based on purchases and browsing
- Uses item-item collaborative filtering

### Spotify
- Suggests songs and playlists based on listening behavior
- Combines collaborative filtering with content-based methods

---

## 10. Advantages of Collaborative Filtering

- No need for item metadata
- Captures real user preferences
- Works well in large-scale systems

---

## 11. Limitations of Collaborative Filtering

- Cold start problem
- Sparse data issues
- Scalability challenges
- Requires large amounts of interaction data

---

## 12. Conclusion

This lecture explained how recommender systems work using collaborative filtering.

Key takeaways:
- User-item matrices are the backbone of recommender systems
- Similarity measures like cosine similarity are essential
- Item-item collaborative filtering is widely used in industry
- Challenges such as cold start and sparsity must be handled carefully

Recommender systems play a crucial role in modern data-driven platforms by enhancing personalization and user engagement.
