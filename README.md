# 🚖 Sprint 16 Project — Taxi Demand Forecasting with Time Series Machine Learning

---

## 🧠 Project Overview

In this project, I worked as a Data Scientist for **Sweet Lift Taxi**, a company seeking to improve driver availability during peak demand periods.

Using historical airport taxi order data, the objective was to develop a machine learning model capable of predicting the number of taxi requests expected during the next hour.

This project introduces **time series forecasting**, feature engineering based on temporal patterns, and predictive modeling for operational planning.

The primary evaluation metric was **RMSE (Root Mean Squared Error)**, with a project requirement of achieving:

✅ **RMSE ≤ 48** on the test dataset.

---

## 🎯 Project Objectives

* Load and prepare historical taxi order data.
* Resample time series data into hourly intervals.
* Analyze trends, seasonality, and temporal patterns.
* Create time-based predictive features.
* Train and compare multiple forecasting models.
* Optimize model hyperparameters.
* Evaluate models using RMSE.
* Select the best-performing model for future demand prediction.

---

## 📁 Dataset Description

**File:** `taxi.csv`

The dataset contains historical taxi orders collected at airports.

### Features

| Column     | Description                  |
| ---------- | ---------------------------- |
| datetime   | Timestamp of the observation |
| num_orders | Number of taxi orders        |

### Target Variable

| Column     | Description                                |
| ---------- | ------------------------------------------ |
| num_orders | Number of taxi orders during the next hour |

---

## 🧩 Project Workflow

### Step 1 — Data Preparation

* Loaded the dataset.
* Converted timestamps to datetime format.
* Set the datetime column as the index.
* Sorted observations chronologically.
* Resampled data into hourly intervals.
* Verified data consistency after aggregation.

---

### Step 2 — Exploratory Data Analysis

Analyzed the behavior of taxi demand over time.

Key areas explored:

* Overall demand trend.
* Daily demand patterns.
* Weekly seasonality.
* Peak and low-demand periods.
* Variability in taxi requests.

Visualization techniques included:

* Time series plots.
* Rolling averages.
* Trend analysis.

---

### Step 3 — Feature Engineering

Created predictive features based on historical observations.

Examples include:

#### Lag Features

Previous demand values:

```python
lag_1
lag_24
lag_48
```

These features help the model learn recurring patterns.

#### Rolling Statistics

Calculated rolling metrics such as:

* Rolling mean
* Rolling standard deviation

to capture local demand trends.

#### Date-Time Features

Extracted:

* Hour of day
* Day of week
* Month

to identify temporal demand behavior.

---

### Step 4 — Train/Test Split

Since this is a time series problem:

* Random shuffling was avoided.
* The final 10% of observations were reserved for testing.
* Earlier observations were used for training and validation.

This approach preserves chronological order and prevents data leakage.

---

## 🤖 Models Evaluated

Several machine learning algorithms were trained and compared.

### 1. Linear Regression

Used as a baseline forecasting model.

Advantages:

* Fast training.
* Simple interpretation.
* Useful benchmark.

---

### 2. Decision Tree Regressor

Hyperparameters explored:

* max_depth
* min_samples_split
* min_samples_leaf

Advantages:

* Captures nonlinear relationships.
* Easy to interpret.

---

### 3. Random Forest Regressor

Hyperparameters explored:

* n_estimators
* max_depth
* min_samples_leaf

Advantages:

* Strong predictive performance.
* Robust against overfitting.

---

### 4. Gradient Boosting Models

Models such as:

* LightGBM
* CatBoost
* XGBoost *(optional)*

were evaluated to improve forecasting accuracy.

Advantages:

* High predictive power.
* Effective handling of complex temporal relationships.

---

## 📊 Evaluation Metric

### RMSE (Root Mean Squared Error)

The primary metric used for model evaluation.

Formula:

```text
RMSE = √(Σ(y_true − y_pred)² / n)
```

Lower RMSE values indicate more accurate forecasts.

Project requirement:

✅ RMSE ≤ 48

---

## 🔍 Model Selection

Models were compared using:

* Cross-validation performance.
* Validation RMSE.
* Test RMSE.
* Computational efficiency.

The best model was selected based on its ability to accurately forecast future taxi demand while maintaining stable performance on unseen data.

---

## 📈 Forecasting Insights

The analysis revealed several important patterns:

* Demand varies significantly throughout the day.
* Airport traffic creates recurring peak hours.
* Historical demand strongly influences future demand.
* Seasonal and cyclical behavior can be leveraged to improve forecasts.

These findings improve operational planning and driver allocation.

---

## 💡 Business Impact

Accurate taxi demand forecasting enables Sweet Lift Taxi to:

* Improve driver scheduling.
* Reduce passenger wait times.
* Increase service availability during peak periods.
* Optimize operational efficiency.
* Improve customer satisfaction.

Machine learning-based forecasting helps ensure that sufficient drivers are available when demand increases.

---

## 🧰 Tools & Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* LightGBM
* CatBoost
* XGBoost
* Statsmodels
* Jupyter Notebook

---

## 📚 Machine Learning Concepts Applied

* Time Series Forecasting
* Regression Modeling
* Feature Engineering
* Lag Features
* Rolling Statistics
* Temporal Data Analysis
* Hyperparameter Tuning
* Cross-Validation
* RMSE Optimization
* Demand Forecasting

---

## 👤 Author

**Jonathan Peña**
