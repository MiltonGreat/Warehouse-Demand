# Warehouse-Demand

## Project Overview

This project aims to analyze historical product demand data, focusing on warehouses and product categories. By exploring trends, seasonality, and correlations, we aim to gain insights into demand patterns over time and across different product categories and warehouses.

## Objective

The main objective of this project is to analyze product demand data over time and uncover insights such as:
- Overall demand trends.
- Seasonal variations in product demand.
- Correlations between product categories, warehouses, and order demand.

## Dataset

The dataset contains historical product demand data across different warehouses and product categories. It includes:

- **Product_Code**: Identifier for each product.
- **Warehouse**: Warehouse from which the product is shipped.
- **Product_Category**: Category of the product.
- **Date**: Date when the demand occurred.
- **Order_Demand**: Number of units ordered.
 
#### Code Explanation:

1. Data Cleaning and Preprocessing

2. Time-Series Visualizations
- 30-day Moving Average: Smoothing out short-term fluctuations.
- 90-day Moving Average: Highlighting long-term trends.

3. Time-Series Decomposition
- Trend: The general direction in which the demand is moving.
- Seasonality: Repeating patterns or cycles in the demand data.
- Residuals: The noise or randomness in the demand data.

4. Trend Detection Using Linear Regression
- Trend Line Slope: 0.445, indicating that the demand is increasing over time.

5. Seasonality Detection
- Autocorrelation Function (ACF): Identified repeating patterns in the demand data.
- Fourier Transform: Detected cyclical patterns in the frequency domain by transforming the time-domain data.

6. Correlation Analysis

#### Insights from the Output:

- The 30-day moving average has the strongest positive correlation with Order_Demand (correlation coefficient: 0.5079), indicating that recent trends in demand have a strong influence.
- Long-term trends (90-day moving average) show a moderate correlation (0.3389).

#### Future Work

- Predictive Modeling: Implement machine learning models to forecast future product demand.
- Warehouse-Specific Analysis: Break down the analysis by warehouses to detect any location-specific trends or patterns.

#### Conclusion

The analysis has shown that product demand is increasing over time, with notable seasonal patterns. The 30-day moving average has the strongest correlation with demand, indicating that recent trends in demand are highly relevant. This information can be used for better inventory planning and demand forecasting across warehouses.

### Source:

https://www.kaggle.com/datasets/sydjaffy/historical-product-demand
