# TurboImpute

`TurboImpute` is a Python library for handling missing values in datasets. It provides tools for detecting, analyzing, imputing, and visualizing missing data.

## Installation

```bash
pip install TurboImpute

```

or 

```bash
git clone https://github.com/yourusername/TurboImpute.git
cd TurboImpute
pip install .
```


# Usage

To use `TurboImpute`, follow these steps:

```python
import pandas as pd
import TurboImpute as tp

# Load your dataset
df = pd.read_csv('your_dataset.csv')

# Detect missing values
missing_summary = tp.missing_summary(df)
print(missing_summary)

# Impute missing values using mean
df = tp.impute_mean(df, columns=['column1', 'column2'])

# Remove rows with missing values
df = tp.drop_missing_rows(df, threshold=0.5)

# Visualize missing values (boxplot for numerical variables)
tp.visualize_missing(df)

# Check best imputation method
best_method, errors = tp.check_best_method(df, columns=['column1', 'column2'])
print(f"Best imputation method: {best_method}")
print(f"Errors: {errors}")
```


# Functions Available

## Detection (`TurboImpute.detection`)

- `identify_missing(df)`: Identifies missing values in the dataframe.
- `missing_summary(df)`: Provides a summary of missing values in the dataframe.

## Imputation (`TurboImpute.imputation`)

- `impute_mean(df, columns=None)`: Imputes missing values using mean.
- `impute_median(df, columns=None)`: Imputes missing values using median.
- `impute_mode(df, columns=None)`: Imputes missing values using mode.
- `impute_value(df, value, columns=None)`: Imputes missing values with a specified value.
- `impute_ml(df, method='knn', columns=None, **kwargs)`: Imputes missing values using machine learning methods such as KNN, Decision Tree, or GBM.
- `impute_knn(df, columns=None, n_neighbors=5)`: Imputes missing values using K-Nearest Neighbors.
- `impute_dt(df, columns=None, **kwargs)`: Imputes missing values using Decision Tree regression.
- `impute_gbm(df, columns=None, **kwargs)`: Imputes missing values using Gradient Boosting regression.

## Removal (`TurboImpute.removal`)

- `drop_missing_rows(df, threshold=0.5)`: Drops rows with missing values based on a threshold.
- `drop_missing_columns(df, threshold=0.5)`: Drops columns with missing values based on a threshold.

## Visualization (`TurboImpute.visualization`)

- `visualize_missing(df)`: Visualizes missing values using boxplots for numerical variables.

## Recommendation (`TurboImpute.recommendation`)

- `check_best_method(df, columns=None, test_size=0.2, random_state=42)`: Determines the best imputation method to use based on mean squared error evaluation.


# License

This project is licensed under the MIT License. See the LICENSE file for details.
