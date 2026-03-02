# Advanced Machine Learning — Mid-Semester Examination  
## Part A: Research Paper Selection  
NST, Rishihood University, Sonipat  

**Student:** Sourabh Sarkar  
**Roll Number:** 230081  

---

## 📄 Selected Paper

| Field | Details |
|------|--------|
| Title | Cost-Sensitive Semi-Supervised Support Vector Machine (CS4VM) |
| Authors | Yu-Feng Li, James T. Kwok, Zhi-Hua Zhou |
| Venue | AAAI Conference on Artificial Intelligence (AAAI-10) |
| Year | 2010 |
| CORE Rank | A* |
| Primary Method | Support Vector Machine (SVM) |
| Category | Classical Machine Learning (Semi-Supervised + Cost-Sensitive SVM) |

---

## 🧠 What This Paper Does

This paper proposes **CS4VM (Cost-Sensitive Semi-Supervised Support Vector Machine)** — a unified framework that combines:

- Cost-sensitive learning (different misclassification costs)
- Semi-supervised learning (using unlabeled data)

The motivation is real-world scenarios where:

- Labeled data is expensive (e.g., medical diagnosis)
- Unlabeled data is abundant
- Some errors are more costly than others (e.g., missing a disease vs false alarm)

The paper extends traditional SVM by modifying the optimization objective to:

1. Incorporate class-dependent misclassification costs  
2. Utilize unlabeled samples to shape the decision boundary  

---

## 🔬 Core Contribution

The main contribution is **methodological**.

The authors introduce:

### 1️⃣ CS4VM Formulation
A new optimization framework that jointly:

- Minimizes margin-based loss
- Accounts for unequal costs
- Exploits unlabeled data

---

### 2️⃣ Label Mean Insight (Key Idea)
A major theoretical insight:

> Instead of estimating labels of all unlabeled data, estimate label means.

This reduces complexity and connects semi-supervised SVM to supervised cost-sensitive SVM.

This makes the method:
- Efficient
- Theoretically grounded

---

### 3️⃣ Efficient Algorithm
The paper proposes a two-stage approach:

1. Estimate label means using margin principles  
2. Train a modified SVM using these estimates  

This allows solving the problem using standard SVM solvers (SMO / LIBSVM).

---

## 📊 Experiments

The authors evaluate CS4VM on **20 UCI datasets**.

### Comparisons Against:
- Supervised cost-sensitive SVM  
- TSVM (Transductive SVM)  
- Laplacian SVM  

### Results:
- Consistent cost reduction
- Better performance under class imbalance
- Faster runtime than other semi-supervised methods

---

## 🎯 Why I Selected This Paper

I selected this paper because it satisfies all Part A constraints while remaining conceptually strong and implementable.

### ✔ Academic Validity
- AAAI 2010 is a **CORE A\*** venue  
- Falls within the **2009–2012 window**
- Classical ML (pre-deep learning)

---

### ✔ Clear Methodological Contribution
- Introduces a new SVM formulation  
- Not just an application paper  
- Strong theoretical grounding

---

### ✔ Conceptual Clarity
Despite having theory, the key idea is intuitive:

> Use label statistics instead of full label estimation.

This makes it explainable in Part C without external tools.

---

### ✔ Real-World Relevance
Applicable to domains like:
- Medical diagnosis
- Fraud detection
- Risk-sensitive classification

---

## 🔬 Reproducibility Plan (Part B Preview)

The method can be reproduced in a simplified form using modern tools.

### Tools
- Python 3
- scikit-learn
- NumPy

---

### Simplified Implementation Strategy

Since the original paper uses MATLAB and custom solvers, reproduction will involve:

1. Baseline linear SVM  
2. Cost-sensitive SVM (class weighting)  
3. Semi-supervised extension using:
   - Pseudo-labeling OR
   - Label mean approximation  

This preserves the core contributions while keeping implementation feasible.

---

## ⚠️ Limitations

- Assumes binary classification
- Sensitive to cost parameter tuning
- Semi-supervised assumptions may fail if unlabeled data is noisy
- Original formulation involves non-trivial optimization

These aspects will be explored during implementation.

---

## 📁 Repository Structure
