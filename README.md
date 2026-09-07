# Store Sales Forecasting

A machine learning project focused on predicting daily store sales using historical sales patterns, store information, promotions, and calendar features.

The project explores how feature engineering and time-aware validation can improve sales forecasting performance.

## Project Status

✅ Completed baseline forecasting project

The project established and evaluated forecasting models, compared their performance, and saved the trained Random Forest model.

## Objective

Predict daily sales for stores using historical and operational information.

The main objective was to understand:

- Which features contribute most to sales prediction
- How historical sales patterns affect future sales
- Whether nonlinear models outperform a linear baseline
- How model performance changes across different time periods

## Dataset

The project uses a store-sales forecasting dataset containing:

- `train.csv`
- `test.csv`
- `store.csv`
- `sample_submission.csv`

The training dataset contains approximately 1 million observations across 1,115 stores.

## Project Workflow

1. Loaded and inspected the datasets
2. Merged sales data with store information
3. Converted dates into datetime format
4. Sorted observations chronologically by store and date
5. Performed exploratory data analysis
6. Created historical sales features
7. Created rolling sales features
8. Trained a Linear Regression baseline
9. Trained a Random Forest Regressor
10. Evaluated models using temporal cross-validation
11. Compared MAE, RMSE, and R²
12. Saved the trained model and feature list

## Feature Engineering

The final Random Forest experiment used the following seven features:

- `Open`
- `Sales_Lag_14`
- `Sales_Lag_7`
- `Sales_Rolling_14`
- `Sales_Rolling_7`
- `Day`
- `Promo`

### Feature descriptions

| Feature | Description |
|---|---|
| `Open` | Indicates whether the store was open |
| `Sales_Lag_7` | Sales from seven days earlier |
| `Sales_Lag_14` | Sales from fourteen days earlier |
| `Sales_Rolling_7` | Rolling sales statistic over the previous seven days |
| `Sales_Rolling_14` | Rolling sales statistic over the previous fourteen days |
| `Day` | Day of the month |
| `Promo` | Indicates whether a promotion was active |

These features capture recent sales behavior, short-term trends, store operating status, calendar information, and promotional effects.

## Models

### Linear Regression

Linear Regression was used as the baseline model.

It provided a simple reference point for evaluating whether more complex models could improve forecasting performance.

### Random Forest Regressor

Random Forest was used to model nonlinear relationships between the engineered features and daily sales.

The model was trained using:

```python
RandomForestRegressor(
    n_estimators=100,
    random_state=42,
    n_jobs=-1
)
