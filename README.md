# Association Rule Mining Mini Assignment

This mini project demonstrates the use of **Association Rule Mining** on simulated transactional data using the **Apriori algorithm**. The goal is to uncover common item patterns from shopping basket data.

---

##  Objective

- Simulate at least 10 fake transactions with 2–5 items each.
- Use the Apriori algorithm to discover frequent itemsets with **minimum support = 0.3**.
- Generate association rules with **confidence ≥ 0.7**.
- Interpret and explain multiple rules based on the results.

---

##  Step-by-Step Breakdown

###  Step 1: Simulate Transactional Data
We created 10 fake shopping transactions using 8 common grocery items:  
`['Bread', 'Milk', 'Eggs', 'Cheese', 'Butter', 'Apples', 'Bananas', 'Cereal']`

Each transaction randomly included 2–5 items.

**Output:**  

association_rules_outputs/generated_transactions_output.PNG

---

###  Step 2: One-hot Encoding
We used `TransactionEncoder` from the `mlxtend` library to convert the list of transactions into a binary matrix where each item is marked as present (1) or absent (0) in a transaction.

**Output:**  

association_rules_outputs/transactionencoder_output.PNG

---

###  Step 3: Frequent Itemsets (Apriori)
We applied the **Apriori algorithm** with:
- `min_support = 0.3` (i.e., itemsets appearing in at least 3 of 10 transactions)

This revealed item combinations that frequently co-occurred.

**Output:**  

association_rules_outputs/apiori_algorithm_output.PNG

---

###  Step 4: Association Rules
We generated rules using:
- **Metric:** Confidence
- **Threshold:** `confidence ≥ 0.7`

Here are some of the strongest rules found:

| Rule | Confidence | Lift | Interpretation |
|------|------------|------|----------------|
| Cheese → Apples | 0.75 | 1.07 | Cheese buyers often buy Apples (75% of the time) |
| Milk → Apples | 0.75 | 1.07 | Milk and Apples are frequently purchased together |
| Bananas → Cereal | 1.00 | 2.00 | Everyone who buys Bananas also buys Cereal — very strong rule |
| Cheese → Eggs | 0.75 | 1.50 | Moderate association between Cheese and Eggs |

**Output:**  

association_rules_outputs/association_rules_output.PNG

---

## What These Rules Mean

- **High confidence** means there's a strong likelihood of one item being bought if another is.
- **Lift > 1** means the rule is stronger than random chance.
- For example, if someone buys **Bananas**, they are **very likely** to also buy **Cereal** (100% of the time in our data).

---

##  Tools Used

- Python
- pandas
- mlxtend
- Jupyter Notebook

---

##  How to Run

1. Clone the repo or open the notebook.
2. Install dependencies:  
   `pip install pandas mlxtend`
3. Run the notebook cell-by-cell to see the simulation, frequent itemsets, and association rules.

---

## Repository Structure
```bash
association_rules.ipynb       # Jupyter notebook with full code and output
README.md                     # Project description and insights
screenshots/                  # Folder with step-by-step output images
```

---

