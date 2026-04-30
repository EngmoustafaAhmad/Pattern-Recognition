# Scale Invariant Feature Transform (SIFT)

## Course Information
- Lecture: 11  
- Topic: Scale Invariant Feature Transform (SIFT) – Part 2  
- Instructor: Dr. Yasmine Mahmoud  
- Semester: Spring 2025–2026  
- Subject: Computer Vision  

---

## Computer Vision Overview

Computer Vision is a subfield of pattern recognition that enables computers to understand images and videos in a way similar to human vision.

Humans recognize objects by identifying features such as shape, edges, and structure. For example, a car is recognized by its wheels, windows, and overall shape.

Computer vision aims to replicate this ability by analyzing pixel data in images.

---

## What is SIFT?

Scale-Invariant Feature Transform (SIFT) is a computer vision algorithm used to:

- Detect keypoints (important points in an image)
- Describe these keypoints for matching purposes

SIFT extracts distinctive features from images and stores them for comparison with other images.

---

## Key Properties of SIFT

SIFT keypoints are invariant to:

- Scale (zoom in/out)
- Rotation
- Translation (movement in image)
- Partial changes (lighting, distortion)

This makes SIFT robust for real-world image analysis.

---

## Applications of SIFT

- Image matching
- Object recognition
- 3D reconstruction
- Forensic analysis (shoe prints, fingerprints, evidence matching)

---

## SIFT Pipeline

SIFT works in four main steps:

1. Scale-Space Extrema Detection  
2. Keypoint Localization  
3. Orientation Assignment  
4. Keypoint Descriptor  

---

# 1. Scale-Space Extrema Detection

This is the first step in SIFT.

## Goal
Detect potential keypoints at multiple scales.

## Idea
Keypoints should remain visible regardless of image zoom.

---

## Scale Space

SIFT creates multiple blurred versions of the same image using Gaussian filters.

This forms a structure called a Gaussian pyramid:

- Each level = more blurred image
- Helps detect features at different scales

---

## Difference of Gaussian (DoG)

SIFT computes:

DoG = Difference between two blurred images

This highlights regions where intensity changes significantly.

---

## Keypoint Detection Rule

A pixel is considered a keypoint candidate if:

- It is brighter or darker than its neighbors
- It stands out across scale levels

---

## Intuition

A bright star in the sky remains visible even if the image is blurred or zoomed out. SIFT detects such stable “stand-out” points.

---

# 2. Keypoint Localization

## Goal
Refine keypoints and remove weak candidates.

## Steps

- Remove low contrast points
- Remove edge-like unstable points
- Refine exact position of keypoints

## Result
Only strong and stable keypoints are kept.

---

## Intuition

- Corners (e.g., window edges) are good keypoints
- Flat surfaces (e.g., walls) are discarded

---

# 3. Orientation Assignment

## Goal
Make keypoints rotation-invariant.

---

## Gradient Concept

A gradient represents:

- Direction of intensity change
- Strength of change

---

## Histogram of Gradients

For each keypoint:

1. Analyze surrounding region
2. Compute gradients
3. Build histogram of directions
4. Select dominant direction

---

## Result

Each keypoint is assigned an orientation, allowing recognition even if rotated.

---

## Intuition

A rotated image should still produce the same keypoint description.

---

# 4. Keypoint Descriptor

## Goal
Create a unique signature for each keypoint.

---

## Descriptor Construction

1. Take region around keypoint
2. Divide into 4x4 grid (16 cells)
3. Compute gradient histogram (8 directions per cell)
4. Combine into feature vector

---

## Final Descriptor Size

4 × 4 × 8 = 128-dimensional vector

This vector uniquely represents the keypoint.

---

## Intuition

A descriptor is like a fingerprint:

- Unique
- Stable
- Matchable across images

---

# Matching Keypoints with SIFT

After extracting descriptors:

## Steps

1. Compare descriptors between two images
2. Use Euclidean distance
3. Find closest matches
4. Apply ratio test to remove weak matches

---

## Ratio Test

A match is valid only if:

Best match is significantly better than second-best match

This reduces false matches.

---

# Example

If two images show the same object:

- SIFT detects keypoints in both images
- Descriptors are matched
- Object is recognized even if:
  - Rotated
  - Scaled
  - Partially visible

---

# Forensic Application: Shoe Print Matching

## Scenario

Investigators want to match a shoe print found at a crime scene with a suspect’s shoe.

---

## Steps

### 1. Image Capture
- Crime scene shoe print
- Suspect shoe sole image

### 2. Apply SIFT
- Detect keypoints in both images
- Extract descriptors

### 3. Match Keypoints
- Compare descriptors
- Find correspondences

### 4. Verification
- If enough strong matches exist (e.g., 10+)
- The shoe is likely the source

---

## Conclusion

SIFT is a powerful feature extraction method that:

- Detects stable keypoints
- Describes them uniquely
- Matches them across images
- Works under scale, rotation, and lighting changes

It is widely used in computer vision and forensic analysis.
