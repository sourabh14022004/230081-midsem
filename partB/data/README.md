# Data Directory

## Dataset: Breast Cancer Wisconsin (Diagnostic)

**Source:** Built into scikit-learn — `sklearn.datasets.load_breast_cancer()`

**No manual download required.** The dataset is loaded directly from scikit-learn in all notebooks using:

```python
from sklearn.datasets import load_breast_cancer
data = load_breast_cancer()
```

## Dataset Description

| Property | Value                           |
| -------- | ------------------------------- |
| Samples  | 569                             |
| Features | 30 (real-valued)                |
| Classes  | 2 (Malignant = +1, Benign = −1) |
| Source   | UCI Machine Learning Repository |

Features are computed from digitised images of fine-needle aspirate (FNA) biopsies. Each feature describes characteristics of cell nuclei present in the image (e.g., radius, texture, perimeter, area, smoothness).

## Label Mapping

The original labels (1 = malignant, 0 = benign) are remapped to {+1, −1} as required by the CS4VM formulation:

```python
y = (data.target * 2 - 1).astype(float)   # {0,1} → {-1,+1}
```

## Usage in Notebooks

| Notebook         | Usage                                                                       |
| ---------------- | --------------------------------------------------------------------------- |
| `task 2 1.ipynb` | Dataset loading, preprocessing, semi-supervised split visualisation         |
| `task 2 2.ipynb` | CS4VM reproduction — training on 10 labeled samples, evaluating on test set |
| `task 2 3.ipynb` | Result comparison across cost ratios                                        |
| `task 3 1.ipynb` | Ablation study — label mean estimation and cost asymmetry components        |
| `task 3 2.ipynb` | Failure mode — misspecified balance parameter r                             |

## Preprocessing

All notebooks apply `StandardScaler` (zero mean, unit variance) fitted on the training split and applied to both train and test sets. A 50/50 stratified train/test split is used (`random_state=42`).

## Why No Data Files Are Stored Here

Since the dataset is a scikit-learn built-in, no CSV or binary files need to be stored. Any environment with `scikit-learn>=1.4.0` can reproduce all results without manual data download.
