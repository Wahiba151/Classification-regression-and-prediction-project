# Predicting High Site Traffic – Classification, Regression & Prediction (R)

## Overview

This group project analyzes and predicts whether a recipe generates high website traffic using statistical and machine-learning methods in R. The dataset contains 947 recipes described by nutritional variables (calories, carbohydrates, sugar, protein), recipe category, number of servings, and a binary indicator of high traffic.

The objective is to identify the main drivers of high traffic and compare predictive performance across Linear Probability Models (LPM), Logit models, and Random Forest.

---

## Methods

### Data Processing
- Conversion of variables to numeric and factors  
- Binary encoding of the outcome variable (`high_traffic`)  
- Removal of missing values (final sample: 895 observations)  
- 70/30 train–test split with stratification  

### Exploratory Data Analysis
- Nutrient density plots by traffic level  
- Probability of high traffic by recipe category  

### Models
- Linear Probability Model (OLS)
- Logistic Regression (with Average Marginal Effects)
- Random Forest (tuned using 10-fold cross-validation)

### Evaluation
- Confusion matrices
- ROC curves
- AUC (Area Under the Curve)
- Variable importance (|t-stats| for LPM/Logit, impurity for RF)

---

## Key Results

- Recipe category is by far the strongest predictor of high traffic across all models.
- Nutritional variables (calories, sugar, protein, carbohydrates) play a much smaller role once category is controlled for.
- Logit and LPM achieve very similar performance (AUC ≈ 0.81).
- Random Forest does not outperform parametric models (AUC ≈ 0.79).
- The Logit model is preferred, as it offers the best balance between predictive accuracy and interpretability through Average Marginal Effects.

Main insight: full-meal recipes (Vegetable, Potato, Pork, Meat, One Dish Meal) are much more likely to generate high traffic than lighter categories such as Beverages or Breakfast.

---

## Conclusions & Recommendations

- Editorial and marketing efforts should prioritize high-performing recipe categories.
- Low-traffic categories could be improved through better presentation or promotion.
- Model performance could be enhanced by adding variables such as seasonality, user ratings, image quality, or marketing indicators.

---

## Repository Structure

- `code/` – R scripts for data cleaning, modeling, and evaluation  
- `data/` – recipe dataset  
- `outputs/` – figures and model outputs  
- `report/` – detailed project report and interpretations  

---

## Team

Group academic project:
- LAZRAQ Wahiba
- NAJM-SBAI Hiba
- ABDEDDAIM Salaheddine

### My contribution (Wahiba Lazraq)
- Data cleaning and preprocessing  
- EDA and visualization  
- Implementation of LPM, Logit, and Random Forest  
- Model evaluation (ROC/AUC, confusion matrices)  
- Interpretation and recommendations  

---

## Tools

- R (tidyverse, rsample, ranger, yardstick, marginaleffects)
