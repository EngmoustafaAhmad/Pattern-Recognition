# Linear Discriminant Analysis (LDA) – Forensic Science Example

## Overview

This document explains a worked example of **Linear Discriminant Analysis (LDA)** applied to a forensic classification problem. The goal is to classify bloodstain patterns as either:

- Class 1: Stabbing
- Class 2: Gunshot

Each sample is represented using two features:
- Diameter (mm)
- Spatter density (droplets/cm²)

---

## Problem Statement

A forensic analyst must classify a new bloodstain pattern based on historical data of known cases. The classification is performed using LDA to find an optimal decision boundary.

---

## Dataset

### Class 1: Stabbing
- [5.0, 10]
- [4.8, 9]
- [5.2, 11]

### Class 2: Gunshot
- [2.0, 20]
- [1.8, 22]
- [2.2, 19]

---

## Step 1: Data Representation

Each sample is represented as a feature vector:

x = [diameter, density]

---

## Step 2: Compute Class Means

### Stabbing (Class 1)

μ₁ = [5.0, 10]

### Gunshot (Class 2)

μ₂ ≈ [2.0, 20.33]

---

## Step 3: Within-Class Scatter Matrix (S_W)

The within-class scatter measures how spread each class is internally.

For each class:
- Compute deviation from mean
- Compute outer products
- Sum all contributions

Final result:

S_W = S₁ + S₂

---

## Step 4: Between-Class Scatter Matrix (S_B)

The between-class scatter measures how far class means are from the overall mean.

### Overall Mean

μ = average of μ₁ and μ₂

### Formula

S_B = Σ nᵢ (μᵢ − μ)(μᵢ − μ)ᵀ

Final S_B reflects strong separation between the two classes.

---

## Step 5: Compute Discriminant Direction

LDA solves:

S_W⁻¹ S_B w = λ w

Steps:
1. Compute S_W⁻¹
2. Multiply S_W⁻¹ S_B
3. Compute eigenvalues and eigenvectors
4. Select eigenvector with largest eigenvalue

---

## Resulting Discriminant Vector

w ≈ [0.998, 0.059]

Interpretation:
- Diameter is the dominant feature
- Density contributes weakly

---

## Step 6: Data Projection

Each sample is projected onto the LDA axis:

z = wᵀ x

This reduces the problem from 2D → 1D.

---

## Step 7: Classification Rule

A threshold is computed (midpoint between projected class means).

Decision rule:
- If z > threshold → Class 1 (Stabbing)
- Else → Class 2 (Gunshot)

---

## Step 8: Classifying New Sample

Given:

x = [3.5, 15]

Result:
- Project onto LDA axis
- Compare with threshold

Final classification:

Class 1 (Stabbing)

---

## Conclusion

LDA successfully finds a projection that maximizes class separation by:

- Maximizing distance between class means
- Minimizing variance within each class

In this example, LDA determines that **diameter is the most discriminative feature** for separating stabbing and gunshot bloodstain patterns.
