# House Price Prediction using Multiple Regression, Random Forest and XGBoost

## Project Overview

This project builds predictive models to estimate house sale prices using the **House Prices: Advanced Regression Techniques** dataset from Kaggle.

The objective of this project is to apply **statistical modeling and machine learning techniques** to identify the key factors affecting house prices and build accurate prediction models.

The project includes:

- Exploratory Data Analysis (EDA)
- Feature engineering
- Multicollinearity detection using VIF
- Stepwise multiple regression
- Random Forest regression
- XGBoost regression
- Model evaluation and comparison

---

## Dataset

The dataset contains **1460 observations and 80 explanatory variables** describing residential homes.

The target variable is:

**SalePrice** – the property's sale price in dollars.

The dataset includes information such as:

- Lot size
- Neighborhood
- House quality
- Living area
- Basement area
- Garage size
- Exterior material
- Construction year
- Remodeling information

---

## Project Workflow

### 1. Data Loading

The dataset is loaded using **Pandas** and initial inspection is performed to understand:

- dataset dimensions
- variable types
- summary statistics

---

### 2. Exploratory Data Analysis (EDA)

EDA is performed to understand the structure of the data and relationships between variables.

Techniques used:

- Histogram of the target variable
- Skewness analysis
- Log transformation of SalePrice
- Scatter plots for numerical predictors
- Boxplots for categorical variables
- Correlation heatmap

---

### 3. Data Preprocessing

#### Missing Value Imputation

Missing values are handled using:

- **Median imputation** for numerical variables
- **Mode imputation** for categorical variables

#### Target Transformation

The target variable is **log transformed** to reduce skewness and stabilize variance.
SalePrice_log = log(SalePrice)


---

### 4. Feature Engineering

Some categorical variables with many levels were grouped to reduce dimensionality.

Examples:

- Exterior material grouped into **top 5 categories**
- Neighborhood grouped into **top 8 categories**

This helps reduce sparsity in dummy variables.

---

### 5. Outlier Detection

Outliers in **GrLivArea** were removed using the **Interquartile Range (IQR) method**.
Lower Bound = Q1 − 1.5 × IQR
Upper Bound = Q3 + 1.5 × IQR

Observations outside this range were removed.

---

### 6. Multicollinearity Detection

Multicollinearity among predictors was evaluated using **Variance Inflation Factor (VIF)**.

Variables with **VIF greater than 5** were iteratively removed to ensure stable regression estimates.

---

### 7. Multiple Linear Regression

A **stepwise backward elimination approach** was used to select statistically significant predictors.

Model diagnostics were performed including:

- Breusch–Pagan test for heteroskedasticity
- Jarque–Bera test for normality of residuals
- Ramsey RESET test for model specification
- Residual analysis plots

---

### 8. Random Forest Regression

A **Random Forest Regressor** was implemented using scikit-learn.

Key model characteristics:

- 500 decision trees
- Parallel processing enabled
- Feature importance analysis

Random Forest helps capture **non-linear relationships and complex interactions** between predictors.

---

### 9. XGBoost Regression

An **XGBoost Regressor** was used to improve predictive performance.

Model parameters:

- n_estimators = 500
- learning_rate = 0.05
- max_depth = 6
- subsample = 0.8
- colsample_bytree = 0.8

XGBoost is a powerful **gradient boosting algorithm** widely used in machine learning competitions.

---

## Model Evaluation

Models were evaluated using:

- **RMSE (Root Mean Squared Error)**
- **MAE (Mean Absolute Error)**

These metrics measure prediction accuracy on unseen test data.

---

## Feature Importance

Feature importance analysis was conducted for:

- Random Forest
- XGBoost

This helps identify the most influential variables affecting house prices.

Examples of important predictors include:

- Living area
- Overall quality
- Garage size
- Basement area
- Neighborhood


















