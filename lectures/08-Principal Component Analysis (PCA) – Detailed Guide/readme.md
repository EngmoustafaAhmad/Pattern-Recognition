# 📊 Principal Component Analysis (PCA) – Detailed Guide

## 📌 Overview

Principal Component Analysis (PCA) is a dimensionality reduction technique that transforms data into a new coordinate system where:

* The **axes (principal components)** represent directions of maximum variance
* The data becomes easier to analyze and visualize

---

## 🎯 PCA Workflow (Step-by-Step)

### 1️⃣ Data Preparation

* Ensure data is:

  * Numerical
  * Structured as a **matrix**

📌 Example:

* Rows → Samples (observations)
* Columns → Features (variables)

---

### 2️⃣ Calculate the Mean

* Compute mean for each feature (column)

📌 Purpose:

* Center data around zero

---

### 3️⃣ Standardize the Data

* Formula:

  * Subtract mean
  * Divide by standard deviation

📌 Why?

* Features may have different scales (e.g., height vs weight)
* PCA is sensitive to scale

---

### 4️⃣ Compute Covariance Matrix

The covariance matrix measures relationships between features:

C = \frac{1}{n-1} X^T X

📌 Key Insights:

* Positive covariance → variables increase together
* Negative covariance → inverse relationship
* Zero → no relationship

---

### 5️⃣ Eigenvalue Decomposition

#### 📌 Eigenvector:

* Direction of data variance

#### 📌 Eigenvalue:

* Magnitude (importance) of that direction

Mathematical definition:

Cov(X) v = \lambda v

---

### 🧠 How to Compute Them?

Solve:

\det(Cov(X) - \lambda I) = 0

Then:

* Substitute λ back to find eigenvectors
* Normalize eigenvectors (unit length)

---

## 📊 Interpretation

### Eigenvectors → Directions

* Represent **principal components (PCs)**
* PC1 = highest variance
* PC2 = second highest variance

### Eigenvalues → Importance

* Larger value → more important component

---

## 🧱 Eigenvector Matrix

Example:

$$
V =
\begin{bmatrix}
0.707 & 0.707 \
0.707 & -0.707
\end{bmatrix}
$$

* Column 1 → PC1
* Column 2 → PC2

---

### 6️⃣ Transform the Data

Transform original data into PCA space:

X_{new} = X_{standardized} \cdot V

📌 Result:

* Data expressed in terms of principal components

---

## 🔄 What Happens After Transformation?

* Dataset is **rotated**
* Aligned with directions of maximum variance
* Redundant information is minimized

---

## 📉 Final Output

* New dataset:

  * Columns = Principal Components
  * Rows = Transformed observations

---

## ✅ Key Takeaways

* PCA reduces dimensions while preserving information
* Eigenvectors define directions
* Eigenvalues define importance
* Transformation projects data onto new axes

---

## 🧪 Example Insight

If:

* Covariance = 0.6185 → strong positive relation
  👉 Features increase together

---

## ⚠️ Notes

* Always standardize data before PCA
* Use (n - 1) for sample covariance (unbiased estimate)

---

## 📎 Conclusion

PCA is a mathematical technique that:

* Simplifies data
* Removes redundancy
* Highlights important patterns

It is widely used in:

* Machine Learning
* Data Visualization
* Feature Engineering

---

## ✍️ Author

Dr. Yasmine Mahmoud
Spring Semester 2025–2026

---
