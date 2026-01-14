# Eigenfaces: Spectral Decomposition for Facial Recognition


## Executive Summary
This project explores the intersection of *Linear Algebra* and *Unsupervised Machine Learning. By leveraging **Singular Value Decomposition (SVD)*, we reduce the dimensionality of the Olivetti Faces dataset to extract "Eigenfaces"—the fundamental building blocks of human facial features. 

This approach demonstrates how complex visual data can be compressed by over *95%* while retaining critical identity features for recognition tasks.

---

## Theoretical Framework
At the heart of this project lies the *SVD Theorem*. We treat a collection of $m$ images (each with $n$ pixels) as a matrix $A \in \mathbb{R}^{m \times n}$.

The decomposition is defined as:
$$A = U \Sigma V^T$$



### Component Breakdown:
* *$U$ (Left Singular Vectors):* Represents the "Face Space" coordinates.
* *$\Sigma$ (Singular Values):* A diagonal matrix representing the "energy" or variance captured by each component.
* *$V^T$ (Right Singular Vectors):* The *Eigenfaces*. These are the basis vectors for the entire dataset.

---

## Implementation Workflow

### 1. Data Tensor Preparation
We normalize and mean-center the facial vectors to ensure the SVD captures *variance* rather than absolute pixel intensity.
* *Dataset:* Olivetti Faces (400 images, 64x64 pixels).
* *Preprocessing:* $A = X - \Psi$ (Where $\Psi$ is the "Average Face").

### 2. Spectral Analysis
We compute the economy-size SVD to identify the most informative features and analyze the "Scree Plot" to determine the optimal cutoff $k$.



### 3. Dimensionality Reduction
We implement *Low-Rank Approximation*. By keeping only the top $k$ singular values, we project high-dimensional image data into a compact latent space.

---

## Visual Benchmarks

### The Eigenface Basis
The first few components capture global features (lighting and head shape), while higher-order components capture localized features (eyes, mouth, facial hair).



### Reconstruction Fidelity
| Components ($k$) | Compression Ratio | Visual Quality |
| :--- | :--- | :--- |
| *5* | 99.8% | Abstract Silhouette |
| *50* | 98.7% | Recognizable Identity |
| *150* | 96.3% | High Fidelity Reconstruction |
