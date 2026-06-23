# Task 4 – The Pre-Processing Protocol

## Objective

The objective of this task is to build a reusable and leak-free preprocessing pipeline using scikit-learn. The pipeline performs feature transformation, missing value handling, encoding, and scaling before model training.

---

## Dataset

Titanic Dataset

Target Variable:
- survived

---

## Preprocessing Steps

### 1. Feature Selection

Removed:
- alive (target leakage)
- deck (more than 75% missing values)

### 2. Train-Test Split

The dataset was split into:
- 80% Training Data
- 20% Testing Data

### 3. Numerical Feature Processing

Features:
- age
- fare
- sibsp
- parch
- pclass

Transformations:
- Median Imputation
- StandardScaler

### 4. Categorical Feature Processing

Features:
- sex
- embarked
- class
- who
- embark_town
- alone
- adult_male

Transformations:
- Most Frequent Imputation
- OneHotEncoder

Additional Setting:
- handle_unknown="ignore"

### 5. Leakage Prevention

The preprocessing pipeline was fitted only on the training dataset to prevent data leakage.

### 6. Pipeline Reusability

The fitted preprocessor was saved using Joblib and reused during inference.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Joblib
- Jupyter Notebook

---

## Project Structure

```text
placemux-task-4
│
├── data
│   └── titanic.csv
│
├── models
│   └── preprocessor.pkl
│
├── notebook
│   └── task4_preprocessing.ipynb
│
├── requirements.txt
│
└── README.md
```

---

## Key Outcomes

- Implemented a reusable preprocessing pipeline.
- Handled missing values using imputation.
- Encoded categorical variables.
- Scaled numerical features.
- Prevented target leakage.
- Prevented train-test leakage.
- Saved preprocessing pipeline for inference reuse.

---

## Output

Successfully created a fitted, leak-free preprocessing pipeline reusable for both training and inference workflows.
