# Feature Selection Techniques (Filter Methods)

## Lecture Information
- Lecture: 13  
- Topic: Feature Selection Techniques  
- Instructor: Dr. Yasmine Mahmoud  
- Semester: Spring 2025–2026  
- Subject: Pattern Recognition / Machine Learning  

---

# Chi-Square Test (Feature Selection)

## Problem Statement

We want to predict whether a customer will buy a product based on:

- Age Group (Young, Middle-aged, Old)
- Income Level (Low, Medium, High)
- Previous Purchases (Yes, No)

Target variable:
- Bought Product (Yes, No)

---

## Dataset (5 Customers)

| Customer | Age Group    | Income Level | Previous Purchases | Bought Product |
|----------|-------------|--------------|---------------------|----------------|
| 1        | Young       | Low          | No                  | Yes            |
| 2        | Young       | Medium       | Yes                 | No             |
| 3        | Middle-aged | High         | Yes                 | Yes            |
| 4        | Old         | Low          | No                  | No             |
| 5        | Middle-aged | Medium       | Yes                 | Yes            |

---

# Step 1: Contingency Tables

We analyze each feature separately.

---

## 1. Age Group vs Bought Product

| Age Group    | Yes | No | Total |
|--------------|-----|----|-------|
| Young        | 1   | 1  | 2     |
| Middle-aged  | 2   | 0  | 2     |
| Old          | 0   | 1  | 1     |
| **Total**    | 3   | 2  | 5     |

---

## 2. Income Level vs Bought Product

| Income Level | Yes | No | Total |
|-------------|-----|----|-------|
| Low         | 1   | 1  | 2     |
| Medium      | 2   | 0  | 2     |
| High        | 0   | 1  | 1     |
| **Total**   | 3   | 2  | 5     |

---

## 3. Previous Purchases vs Bought Product

| Previous Purchases | Yes | No | Total |
|--------------------|-----|----|-------|
| Yes                | 3   | 0  | 3     |
| No                 | 0   | 2  | 2     |
| **Total**          | 3   | 2  | 5     |

---

# Step 2: Expected Frequencies

We compute expected values assuming no relationship between features and target.

Formula:

E = (Row Total × Column Total) / Grand Total

---

## Example Calculation

For (Young, Yes):

E = (2 × 3) / 5 = 1.2

---

## Expected Table (Age Group)

| Age Group    | Yes | No |
|--------------|-----|----|
| Young        | 1.2 | 0.8 |
| Middle-aged  | 1.2 | 0.8 |
| Old          | 0.6 | 0.4 |

---

# Step 3: Chi-Square Statistic

Formula:

χ² = Σ (O − E)² / E

Where:
- O = observed value
- E = expected value

---

## Interpretation

We compute Chi-Square for each cell in the table and sum them.

---

### Example Concept

For each cell:

- Compare observed vs expected
- Measure how much they differ
- Larger difference → stronger relationship

---

# Step 4: Significance Test

After calculating χ² for each feature:

- Compare with critical value from Chi-Square table
- Based on degrees of freedom

Decision:
- If χ² > critical value → feature is important
- If χ² ≤ critical value → feature is not important

---

# Step 5: Feature Selection Decision

We select features based on statistical significance:

- Keep features strongly related to target
- Remove weak or independent features

Example conclusion:
- If Age Group shows strong χ² → keep it
- Otherwise → discard it

---

# Wrapper Methods

Wrapper methods select features based on model performance.

## Techniques:
- Recursive Feature Elimination (RFE)
- Forward Selection
- Backward Elimination

---

## Advantages
- Considers feature interactions
- Better feature subsets

## Disadvantages
- Computationally expensive
- Risk of overfitting on small datasets

---

# Embedded Methods

Feature selection happens during model training.

## Techniques:
- Lasso Regression (L1 Regularization)
- Random Forest Feature Importance
- Gradient Boosting Machines

---

## Advantages
- Efficient
- Integrated with model training

## Disadvantages
- Can be biased toward certain feature types
- Less interpretable in some cases

---

# Conclusion

Feature selection improves machine learning models by:

- Reducing dimensionality
- Removing irrelevant features
- Improving accuracy
- Reducing overfitting

Chi-Square is a powerful filter method for categorical data, while wrapper and embedded methods provide more model-driven selection strategies.
