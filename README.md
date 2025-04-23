# Sales Insights Data Analysis Project

# Project Overview
This end-to-end data analysis project demonstrates how to transform raw sales data into actionable business insights using Power BI. Based on the Codebasics tutorial series, this project covers data cleaning, ETL processes, SQL analysis, and interactive dashboard creation for a computer hardware business.

# Tools & Technologies
Power BI - Data visualization and dashboarding
MySQL - Database management
SQL - Data querying and analysis
Power Query - Data transformation and cleaning

# Dataset
The dataset contains sales records from 2017-2020 with the following tables:
Customers
Transactions
Markets
Products
Date

# Project Steps
1. MySQL Setup & Data Import
Installed MySQL locally
Imported database using provided db_dump.sql file
Verified all tables were loaded correctly

2. SQL Data Analysis
Key analysis queries included:

sql
-- Chennai market analysis
SELECT * FROM transactions WHERE market_code='Mark001';

-- Revenue calculation for 2020
SELECT SUM(sales_amount) FROM transactions 
INNER JOIN date ON transactions.order_date = date.date 
WHERE year=2020 AND currency IN ('INR\r', 'USD\r');

3. Power BI Data Cleaning & ETL
Removed invalid records (sales_amount ≤ 0)
Normalized currencies (USD to INR conversion)
Handled missing values and inconsistencies
Created calculated columns:

powerquery
norm_amount = IF [currency] = "USD" THEN [sales_amount]*75 ELSE [sales_amount]

4. Dashboard Development
Created interactive visualizations including:
Revenue trend analysis (time series)
Market performance comparison
Product category breakdowns
Key metrics cards (total revenue, profit)

# Installation & Usage
Clone this repository
Import the database using db_dump.sql
Open the .pbix file in Power BI Desktop
Refresh data connections if needed
Interact with the dashboard visuals

# Learning Outcomes
Through this project, I gained hands-on experience with:
Connecting Power BI to MySQL databases
Writing complex SQL queries for analysis
Data cleaning and transformation in Power Query
Creating measures and calculated columns
Designing effective data visualizations
Building interactive dashboards with filters

