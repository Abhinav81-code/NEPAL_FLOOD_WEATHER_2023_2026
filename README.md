# NEPAL_FLOOD_WEATHER_2023_2026

# 🌊 Nepal Flood & Weather Prediction Using Machine Learning

## 📌 Project Overview

The **Nepal Flood & Weather Prediction Project** is a Machine Learning project that analyzes historical weather conditions and river discharge data from 10 river monitoring stations across Nepal (January 2023 – August 2026).

The project focuses on predicting next-day river discharge and identifying potential high-flow conditions using historical weather, rainfall, and hydrological data.

It includes two major prediction tasks:

- **Regression:** Predict the next day's river discharge (m³/s).
- **Classification:** Identify whether the next day will experience high river flow (1) or normal river flow (0).

The project also explores rainfall-discharge relationships, seasonal patterns, unusual river-flow events, and model performance.

## 🎯 Project Objectives

- Analyze historical weather and river discharge data.
- Perform Exploratory Data Analysis (EDA).
- Understand rainfall and river discharge relationships.
- Identify seasonal and monthly river-flow patterns.
- Engineer meaningful features using historical data.
- Predict next-day river discharge using regression models.
- Classify high-flow and normal-flow conditions.
- Compare machine learning models using evaluation metrics.
- Identify the most important features influencing predictions.

## 📂 Dataset Information

| Description | Details |
|---|---|
| Dataset | Nepal Flood & Weather Dataset |
| Data Period | January 2023 – August 2026 |
| Total Records | 13,390 |
| Total Features | 19 |
| River Stations | 10 |
| Missing Values | 0 |
| Duplicate Records | 0 |
| Target Variable | `river_discharge_m3s` |

### River Monitoring Stations

- Kusum
- Belsot
- Chameliya/Nayalbadi
- Bahrabise
- Devghat
- Khokana
- Chatara
- Rasuwagadhi
- Chisapani
- Bhada Bridge

### Important Dataset Features

**Weather Features**
- Precipitation
- Rainfall
- Temperature
- Dew Point
- Soil Moisture
- Relative Humidity
- Wind Speed
- Wind Gusts
- Wind Direction

**Hydrological Features**
- River Discharge
- River Station
- River Basin
- Location
- Elevation

**Engineered Features**
- Rainfall Lag Features (1, 2, 3 Days)
- Rolling Rainfall (3-Day and 7-Day)
- Discharge Lag Features
- Day of Year
- Day of Week
- Monthly Cyclical Features

## 🛠️ Technologies & Tools Used

| Technology | Purpose |
|---|---|
| Python | Programming Language |
| Pandas | Data Manipulation |
| NumPy | Numerical Computing |
| Matplotlib | Data Visualization |
| Seaborn | Statistical Visualization |
| Scikit-learn | Machine Learning |
| Joblib | Model Saving and Loading |
| Jupyter Notebook | Development Environment |

## 🔄 Project Workflow

1. **Data Loading & Inspection** – Load the dataset and inspect its structure, data types, missing values, and duplicates.

2. **Exploratory Data Analysis (EDA)** – Analyze river discharge distribution, rainfall relationships, station-wise patterns, and seasonal trends.

3. **Data Preprocessing** – Handle dates, prepare features, and organize the dataset for machine learning.

4. **Feature Engineering** – Create rainfall lags, rolling rainfall statistics, historical discharge features, and calendar features.

5. **Target Variable Creation** – Generate the next-day river discharge target using historical observations.

6. **Train-Test Splitting** – Apply an 80:20 chronological split to avoid mixing future and past records.

7. **Regression Modelling** – Train and compare multiple regression algorithms.

8. **Classification Modelling** – Predict high-flow and normal-flow conditions.

9. **Model Evaluation** – Evaluate models using regression and classification metrics.

10. **Results & Export** – Save the trained models, prediction results, and analysis outputs.

## 🤖 Machine Learning Models

### 1. Regression Models

The following algorithms are implemented to predict next-day river discharge:

- Linear Regression
- Random Forest Regressor
- Gradient Boosting Regressor

### Regression Performance

| Model | MAE | RMSE | R² Score |
|---|---:|---:|---:|
| Gradient Boosting | 4.16 | 24.37 | 0.829 |
| Linear Regression | 11.66 | 24.63 | 0.825 |
| Random Forest | 3.82 | 27.05 | 0.789 |

