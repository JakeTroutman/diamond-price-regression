# Diamond Price Prediction: A Regression Analysis

Multiple linear regression analysis predicting diamond prices from physical and quality characteristics, built for PSTAT 126 (Regression Analysis) at UC Santa Barbara.

## Overview

Using a random sample of 1,000 diamonds drawn from a [53,943-observation Kaggle dataset](https://www.kaggle.com/datasets/nancyalaswad90/diamonds-prices), this project builds and refines a regression model to predict price from carat, cut, color, and clarity — testing and correcting for violations of linear regression assumptions along the way.

## Methods

- **Exploratory analysis** — summary statistics, histograms, and bar plots for all quantitative and categorical variables
- **Correlation analysis** — identified strong correlation between carat and physical dimensions (length, width, depth)
- **Simple linear regression** (`price ~ carat`) — baseline model, adjusted R² = 0.856
- **Assumption testing** — diagnosed heteroscedasticity and non-normality of residuals via residual, Q-Q, and scale-location plots
- **Log transformation** — corrected assumption violations and improved adjusted R² to 0.937
- **Outlier detection** — used Cook's Distance to identify and remove a data-entry error (a diamond with 0mm dimensions)
- **Model selection** — stepwise AIC in both directions to compare candidate models
- **Multicollinearity check** — Variance Inflation Factor (VIF) analysis to eliminate redundant physical-dimension predictors
- **Final model** — `log(price) ~ log(carat) + cut + clarity + color`, adjusted R² = 0.984
- **Inference** — confidence and prediction intervals for price estimates on specific diamond specifications

## Key Result

The final four-predictor model explains **98.4% of the variance** in diamond price, confirming that carat, cut, clarity, and color (the "4 C's" used in the diamond industry) are sufficient to predict price accurately — physical dimensions (length, width, depth) add no explanatory power once carat is included, since they are collinear with it.

## Files

- `PSTAT126-Final_Project.Rmd` — R Markdown source with all code, plots, and analysis
- `PSTAT126-Final_Project.pdf` — Knitted final report
- 'Final_Project.pdf' — Project Instructions

## Tools

R, ggplot2, dplyr, corrplot, car (VIF), MASS (stepAIC)
