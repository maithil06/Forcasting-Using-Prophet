# Time Series Forecasting with Prophet

This Jupyter Notebook (`Prophet.ipynb`) demonstrates how to perform time series forecasting using Facebook's Prophet library. The notebook walks through the entire process, from data loading and preprocessing to model creation, evaluation, and scaling the forecasting process for multiple time series.

## Table of Contents
- [Overview](#overview)
- [Key Features](#key-features)
- [Dependencies](#dependencies)
- [Data](#data)
- [Notebook Sections](#notebook-sections)
- [Usage](#usage)

## Overview
This notebook provides a practical example of implementing time series forecasting using the `fbprophet` library. It's designed to be a straightforward guide for beginners and a quick reference for those familiar with time series analysis.

## Key Features
- **Data Loading and Preprocessing**: Demonstrates how to load data from a CSV file and prepare it for Prophet, including date conversion and renaming columns.
- **Prophet Model Implementation**: Shows the steps to initialize, fit, and predict with a Prophet model.
- **Model Evaluation**: Visualizes the forecast and its components (trend, weekly, yearly seasonality).
- **Scalability**: Includes a "Bonus Round" section that illustrates how to apply the forecasting model to multiple time series efficiently.

## Dependencies
The following Python libraries are required to run this notebook:
- `pandas`
- `fbprophet`

You can install `fbprophet` using pip:
```bash
!pip install fbprophet
```

## Data
The notebook expects a CSV file named `dataset.csv` in the same directory. This dataset should contain at least the following columns:
- **Date**: Date information (expected format: YYYYMMDD).
- **Store/Product**: A categorical column identifying different time series (e.g., `LOS_ANGELES-TESLA_MODEL_X`).
- **Value**: The numerical value to be forecasted.

## Notebook Sections
The notebook is structured into the following key sections:

1. **Import Dependencies**
   - Imports `pandas` for data manipulation and `Prophet` for forecasting.

2. **Load Data**
   - Reads the `dataset.csv` file into a pandas DataFrame and displays the first few rows and data types.

3. **Apply Data Preprocessing**
   - Converts the `Date` column to datetime objects, filters the data for a specific `Store/Product` line (`LOS_ANGELES-TESLA_MODEL_X`), and renames columns to `ds` (datestamp) and `y` (dependent variable) as required by Prophet.

4. **Create Time Series Model**
   - Initializes and fits the Prophet model to the preprocessed data.

5. **Evaluate Model**
   - Generates future dates, makes predictions using the trained model, and plots the forecast and its individual components (trend, weekly seasonality, yearly seasonality).

6. **BONUS ROUND - Scaling Up**
   - Demonstrates how to:
     - Identify all unique time series in the `Store/Product` column.
     - Iterate through each unique time series.
     - Preprocess data for each series.
     - Train a separate Prophet model for each series and store them in a dictionary.
     - Generate a forecast for one of the additional time series (`LOS_ANGELES-TESLA_MODEL_S`) as an example.

## Usage
1. Ensure you have Python installed.
2. Install the required dependencies using the command provided above.
3. Place your `dataset.csv` file in the same directory as the `Prophet.ipynb` notebook.
4. Open the Jupyter Notebook and run the cells sequentially to understand the forecasting process.
5. Modify the "BONUS ROUND" section to forecast other time series or extend the forecast period as needed.
