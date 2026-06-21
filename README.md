# Retail Sales Power BI Dashboard

A Power BI project analyzing retail sales data across regions, products, and sales representatives using a 5-table relational data model.

## Project Overview

This project simulates real-world messy business data with intentional data quality issues — nulls, duplicates, inconsistent formatting, and mixed date formats — to practice professional data cleaning and dashboard development.

## Data Model

Star schema with 1 fact table and 4 dimension tables:

- **Orders** (Fact table) — transactions, quantities, pricing, profit
- **Customers** — customer details and segments
- **Products** — product categories and subcategories
- **Regions** — geographic information
- **Sales_Reps** — sales representative details

## Data Cleaning (Power Query)

- Removed duplicate order records
- Standardized inconsistent text values (Payment_Method, Order_Status, Category, Team) using Trim and Capitalize Each Word
- Fixed 3 different date formats using custom `Date.FromText` formula with try/otherwise logic
- Handled NULL values in Quantity, Unit_Price, and Discount_% based on business context
- Recalculated Gross_Sales, Discount_Amount, and Net_Sales using custom columns
- Fixed incorrect data types across all tables

## DAX Measures

- Total Revenue
- Total Profit
- Total Orders
- Total Customers (DISTINCTCOUNT)
- Total Quantity
- Completed Orders (CALCULATE)
- Average Order Value (DIVIDE)
- Profit Margin %

## Dashboard Features

- 6 KPI cards showing key business metrics
- Revenue by Region (bar chart)
- Monthly Revenue Trend (line chart)
- Order Status breakdown (pie chart)
- Top Products by Revenue (bar chart)
- Sales Rep Performance (bar chart)
- Payment Method Analysis (donut chart)

## Tools Used

Power BI Desktop, Power Query, DAX

## Key Insight

Only 39% of orders reached "Completed" status, highlighting a significant order fulfillment issue worth investigating further.
