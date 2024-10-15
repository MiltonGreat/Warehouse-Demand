# Warehouse-Demand

This project performs exploratory analysis on historical product demand data to identify trends, seasonal variations, and other patterns that can be useful for demand forecasting and inventory planning.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Objective](#objective)
- [Features](#features)
- [Project Workflow](#project-workflow)
  - [Data Preprocessing](#data-preprocessing)
  - [Time Series Analysis](#time-series-analysis)
  - [Trend and Seasonality Analysis](#trend-and-seasonality-analysis)
  - [Correlation Analysis](#correlation-analysis)
- [Key Insights](#key-insights)
- [Usage](#usage)
- [License](#license)

## Project Overview

This project focuses on exploratory data analysis (EDA) of historical product demand data. By analyzing the dataset, we aim to detect trends, seasonal patterns, and important correlations between product demand and other factors, such as warehouse locations or product categories. Identifying these patterns can assist in forecasting and managing product inventory.

## Dataset

The dataset contains historical product demand data across different warehouses and product categories. It includes:
- **Product_Code**: Identifier for each product.
- **Warehouse**: Warehouse from which the product is shipped.
- **Product_Category**: Category of the product.
- **Date**: Date when the demand occurred.
- **Order_Demand**: Number of units ordered.

### Features:

- **Product_Code**: Unique code for each product.
- **Warehouse**: The warehouse where the product is stored.
- **Product_Category**: The category of the product (e.g., electronics, furniture).
- **Date**: The date when the product was ordered.
- **Order_Demand**: Number of product units ordered on a particular date.

## Objective

The main objective of this project is to analyze product demand data over time and uncover insights such as:
- Overall demand trends.
- Seasonal variations in product demand.
- Correlations between product categories, warehouses, and order demand.

## Features

The key features used in the analysis include:
- **Order_Demand**: The primary metric analyzed to uncover trends and seasonal variations.
- **Moving Averages**: 30-day and 90-day moving averages are calculated to smooth out short-term fluctuations and identify long-term trends.
- **Time Series Decomposition**: To decompose the demand into trend, seasonality, and residual components.
- **Correlation Matrix**: To examine how other features like product categories and warehouses correlate with order demand.

## Project Workflow

### Data Preprocessing

1. **Loading the Data**:
   - The dataset is loaded, and the columns are checked for missing values and data types.
   
2. **Handling Missing and Invalid Data**:
   - Missing dates are handled by dropping rows with missing values.
   - The **Order_Demand** column is cleaned to remove any non-numeric values, and rows with missing or invalid data are removed.

3. **Converting Date and Indexing**:
   - The **Date** column is converted to a `datetime` format, and it is set as the index for time series analysis.

### Time Series Analysis

1. **Visualizing Demand Over Time**:
   - The historical product demand is visualized to observe how demand fluctuates over time.

2. **Moving Averages**:
   - **30-day** and **90-day** moving averages are calculated to identify short- and long-term trends in product demand.

3. **Trend Decomposition**:
   - The time series is decomposed into three components:
     - **Trend**: The overall direction of the demand.
     - **Seasonality**: Repeating patterns that occur at regular intervals.
     - **Residuals**: The remaining variability after accounting for trend and seasonality.

4. **Trend Detection with Linear Regression**:
   - A linear regression model is fitted to detect the overall trend of product demand over time. The slope of the trend line indicates whether demand is increasing, decreasing, or stable.

### Trend and Seasonality Analysis

1. **Seasonal Decomposition**:
   - Time series decomposition is applied to separate the trend and seasonal components, allowing a clearer view of repeating seasonal patterns in demand.

2. **Autocorrelation Analysis**:
   - The autocorrelation function (ACF) plot is used to detect patterns and periodicity in the data, which can help confirm seasonality.

3. **Fourier Transform**:
   - Fourier Transform is applied to identify cyclical patterns in the demand data that may not be immediately visible through standard time series analysis.

### Correlation Analysis

1. **One-Hot Encoding**:
   - Categorical variables, such as **Product_Category** and **Warehouse**, are encoded using one-hot encoding for numerical analysis.

2. **Correlation Matrix**:
   - A correlation matrix is generated to analyze the relationships between **Order_Demand** and other features (product categories, warehouses).

3. **Correlation Insights**:
   - Features with the highest positive or negative correlation with **Order_Demand** are highlighted.

## Key Insights

1. **Missing Dates**:
   - The dataset contains missing dates, but these are handled by dropping the affected rows to maintain data integrity for time series analysis.

2. **Moving Averages**:
   - The 30-day and 90-day moving averages help smooth out short-term fluctuations and reveal the long-term trend of product demand.

3. **Seasonality**:
   - The decomposition of the time series reveals distinct seasonal patterns in product demand, which can be useful for demand forecasting.

4. **Trend Detection**:
   - Linear regression analysis indicates the overall trend in product demand. In the sample dataset, the slope of the trend is slightly positive, indicating an overall increase in demand.

5. **Autocorrelation**:
   - The autocorrelation function shows strong periodic patterns in the data, confirming the presence of seasonality.

6. **Correlations with Demand**:
   - Some product categories and warehouses show significant correlations with **Order_Demand**, which can help target inventory planning for specific products or locations.

### Code Explanation and Insights

#### Code Explanation:

The provided code performs exploratory data analysis on historical product demand data, identifying trends, seasonal variations, and relationships with other variables like product categories and warehouses. Here’s a breakdown of the steps involved:

1. **Data Loading**:
   - The dataset is loaded into a Pandas DataFrame, and the first few rows and columns are inspected.
   
2. **Data Cleaning**:
   - Missing or invalid dates are dropped.
   - The **Order_Demand** column is cleaned by removing non-numeric values, and rows with invalid demand values are dropped.
   
3. **Time Series Visualization**:
   - The demand over time is plotted to visualize how demand fluctuates daily.
   
4. **Moving Averages**:
   - Both 30-day and 90-day moving averages are calculated to smooth out short-term fluctuations and identify long-term demand trends.

5. **Trend Decomposition**:
   - The time series is decomposed into three components: trend, seasonality, and residuals using an additive model. This reveals underlying patterns in the data.

6. **Linear Trend Detection**:
   - A linear regression model is fitted to detect the overall trend in product demand. A positive slope indicates increasing demand, while a negative slope indicates a decline.

7. **Seasonality Analysis**:
   - Autocorrelation is analyzed to detect seasonality and repeating patterns in demand.
   - Fourier Transform is used to detect cyclical patterns and frequencies in demand data.

8. **Correlation Analysis**:
   - Categorical variables (product categories, warehouses) are one-hot encoded.
   - A correlation matrix is generated to understand relationships between features and **Order_Demand**.

#### Insights from the Output:

1. **Trend Detection**:
   - The linear regression analysis shows a slight positive slope, indicating that product demand is generally increasing over time.

2. **Seasonality**:
   - Seasonal decomposition reveals clear seasonal patterns in product demand, likely tied to periodic changes (such as holidays or promotions).

3. **Autocorrelation**:
   - The autocorrelation plot confirms repeating patterns in the demand data, indicating regular periodicity, which aligns with the detected seasonality.

4. **Correlation Analysis**:
   - The highest correlation with **Order_Demand** is found in moving averages, which suggests that recent demand is a strong predictor of future demand.
   - Certain product categories (e.g., Category_019) show a significant positive correlation with demand, while others have a slight negative correlation.

### Source:

https://www.kaggle.com/datasets/sydjaffy/historical-product-demand
