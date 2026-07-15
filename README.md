# Cafe Sales - data cleaning & visualisation
Project involving the cleaning of a “dirty” dataset of cafe sales.
The goal is to practice data wrangling using realistic data that contains missing values and errors.

Link: https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training

# About dataset
The Dirty Cafe Sales dataset contains 10,000 rows of synthetic data representing sales transactions in a cafe. This dataset is intentionally "dirty," with missing values, inconsistent data, and errors introduced to provide a realistic scenario for data cleaning and exploratory data analysis (EDA). It can be used to practice cleaning techniques, data wrangling, and feature engineering.
File Information

    File Name: dirty_cafe_sales.csv
    Number of Rows: 10,000
    Number of Columns: 8

| Column Name | Description | Example Values |
| --- | --- | --- |
| Transaction ID | A unique identifier for each transaction. Always present and unique. | TXN_1234567 |
| Item | The name of the item purchased. May contain missing or invalid values (e.g., "ERROR"). | Coffee, Sandwich |
| Quantity | The quantity of the item purchased. May contain missing or invalid values. | 1, 3, UNKNOWN |
| Price Per Unit | The price of a single unit of the item. May contain missing or invalid values. | 2.00, 4.00 |
| Total Spent | The total amount spent on the transaction. Calculated as Quantity * Price Per Unit. | 8.00, 12.00 |
| Payment Method | The method of payment used. May contain missing or invalid values (e.g., None, "UNKNOWN"). | Cash, Credit Card |
| Location | The location where the transaction occurred. May contain missing or invalid values. | In-store, Takeaway |
| Transaction Date | The date of the transaction. May contain missing or incorrect values. | 2023-01-01 |

# What was done
Replaced ERROR / UNKNOWN with NaN
Converted numeric columns to proper types (float)
Recovered missing values using Total = Quantity × Price Per Unit
Parsed dates (pd.to_datetime) and engineered features (month, weekday)
Built visualizations of sales trends and top-selling items

# Conclusions

After cleaning, the dataset shrank from 10,000 to ~8,500 valid rows. Key findings: Coffee and Tea are the top-selling items by volume. In-store transactions dominate over Takeaway. Sales peak on weekdays, with a slight dip on weekends. Cash and Credit Card are the most common payment methods. Most transactions are single-item purchases with low total spend. Missing values were concentrated in Item, Quantity, and Price Per Unit columns — many were recoverable using the Total = Quantity × Price Per Unit formula.

# Future Improvements

Add time-series analysis to detect seasonal trends across months. Cluster customers by spending patterns using K-Means. Build a simple demand forecasting model (e.g. LinearRegression on weekday/month features). Enrich the dataset with weather data to see if weather affects sales. Create an interactive dashboard (Plotly/Dash) for live sales monitoring.

# Visualization

Sales trend by month (line chart), top-selling items by quantity (bar chart), revenue by payment method (bar chart), transaction count by location (pie chart), weekday vs weekend sales comparison (bar chart).

# Project structure
├── data/
│   ├── dirty_cafe_sales.csv      # raw data
│   └── clean_cafe_sales.csv      # cleaned data
├── notebooks
    ├── EDA_cafe_sales.ipynb       # main notebook
│   └── cafe_cleaning_version_2    # cleaning example
├── images/                        # charts for README
└── README.md


# Tech Stack
Python / pandas / NumPy / matplotlib
