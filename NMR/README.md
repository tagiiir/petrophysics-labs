# Building T2 Spectra Using Least Squares and Regularization

## Task Description

The goal is to reconstruct the T2 relaxation time spectra from experimental relaxation curve data (amplitude vs time) using linear regression and regularized versions (Ridge, Lasso, ElasticNet).

**Input data:**
- `.prn` files containing two columns: `Time` (in microseconds) and `Amplitude` (in percent).
- Three samples: `И124.prn`, `И4529.prn`, `РБ122.prn`.

**Requirements:**
- Build the decay matrix based on a logarithmic grid of T2 values ranging from 0.1 to 1000 ms (~56 points).
- Train models to reconstruct the spectrum:
  - Standard Linear Regression (OLS)
  - Ridge Regression
  - Lasso Regression
  - ElasticNet Regression
- Tune model parameters using `GridSearchCV`.
- Visualize results:
  - Comparison of real and predicted amplitude.
  - Plot T2 spectra for all models.

## Code Structure

1. **Importing Libraries**
2. **Reading and Preprocessing Data**
3. **Building the Decay Matrix**
4. **Defining Models and Parameters**
5. **Training Models Using GridSearchCV**
6. **Selecting the Best Model Based on R²**
7. **Plotting Amplitude Fits and T2 Spectra**

## How to Use

1. Place the `И124.prn`, `И4529.prn`, `РБ122.prn` files in the appropriate directory.
2. Update the file paths in `file_path1`, `file_path2`, `file_path3` variables.
3. Run the script.

## Main Functions

- `build_decay_matrix(t, T2_values)`
  - Constructs the decay matrix \( \exp(-t/T2) \).

- `fit_best_model(X, y, model_dict, param_dict)`
  - Trains all models and selects the best based on cross-validation.

- `plot_amplitude_fit(t, amp, model, X, sample_name)`
  - Plots the real and predicted amplitude.

- `plot_T2_spectra(results, T2_values, sample_name)`
  - Plots T2 relaxation spectra for all models.

## Used Libraries

- `numpy`
- `pandas`
- `matplotlib`
- `scikit-learn`

## Notes

- Time is divided by 1000 **only once** when reading the data.
- Exponential decay matrix is used as feature matrix.
- Models are evaluated using 5-fold cross-validation (`cv=5`).
- Main performance metric is the R² score.

## Example Plots

- Relaxation curve plot (amplitude vs time)
- T2 spectra for LinearRegression, Ridge, Lasso, ElasticNet models