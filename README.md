# Sales Forecasting For Inventory Management

## Project Overview

This project focuses on time series forecasting. We aim to predict store sales using data from **Corporation Favorita**, a major grocery retailer based in Ecuador.

Our goal is to develop a model that can more accurately forecast the unit sales of thousands of items sold across various Favorita stores.

# DATA UNDERSTANDING

The project involves a diverse dataset collection, with the primary dataset, train.csv, providing time series data on store, product family, sales, and promotions. Target sales predictions are the focus, with test.csv mirroring the features for predictions. transaction.csv adds transaction data for sales context. Store metadata is in stores.csv, oil prices in oil.csv, and holidays/events in holidays_events.csv. This comprehensive dataset suite aids in forecasting sales and gaining valuable retail insights.

The initial phase involved loading the data from the provided ZIP file using Python libraries like zipfile and pandas.

# Data Cleaning

- Missing Value Handling: The oil dataset exhibited missing values in the dcoilwtico column. The mean value was used to handle these missing values.
  
- Data Type Conversion: Necessary data type conversions were performed.

# Exploratory Data Analysis (EDA)

### Univariate Analysis

- Descriptive Statistics: Summary statistics for numerical variables like sales, price, and transactions were calculated to understand their central tendencies and variability.

- Data Distributions: Histograms and box plots were created to visualize the distributions of key variables, identifying potential outliers or skewness.

- Time Series Plots: Time series plots were generated for sales to identify trends, seasonality, and any anomalies.
  ![newplot (17)](https://github.com/user-attachments/assets/395e7428-769d-45e7-9fa8-fdd34b0c181b)
Time Series Plot of Total Sales Over Time, the vertical line marks the date of the earthquake

### Bivariate Analysis

- Scatter Plots: Scatter plots were created to explore relationships between sales and variables like onpromotion, price, and transactions.
[Chart 2]: Scatter Plot of Sales vs. On Promotion

- Correlation Analysis: Correlation coefficients were calculated to quantify the strength of linear relationships between variables.
[Chart 3]: Correlation Heatmap between key variables (e.g., sales, onpromotion, price)

- Grouped Analysis: Sales were analyzed by different groups (e.g., city, state, store_type, cluster) to identify variations in sales performance across different regions and store types.





