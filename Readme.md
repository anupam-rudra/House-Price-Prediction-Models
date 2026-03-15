# House Price Prediction using Multiple Regression, Random Forest and XGBoost


## Project Overview
This project builds multiple regression and machine learning models to predict house prices using the **House Prices: Advanced Regression Techniques** dataset from Kaggle. The goal is to understand the impact of different property features on house prices and compare the performance of statistical and machine learning models.

The objective of this project is to apply **statistical modeling and machine learning techniques** to identify the key factors affecting house prices and build accurate prediction models.

The project includes:

- Exploratory Data Analysis (EDA)
- Feature engineering
- Multicollinearity reduction
- Regression diagnostics
- Tree-based machine learning models
- Regularization and hyperparameter tuning
- Model performance comparison

---

## Dataset
Dataset: **House Prices: Advanced Regression Techniques(train.csv)**

The dataset contains information about residential homes in Ames, Iowa. It includes **79 explanatory variables** describing different aspects of houses.

Examples of features:

- Lot size
- Overall quality of the house
- Living area
- Garage size
- Basement area
- Neighborhood
- Exterior materials

Target Variable:

`SalePrice` – Final sale price of the house.

To reduce skewness, the target variable was transformed using a **log transformation**.

---

## Project Workflow

### 1. Data Loading
The dataset is loaded using pandas and initial inspection is performed to understand structure, datatypes and summary statistics.

### 2. Exploratory Data Analysis
EDA includes:

- Distribution of sale prices
- Skewness analysis
- Scatter plots between important numerical features and price
- Boxplots for categorical variables
- Correlation heatmap

### 3. Data Cleaning
Missing values were handled using:

- Median imputation for numerical variables
- Mode imputation for categorical variables

### 4. Feature Engineering
Several categorical features with many levels were grouped to reduce dimensionality.

Examples:

- Exterior types grouped into top categories
- Neighborhood categories reduced
- Dummy encoding applied to categorical variables

### 5. Outlier Detection
Outliers were detected using the **IQR method** and removed for the variable:

`GrLivArea`

### 6. Multicollinearity Handling
Variance Inflation Factor (VIF) was used to detect multicollinearity among numerical variables.

A custom iterative function was implemented to remove variables with high VIF values.

### 7. Multiple Linear Regression
A statistical model was built using **statsmodels OLS**.

Backward elimination was applied using p-values to remove insignificant variables.

Model diagnostics performed:

- Breusch–Pagan test (heteroskedasticity)
- Jarque–Bera test (normality)
- Ramsey RESET test (model specification)
- Residual analysis

### 8. Machine Learning Models

Three machine learning models were trained:

1. Random Forest Regressor  
2. XGBoost Regressor  
3. Regularized versions of both models using hyperparameter tuning

### 9. Hyperparameter Tuning
Hyperparameter tuning was performed using **RandomizedSearchCV** to improve model generalization.

For Random Forest:

- max_depth
- min_samples_split
- min_samples_leaf
- max_features

For XGBoost:

- learning_rate
- max_depth
- subsample
- colsample_bytree
- reg_alpha (L1 regularization)
- reg_lambda (L2 regularization)

### 10. Model Evaluation
Models were evaluated using:

- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)

## The final notebook compares the performance of:

- Multiple Linear Regression
- Random Forest
- XGBoost
- Regularized Random Forest
- Regularized XGBoost


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


















