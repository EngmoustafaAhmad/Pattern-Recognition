# Linear Discriminant Analysis (LDA)

## Overview
Linear Discriminant Analysis (LDA) is a supervised machine learning technique used for:
- Classification
- Dimensionality reduction

It is widely used in pattern recognition and aims to separate different classes of data as clearly as possible.

---

## Intuition

Consider a dataset with two classes:
- Apples
- Oranges

Each data point has features such as:
- Size
- Weight

Some apples may overlap with oranges, making classification difficult. LDA finds the best boundary (line or axis) that separates the two classes.

---

## Goal of LDA

LDA tries to achieve two main objectives:

### 1. Maximize Between-Class Separation
- Make different classes far apart
- Increase the distance between class centers

### 2. Minimize Within-Class Spread
- Make data points within the same class close together
- Reduce variation inside each class

This leads to:
- Easier classification
- Higher accuracy
- More stable predictions


## Data Representation

Each data point is represented as a vector:
---


x = [size, weight]

- 2 features → 2D space
- 3 features → 3D space
- More features → Higher-dimensional space

---

## Key Concepts

### Within-Class Scatter (SW)

Measures how spread out the data points are within each class.

Goal:
- Keep SW small

Formula:
S_W = S_1 + S_2



---

### Between-Class Scatter (SB)

Measures the distance between class means.

Goal:
- Keep SB large

---

## LDA Optimization

LDA finds a projection direction (W) that maximizes class separation:

W = S_W^{-1} S_B


---

## Projection

After finding the optimal direction, data is projected onto it:

Y = W^T X


This reduces dimensionality and improves class separation.

---

## LDA Algorithm Steps

1. Compute mean of each class:

μ_i = (1/n) Σ x_i


2. Compute Within-Class Scatter Matrix (SW)

3. Compute Between-Class Scatter Matrix (SB)

4. Compute:

W = S_W^{-1} S_B


5. Find eigenvalues and eigenvectors

6. Select the eigenvector with the largest eigenvalue

7. Project data:

Y = W^T X


8. Classify new data

---

## Example: Apples vs Oranges

### Data

Apples:
[2, 1], [2.2, 1.1], [1.8, 0.9], [2.1, 1.0], [1.9, 1.2]


Oranges:
[3, 2], [3.2, 2.1], [2.8, 1.9], [3.1, 2.0], [2.9, 2.2]


---

### Means

Apples:
μ₁ = [2, 1]


Oranges:
μ₂ = [3, 2]


---

## Example: Forensic Application

### Problem
Classify bloodstains as:
- Stabbing (Class 1)
- Gunshot (Class 2)

### Features
- Diameter
- Density

---

### Data

Stabbing:

[5.0, 10]
[4.8, 9]
[5.2, 11]


Gunshot:

[2.0, 20]
[1.8, 22]
[2.2, 19]


---

### Means

Stabbing:
μ₁ = [5.0, 10]


Gunshot:
μ₂ = [2.0, 20.33]


---

### Observation
- Stabbing: larger diameter, lower density
- Gunshot: smaller diameter, higher density

---

### Classification Example

New sample:
[3.5, 15]


Steps:
1. Project onto discriminant axis
2. Determine which class it belongs to

---

## LDA vs PCA

| Feature | LDA | PCA |
|--------|-----|-----|
| Type | Supervised | Unsupervised |
| Uses labels | Yes | No |
| Goal | Maximize class separation | Maximize variance |
| Best for | Classification | Dimensionality reduction |

---

## Summary

LDA works as follows:
1. Compute class means
2. Measure within-class scatter
3. Measure between-class separation
4. Find optimal projection direction
5. Project data into lower dimension
6. Classify new samples

Main idea:
LDA finds a linear boundary that best separates different classes while minimizing overlap.