**Best Regression Model: Gradient Boosting Regressor**

It achieved the lowest RMSE of 24.37 and an R² score of 0.829 on the test dataset.

### 2. Classification Models

The classification task identifies high-flow and normal-flow conditions.

Models implemented:

- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier

### Classification Performance

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---:|---:|---:|---:|
| Random Forest | 0.958 | 0.640 | 0.792 | 0.708 |
| Decision Tree | 0.883 | 0.353 | 0.971 | 0.518 |
| Logistic Regression | 0.846 | 0.296 | 1.000 | 0.456 |

**Best Classification Model: Random Forest Classifier**

It achieved an F1 score of 0.708, providing the best balance between precision and recall among the tested classifiers.

High-flow conditions are defined using the station-specific 90th percentile of training-period river discharge.

## 📊 Key Findings

- Kusum recorded the highest average river discharge, approximately 125.8 m³/s.
- Monsoon season recorded the highest average discharge.
- August was identified as the month with the highest average discharge.
- Same-day rainfall showed a weak Pearson correlation with river discharge (approximately 0.10).
- Dew point showed the strongest individual weather correlation (approximately 0.23).
- Previous-day river discharge (`discharge_lag1`) contributed approximately 70% of the Gradient Boosting model's feature importance.
- Feature engineering improved the reported RMSE from 28.22 to 24.37 (13.66%).

## 📈 Model Evaluation Metrics

**Regression Metrics**
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

**Classification Metrics**
- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

## 📁 Project Structure

```text
Nepal-Flood-Weather-Prediction/
│
├── NEPAL_FLOOD_WEATHER_2023_2026.ipynb
│
├── Nepal Flood & Weather Prediction Project Documentation.docx
│
├── CORRECTED_2023_2026_NEPAL_FLOOD_WEATHER_KAGGLE.csv
│
├── nepal_flood_outputs/
│   ├── cleaned_feature_engineered_dataset.csv
│   ├── regression_model_comparison.csv
│   ├── classification_model_comparison.csv
│   ├── regression_predictions_and_errors.csv
│   ├── location_prediction_errors.csv
│   ├── high_flow_thresholds.csv
│   ├── best_regression_model.joblib
│   └── best_high_flow_classifier.joblib
│
└── README.md
```

*Note: The dataset and output files must be added separately if they are not included in the repository.*

## ⚙️ Installation & Setup

### Step 1: Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git
```

### Step 2: Navigate to the Project Folder

```bash
cd YOUR_REPOSITORY_NAME
```

### Step 3: Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib jupyter
```

### Step 4: Add the Dataset

Place the following CSV file in the same directory as the Jupyter Notebook:

```text
CORRECTED_2023_2026_NEPAL_FLOOD_WEATHER_KAGGLE.csv
```

### Step 5: Run the Jupyter Notebook

```bash
jupyter notebook
```

Open `NEPAL_FLOOD_WEATHER_2023_2026.ipynb` and execute all cells from top to bottom.

### Step 6: Access the Results

After successful execution, the notebook automatically creates:

```text
nepal_flood_outputs/
```

This folder contains the trained models, prediction results, comparison tables, and processed datasets.

## ⚠️ Limitations

- The model relies on historical weather and river discharge observations.
- Unprecedented extreme flood events may not be predicted accurately.
- Extreme river-flow events are underrepresented in the dataset.
- Prediction errors are significantly higher at the Kusum station.
- High-flow classification uses a statistical 90th-percentile threshold, not an official flood-warning threshold.
- The model has not been tested using forecasted next-day weather observations.
- Test performance is based on a single nine-month period and may vary across other periods.

**Important:** This project is an academic and analytical machine learning project. It is not an operational flood-warning or disaster-management system.

## 🚀 Future Improvements

- Implement time-series cross-validation.
- Perform hyperparameter tuning.
- Experiment with XGBoost, LightGBM, and other advanced models.
- Improve predictions for extreme river-flow events.
- Develop a real-time flood monitoring dashboard.
- Integrate weather forecast data.
- Build a web application using Streamlit.
- Explore station-specific prediction models.

## 👨‍💻 Author

**Abhinav M**

B.Sc. Computer Science | Machine Learning & Data Analytics

GitHub: https://github.com/Abhinav81-code

---

⭐ If you find this project useful, consider giving this repository a star!
