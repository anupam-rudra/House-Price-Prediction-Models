# House Price Prediction using Multiple Regression, Random Forest and XGBoost

## Project Overview

This project develops predictive models to estimate residential property sale prices using the **House Prices: Advanced Regression Techniques** dataset from Kaggle.

The goal of the project is to apply **statistical analysis and machine learning techniques** to understand the factors that influence house prices and build models capable of predicting sale prices accurately.

The workflow includes:

- Exploratory Data Analysis (EDA)
- Feature engineering
- Multicollinearity analysis using VIF
- Multiple Linear Regression
- Random Forest Regression
- XGBoost Regression
- Model evaluation and comparison

---

# Dataset

The dataset used in this project is the **House Prices: Advanced Regression Techniques** dataset from Kaggle.

It contains detailed information about residential homes in **Ames, Iowa**.

### Dataset Size

- **Observations:** 1460 houses
- **Features:** 80 explanatory variables
- **Target variable:** SalePrice

Each record represents the sale of a residential property along with its structural and location-related attributes.

---

# Data Description 
# Also Refer data_description.txt

The dataset contains variables describing different aspects of the house.

These variables can be broadly grouped into several categories.

---

## 1. Identification Variables

These variables uniquely identify each property.

| Variable | Description |
|--------|-------------|
| Id | Unique identifier for each house |

---

## 2. Location and Neighborhood

These variables describe the location and surrounding area of the property.

| Variable | Description |
|--------|-------------|
| MSSubClass | Building class |
| MSZoning | General zoning classification |
| Neighborhood | Physical location within Ames |
| Condition1 | Proximity to main road or railroad |
| Condition2 | Secondary proximity condition |

Neighborhood is one of the most important variables influencing house prices.

---

## 3. Lot and Land Features

These variables describe the size and physical characteristics of the land.

| Variable | Description |
|--------|-------------|
| LotFrontage | Linear feet of street connected to property |
| LotArea | Lot size in square feet |
| LotShape | General shape of property |
| LandContour | Flatness of the property |
| Utilities | Type of utilities available |
| LotConfig | Lot configuration |

---

## 4. Exterior Features

These variables describe the external materials and appearance of the house.

| Variable | Description |
|--------|-------------|
| Exterior1st | Exterior covering on house |
| Exterior2nd | Secondary exterior covering |
| RoofStyle | Type of roof |
| RoofMatl | Roof material |
| MasVnrType | Masonry veneer type |

In this project, exterior materials were grouped into **top categories** to reduce dimensionality.

---

## 5. House Quality and Condition

These variables represent the quality and condition of the property.

| Variable | Description |
|--------|-------------|
| OverallQual | Overall material and finish quality |
| OverallCond | Overall condition rating |
| YearBuilt | Original construction year |
| YearRemodAdd | Remodeling year |

**OverallQual** is one of the strongest predictors of sale price.

---

## 6. Basement Features

These variables describe the basement area and its quality.

| Variable | Description |
|--------|-------------|
| TotalBsmtSF | Total basement area in square feet |
| BsmtQual | Basement height |
| BsmtCond | Basement condition |
| BsmtExposure | Walkout or garden level walls |

Basement area significantly contributes to the total living space.

---

## 7. Living Area

These variables describe the interior living space.

| Variable | Description |
|--------|-------------|
| GrLivArea | Above ground living area |
| BedroomAbvGr | Number of bedrooms above ground |
| KitchenAbvGr | Number of kitchens |
| TotRmsAbvGrd | Total rooms above ground |

**GrLivArea** is strongly correlated with house prices.

---

## 8. Garage Features

These variables describe the garage characteristics.

| Variable | Description |
|--------|-------------|
| GarageType | Garage location |
| GarageArea | Size of garage |
| GarageCars | Capacity of garage |

Garages increase property value significantly.

---

## 9. Sale Information

These variables describe the transaction details.

| Variable | Description |
|--------|-------------|
| YrSold | Year of sale |
| MoSold | Month of sale |
| SaleType | Type of sale |
| SaleCondition | Condition of sale |

---

# Target Variable

The target variable is:

**SalePrice**

- The sale price of the house in US dollars.

The distribution of SalePrice is **right-skewed**, so a **log transformation** was applied:
SalePrice_log = log(SalePrice)
This transformation improves model performance and stabilizes variance.
