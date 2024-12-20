---
layout: default
---

# Credit Default Prediction

**Project Overview:**
Developed a logistic regression model to predict whether loan applicants would default based on financial data.

**Dataset:**
- Contains 1,000 loan applications with 17 variables.
- Features include loan amount, account balances, age, and financial history.

---

### Data Preprocessing
- Addressed missing values for categorical variables like `checking_balance` and `savings_balance` (40% of data marked as "unknown").
- Encoded categorical variables:
  - **Ordinal:** Used label encoding.
  - **Nominal:** Applied one-hot encoding.
- Standardized numerical features to optimize model performance.

---

### Model Selection
**Explored Models:**
1. Logistic Regression
2. Naïve Bayes
3. Decision Tree
4. SVM
5. K-Nearest Neighbors

**Chosen Model: Logistic Regression**
- Prioritized minimizing **false negatives**.
- Provided interpretable coefficients for decision-making.

---

### Results
- Accuracy: **77%**
- Recall (defaults): **66%** after SMOTE.
- ROC-AUC: **0.79**

**Insights:**
- Higher loan amounts and low-quality credit history were strong indicators of default.
- Applicants with "unknown" account balances showed lower risk.

---

### Tools & Libraries Used
- Python (pandas, scikit-learn, imbalanced-learn)
- Jupyter Notebook
- Matplotlib, Seaborn

**Next Steps:**
- Explore additional features or transformations to improve accuracy.
- Fine-tune hyperparameters using grid search.
- Investigate ensemble methods like Random Forest or Gradient Boosting.

- [View Jupyter Notebook](./project-credit-default.html)
