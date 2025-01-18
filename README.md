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

![image](https://github.com/user-attachments/assets/be80470c-74a8-4d35-a8d6-023867b85b91)

Scatter Plot of Sales vs. On Promotion

- Correlation Analysis: Correlation coefficients were calculated to quantify the strength of linear relationships between variables.

![newplot (18)](https://github.com/user-attachments/assets/c0167d86-8e55-4633-8952-f3234bbde725)

Correlation Heatmap between sales and onpromotion

The Pearson correlation coefficient between the number of products under promotion and supermarket sales is 0.4180, with a p-value of 0.0000, indicating a statistically significant positive relationship. This suggests that as the number of promoted products increases, sales tend to rise. Supermarkets can leverage this insight by optimizing their promotional strategies to boost sales and revenue effectively.

- Grouped Analysis: Sales were analyzed by different groups to identify variations in sales performance across different regions and store types.

![image](https://github.com/user-attachments/assets/7973a8cc-fd99-4440-a2ca-11fe4f06d2f6)
Bar charts for Top 5 Sales by City, Cluster, State, and Store Type

Insight: The sales analysis reveals key insights across various groupings. Quito and Guayaquil are the top-performing cities, while Cluster 14 and Pichincha lead in total sales by cluster and state, respectively. Holiday stores generate the highest revenue among store types, highlighting areas for focused strategic decision-making to enhance profitability.

# Data Preprocessing

### Feature Engineering

New features were created from existing ones to capture potential insights:
- day_of_week, quarter, is_weekend, is_holiday from the date column.

- Lag features for price and sales (e.g., oil_price_lag1, sales_lag7).

- Rolling averages for sales (e.g., rolling_mean_7, rolling_mean_30).

- Cyclical features (sine and cosine transformations) for month and day_of_week to capture seasonality.

- Data Splitting:
   - The data was split into training and validation sets to evaluate model performance.

# Model Building

- Model Selection:
   - XGBoost was chosen as the machine learning model for its ability to handle complex relationships and capture non-linear patterns in time series data.

- Model Training and Tuning:
   - The XGBoost model was trained on the training data.
   - Hyperparameter tuning was performed using RandomizedSearchCV to optimize model performance.

- Model Evaluation:
   - The trained model was evaluated on the validation set using metrics like Root Mean Squared Error (RMSE).

# Results

- Model Performance: The final XGBoost model achieved an RMSE of 0.0155 on the validation set, indicating an excellent fit to the data with minimal error compared to other models evaluated.
![newplot (17)](https://github.com/user-attachments/assets/efac61b3-4cf6-4d86-8603-a4f2bb47712d)
After carefully assessing the performance of our models using key evaluation metrics, it is evident that the XGBoost model stands out as the most effective choice for our dataset. The RMSLE (Root Mean Squared Logarithmic Error) serves as a crucial indicator, and the XGBoost model achieved the lowest RMSLE of 0.0054 among all models evaluated. This indicates that the XGBoost model provides the most accurate and precise predictions when compared to ARIMA, SARIMA, and ETS models.

- Feature Importance: Feature importance analysis was conducted to identify the most influential features in the model's predictions.
![image](https://github.com/user-attachments/assets/a51471df-866f-4397-bc83-ad8bc5036a46)
Bar chart of Feature Importance


# Prediction(Forecast)

The pre-trained model was utilized to generate forecasts for unseen test data. The predictions include estimated sales for various product families on specific dates, considering features like promotions, day of the week, and lagged sales metrics.


For example:
- **AUTOMOTIVE** on 2017-08-16 had a forecast of **0.000112**.
- **BEVERAGES** on 2017-08-16 had a forecast of **0.019104**, reflecting higher expected sales compared to other categories.
- The model incorporates features like `onpromotion`, `lag_1`, and `rolling_mean` to enhance forecast accuracy.


# Conclusion

- This project successfully developed a time series forecasting model for predicting store sales using a combination of data exploration, feature engineering, and machine learning techniques.

- The XGBoost model demonstrated promising performance on the validation set, indicating its potential for accurate sales predictions.

- Further improvements could be explored, such as incorporating more sophisticated time series models (e.g., Prophet), refining feature engineering, and exploring ensemble methods.


# Limitations

- The analysis may be limited by the availability and completeness of the data.

- External factors not included in the dataset (e.g., economic conditions, competitor actions) could also influence sales and may not be fully captured by the model.






