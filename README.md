# Machine Learning Project: Shape Classification (Square vs Circle)

This repository presents a complete **machine learning project** focused on solving a **binary classification problem** using real-world techniques such as feature engineering, model evaluation, and active learning.

The project is structured into three main notebooks:
1. **Part A** — Core machine learning pipeline
2. **Part B** — Active Learning strategies
3. **Kaggle Notebook** — Competitive modeling and submission-oriented optimization

This repository is designed to be understandable **without any prior knowledge** of the original course, assignment, or competition.

---

## Problem Description

The task is to classify data samples into one of two geometric shapes:

- **Square**
- **Circle**

Each sample is described by multiple numerical and categorical features (e.g., `f1`, `f5`, `f6`, `f11`, etc.).  
The challenge lies in:
- **Class imbalance** (one class appears much less frequently)
- **Non-obvious decision boundaries**
- **Missing values** in several features

---

## Evaluation Metric

The project focuses on **F1-score**, specifically **Macro F1-score**.

Why F1-score?
- Accuracy is misleading when classes are imbalanced
- F1-score balances:
  - **Precision** (How many predicted positives are correct)
  - **Recall** (How many actual positives are found)
- Macro F1 treats all classes equally, regardless of their frequency

---

## Project Structure

### 1. PartA.ipynb — Core Machine Learning Pipeline

This notebook builds a complete, end-to-end machine learning solution.

#### What is done in Part A?

**1. Exploratory Data Analysis (EDA)**
- Inspect class distribution
- Analyze missing values
- Understand feature behavior

**2. Data Preprocessing**
- Encode target labels:
  - `square → 0`
  - `circle → 1`
- Encode categorical features (e.g., `f11`)
- Preserve missing values for tree-based models

**3. Feature Engineering**
- Ratio-based features (e.g., `f1 / f6`, `f5 / f6`)
- Log-space transformations
- Missing-value indicator features
- Simple interaction features

**4. Model Training**
- Multiple machine learning models are explored:
  - Linear models
  - Tree-based models
  - Neural network baseline
- Stratified K-Fold Cross Validation is used to ensure robust evaluation

**5. Model Evaluation**
- Models are evaluated using F1-score
- Cross-validation results are compared to select the most effective approach

---

### 2. PartB.ipynb — Active Learning

Part B explores **Active Learning**, a technique used when labeling data is expensive.

#### What is Active Learning?

Instead of labeling all data at once:
1. Start with a small labeled subset
2. Train a model
3. Ask the model which unlabeled samples it is **most uncertain about**
4. Label those samples
5. Repeat

#### Implemented Strategies

- **Least Confidence Sampling**
- **Entropy Sampling**

#### Model Used
- Logistic Regression (chosen for interpretability and simplicity)

#### Goal
To show that intelligent sample selection can:
- Achieve good performance
- Using significantly fewer labeled samples

---

### 3. kaggle.ipynb — Competitive Modeling & Optimization

This notebook focuses on **maximizing performance** under competitive conditions.

#### Key Techniques Used

- Advanced feature engineering
- LightGBM ensemble models:
  - GBDT
  - DART
- Handling class imbalance using `scale_pos_weight`
- Multiple random seeds to reduce variance
- Threshold optimization (instead of using 0.5)
- Out-of-Fold (OOF) predictions for reliable evaluation

#### Output
- Generates a final prediction file:
  - `Submission_final_last_try.csv`

---

## How to Run the Project

### Requirements

```bash
pip install numpy pandas scikit-learn lightgbm jupyter
```

## How to Run the Project

Run Jupyter Notebook:

```bash
jupyter notebook
```

Then open:

- PartA.ipynb
- PartB.ipynb
- kaggle.ipynb

---

## Key Takeaways

- Handling class imbalance is crucial in real-world machine learning problems.
- Feature engineering can significantly outperform raw models.
- Active Learning reduces labeling cost without sacrificing performance.
- Cross-validation and threshold tuning are essential for reliable evaluation metrics.

---

## Author

**Muhannad (MQHANAD)**  
GitHub: https://github.com/MQHANAD

