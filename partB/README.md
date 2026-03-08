# Dataset: Breast Cancer Wisconsin (Diagnostic)

## Source
The dataset is loaded directly from sklearn.datasets:
```python
from sklearn.datasets import load_breast_cancer
data = load_breast_cancer()
```
No manual download is required. The dataset is bundled with scikit-learn.

## Description
- 569 samples, 30 numeric features
- Binary labels: 0 = benign, 1 = malignant
- Remapped to {-1, +1} for SVM compatibility: `y = (target * 2 - 1)`

## Usage
- Used in: task 2 1.ipynb, task 2 2.ipynb, task 2 3.ipynb, task 3 1.ipynb, task 3 2.ipynb
- Split: 50% train (284 samples) / 50% test (285 samples), stratified
- Semi-supervised split: 10 labeled + 274 unlabeled per trial
- All features standardised with StandardScaler (fit on train, transform both)

## Relevance to CS4VM
The medical diagnosis context directly matches the paper's motivating example:
- False negative (malignant classified as benign) >> False positive (benign classified as malignant)
- Maps to c(+1) > c(-1) in the CS4VM cost structure
