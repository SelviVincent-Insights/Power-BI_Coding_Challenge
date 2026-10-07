# 📊 Power BI Assignment 1 — E-Commerce Sales Analysis

## Overview
This project demonstrates end-to-end data transformation and data modeling 
in Power BI, using real-world style e-commerce data. It was completed as 
part of the Data Analytics course at **Entri Elevate**, under the guidance 
of mentor **Joseph Delmon**.

## Objective
To clean, transform, merge, and model raw sales data into a 
reporting-ready structure, following standard Power BI best practices.

## Dataset
Three source files were used:
- **List of Orders.csv** — order-level details (Order ID, Date, Customer, Location)
- **Order Details.csv** — line-item details (Category, Sub-Category, Profit, Amount, Quantity)
- **Sales target.csv** — monthly sales targets by category

## Tools Used
- Power BI Desktop (Power Query Editor, Data Modeling)
- Power Query M language (custom columns, conditional logic)

## Project Workflow

### 1. Data Import
Imported all three CSV files and removed 60 blank rows from List of Orders, 
leaving 500 valid orders.

### 2. Data Transformation
- Corrected date parsing using **Locale (English - India)** to fix day/month order
- Cleaned text columns using Trim and Proper Case formatting
- Built a combined **Location** column (City, State)
- Added calculated columns: **Profit Margin** and **Profit Status** (Loss / Break-Even / Profit)
- Fixed month-year parsing in the Sales Target table using `Date.FromText()`

### 3. Merging Data (Joins)
Created a referenced query (**Orders Data**) and merged Order Details into 
it using a Left Outer Join on Order ID, then expanded relevant columns.

### 4. Data Quality Checks
Verified no missing values remained, and confirmed Order ID repetition in 
Order Details was expected (multiple products per order).

### 5. Sorting & Filtering
Sorted orders by date (descending) and filtered by location (Tamil Nadu) 
to validate the cleaned dataset.

### 6. Grouping & Aggregation
Built summary tables: Order Count, Profit by Category, Amount by 
Sub-Category, and Target by Month.

### 7. Data Modeling
Established a clean relationship model:
- **Order Details (Order ID) → List of Orders (Order ID)** — One-to-many, Active
- **Order Details (Category) ↔ Sales Target (Category)** — Many-to-many, Active

## Repository Structure
