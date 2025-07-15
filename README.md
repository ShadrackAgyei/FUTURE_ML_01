# FUTURE_ML_01
AI POWERED SALES FORECASTING DASHBOARD
# Retail Sales Forecasting Project

This project focuses on forecasting retail sales using time series analysis techniques in Python. The goal is to build a predictive model that can help understand sales trends, identify seasonality, and forecast future sales.

## Table of Contents

- [Introduction](#introduction)
- [Data](#data)
- [Methodology](#methodology)
- [Results and Evaluation](#results-and-evaluation)
- [Insights](#insights)
- [Future Work](#future-work)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [License](#license)
- [Contact](#contact)

## Introduction

Accurate sales forecasting is crucial for businesses to manage inventory, plan marketing strategies, and make informed decisions. This project utilizes time series analysis to predict future retail sales, providing insights into historical patterns and potential future trends. The Prophet library, developed by Facebook, is employed for its ability to handle various time series characteristics like seasonality and holidays.

## Data

The dataset used for this project is loaded from a CSV file named `mock_kaggle.csv`. This dataset contains historical retail sales data.

- **Source:** `mock_kaggle.csv`
- **Content:** Time series data representing retail sales (`venda`).
- **Key Columns:** The dataset has a datetime index representing the time of the sales, and a column named 'venda' representing the sales value.
- **Time Period:** The data covers a specific time period, which can be observed from the data exploration phase.

## Methodology

The project follows a standard time series forecasting workflow:

1.  **Data Loading and Exploration:** The `mock_kaggle.csv` file is loaded into a pandas DataFrame, with the first column set as the datetime index. The initial sales data is visualized to observe overall trends and patterns.
2.  **Feature Engineering:** New features are created from the datetime index to capture temporal information. These include hour, day of week, weekday name, quarter, month, year, day of year, day of month, week of year, and season. This helps the model identify patterns related to specific times or periods.
3.  **Train/Test Split:** The dataset is split into training and testing sets based on a specified date (`1-Jan-2015`). Data before this date is used for training, and data after is used for testing the model's performance on unseen data.
4.  **Model Selection:** The Prophet library is chosen for its robustness in handling time series data with strong seasonality and holiday effects.
5.  **Model Training:** A Prophet model is initialized with default parameters and trained on the preprocessed training data (`pjme_train_prophet`), which is formatted with 'ds' (datestamp) and 'y' (sales) columns.
6.  **Forecasting:** The trained model is used to generate forecasts on the test dataset (`pjme_test_prophet`).
7.  **Evaluation:** The performance of the forecast is evaluated against the actual sales in the test set using the Root Mean Squared Error (RMSE) and Mean Absolute Percentage Error (MAPE) metrics. A custom MAPE function is used to handle potential zero values in the actual data.
8.  **Visualization:** Visualizations are created to compare the Prophet forecast with the actual sales data, both for the entire test period and for a zoomed-in period (e.g., January 2015). The components of the Prophet forecast (trend, seasonality) are also visualized. Monthly and yearly sales comparisons are made on the historical data.

## Results and Evaluation

The Prophet model was trained and evaluated on the test set.

- **RMSE:** The Root Mean Squared Error is calculated to quantify the average magnitude of the forecast errors.
- **MAPE:** The Mean Absolute Percentage Error is calculated to provide a percentage-based measure of forecast accuracy, particularly useful for understanding the error relative to the actual sales values.

*(To provide specific RMSE and MAPE values here, you would need to run the code and get the output of the evaluation metrics. You can manually add those values after running the notebook.)*

The visualizations show how well the Prophet model's forecast aligns with the actual sales data, highlighting the model's ability to capture the general trend and seasonal patterns.

## Insights

Based on the data analysis and forecasting, the following insights were observed:

- **Seasonal Patterns:** The boxplot of sales by weekday and season indicates clear seasonal variations in sales. Sales tend to be lower during the Winter season compared to others.
- **Monthly and Yearly Trends:** Analysis of monthly and yearly sales highlights the overall sales trajectory and year-over-year comparisons.
- **Model Performance:** The RMSE and MAPE values provide a quantitative measure of the model's forecasting accuracy on the test set.

*(If your data contained an 'item' column, you could add insights about top-selling items here as well, based on the code provided in your notebook.)*

An insight card summarizes key performance metrics:
- Overall Average Daily Sales
- RMSE of the Prophet Model on the Test Set
- MAPE of the Prophet Model on the Test Set
- An observation about the low sales in the Winter season.

## Future Work

Future enhancements for this project could include:

- **Incorporating Holiday Effects:** Explicitly defining holidays in the Prophet model to see if it improves forecast accuracy.
- **Adding Regressors:** Including external factors as additional regressors in the Prophet model (e.g., promotional events, weather data) if available.
- **Exploring Other Models:** Comparing the performance of Prophet with other time series forecasting techniques like ARIMA, SARIMA, or machine learning models (e.g., Gradient Boosting).
- **Hyperparameter Tuning:** Optimizing the parameters of the Prophet model to potentially improve performance.
- **Investigating Anomalies:** Further analyzing periods where the forecast significantly deviates from actuals to understand potential causes.

## Dependencies

The following Python libraries are required to run the code in this project:

- pandas
- numpy
- matplotlib
- seaborn
- prophet
- sklearn

## Usage

To use this project:

1.  Clone this repository to your local machine or open the notebook in Google Colab.
2.  Ensure the `mock_kaggle.csv` file is available in the `/content/` directory or modify the code to load your data from a different location.
3.  Run the code cells in the provided Jupyter Notebook (`.ipynb`) file sequentially. The notebook contains comments explaining each step of the process.

## License

*(Please specify the license you want to use for your project here. If you don't have a specific license, you can state something like "No License Specified" or "All Rights Reserved".)*

## Contact

*(Would you like to include your GitHub profile link or another form of contact information here? Please let me know.)*

---
