# Capillary Model Analysis

## Overview
This project implements a comprehensive capillary model analysis for predicting petrophysical properties of porous media using five different mathematical models. The goal is to accurately model and predict parameters related to relative permeability using capillary pressure data.

---

## Features
- Data Loading and Preprocessing:
  - Reads data from an Excel file.
  - Cleans data by handling NaN values and correcting column names.
  - Supports numerical columns for pressure and permeability values.

- Model Calculation:
  - **Brooks-Corey Model:** Calculates relative permeability using the formula:
    \[
    K_v = K_{vo} \left(\frac{Pc}{Pc_{вх}}\right)^{-n}
    \]
  - **Kinetic Model:** Uses a non-linear approach to model the relationship between pressure and permeability:
    \[
    K_v = K_{vo} + \frac{(Pc - Pc_{вх})}{(Pd - Pc) \cdot a} ^{\frac{1}{b}}
    \]
  - **Trigonometric Model:** Models permeability using a trigonometric approach:
    \[
    K_v = K_{vo} + (100 - K_{vo}) \left(\frac{\pi / 2 - \arctan((Pc - A) / B)}{\pi}\right)^{1 / C}
    \]
  - **Polynomial Model:** Fits a polynomial curve to model the relationship:
    \[
    K_v = a \cdot Pc^2 + b \cdot Pc + c
    \]
  - **Custom Regression Model:** Applies linear regression to predict key parameters:
    - \( a \), \( b \), \( K_{vo} \), \( Pc_{вх} \).

- Visualization:
  - Generates scatter plots for each model.
  - Plots predicted vs. actual values for model validation.
  - Compares the performance of all five models on a single plot.

- Error Calculation:
  - Computes Mean Absolute Percentage Error (MAPE) for each model to evaluate accuracy.

---

## Installation
Ensure that you have Python installed with the necessary libraries:
```bash
pip install pandas numpy matplotlib scikit-learn scipy
