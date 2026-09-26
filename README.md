# Sales & Demand Forecasting

A machine learning project that predicts store sales using historical sales, promotions, store activity, and time-based features.

## Approach

* Performed data preprocessing and exploratory analysis
* Created lag, rolling, trend, volatility, and demand-related features
* Used chronological data splitting to preserve the time-series structure
* Compared different feature sets and regression models
* Used **Random Forest Regressor** for the final model
* Performed time-based cross-validation to evaluate model stability
* Tested the final model on unseen data

## Final Model

**Random Forest Regressor**

Key features include:

* Previous sales values
* Rolling sales averages
* Promotion information
* Store operating status
* Calendar features
* Demand trend, volatility, and stability features

## Results

* **Test R²:** ~94%
* **Time-based Cross-Validation R²:** ~92–94%

The similar performance across the unseen test set and time-based validation folds indicates that the model maintains consistent performance across different time periods.

## Tech Stack

Python • Pandas • NumPy • Scikit-learn • Matplotlib

## Status

**Completed** — feature engineering, model development, cross-validation, stability analysis, and final evaluation completed.
