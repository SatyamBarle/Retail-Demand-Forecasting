#  Retail Demand Forecasting using LightGBM & XGBoost

A machine learning project that predicts daily retail product demand across multiple stores using gradient boosting algorithms. The objective is to build an accurate forecasting pipeline that helps retailers optimize inventory planning, reduce stock shortages, and improve supply chain decisions.

---

##  Project Overview

Demand forecasting plays a critical role in retail operations. Overstocking increases inventory holding costs, while understocking results in lost sales and poor customer experience.

In this project, I developed an end-to-end demand forecasting pipeline using **LightGBM** and **XGBoost**. The workflow includes exploratory data analysis, leakage detection, feature engineering, chronological model validation, performance evaluation, and interpretation of model predictions.

The project focuses on learning meaningful demand patterns from historical sales data while ensuring that the forecasting pipeline reflects a realistic production scenario.

---

##  Objectives

- Forecast daily retail demand for multiple products and stores
- Understand demand patterns using exploratory data analysis
- Prevent data leakage during model training
- Engineer meaningful temporal and historical demand features
- Compare LightGBM and XGBoost models
- Evaluate forecasting performance using regression metrics
- Interpret model behavior using feature importance analysis

---

##  Dataset

**Dataset Type:** Multi-store, Multi-product Retail Demand Dataset

The dataset contains historical retail information including:

- Store information
- Product details
- Historical demand
- Pricing information
- Promotional activities
- Seasonal information
- Date-based features

**Prediction Target**

Daily product demand.

---

## Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- LightGBM
- XGBoost

---

# Project Workflow

```
Data Collection
        │
        ▼
Data Cleaning
        │
        ▼
Leakage Detection
        │
        ▼
Exploratory Data Analysis
        │
        ▼
Feature Engineering
        │
        ▼
Time-based Train/Validation Split
        │
        ▼
LightGBM Model
        │
        ▼
XGBoost Model
        │
        ▼
Performance Evaluation
        │
        ▼
Feature Importance Analysis
        │
        ▼
Demand Forecast Visualization
```

---

#  Exploratory Data Analysis

The exploratory analysis focuses on understanding demand behaviour before model development.

Key analyses include:

- Demand distribution
- Seasonal demand trends
- Correlation analysis
- Feature relationships
- Leakage identification

<img width="1192" height="691" alt="image" src="https://github.com/user-attachments/assets/0c879827-a3a5-4fdd-a712-dfe556b1a055" />

>  Demand Distribution

---
<img width="882" height="732" alt="image" src="https://github.com/user-attachments/assets/6d3318f9-c9ed-4d1f-9b82-ced2ce8e4fa0" />

> Correlation Heatmap

---

##  Data Leakage Detection

Before model training, potential leakage variables were identified.

Features such as **Units Sold** and **Units Ordered** showed extremely strong correlations with the target variable. Since these values would not be available during future prediction, they were removed from the training dataset to ensure realistic forecasting performance.

---

#  Feature Engineering

To improve predictive performance, several feature groups were created.

### Temporal Features

- Day of Week
- Month
- Quarter
- Week of Year
- Weekend Indicator

### Historical Demand Features

- Lag 1
- Lag 7
- Lag 14
- Lag 28

### Rolling Window Features

- Rolling Mean
- Rolling Standard Deviation

### Pricing Features

- Discount Features
- Competitor Price Difference

### Encoded Categorical Features

- Store
- Product
- Region
- Category
- Season
- Weather

These engineered features allow the models to capture seasonality, recent demand behaviour, and pricing effects more effectively.

---

##  Time-Series Validation

Unlike conventional machine learning problems, retail forecasting requires preserving chronological order.

Instead of randomly splitting the data, a **time-based validation strategy** was used so that the model only learns from historical information while being evaluated on future observations.

This prevents data leakage and better simulates real-world forecasting.

---

# Models Used

## LightGBM

LightGBM is a histogram-based gradient boosting algorithm optimized for speed and efficiency on structured datasets.

Advantages:

- Fast training
- Low memory usage
- Excellent performance on tabular data

---

## XGBoost

XGBoost is one of the most widely used boosting algorithms for predictive analytics.

Advantages:

- Strong regularization
- High predictive accuracy
- Robust handling of nonlinear relationships

---

#  Model Evaluation

Model performance was evaluated using:

- RMSE
- MAE
- R² Score

Both models demonstrated strong forecasting capability, with feature engineering contributing significantly to prediction performance.

<img width="1022" height="375" alt="image" src="https://github.com/user-attachments/assets/2e61e48e-4139-403d-bf5d-22494a0fa7a6" />

> Model Performance Comparison

---

#  Feature Importance

Feature importance analysis was used to understand which variables contributed most to forecasting performance.

Historical demand features consistently ranked among the most influential predictors, followed by temporal variables.

<img width="1157" height="512" alt="image" src="https://github.com/user-attachments/assets/a5e399ac-25bc-4dee-ac3c-e0800fcd4713" />

>  Feature Importance Plot

---

#  Forecast Visualization

The predicted demand closely follows the overall demand trend while capturing seasonal fluctuations.

Although sudden demand spikes remain challenging, both models successfully learn the underlying purchasing patterns.

<img width="1123" height="401" alt="image" src="https://github.com/user-attachments/assets/da913808-48f8-44f0-ab2e-02c9fc63a760" />


>  Actual vs Predicted Demand

---

#  Business Impact

Accurate retail demand forecasting can help businesses:

- Reduce stock shortages
- Minimize excess inventory
- Improve warehouse planning
- Optimize replenishment schedules
- Improve customer satisfaction
- Reduce inventory holding costs

Although this project uses a public dataset, the workflow can be adapted for real-world inventory planning and supply chain optimization.

---

#  Future Improvements

Potential improvements include:

- Holiday and festival calendars
- Weather forecast integration
- Hyperparameter optimization using Optuna
- Deep learning models (LSTM / TFT)
- Automated retraining pipeline
- Model deployment using FastAPI and Docker

---

## 👨‍💻 Author

**Satyam Barle**

Machine Learning • Backend Development • Data Engineering
