Superstore Sales Analysis Dashboard | Power BI

Project Overview

This project is an interactive Superstore Sales Analysis Dashboard built in Microsoft Power BI.
The report analyzes overall sales performance, product and category performance, customer behavior, regional performance, profitability, and year-over-year growth.

The dashboard is organized into four report pages so users can move from a high-level business overview to more detailed product, customer, regional, and profitability analysis.

Dashboard Pages

1. Sales Overview

Provides a high-level view of overall business performance.

KPIs
Total Sales
Total Profit
Total Orders
Total Quantity Sold
Sales YoY %
Profit YoY %
Orders YoY %
Quantity Sold YoY %
Visuals
Monthly Sales Trend
Sales and Profit by Category
Sales by Region
Sales by Customer Segment

2. Product and Category Analysis

Focuses on the products, categories, and sub-categories that contribute most to sales and profitability.
KPIs
Top Category
Top Sub-Category
Most Profitable Product
Lowest Profitable Sub-Category
Visuals
Profit by Sub-Category
Sales by Product
Profit by Product
Quantity Sold vs. Profit by Sub-Category

3. Customer & Regional Analysis

Analyzes customer performance and the geographic distribution of sales.

KPIs

Top Customer
Top State
Average Sales
Repeat Customers
Visuals
Customer Sales Decomposition Analysis
Sales by State Map
Orders and Profit by Region

4. Profitability & Growth Analysis

Provides deeper analysis of business growth and profitability over time.

KPIs
YTD Profit
Profit Margin %
Sales YoY %
Profit YoY %

Visuals

YTD Sales and YTD Profit by Year
Sales YoY % by Year
Previous-Year Profit Trend
Profit Margin % by Year

Data Model

The report uses a dimensional model with a central order fact table and supporting dimension tables.

Tables

Order fact

Customer dim

Product dim

Location dim

calendar

Measaure Table

This structure supports efficient filtering and analysis across customers, products, locations, and time.

Key DAX / Analytical Measures

The report includes measures for:

Total Sales

Total Profit

Total Orders

Total Quantity Sold

Profit Margin %

Year-to-Date Sales

Year-to-Date Profit

Sales YoY %

Profit YoY %

Orders YoY %

Quantity Sold YoY %

Previous-Year Profit

Top Customer

Top State

Top Category

Top Sub-Category

Most Profitable Product

Lowest Profitable Sub-Category

Repeat Customers

Average Sales

Power BI Features Used

DAX Measures

Time Intelligence

Calendar / Date Table

Star-Schema Data Modeling

KPI Cards

Line and Area Charts

Bar and Column Charts

Scatter Chart

Treemap

Donut / Pie Chart

Funnel Chart

Map Visual

Waterfall Chart

Ribbon Chart

Decomposition Tree

Slicers

Page Navigation

Buttons and Icons

Bookmark-Based Filter Panel

Cross-Filtering and Interactive Visuals

Business Questions Answered

The dashboard helps answer questions such as:

What are the overall sales, profit, orders, and quantity sold?

How are sales and profit changing compared with the previous year?

Which categories and sub-categories generate the most profit?

Which products are the most and least profitable?

Which customers contribute the most sales?

How many customers are repeat customers?

Which states and regions generate the most sales?

How do order volume and profit vary across regions?

What is the current profit margin?

How are YTD sales and profit progressing?

How has business performance changed year over year?

Tools Used

Microsoft Power BI Desktop

Power Query

DAX

Data Modeling

Data Visualization

Repository Structure

superstore-power-bi-analysis/
│
├── superstore.pbix
├── README.md
│
└── images/
    ├── sales-overview.png
    ├── product-category-analysis.png
    ├── customer-regional-analysis.png
    └── profitability-growth-analysis.png

Dashboard Preview

Add screenshots of each report page to an images folder and display them here:

Sales Overview

![Sales Overview](images/sales-overview.png)

Product and Category Analysis

![Product and Category Analysis](images/product-category-analysis.png)

Customer & Regional Analysis

![Customer & Regional Analysis](images/customer-regional-analysis.png)

Profitability & Growth Analysis

![Profitability & Growth Analysis](images/profitability-growth-analysis.png)

How to View the Project

Download superstore.pbix from this repository.

Install Microsoft Power BI Desktop if required.

Open the .pbix file in Power BI Desktop.

Use the page navigation, slicers, filters, and interactive visuals to explore the report.

Skills Demonstrated

This project demonstrates practical skills in:

Business Intelligence

Data Cleaning and Transformation

Data Modeling

DAX

Time Intelligence

KPI Development

Customer Analysis

Product Analysis

Geographic Analysis

Profitability Analysis

Dashboard Design

Interactive Report Development

Author
Mohamed Fahad
Aspiring Data Analyst

