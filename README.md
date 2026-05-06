# End-to-End Time Series Forecasting System with API

## Project Overview

This project is an end-to-end time series forecasting system developed to predict the next 8 weeks of sales for each state using historical sales data. The system combines statistical models, machine learning algorithms, deep learning techniques, and backend API integration to simulate a real-world production forecasting pipeline.

The project includes:

* Data preprocessing and cleaning
* Feature engineering
* Time-series forecasting
* Model comparison and evaluation
* REST API integration using FastAPI

---

# Objective

The main objective of this project is to forecast future sales for each state using historical sales records while handling:

* Missing values
* Missing dates
* Trend and seasonality
* Holiday effects
* Time-series dependencies

The system automatically compares multiple forecasting models and selects the best-performing model based on evaluation metrics.

---

# Technologies Used

| Technology         | Purpose                      |
| ------------------ | ---------------------------- |
| Python             | Programming Language         |
| Pandas             | Data Processing              |
| NumPy              | Numerical Operations         |
| Matplotlib         | Data Visualization           |
| Statsmodels        | SARIMA Forecasting           |
| Prophet            | Trend & Seasonal Forecasting |
| XGBoost            | Machine Learning Forecasting |
| TensorFlow / Keras | LSTM Deep Learning           |
| FastAPI            | REST API Development         |
| Scikit-learn       | Evaluation Metrics           |
| Joblib             | Model Saving                 |

---

# Dataset Description

The dataset contains historical sales information across multiple states.

## Dataset Columns

| Column   | Description       |
| -------- | ----------------- |
| state    | Name of the state |
| date     | Sales date        |
| sales    | Total sales value |
| category | Product category  |

---

# Data Preprocessing

The following preprocessing steps were performed:

* Date conversion using Pandas
* Handling invalid dates
* Numeric conversion of sales column
* Missing value handling
* Sorting data based on state and date
* Removal of invalid records

---

# Feature Engineering

Several time-series features were created to improve forecasting performance.

## Lag Features

* lag_1
* lag_7
* lag_30

## Rolling Features

* rolling_mean_7
* rolling_std_7

## Date Features

* day_of_week
* month
* week

## Holiday Feature

* is_holiday

These features helped models capture trend, seasonality, and historical dependencies.

---

# Forecasting Models Implemented

## 1. SARIMA

Classical statistical forecasting model capable of handling seasonality and trend.

## 2. Facebook Prophet

Business forecasting model that automatically captures seasonality and holiday effects.

## 3. XGBoost

Gradient boosting machine learning algorithm trained using engineered time-series features.

## 4. LSTM

Deep learning recurrent neural network model for sequential forecasting.

---

# Model Evaluation

The models were evaluated using:

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)

The best-performing model was selected based on minimum forecasting error.

---

# Forecast Visualization

The project includes visualizations such as:

* Sales trend analysis
* Actual vs Predicted graphs
* Forecast plots

---

# API Development

A FastAPI backend service was created to expose predictions through REST APIs.

## Example Endpoint

```bash
GET /forecast/{state}
```

## Example Response

```json
{
  "state": "Andhra Pradesh",
  "forecast": [
    {
      "date": "2025-09-01",
      "sales": 123456
    }
  ]
}
```

---

# Project Structure

```bash
sales-forecasting-system/
│
├── notebook/
│   └── forecasting.ipynb
│
├── api/
│   └── app.py
│
├── models/
│   └── best_model.pkl
│
├── outputs/
│   └── forecast_graphs.png
│
├── requirements.txt
│
└── README.md
```

---

# How To Run

## Install Dependencies

```bash
pip install -r requirements.txt
```

## Run Notebook

Open:

```bash
forecasting.ipynb
```

## Run API

```bash
uvicorn app:app --reload
```

---

# Results

The forecasting system successfully:

* Learned historical sales patterns
* Captured seasonality and trends
* Generated future sales forecasts
* Compared multiple forecasting models
* Served predictions through REST APIs

---

# Future Improvements

Possible future enhancements include:

* Hyperparameter tuning
* Real-time forecasting pipelines
* Cloud deployment
* Automated retraining
* Dashboard integration

---

# Conclusion

This project demonstrates a complete production-style forecasting workflow using machine learning, deep learning, and backend API integration. The solution provides scalable and accurate sales forecasting capabilities suitable for real-world business analytics applications.
