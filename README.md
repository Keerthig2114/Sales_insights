#  Sales Insight Dashboard

This project presents a comprehensive **Sales Insights Dashboard** built using **Power BI**, aimed at providing meaningful business intelligence from raw sales data. The dashboard helps stakeholders understand sales performance across products, markets, and customers.

---

##  Dataset Overview

- **Source**: External sales data source (public dataset)
- **Tables Used**:
  - `sales transactions`
  - `customer`
  - `product`
  - `market`
  - `date`

---

##  Data Processing Workflow

### 1.  Data Collection
- Loaded sales data from CSV/Excel files into Power BI
- Verified schema for customer codes, product mapping, market zones, and sales figures

### 2.  Data Cleaning & Transformation (Power Query)
- Removed duplicate records
- Standardized column formats and renamed for clarity
- Created calculated columns such as:
  - `Sales Amount = Unit Price × Quantity`
  - `Profit = Sales - Cost`
- Established relationships using a star schema model
- Added a date hierarchy with Year and Month levels

---

##  SQL-Based Exploratory Analysis (MySQL Workbench)

Preliminary data exploration and validation were performed in **MySQL Workbench** before Power BI visualization.

###  Key SQL Tasks:
- Total sales and sales quantity by product and market
- Top 5 customers and products
- Monthly revenue trends using `GROUP BY` with `YEAR()` and `MONTH()`
- Joining multiple tables for deep-dive analysis
- Identified and filtered out inconsistent or invalid records

---

##  Dashboard Highlights

###  Key Visuals and Metrics
- **Revenue** – Card
- **Sales Quantity** – Card
- **Top 5 Products by Sales** – Bar Chart
- **Top 5 Customers by Revenue** – Bar Chart
- **Monthly Revenue Trend** – Line Chart
- **Revenue by Markets** – Stacked Bar Chart
- **Sales Quantity by Markets** – Stacked Bar Chart

---
###  Interactivity
- Page-level filters by market, product, and date
- Tooltips for detailed on-hover insights

---

##  DAX Measures Used

```dax
Revenue = SUM('sales transactions'[norm_sales_amount])

Sales qty = SUM('sales transactions'[sales_qty])

Total Sales = SUM('sales transactions'[sales_amount])
