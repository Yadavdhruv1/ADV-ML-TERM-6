# Lecture 9: Recommender Systems and Apriori Algorithm

## 1. Introduction to Recommender Systems

Recommender systems are an important part of modern applications.  
They help users discover items they are likely to be interested in, instead of searching through thousands of options.

Teacher’s intuition:  
When a platform understands what you like, it can guide you better — just like a shopkeeper who knows your preferences.

Common examples:
- Netflix suggesting movies
- Amazon recommending products
- Spotify recommending songs

---

## 2. Why Companies Need Recommender Systems

Recommender systems are not just technical tools; they directly impact business outcomes.

### 2.1 Increase Revenue and Profit
By recommending relevant products, companies increase the chance of additional purchases.

Example:
If a user buys a phone, recommending earphones or a cover increases total sales.

---

### 2.2 Improve User Experience
Personalized recommendations reduce effort for users.
They do not need to search extensively to find what they want.

---

### 2.3 Increase Engagement and Retention
When users see relevant content, they stay longer on the platform and are more likely to return.

---

## 3. How Recommender Systems Work

Recommender systems make predictions based on:

- Past purchases
- Browsing history
- Ratings or clicks
- Behavior of similar users
- Similarity between products

Teacher’s intuition:  
“If users like X and Y together, another user who likes X may also like Y.”

---

## 4. Market Basket Analysis (MBA)

Market Basket Analysis focuses on understanding which items are frequently bought together.

It is widely used in retail and e-commerce.

Example:
- Bread and butter
- Laptop and mouse
- Chips and cold drink

---

### 4.1 Why Market Basket Analysis is Useful

#### Combo Offers
Products that are often bought together can be bundled and sold at discounted prices.

#### Inventory Planning
If two products are frequently co-purchased, both should be stocked adequately.

#### Cross-Selling
When a user adds one product to the cart, related items can be suggested.

---

## 5. Apriori Algorithm

The Apriori algorithm is a classic algorithm used in Market Basket Analysis.

Its goal is to:
- Find frequent item sets
- Generate association rules between items

---

## 6. Key Concepts in Apriori

### 6.1 Support

Support measures how frequently an item or item set appears in the dataset.

Example:
If “milk” appears in 6 out of 10 transactions:

Support(milk) = 6 / 10 = 0.6

---

### 6.2 Confidence

Confidence tells us how often item B is purchased when item A is purchased.

Example:
If users who buy bread also buy butter 70% of the time:

Confidence(bread → butter) = 0.7

---

### 6.3 Lift

Lift measures the strength of an association compared to random chance.

Interpretation:
- Lift > 1 → strong association
- Lift = 1 → no association
- Lift < 1 → weak or negative association

Teacher’s intuition:  
Lift tells us whether the rule is actually useful or just coincidental.

---

## 7. Steps in the Apriori Algorithm

1. Calculate support for individual items
2. Remove items below minimum support
3. Create item pairs and calculate their support
4. Generate larger item sets iteratively
5. Create association rules
6. Filter rules using confidence and lift

---

## 8. Understanding Apriori Results

Strong rules:
- High support
- High confidence
- Lift greater than 1

Weak rules:
- Low confidence
- Lift less than or equal to 1

Only strong rules are useful for business decisions.

---

## 9. Advantages of the Apriori Algorithm

- Easy to understand
- Simple to implement
- Useful for retail and transactional data
- Provides interpretable rules

---

## 10. Limitations of the Apriori Algorithm

- Slow for large datasets
- Computationally expensive
- Not suitable for continuous numerical data
- Generates many candidate item sets

---

## 11. Applications of Recommender Systems and MBA

### E-commerce
- Product recommendations
- Combo offers
- Cross-selling

### Entertainment
- Movie recommendations
- Song playlists
- Content personalization

---

## 12. Key Takeaways from the Lecture

- Recommender systems improve business value and user experience
- Market Basket Analysis helps understand co-purchase behavior
- Apriori algorithm finds frequent item sets and association rules
- Support, confidence, and lift are core evaluation metrics
- Business interpretation is as important as algorithm output

---

## 13. Conclusion

Recommender systems and the Apriori algorithm play a crucial role in modern data-driven businesses.

Understanding both the **technical logic** and the **business intuition** behind them is essential for building effective, real-world machine learning solutions.
