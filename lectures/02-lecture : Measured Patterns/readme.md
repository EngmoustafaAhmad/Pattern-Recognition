# 📚 Lec. 2: Measured Patterns

 

---

## 1. What is a Pattern?

A **pattern (نمط)** is any entity of interest that we want to **recognize (التعرف عليه)** or **identify (تمييزه)**.

Examples of patterns include:
- Images
- Handwritten characters
- Faces
- Sounds
- Objects in videos

A pattern usually has **properties or attributes (خصائص أو سمات)** that distinguish it from other patterns.

Patterns can be observed in two ways:

- **Physically (بشكل مادي)**  
  Example: images, videos, objects.

- **Mathematically (رياضيًا)**  
  By applying **statistical algorithms (خوارزميات إحصائية)** to analyze data.

---

## 2. Measurements (القياسات)

In pattern recognition, we collect **measurements (قياسات)** from the pattern.

Measurements describe the object numerically so that a machine can analyze it.

Examples:

- **Fruit example**
  - Size
  - Weight
  - Color

- **Face example**
  - Distance between eyes
  - Face width
  - Nose length

These measurements help the system understand the pattern.

---

## 3. Multiple Measurements

Usually, **more than one measurement** is taken from a pattern.

These measurements should represent the **important attributes (الخصائص المهمة)** of the object.

Example:

For face recognition, the system may measure:

- Eye distance
- Mouth width
- Face shape
- Jaw angle

Each measurement provides useful information for recognition.

---

## 4. Relevant vs Irrelevant Measurements

Not all measurements are useful.

One important step in **Pattern Recognition (التعرف على الأنماط)** is deciding whether a measurement is:

- **Relevant (مفيد)** → Helps classification  
- **Irrelevant (غير مفيد)** → Does not help classification

Example:

If we want to recognize **faces**, measuring **shoe size** would be useless.

Therefore, selecting the right measurements is very important.

---

## 5. Importance of Measurement Selection

Choosing the right measurements is a **critical step in system design**.

Reasons:

- Some measurements **cost money** to collect.
- Some measurements **take time** to compute.
- Poor measurements lead to **poor classifier performance (أداء ضعيف للمصنف)**.

So we must carefully select the most useful measurements.

---

## 6. Features (المميزات)

In Pattern Recognition:

**Features (المميزات)** are functions or transformations of the measurements.


