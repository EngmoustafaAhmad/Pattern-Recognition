# Feature Selection Techniques

## Course Information
- Lecture: 13  
- Topic: Feature Selection Techniques  
- Prepared by: Dr. Yasmine Mahmoud  
- Semester: Spring 2025–2026  
- Subject: Pattern Recognition / Machine Learning  

---

## 1. Introduction to Feature Selection

Feature selection is the process of identifying the most relevant variables (features) in a dataset that contribute to the prediction task, while removing irrelevant, redundant, or noisy features.

It is an important step in building efficient machine learning models because it:
- Improves accuracy
- Reduces overfitting
- Decreases computational cost
- Enhances interpretability

---

### Importance of Feature Selection

Feature selection is not only a preprocessing step, but a fundamental part of model building.

Benefits include:
- Better generalization to unseen data
- Easier interpretation of model decisions
- Faster training and inference

---

### Example

In an image dataset with 10,000 images and 1,000 pixels each:

Instead of using all pixels as features, feature selection identifies the most informative pixels that contribute to classification.

---

## 2. Importance of Feature Selection

### Reducing Dimensionality
- Prevents curse of dimensionality
- Reduces computation and memory usage
- Simplifies the dataset

### Improving Model Performance
- Removes irrelevant/noisy features
- Improves generalization
- Reduces training time

### Enhancing Interpretability
- Simpler models are easier to explain and visualize

### Decreasing Overfitting
- Focuses only on relevant features
- Reduces learning from noise

### Noise Reduction
- Eliminates irrelevant or redundant variables

---

## 3. Types of Features

- Continuous Features: numerical values (e.g., height, weight)
- Categorical Features: discrete categories (e.g., color, type)
- Ordinal Features: ordered categories (e.g., low, medium, high)
- Binary Features: two values (e.g., 0/1, true/false)

---

## 4. Feature Selection Methods

There are three main categories:

- Filter Methods
- Wrapper Methods
- Embedded Methods

---

## 5. Filter Methods

Filter methods select features based on statistical measures.

### Characteristics
- Independent of machine learning models
- Used as preprocessing step

### Advantages
- Fast and simple
- No model training required

### Disadvantages
- Ignores feature interactions
- May not be optimal for specific models

---

### Common Techniques

- Correlation Coefficient
- Chi-Square Test
- Mutual Information
- ANOVA F-test

---

## Correlation Coefficient Method

This method selects features based on how strongly they are correlated with the target variable.

- High correlation → important feature
- Low correlation → less important feature

---

### Pearson Correlation Coefficient

Measures linear relationship between two variables:

- r = 1 → perfect positive correlation
- r = -1 → perfect negative correlation
- r = 0 → no linear relationship

Formula:

r = Cov(X, Y) / (σX · σY)

Where:
- Cov(X, Y): covariance
- σX, σY: standard deviations

---

### Example Dataset

| F1 | F2 | F3 | F4 | Y |
|----|----|----|----|----|
| 1  | 2  | 3  | 4  | 10 |
| 2  | 3  | 4  | 5  | 20 |
| 3  | 4  | 5  | 6  | 30 |
| 4  | 5  | 6  | 7  | 40 |
| 5  | 6  | 7  | 8  | 50 |

---

### Step 1: Mean Values

- μF1 = 3  
- μF2 = 4  
- μF3 = 5  
- μF4 = 6  
- μY = 30  

---

### Step 2: Covariance

Example:

Cov(F1, Y) = 20

Similarly:
- Cov(F2, Y) = 20  
- Cov(F3, Y) = 20  
- Cov(F4, Y) = 20  

---

### Step 3: Standard Deviation

- σF1 = 1.414  
- σF2 = 1.414  
- σF3 = 1.414  
- σF4 = 1.414  
- σY = 14.142  

---

### Step 4: Pearson Correlation

r = Cov / (σX · σY)

For F1:

rF1 = 20 / (1.414 × 14.142) = 1

Similarly:
- rF2 = 1  
- rF3 = 1  
- rF4 = 1  

---

### Interpretation

All features are perfectly correlated with the target variable, meaning:

- All features are equally important
- No feature can be removed based on correlation

---

## 6. Chi-Square Test

The Chi-Square test checks whether two categorical variables are independent.

### Purpose
- Determines relationship between features and target
- Used for categorical data

---

### Key Idea

If two variables are independent:
- They are not useful for prediction

If dependent:
- They are useful features

---

### Example

Does age group affect product purchase?

- Age group: young, middle, old  
- Purchase: yes, no  

---

### Contingency Table

A table showing frequency distribution between two categorical variables.

It is used to compute Chi-Square statistics and measure dependency.

---

## Conclusion

Feature selection improves machine learning performance by:

- Reducing dimensionality
- Removing irrelevant features
- Improving accuracy and generalization
- Enhancing interpretability

Filter methods like correlation and Chi-Square are fast and commonly used preprocessing techniques.
