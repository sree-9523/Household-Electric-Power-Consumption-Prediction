# **_Household Power Consumption Analysis and Prediction_**
This project analyzes household power consumption data and builds predictive models to forecast power usage.

## **Dataset Source**
The data is sourced from the UCI Machine Learning Repository: Individual household electric power consumption Data Set. The measurements were collected between December 2006 and November 2010 (47 months).

## **Dataset Description**
The dataset contains measurements of electric power consumption in one household with a one-minute sampling rate over a period of time. Features include:
  - Date and Time stamps
  - Global active/reactive power
  - Global intensity
  - Sub-metering readings (1-3)

## **Project Structure**
### 1. Data Exploration
  * Analysis of data shape (2,075,259 rows × 9 columns)
  * Missing value analysis (1.25% missing values)
  * Data type examination and conversion
  * Data type examination and conversion

### 2. Data Preprocessing
  * Handling missing values
  * Feature engineering:
      - Time-based features (Hour, Day, Month, DayOfWeek)
      - Binary features (Is_weekend, Is_peak_hour)
      - Aggregated features (Total_submetering, Unmetered_power)
  * Outlier detection and removal
  * Data normalization
    
### 3.  Modeling
Three models were implemented and compared:

#### Linear Regression
  * Perfect scores indicated unsuitability for non-linear power consumption patterns

#### Random Forest
  - Initial metrics:
    - Test RMSE: 0.014
    - Test R² Score: 0.999
    - Train RMSE: 0.005
    - Train R² Score: 0.999

  - After optimization:
    - Test RMSE: 0.018
    - Test R² Score: 0.999
    - Train RMSE: 0.015
    - Train R² Score: 0.999

  - Hyperparameters:
    - max_depth: 15
    - min_samples_leaf: 2
    - min_samples_split: 4
    - n_estimators: 100

#### XGBoost
  - Initial metrics:
    - Test RMSE: 0.017
    - Test R² Score: 0.999
    - Train RMSE: 0.017
    - Train R² Score: 0.999

  - After optimization:
    - Test RMSE: 0.011
    - Test R² Score: 0.999
    - Train RMSE: 0.009
    - Train R² Score: 0.999

  - Hyperparameters:
    - max_depth: 9
    - learning_rate: 0.1
    - n_estimators: 300
    - subsample: 0.8
    - min_child_weight: 5

## **Key Findings**
  1. Strong negative correlation between power consumption and voltage
  2. XGBoost outperformed other models in prediction accuracy
  3. Successful handling of temporal patterns in power consumption
  4. High model generalization with minimal train-test performance gap

## **Dependencies**
  * pandas
  * numpy
  * scikit-learn
  * xgboost
  * matplotlib
  * seaborn


