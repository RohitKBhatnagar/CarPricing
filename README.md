# 🚗 Used Car Price Prediction — Practical Application II Project 
*A Machine Learning Project for Predicting Used Car Prices Using Real‑World Marketplace Data*

---

## 📌 **Project Overview**

This project builds a machine learning model to predict **used car prices** based on real‑world vehicle listings. The goal is to help used‑car dealerships understand which vehicle attributes most strongly influence price and to support smarter inventory and pricing decisions.

The project follows the [**CRISP‑DM**](https://www.datascience-pm.com/crisp-dm-2/) framework and includes:

- A clearly defined business problem  
- Multi‑step data preparation  
- Regression modeling (Linear, Ridge, Lasso)  
- Model evaluation  
- Actionable business insights  

---

## 🎯 **Problem Statement**

Used car prices vary widely based on age, mileage, brand, condition, and other attributes. Dealerships often rely on experience or intuition to price vehicles, which can lead to inconsistent valuations.

**Objective:**  
Build a predictive model that estimates used car prices and identifies the strongest price drivers.

**Business Value:**  
Dealers can use these insights to:

- Optimize inventory acquisition  
- Improve pricing accuracy  
- Understand what consumers value most  
- Increase profitability and turnover  

---

## 📊 **Modeling Approach**

This is a **supervised regression** problem.

Models used:

- **Linear Regression** (baseline)  
- **Ridge Regression** (L2 regularization)  
- **Lasso Regression** (L1 regularization)  

The target variable is **log-transformed price** (`log_price`) to reduce skewness and stabilize variance.

---

## 🧹 **Data Preparation**

The dataset contained **426,000+ used car listings** with 18 features. Key preparation steps included:

### ✔ Handling Missing Values
- Dropped rows missing essential numeric fields  
- Filled categorical missing values with `"unknown"`  
- Removed unrealistic values (e.g., price = 0, year < 1985, odometer > 500,000)

### ✔ Feature Engineering
- Created `age = 2022 - year`  
- Log‑transformed price  
- Removed high‑cardinality columns (model, VIN, region, state, paint_color)

### ✔ Encoding
- **Frequency encoding** for medium‑cardinality features  
- **One‑hot encoding** for low‑cardinality features  
- Ensured all features were numeric for modeling

---

## 🧠 **Model Evaluation**

After training all three models, performance was nearly identical:

| Model               | RMSE      | MAE      | R²       |
|---------------------|-----------|----------|----------|
| Linear Regression   | 1.039841  | 0.562474 | 0.272582 |
| Ridge Regression    | 1.039843  | 0.562476 | 0.272579 |
| Lasso Regression    | 1.039911  | 0.562623 | 0.272484 |

### ✔ Interpretation

- All models performed similarly because the cleaned dataset was low‑dimensional and well‑behaved.
- **Ridge Regression** was selected as the final model due to its stability and smooth coefficient behavior.
- The model explains **~27% of the variance** in used car prices — typical for real‑world automotive datasets.

---

## 🔍 **Key Findings**

### 1. **Age and Mileage are the strongest predictors**
Older cars and high‑mileage vehicles consistently sell for less.

### 2. **Brand popularity matters**
Manufacturers with high listing frequency (Toyota, Honda, Ford) command higher prices.

### 3. **Condition influences price, but less than expected**
Age and mileage dominate pricing; condition is secondary.

### 4. **Transmission, fuel type, and drive type have moderate effects**
Automatic, AWD/4WD, and fuel‑efficient vehicles tend to be priced higher.

### 5. **Model is stable and interpretable**
Ridge Regression provides reliable coefficient estimates that align with market behavior.

---

## 📁 **Repository Structure**

```
├── data/                 # Raw and cleaned datasets
├──                       # Jupyter notebook with full workflow
├── images/               # Visualizations (plots, charts)
├── README.md             # Project overview (this file)
└── report/               # Final non-technical report
```

---

## 🧪 **How to Run the Notebook**

1. Clone the repository  
2. Install dependencies  
3. Open the Jupyter notebook  
4. Run cells sequentially  

The notebook includes:

- Data cleaning  
- Feature engineering  
- Encoding  
- Modeling  
- Evaluation  
- Visualizations  

---

## 📦 **Technologies Used**

- Python  
- Pandas  
- NumPy  
- Scikit‑learn  
- Matplotlib / Seaborn  
- Jupyter Notebook  

---

## 📘 **Final Report**

A non‑technical report summarizing the project, findings, and recommendations for used‑car dealers is included in the `report/` folder.

---

## 👤 **Author**

**Rohit K. Bhatnagar**  
Data Scientist  

---