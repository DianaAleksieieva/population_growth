# 🌍 Population Growth Modeling & Forecasting

A statistical and machine-learning analysis of global demographic change using World Bank and UN data

This project analyzes worldwide population dynamics and builds a forecasting model using demographic indicators such as birth rate, death rate, migration, income group, and region.
The goal is to understand global growth patterns and generate short- and long-term predictions for 180+ countries.

The analysis is implemented in R using Quarto, linear modeling, interaction terms, and rolling-window cross-validation.

GitHub page: https://dianaaleksieieva.github.io/population_growth/

### 1. Data Cleaning & Feature Engineering

Processed World Bank population and demographic datasets
Computed instantaneous growth rate:

\( r_t = \ln\left(\frac{N_{t+1}}{N_t}\right) \)

Encoded region and income groups as categorical features
Constructed model matrices with interaction terms

### 2. Statistical Modeling

Implemented three levels of linear models:

Basic model (birth, death, migration, region, income group)

Extended model with interaction terms

Reduced model selected using subset selection (BIC, Cp, adj-R²)

The reduced model achieved:

R² ≈ 0.466

Residual error ≈ 0.013

Nearly identical performance to the full extended model with fewer predictors

### 3. Model Diagnostics

Residual analysis by region

Coefficient magnitude plots

Predicted vs actual scatterplots

Cross-region error behavior

### 4. Forecasting

Generated 10-year projections for every country

Aggregated results by region

Visualized historical vs. forecasted population trends

### 5. Rolling-Window Cross-Validation

Evaluated forecasting accuracy at horizons 1, 5, and 10 years:

Horizon	MAPE	MALPE (Bias)
1 year	0.21%	-0.03
5 years	2.26%	0.45
10 years	6.14%	2.08

The model achieves excellent short-term accuracy and stable long-term behavior.

## 📁 Repository Structure
population_project/
│
├── Data-preprocessing.qmd        # Data cleaning & preparation
├── population_modeling.qmd       # Modeling, evaluation, forecasting
├── _quarto.yml                   # Quarto website configuration
├── _site/                        # Rendered website files (for GitHub Pages)
├── data/                         # Clean & raw datasets (if included)
└── README.md                     # Project documentation

## 🛠️ Technologies Used

R, Tidyverse, dplyr, ggplot2

leaps, glmnet, MASS

Quarto for documentation & publishing

World Bank & UN demographic data

## 🔮 Results Summary

Sub-Saharan Africa and the Middle East & North Africa show the strongest expected population increases.
Europe and North America exhibit stable, slow growth with small forecast error.
Interaction effects prove critical: demographic variables behave differently across income groups and regions.
The reduced model balances performance and simplicity, making it suitable for forecasting.