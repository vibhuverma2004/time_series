# Time Series Forecasting

This project focuses on predicting energy usage in megawatts (MW) using time series forecasting techniques. The dataset consists of hourly energy consumption data. The project demonstrates the process of preparing data, creating features, building an XGBoost regression model, and evaluating its performance.

## Project Overview

### Data Preparation

1. **Data Loading**: 
   - The data is loaded from a CSV file named `hourly.csv`.
   - The `Datetime` column is set as the index, and the index is converted to a datetime format.

2. **Data Visualization**: 
   - A time series plot of energy usage is generated to observe trends and patterns.
   - The dataset is split into a training set (data before 01-01-2015) and a test set (data from 01-01-2015 onwards).

### Feature Engineering

Features are created based on the time series index:

- **Hour of the Day** (`hour`)
- **Day of the Week** (`dayofweek`)
- **Quarter of the Year** (`quarter`)
- **Month of the Year** (`month`)
- **Year** (`year`)
- **Day of the Year** (`dayofyear`)
- **Day of the Month** (`dayofmonth`)
- **Week of the Year** (`weekofyear`)

### Data Visualization

The relationship between the target variable (`PJME_MW`) and the generated features is visualized using box plots:

- **MW by Hour**
- **MW by Month**

### Model Building

An XGBoost regression model is used to forecast energy usage:

- **Features**: `dayofyear`, `hour`, `dayofweek`, `quarter`, `month`, `year`
- **Target**: `PJME_MW`
- The model is trained on the training set and evaluated on the test set.

### Model Evaluation

- **Feature Importance**: A bar plot of feature importance is generated to understand which features contribute the most to the model's predictions.
- **Predictions**: The model's predictions are plotted against the actual values.
- **RMSE Score**: The Root Mean Squared Error (RMSE) is calculated to evaluate the model's performance on the test set.

### Error Analysis

- The absolute error between the predictions and the actual values is calculated.
- The days with the highest average error are identified to analyze the model's performance on the worst-predicted days.

## Results

- **RMSE Score on Test Set**: The RMSE score is a measure of the model's accuracy. The lower the score, the better the model's predictions.
- **Feature Importance**: Understanding the importance of different features helps in improving the model and selecting relevant features for future models.

## Conclusion

This project demonstrates the process of building a time series forecasting model, from data preparation and feature engineering to model evaluation and error analysis. The XGBoost model provides a reliable method for predicting energy usage, but further tuning and experimentation with different models could potentially improve the results.

## Dependencies

- Python 3.x
- Pandas
- NumPy
- Matplotlib
- Seaborn
- XGBoost
- Scikit-learn

## Running the Project

1. Clone the repository.
2. Ensure all dependencies are installed.
3. Run the Jupyter notebook or Python script to see the results.

## Acknowledgments

- The dataset used for this project.
- The XGBoost library for providing powerful tools for machine learning.
