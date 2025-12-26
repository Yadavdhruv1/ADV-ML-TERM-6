# Lecture 10: Market Basket Analysis and Apriori Algorithm

## 1. Introduction to Market Basket Analysis (MBA)

Market Basket Analysis is a data mining technique used to find patterns in customer purchase behavior.  
It helps us understand **which items are frequently bought together** in real-world transactions.

Teacher’s intuition:  
When customers buy one product, they often buy related products. MBA helps us identify those relationships.

MBA is widely used in:
- Retail stores
- E-commerce platforms
- Supermarkets
- Online shopping applications

---

## 2. Why Market Basket Analysis is Important

Market Basket Analysis helps businesses take better decisions.

### 2.1 Product Placement
Items that are frequently bought together can be placed nearby in stores.

### 2.2 Promotions and Offers
Products with strong associations can be bundled into combo offers.

### 2.3 Inventory Management
Frequently co-purchased items should always be available in stock.

---

## 3. Key Terms in Market Basket Analysis

### 3.1 Frequent Itemsets
A frequent itemset is a group of items that appears together in transactions many times.

Example:
- {milk, bread}
- {laptop, mouse}

---

### 3.2 Association Rules
Association rules show relationships between items in the form:

X → Y

Meaning:
If a customer buys X, they are likely to buy Y.

---

## 4. Apriori Algorithm

The Apriori algorithm is a classic and widely used algorithm for Market Basket Analysis.

It is used to:
- Find frequent itemsets
- Generate association rules

Apriori follows a **bottom-up approach**, meaning:
- Start with single items
- Gradually build larger itemsets

Important principle:
> If an itemset is frequent, all of its subsets must also be frequent.

---

## 5. Working of Apriori Algorithm

### Step 1: Data Preparation

The transaction data is collected, usually in the form of a CSV file.

Teacher’s note:
Transactions with only one item are removed because association rules require co-occurrence.

---

### Step 2: Generating Frequent Itemsets

The algorithm scans the entire dataset to find itemsets that meet a minimum support threshold.

Only those itemsets whose support is above the threshold are kept.

---

### Step 3: Rule Generation

Once frequent itemsets are identified, association rules are generated.

Each rule has:
- Antecedent (left-hand side)
- Consequent (right-hand side)

---

## 6. Key Metrics in Apriori Algorithm

### 6.1 Support

Support shows how frequently an item or itemset appears in the dataset.

Formula:

Support(X) =  
Number of transactions containing X / Total number of transactions

Example:
If milk appears in 30 out of 100 transactions:

Support(milk) = 0.30

---

### 6.2 Confidence

Confidence measures how often item Y is bought when item X is bought.

Formula:

Confidence(X → Y) =  
Support(X ∪ Y) / Support(X)

Example:
If 20 customers bought both bread and butter, and 25 bought bread:

Confidence(bread → butter) = 20 / 25 = 0.8

---

### 6.3 Lift

Lift measures the strength of a rule compared to random chance.

Formula:

Lift(X → Y) =  
Confidence(X → Y) / Support(Y)

Interpretation:
- Lift > 1 → strong positive association
- Lift = 1 → no association
- Lift < 1 → negative or weak association

---

## 7. Example Application of Apriori Algorithm

Consider an online retail dataset.

### Objective:
To find which products are frequently purchased together.

---

### Data Preparation Steps

1. Group data using invoice number
2. Combine items bought in the same transaction
3. Convert rows into columns (pivot table)
4. Encode data into binary format:
   - 1 → item present
   - 0 → item absent

---

## 8. Code-Level Workflow (Conceptual)

### 8.1 Data Import and Cleaning
- Read dataset using pandas
- Remove negative values from quantity and price
- Handle missing values

---

### 8.2 Data Transformation
- Group transactions
- Pivot the data
- Encode values into 0s and 1s

---

### 8.3 Applying Apriori
- Use apriori function from `mlxtend`
- Set minimum support
- Generate frequent itemsets
- Generate association rules using confidence and lift

---

## 9. Understanding Association Rules

### Antecedent
The items already purchased.

### Consequent
The items likely to be purchased next.

Example rule:
(milk, bread) → (jam)

Meaning:
Customers who buy milk and bread are likely to buy jam.

---

## 10. Practical Insights

### Co-occurrence Filtering
Transactions with less than two items are removed since they do not help in rule mining.

---

### Binary Encoding
After transformation, data is encoded as:
- 1 → item present
- 0 → item absent

This format is required by the Apriori algorithm.

---

## 11. Advantages of Apriori Algorithm

- Easy to understand
- Interpretable results
- Useful for exploratory analysis
- Widely used in retail analytics

---

## 12. Limitations of Apriori Algorithm

- Slow for large datasets
- High computational cost
- Generates many candidate itemsets
- Not suitable for continuous data

---

## 13. Conclusion

Market Basket Analysis helps businesses understand customer purchasing behavior.

The Apriori algorithm plays a key role in discovering:
- Frequent itemsets
- Strong association rules

A clear understanding of support, confidence, and lift is essential for applying Apriori effectively in real-world business problems.
