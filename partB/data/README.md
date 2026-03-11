# Toy Dataset for MKL Experiments

## Overview
This project uses a **synthetic toy dataset** generated via `sklearn.datasets.make_classification` instead of the original datasets from the paper by Gönen & Alpaydın (2011).

## Dataset Specification
| Property | Value |
|---|---|
| Generator | `sklearn.datasets.make_classification` |
| Total Samples | 200 |
| Features | 2 (informative) |
| Classes | 2 (binary classification) |
| Class Balance | Balanced (100 per class) |
| Random Seed | 42 |
| Redundant Features | 0 |
| Clusters per Class | 2 |

## Why This Dataset?
- **Non-linearity**: With 2 clusters per class, the decision boundary is non-linear, making it a meaningful testbed for comparing linear vs. RBF kernels and for demonstrating the benefit of kernel combination in MKL.
- **Low dimensionality (2D)**: Enables clear visualisation of decision boundaries and kernel effects.
- **Sufficient size (200 samples)**: Meets the ≥100 sample requirement while remaining tractable for CPU-only training.

## Preprocessing
- **StandardScaler** is applied to zero-mean and unit-variance normalise both features before kernel computation.
- An 80/20 train/test split is used with `stratify=y` to preserve class balance.

## Reproducibility
All code uses `random_state=42` (or `SEED=42`) to ensure full reproducibility across runs.
