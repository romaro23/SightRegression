# Machine Learning for Uncorrected Visual Acuity Evaluation

## 📌 Overview
This project focuses on predicting uncorrected visual acuity using clinical ophthalmological data. By leveraging various machine learning regression algorithms and feature selection techniques, the goal is to provide an accurate, automated evaluation of patient vision metrics.

## 🛠 Tech Stack
* **Language:** Python
* **Libraries:** Scikit-learn, Pandas, NumPy, Matplotlib, Seaborn
* **Environment:** Jupyter Notebook

## 📂 Project Structure
```text
├── data/
│   ├── data.csv              # Raw clinical data
│   ├── age.csv               # Patient age data
│   ├── merged_data.csv       # Intermediate merged dataset
│   └── prepared_data.csv     # Final cleaned and processed dataset ready for training
├── data_preparing.ipynb      # Notebook for data cleaning, merging, and preprocessing
├── regression.ipynb          # Notebook for model training, evaluation, and tuning
└── requirements.txt          # Project dependencies

```

## 📊 Dataset & Preprocessing

The data pipeline is documented in `data_preparing.ipynb`. Key steps include:

1. **Data Integration:** Merging raw clinical measurements (`data.csv`) with demographic data (`age.csv`).
2. **Cleaning & Imputation:** Handling missing values, removing outliers (e.g., via IsolationForest), and normalizing clinical metrics.
3. **Feature Engineering & Selection:** Utilizing techniques like **PCA (Principal Component Analysis)** and **RFECV (Recursive Feature Elimination with Cross-Validation)** to reduce dimensionality while preserving predictive power.

## 🧠 Methodology & Models

The `regression.ipynb` notebook explores and compares multiple regression models to find the optimal fit for the clinical data:

* **ElasticNet**
* **Random Forest Regressor**
* **MLPRegressor (Multi-Layer Perceptron)**

| Model | MAE | RMSE | R² Score |
| --- | --- | --- | --- |
| Random Forest | 0.078 | 0.171 | 0.625 |
| MLPRegressor | 0.00 | 0.00 | 0.497 |
| ElasticNet | 0.00 | 0.00 | 0.273 |

## 🚀 How to Run

1. **Clone the repository:**
```bash
git clone [https://github.com/romaro23/SightRegression.git](https://github.com/romaro23/SightRegression.git)
cd SightRegression

```


2. **Install dependencies:**
```bash
pip install -r requirements.txt

```


3. **Execute the pipeline:**
* Launch Jupyter: `jupyter notebook`
* Run `data_preparing.ipynb` first to generate the `prepared_data.csv` file in the `data/` directory.
* Run `regression.ipynb` to train the models and output the evaluation metrics.



## 📝 License

This project is open-source and available under the [MIT License](https://www.google.com/search?q=LICENSE).
