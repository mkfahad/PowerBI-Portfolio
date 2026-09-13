# E-Commerce Data Cleaning & Power BI Analysis

## Project Overview

This project analyzes a Brazilian e-commerce dataset covering customers, orders, products, payments, reviews, and delivery performance.

The project was completed in two stages:

1. **Excel Data Cleaning & Preparation** – cleaned, standardized, validated, and prepared the raw data for analysis.
2. **Power BI Dashboard Development** – built an interactive multi-page dashboard to analyze sales, customers, products, payments, delivery performance, and customer reviews.

The main goal was to turn a multi-table raw dataset into a clean analytical model and present meaningful business insights through an interactive dashboard.

---

## Project Objectives

- Clean and standardize the raw e-commerce data.
- Validate IDs, missing values, categories, dates, and payment fields.
- Create useful calculated fields for analysis.
- Build relationships between the different business tables.
- Analyze revenue, orders, customer behavior, product performance, payments, delivery efficiency, and review scores.
- Create an interactive Power BI dashboard with navigation, slicers, drill-through, KPIs, and dynamic visuals.
- Generate actionable business insights and recommendations.

---

# Part 1: Excel Data Cleaning

## Dataset Structure

The workbook contains multiple related worksheets:

| Worksheet | Description |
|---|---|
| **Customers** | Customer identifiers and geographic information |
| **Orders** | Order status, purchase date, delivery date, and estimated delivery date |
| **Order Items** | Products purchased in each order, item price, and freight value |
| **Products** | Product IDs and product category information |
| **Payments** | Payment method, installments, and payment value |
| **Reviews** | Review score associated with each order |
| **Category Translation** | Translation of product categories into English |
| **State Names** | Brazilian state code to full state name mapping |
| **Pivot Table** | Excel analysis and validation outputs |
| **Explanation / Documentation** | Notes on cleaning logic and project decisions |

---

## Data Cleaning Performed

### Customers

- Checked customer IDs and unique customer IDs.
- Used **Customer Unique ID** to identify the actual customer across multiple orders.
- Standardized geographic information.
- Converted Brazilian state codes to full state names using a lookup table.
- Validated customer records for use in customer-level analysis.

### Orders

- Checked order IDs and order status values.
- Standardized purchase and delivery date fields.
- Created a date field suitable for time-based analysis.
- Created a **Delivered Time Status** field with categories such as:
  - Early Delivery
  - On-Time
  - Late Delivery
  - Unavailable
- Created **Days for Delivery** to analyze delivery duration.
- Used actual delivery dates for delivered orders and handled unavailable delivery dates separately.

### Order Items

- Validated `Order ID`, `Order Item ID`, and `Product ID`.
- Confirmed that multiple rows can belong to the same order because one order can contain multiple products.
- Checked product IDs against the Products table.
- Used:
  - `Price` for product revenue analysis
  - `Freight Value` for shipping-cost analysis

### Products

- Validated product IDs.
- Confirmed that product IDs in the Products table are represented in Order Items.
- Handled missing product-category information.
- Used the category translation table to create English product-category names.
- Retained products with missing category information rather than deleting valid transaction records.

### Payments

- Standardized payment-type values.
- Renamed payment terminology where needed for easier interpretation.
- Handled unknown payment types without deleting valid payment records.
- Validated:
  - Payment Type
  - Payment Sequential
  - Payment Installments
  - Payment Value

### Reviews

- Validated review scores.
- Linked reviews to orders through `Order ID`.
- Used review scores to analyze customer satisfaction and delivery performance.

---

## Excel Validation Checks

Several validation checks were performed before building the Power BI model:

- Checked whether all Product IDs in the Products table were present in Order Items.
- Checked duplicates and distinct IDs across tables.
- Validated missing and unknown values.
- Checked customer counts using `Customer Unique ID`.
- Checked order counts using distinct `Order ID`.
- Compared payment totals, item-price totals, and freight values.
- Verified delivery-status logic.
- Used PivotTables to validate cleaned outputs before dashboard development.

---

# Part 2: Power BI Dashboard

## Data Model

The Power BI model follows a relational structure:

```text
Customers
    |
    | Customer ID
    v
Orders
    |
    | Order ID
    +-------------------+
    |                   |
    v                   v
Order Items          Payments
    |                   |
    | Product ID        |
    v                   |
Products             Reviews
```

Main relationships:

- `Customers[Customer ID]` → `Orders[Customer ID]`
- `Orders[Order ID]` → `Order Items[Order ID]`
- `Products[Product ID]` → `Order Items[Product ID]`
- `Orders[Order ID]` → `Payments[Order ID]`
- `Orders[Order ID]` → `Reviews[Order ID]`

A dedicated **Calendar table** was created using the order purchase date for time-intelligence analysis.

---

## Dashboard Pages

### 1. Executive Overview

**Subtitle:**  
*Revenue, orders, customers, and key business trends.*

Main analysis includes:

- Total Revenue
- Total Orders
- Total Customers
- Average Order Value
- Revenue trend
- Revenue by state
- Top product categories
- Overall business performance

---

### 2. Customer Analysis

**Subtitle:**  
*Customer behavior, location, and purchasing patterns.*

Main analysis includes:

- Total Customers
- Repeat Customers
- Repeat Customer %
- Average Orders per Customer
- New vs Repeat Customers
- Customer Order Frequency
- Customer distribution by geography
- Customer-level purchasing behavior

