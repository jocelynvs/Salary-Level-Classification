# Salary Level Classification in Indonesia using Machine Learning

This repository contains the implementation of our study on **salary level classification in Indonesia** using both **individual machine learning classifiers** and **ensemble learning methods**.

The objective is to classify a job posting into one of three salary levels:
- Rendah (Low)
- Sedang (Medium)
- Tinggi (High)

The complete implementation follows the methodology presented in our IEEE publication.

**Publication:** https://ieeexplore.ieee.org/document/10127828

---

## Dataset

**Source:** Kaggle – Job Description and Salary in Indonesia

https://www.kaggle.com/datasets/canggih/jog-description-and-salary-in-indonesia

The dataset contains approximately **34,700 Indonesian job postings**, including:

- Job title
- Job description
- Career level
- Experience level
- Employment type
- Company information
- Location
- Salary

---

# Repository Structure

```
.
├── 1_eda.ipynb                     # Exploratory Data Analysis
├── 2_data_preparation.ipynb        # Data cleaning & feature engineering
├── 3_modeling.ipynb                # Model training, tuning, and evaluation
├── preprocessed_data_encoded.csv   # Final encoded dataset
├── preprocessed_data_unencoded.csv # Cleaned dataset before encoding
└── README.md
```

---

# Workflow

## 1. Exploratory Data Analysis (`1_eda.ipynb`)

This notebook explores the dataset characteristics through descriptive statistics and visualizations. Main analyses include:
- Dataset overview
- Salary distribution
- Salary vs. career level
- Salary vs. experience level
- Salary vs. employment type
- Salary vs. company size
- Salary vs. company industry
- Salary vs. company hiring process
- Analysis of high-cardinality categorical variables

---

## 2. Data Preparation (`2_data_preparation.ipynb`)

This notebook prepares the dataset for machine learning.

### Data Cleaning

- Remove records with missing salary
- Remove extreme salary outliers
- Impute missing categorical values

### Feature Engineering

- Convert salary from USD to IDR
- Standardize experience level
- Group city locations into provinces
- Create salary level labels using Indonesian Provincial Minimum Wage (UMP)
- Remove unnecessary variables
- Label encode categorical variables
- Correlation analysis and feature selection

Outputs:

- `preprocessed_data_encoded.csv`
- `preprocessed_data_unencoded.csv`

---

## 3. Modeling (`3_modeling.ipynb`)

### Data Preprocessing

- Train / Validation / Test split (60/20/20)
- Feature standardization
- SMOTE oversampling for class balancing

### Machine Learning Models

#### Individual Classifiers

- Logistic Regression
- K-Nearest Neighbor (KNN)
- Decision Tree
- Support Vector Machine (SVM)

#### Ensemble Methods

- Voting Classifier
- Bagging Classifier
- Random Forest
- Boosting

### Hyperparameter Tuning

Grid Search was performed to optimize each model.

### Model Evaluation

Models were evaluated using metrics such as Accuracy, Precision, Recall, F1-score, and Confusion Matrix. The best-performing models were:
- Random Forest (F1-Score = 72%)
- Bagging Classifier (F1-Score = 72%)

---

## Final Prediction

The trained model is used to classify salary levels for job postings and generate insights regarding:
- Salary level by province
- Salary level by career level
- Salary level by job function
- Most popular job categories in Indonesia

---

# Methodology

The overall workflow is summarized below:

```
Raw Dataset
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Data Cleaning
      │
      ▼
Feature Engineering
      │
      ▼
Label Encoding
      │
      ▼
Train / Validation / Test Split
      │
      ▼
Feature Scaling
      │
      ▼
SMOTE Class Balancing
      │
      ▼
Model Training
      │
      ▼
Hyperparameter Tuning
      │
      ▼
Model Evaluation
      │
      ▼
Salary Level Prediction
```

---

# Results

The study compares multiple individual and ensemble machine learning algorithms. Among the evaluated methods, **Random Forest** and **Bagging Classifier** achieved the best overall performance after hyperparameter tuning, with strong capability in classifying salary levels into **Low**, **Medium**, and **High** categories.

---

**This repository is provided for academic and research purposes.**
