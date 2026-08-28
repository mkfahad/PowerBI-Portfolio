Sales Performance & Target Analysis Dashboard

A multi-page Power BI sales analytics project built to analyze sales, profitability, targets, customer performance, year-to-date trends, sub-category performance, and geographic sales patterns.
This project was created as a Power BI assignment and refined as a portfolio project. The report includes interactive filters, navigation buttons, bookmarks, KPI cards, and multiple analytical visuals.

Power BI file: Sales_Performance_Target_Analysis.pbix

Project Overview

The dashboard is organized into three report pages, each with a different analytical focus:

Sales Overview — overall sales, profit, targets, trends, and category performance

Detailed Sales Performance Analysis — product, sub-category, profitability, and geographic analysis

Sales & Customer Performance Analysis — customer contribution, top customers, orders, and YTD sales

Dashboard Pages

1. Sales Overview

The main dashboard provides a high-level view of sales and target performance.

Key elements include:

Total Sales

Total Profit

Sales Target

Target Achievement %

Sales vs. Target by Category

Monthly Sales Trend

Profit vs. Quantity by Sub-Category

Sales Performance Matrix

Profit by Category

Interactive filters for Year, Month, Category, and State

2. Detailed Sales Performance Analysis

This page focuses on deeper product and geographic performance.

Key elements include:

Top Sub-Category

Top State

Top Category

Revenue by Sub-Category

Profit Margin % by Sub-Category

Order Count by State

Geographic sales analysis

Interactive slicers for Year, Month, Category, and State

3. Sales & Customer Performance Analysis

This page focuses on customer contribution and time-intelligence analysis.

Key elements include:

Top Customer

Unique Orders

Year-to-Date (YTD) Sales

Top 5 Customers by Sales

Customer-level sales analysis

Revenue by City

Interactive slicers for Year, Month, Category, and State

Key Power BI Features Used

DAX measures for sales, profit, targets, rankings, and KPI analysis

Calendar table for time-intelligence calculations

YTD and year-over-year analysis

TOPN and ranking logic for top-performing customers, states, categories, and sub-categories

Bookmarks for interactive filter panels

Page navigation buttons

Synchronized slicers across report pages

Interactive tooltips and information buttons

Data modeling across orders, order details, targets, and calendar tables

Data Model

The report uses the following core tables:

List of Orders

Order Details

Sales target

Calendar

The model separates order-level data, transaction-level sales information, targets, and dates so measures can be analyzed correctly across time, category, customer, and geography.

Example DAX Measures

Total Profit

Total Profit =
SUM('Order Details'[Profit])

YTD Sales

YTD Sales =
TOTALYTD(
    [Total Sales],
    'Calendar'[Date]
)

Target Achievement %

Target Achievement % =
DIVIDE(
    [Total Sales],
    [Sales Target],
    0
)

The report also uses ranking and top-performer logic to identify leading customers, categories, states, and sub-categories.

Visualizations Used

KPI Cards

Column and Bar Charts

Line Charts

Scatter Chart

Matrix

Donut Charts

Treemap

Funnel Chart

Map

Slicers

Dashboard Design

The report uses a consistent green sales-performance theme with:

Clean KPI cards

Consistent page titles and subtitles

Navigation icons

Popup-style filter panels

Multi-page report navigation

Consistent slicers and formatting across pages

The design moves from a high-level overview to detailed sales and customer analysis without overcrowding a single page.

Dashboard Preview

GitHub cannot display .pbix files interactively, so screenshots of the report pages are included below.

Sales Overview



Detailed Sales Performance Analysis



Sales & Customer Performance Analysis



How to View the Interactive Report

To explore the full interactive dashboard:

Download the .pbix file from this repository.

Install or open Microsoft Power BI Desktop.

Open Sales_Performance_Target_Analysis.pbix.

Use the page-navigation buttons to move between dashboard pages.

Use the Year, Month, Category, and State slicers to filter the report.

Explore the bookmarks, filter panel, KPI cards, charts, maps, and customer analysis interactively.

Power BI Desktop is required to open the .pbix file. An online Power BI Service link is not included in this repository.

Repository Structure

power-bi-sales-performance-analysis/
│
├── README.md
├── Sales_Performance_Target_Analysis.pbix
│
├── images/
│   ├── sales-overview.png
│   ├── detailed-analysis.png
│   └── customer-sales-analysis.png
│
└── data/
    └── source-data.xlsx   # optional, only if permitted to share

Skills Demonstrated

Power BI Desktop

DAX

Data Modeling

Time Intelligence

KPI Development

Data Visualization

Dashboard Design

Interactive Slicers

Bookmarks and Navigation

Sales Analysis

Customer Analysis

Business Questions Addressed

The dashboard helps answer questions such as:

What are the overall sales and profit values?

How is actual sales performance comparing with sales targets?

How are sales changing over time?

Which categories and sub-categories perform best?

Which states contribute the most revenue and orders?

Which customers generate the highest sales?

How are profit and quantity related across sub-categories?

What is the year-to-date sales performance?

Project Objective

The objective of this project is to transform raw order and sales-target data into an interactive business intelligence report that supports analysis of sales performance, profitability, targets, customer contribution, and geographic trends.