> `Customer Unique ID` is used for customer-based KPIs to avoid over-counting the same real customer.

---

### 3. Product & Payment Analysis

**Subtitle:**  
*Product sales, categories, pricing, and payment behavior.*

Main analysis includes:

- Products Sold
- Unique Products Sold
- Average Item Price
- Top Product Categories by Orders
- Product-category revenue
- Payment Value by Payment Method
- Payment Installments Distribution
- Product-category drill-through analysis

A drill-through page allows users to right-click a product category and view detailed product-level information.

---

### 4. Delivery & Reviews

**Subtitle:**  
*Delivery performance and customer satisfaction.*

Main analysis includes:

- Early Delivery %
- Late Delivery %
- On-Time Delivery %
- Average Delivery Days
- Average Review Score
- Average Review Score by Delivery Status
- Delivery-performance distribution
- Review-score comparison

This page helps evaluate the relationship between delivery performance and customer satisfaction.

---

## Key DAX Measures

Examples of measures used in the dashboard:

```DAX
Total Revenue =
SUM('Order Items'[Price])
```

```DAX
Total Orders =
DISTINCTCOUNT(Orders[Order ID])
```

```DAX
Total Customers =
DISTINCTCOUNT(Customers[Customer Unique ID])
```

```DAX
Average Order Value =
DIVIDE(
    [Total Revenue],
    [Total Orders],
    0
)
```

```DAX
Products Sold =
COUNTROWS('Order Items')
```

```DAX
Average Item Price =
AVERAGE('Order Items'[Price])
```

```DAX
Average Review Score =
AVERAGE(Reviews[Review Score])
```

```DAX
Repeat Customer % =
DIVIDE(
    [Repeat Customers],
    [Active Customers],
    0
)
```

```DAX
Late Delivery % =
DIVIDE(
    [Late Deliveries],
    [Evaluated Deliveries],
    0
)
```

---

## Interactive Features

The report includes:

- Page navigation buttons
- Hover-state navigation design
- Slicers
- Month / Year field-parameter toggle
- Dynamic visuals
- Drill-through to Product Details
- Back buttons for drill-through navigation
- Hidden drill-through page
- KPI cards
- Tooltips
- Cross-filtering between visuals

---

## Key Insights

Some of the main findings from the analysis include:

- Revenue is concentrated in a small number of high-performing states, with **Sao Paulo** leading the market.
- High-order-volume categories are not always the highest-revenue categories.
- **Credit Card** is the dominant payment method.
- One-installment payments are the most common payment pattern.
- Most orders are successfully delivered.
- Late deliveries are associated with noticeably lower customer review scores.
- Overall customer satisfaction is strong, but delivery delays negatively affect the customer experience.
- Repeat customers account for only a small share of the customer base, highlighting an opportunity to improve customer retention.

---

## Business Recommendations

### Improve Customer Retention

- Introduce loyalty programs and repeat-purchase incentives.
- Use personalized product recommendations.
- Target previous customers with category-based promotions.
- Analyze repeat-purchase behavior by product category.

### Reduce Late Deliveries

- Identify states and categories with the highest late-delivery rates.
- Monitor delivery performance by location.
- Investigate freight and fulfillment bottlenecks.
- Prioritize delivery reliability because late deliveries are linked to lower review scores.

### Expand Regional Revenue

- Maintain strong performance in leading states.
- Target high-potential states with lower current revenue.
- Use location-specific marketing and product strategies.

### Optimize Product Strategy

- Compare product categories using both order volume and revenue.
- Prioritize high-volume categories for inventory availability.
- Use average item price and category revenue together when making product decisions.

### Improve Payment Experience

- Keep the credit-card checkout process simple and reliable.
- Retain alternative payment methods for customer flexibility.
- Analyze installment behavior for higher-priced product categories.

---

## Tools Used

- **Microsoft Excel**
  - Data Cleaning
  - Lookup formulas
  - Validation checks
  - PivotTables
  - Data preparation

- **Power BI**
  - Data modeling
  - DAX
  - Calendar table
  - Field parameters
  - Interactive dashboard design
  - Drill-through
  - Slicers
  - KPI cards
  - Business visualization

---

## Project Files

```text
E-Commerce-Analysis/
│
├── E-Commerce Data Cleaning.xlsx
├── E-Commerce.pbix
├── README.md
└── Screenshots/
    ├── Executive_Overview.png
    ├── Customer_Analysis.png
    ├── Product_Payment_Analysis.png
    └── Delivery_Reviews.png
```

---

## Skills Demonstrated

- Data Cleaning
- Data Validation
- Excel
- PivotTables
- Data Modeling
- Power BI
- DAX
- Data Visualization
- Dashboard Design
- Business Analysis
- Customer Analysis
- Sales Analysis
- Delivery Performance Analysis
- Data Storytelling

---

## Author

**Mohamed Fahad**

Aspiring Data Analyst | Excel | Power BI | SQL | Python

GitHub: `mkfahad`

---

## Final Note

This project demonstrates the complete analytics workflow from raw data preparation to an interactive business-intelligence dashboard. The focus was not only on creating visuals, but also on validating the underlying data, building a reliable data model, identifying business patterns, and translating those findings into actionable recommendations.
