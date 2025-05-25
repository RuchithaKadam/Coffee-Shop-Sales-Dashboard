# Coffee-Shop-Sales-Dashboard
## Overview
The *CoffeeShops Sales Dashboard* is a business intelligence project designed to provide clear and actionable insights into sales performance across multiple coffee shop locations. Built with *SQL, **Power BI, and **DAX*, the dashboard enables business stakeholders to:
- Monitor revenue and sales trends
- Identify top-performing products and categories
- Analyze customer behavior and purchasing patterns
- Compare performance across different store locations
- Track seasonal trends and promotional impacts

## Tech Stack
- *SQL*: Data extraction, transformation, and preparation
- *Power BI*: Data visualization and dashboard creation
- *DAX*: Calculated measures, KPIs, and time intelligence functions

## Features
- *Interactive Dashboard* with slicers (e.g., date, store, product category)
- *Sales KPIs*: Total Revenue, Average Order Value, Units Sold
- *Time-Series Analysis*: Month-over-month and year-over-year growth
- *Product Analysis*: Best-selling items, revenue by product category
- *Geographical Insights*: Store-level performance comparison
- *Customer Insights*: Repeat purchases, average spend per customer

## Data Model
The data model includes the following tables:
- Sales: Transaction-level sales data
- Products: Product and category details
- Stores: Store information including location and type
- Customers: Customer demographic and behavioral data
- Calendar: A date dimension table for time intelligence

## Example DAX Measures
- dax
Total Revenue = SUM(Sales[Revenue])

Average Order Value = DIVIDE([Total Revenue], DISTINCTCOUNT(Sales[OrderID]))

YoY Revenue Growth = 
CALCULATE([Total Revenue], SAMEPERIODLASTYEAR(Calendar[Date]))

Top Products = 
TOPN(5, SUMMARIZE(Products, Products[ProductName], "Revenue", [Total Revenue]), [Revenue], DESC)
