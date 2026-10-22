# Visual Acuity Prediction Using Regression Models

🌐 **Language:** [English](README.md) | [Українська](README.uk.md)

## 📌 Overview

This project focuses on developing and comparing machine learning regression models to predict **uncorrected distance visual acuity** using a real-world ophthalmological dataset.

By leveraging ensemble learning methods, regularized linear regression, artificial neural networks, and robust feature selection techniques, the project aims to provide accurate, automated predictions of patients' visual acuity while reducing the risk of overfitting.

A key aspect of the project is reducing the feature space from **130 to 8 clinically relevant predictors**, enabling a more compact and interpretable predictive model.

## 🛠 Tech Stack

- **Programming Language:** Python
- **Libraries:** Scikit-learn, Pandas, NumPy, Matplotlib, Seaborn
- **Development Environment:** Jupyter Notebook / PyCharm

## 📂 Project Structure

```text
├── data/
│   ├── data.csv              # Raw clinical data
│   ├── age.csv               # Patient age data
│   ├── merged_data.csv       # Intermediate merged dataset
│   └── prepared_data.csv     # Cleaned and preprocessed dataset
├── data_preparing.ipynb      # Data cleaning, merging, and preprocessing
├── regression.ipynb          # Model training, hyperparameter tuning, and evaluation
└── requirements.txt          # Project dependencies
```

## 📊 Data and Preprocessing

The data preparation pipeline is implemented in `data_preparing.ipynb` and consists of the following steps:

1. **Data Integration:** Merging raw clinical measurements (`data.csv`) with patient demographic information (`age.csv`).
2. **Data Cleaning and Imputation:** Handling missing values using `SimpleImputer`, detecting and removing outliers with `IsolationForest`, and standardizing numerical features.
3. **Feature Selection and Dimensionality Reduction:** Exploring Principal Component Analysis (PCA) and Recursive Feature Elimination with Cross-Validation (RFECV). The final modeling approach incorporates stability-based feature selection, reducing the original 130 features to the 8 most informative ophthalmological predictors.

## 🧠 Methodology and Models

The `regression.ipynb` notebook explores and compares several regression algorithms to identify the most effective predictive approach:

- **Random Forest Regressor** — Ensemble-based regression using decision trees.
- **MLPRegressor** — A feedforward artificial neural network.
- **ElasticNet** — Linear regression with combined L1 and L2 regularization.

Hyperparameter optimization was performed using `RandomizedSearchCV` with group-aware cross-validation (`GroupKFold`) to account for dependencies between observations.

### Model Performance Comparison (Top 8 Features)

| Model | R² Score | MAE | RMSE |
| --- | --- | --- | --- |
| **Random Forest (Final Model)** | **0.625** | **0.078** | **0.171** |
| MLPRegressor | 0.497 | ~0.105* | ~0.198* |
| ElasticNet | 0.273 | ~0.134* | ~0.231* |

*Note: MAE and RMSE values for MLPRegressor and ElasticNet are approximate estimates rather than directly recorded evaluation results. Model optimization primarily tracked the R² score.*

### Key Results

- **Best-performing model:** Random Forest Regressor.
- **Predictive performance:** Achieved an R² score of **0.625** on the test dataset.
- **Feature reduction:** Reduced the original feature space from **130 to 8 predictors**.
- **Error metrics:** Achieved an MAE of **0.078** and an RMSE of **0.171**.

These findings suggest that ensemble-based regression can capture meaningful relationships between ophthalmological measurements and uncorrected distance visual acuity.

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/romaro23/SightRegression.git
cd SightRegression
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the Pipeline

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Then execute the notebooks in the following order:

1. **`data_preparing.ipynb`** — Clean, merge, and preprocess the clinical data to generate `data/prepared_data.csv`.
2. **`regression.ipynb`** — Train regression models, optimize hyperparameters, evaluate predictive performance, and visualize the results.
