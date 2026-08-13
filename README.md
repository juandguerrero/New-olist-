# Olist Marketplace Sales & Logistics Analytics

**SQL Server · SQL · Power BI · ETL · Data Warehousing · Star Schema**

## Project Overview

**Olist** is a Brazilian e-commerce marketplace that connects independent sellers with customers across Brazil.

Instead of operating as a traditional retailer, Olist enables multiple sellers to offer products through its marketplace ecosystem. This generates transactional and operational data across **customers, orders, products, sellers, payments, reviews, geographic locations, and deliveries**.

The goal of this project was to transform this fragmented data into a structured analytics solution capable of answering key questions about **sales performance, products, customers, sellers, geography, and logistics**.

I built an end-to-end solution using **SQL Server and Power BI**, covering:

**Data Profiling → Data Modeling → ETL → Data Validation → SQL Analytics → Power BI → Business Insights**

---

## Key Business Findings

- Olist generated **R$13.22M in product revenue** across **96,478 delivered orders**, with an **average order value of R$137.04**.
- Order volume expanded significantly: **Jan–Aug 2018 recorded 52,783 orders vs. 21,998 during the same period in 2017**, an increase of approximately **140%**.
- **November 2017** was the strongest month by order volume with **7,289 orders**.
- **Health & Beauty** generated the most revenue at **R$1.23M**, while **Bed, Bath & Table** had the highest sales volume with **10,953 order items**.
- The top five product categories generated approximately **40% of total marketplace revenue**.
- **São Paulo generated R$5.07M**, representing approximately **38.3% of total revenue**.
- São Paulo, Rio de Janeiro, and Minas Gerais together generated approximately **63.4% of marketplace revenue**, showing strong geographic concentration.
- The largest individual seller generated approximately **R$227K**, only around **1.7% of total revenue**, indicating that seller revenue is relatively diversified.
- Average delivery time was **12 days**, with **7,826 late orders** and an **8.11% late-delivery rate**.

---

## Business Recommendations

1. **Protect high-performing categories**  
   Health & Beauty, Watches & Gifts, Bed, Bath & Table, Sports & Leisure, and Computers & Accessories generate roughly 40% of marketplace revenue.

2. **Evaluate both revenue and sales volume**  
   High-volume categories are not necessarily the highest-value categories. Product strategy should consider both metrics.

3. **Reduce geographic concentration**  
   With 38.3% of revenue coming from São Paulo and 63.4% from the three largest states, Olist should explore growth opportunities in less-developed regional markets.

4. **Investigate late deliveries**  
   Analyze late deliveries by seller, region, and period to identify the main drivers behind the **8.11% late-delivery rate**.

5. **Monitor marketplace growth**  
   Order volume grew strongly between 2017 and 2018, but the stabilization around 6,000–7,000 monthly orders during much of 2018 should be monitored.

---

## Business Questions Answered

### How much revenue does Olist generate?

Olist generated approximately **R$13.22M in product revenue** from **96,478 delivered orders**, with an **average order value of R$137.04**.

---

### How have sales changed over time?

Order volume increased significantly during the analyzed period.

- **Jan–Aug 2017:** 21,998 orders
- **Jan–Aug 2018:** 52,783 orders
- **Growth:** approximately 140%

The strongest month was **November 2017**, with **7,289 orders**.

During much of 2018, monthly order volume stabilized around **6,000–7,000 orders**, following the rapid expansion observed throughout 2017.

---

### Which product categories perform best?

The highest-revenue categories were:

| Product Category | Revenue |
|---|---:|
| Health & Beauty | R$1.23M |
| Watches & Gifts | R$1.17M |
| Bed, Bath & Table | R$1.02M |
| Sports & Leisure | R$954.9K |
| Computers & Accessories | R$888.7K |

Together, these categories generated approximately **40% of total marketplace revenue**.

Revenue and sales volume also tell different stories.

**Bed, Bath & Table** had the highest volume with **10,953 order items**, while **Watches & Gifts** ranked second in revenue despite ranking only seventh in volume.

This suggests that Watches & Gifts generates substantially more revenue per item sold than some higher-volume categories.

---

### Which regions generate the most sales?

Revenue is strongly concentrated in Brazil's Southeast.

| Customer State | Revenue |
|---|---:|
| São Paulo | R$5.07M |
| Rio de Janeiro | R$1.76M |
| Minas Gerais | R$1.55M |
| Rio Grande do Sul | R$728.9K |
| Paraná | R$666.1K |

**São Paulo alone generated approximately 38.3% of total marketplace revenue.**

São Paulo, Rio de Janeiro, and Minas Gerais together accounted for approximately **63.4% of revenue**, demonstrating significant geographic concentration.

---

### Which sellers generate the most revenue?

The five highest-revenue sellers generated approximately:

| Seller | Revenue |
|---|---:|
| Seller 1 | R$227.0K |
| Seller 2 | R$217.9K |
| Seller 3 | R$196.9K |
| Seller 4 | R$190.9K |
| Seller 5 | R$186.6K |

Together, the top five sellers generated approximately **7.7% of total marketplace revenue**.

Even the largest seller represented only around **1.7% of total revenue**, suggesting that Olist's revenue is relatively diversified across its seller base rather than being dependent on a few sellers.

---

### How efficiently are orders delivered?

The average delivery time was **12 days**.

Of **96,478 delivered orders**:

- **7,826 were delivered late**
- **8.11% missed their estimated delivery date**
- Approximately **91.9% were delivered on time**

Although most orders arrived within the estimated delivery period, nearly **1 in every 12 orders was late**, making delivery reliability an important operational KPI.

---

## Power BI Dashboard

The final Power BI dashboard provides an interactive view of **sales, product, geographic, seller, and logistics performance**.

![Olist Marketplace Power BI Dashboard](dashboard/Dashboards.jpg)

### Main KPIs

- Total Revenue
- Total Orders
- Average Order Value
- Average Delivery Time
- Late Orders
- Late Delivery Rate

### Dashboard Analysis

The dashboard allows users to explore:

- Orders over time
- Revenue by product category
- Orders by product category
- Revenue by customer state
- Revenue by seller
- Delivery performance

Interactive filters allow analysis by **Year, Product Category, Customer State, and Seller State**.

### Power BI File

The complete interactive Power BI report is available here:

[`dashboard/Dashboards.pbix`](dashboard/Dashboards.pbix)

---

## Solution Architecture

All data processing and analytics development were performed in **SQL Server**, including **data profiling, data cleaning, transformation, ETL, data warehousing, dimensional modeling, data validation, and SQL analytics**.

**Power BI** was used as the final visualization and reporting layer.

```text
Olist CSV Datasets
        │
        ▼
SQL Server
        │
        ├── Data Profiling
        │
        ├── Data Cleaning & Transformation
        │
        ├── ETL Pipeline
        │
        ├── Data Warehouse
        │
        ├── Star Schema
        │
        ├── Data Validation
        │
        └── SQL Analytics
        │
        ▼
Power BI
        │
        ▼
Business Insights
```

---

## Data Warehouse

A dimensional **Star Schema** was designed to provide an analytics-ready model for SQL and Power BI.

```text
                 DimDate
                    │
                    │
DimCustomer ─── FactSales ─── DimProduct
                    │
                    │
                 DimSeller
```

### Dimension Tables

- `DimDate`
- `DimProduct`
- `DimSeller`
- `DimCustomer`

### Fact Table

- `FactSales`

The fact table contains more than **110,000 delivered order-item records** and stores measures including:

- Product Price
- Freight Value
- Delivery Days
- Late Delivery Flag

---

## ETL Pipeline

The SQL ETL pipeline transforms the operational Olist data into the dimensional warehouse.

Key transformations include:

- Data cleaning and standardization
- Product-category translation from Portuguese to English
- City-name standardization
- Duplicate handling
- Date-key generation
- Business-key to surrogate-key mapping
- Delivery-time calculation
- Late-delivery flag creation
- Filtering to delivered orders

---

## Data Validation

The warehouse was validated before being used for reporting.

Validation included:

- Source vs. warehouse row counts
- Revenue reconciliation
- Order-count reconciliation
- Duplicate detection
- Referential-integrity checks
- Missing dimension-key checks
- Delivery-time validation
- Late-delivery validation

This created an additional quality-control layer between the ETL pipeline and Power BI reporting.

---

## SQL Analytics

The analytical layer calculates business KPIs across:

**Sales**
- Total Revenue
- Average Order Value
- Orders by Month
- Revenue by Category
- Revenue by State
- Revenue by Seller

**Customers & Products**
- Orders by Category
- Customers by State
- Repeat Customers

**Logistics**
- Average Delivery Time
- Late Orders
- Late Delivery Rate

---

## Technology Stack

| Area | Technology |
|---|---|
| Database | SQL Server |
| Data Analysis | SQL / T-SQL |
| ETL | SQL / T-SQL |
| Data Warehousing | SQL Server |
| Data Modeling | Star Schema |
| Data Validation | SQL |
| Business Intelligence | Power BI |
| Version Control | Git & GitHub |

---

## Repository Structure

```text
Olist/
│
├── dashboard/
│   ├── Dashboards.jpg
│   └── Dashboards.pbix
│
├── data/
│   └── Olist CSV datasets
│
├── sql/
│   ├── 01_data_profiling/
│   ├── 02_data_modeling/
│   ├── 03_etl/
│   ├── 04_validation/
│   └── 05_analytics/
│
└── README.md
```

---

## Project Outcome

This project transformed fragmented Olist marketplace data into a **validated SQL Server data warehouse and interactive Power BI analytics solution**.

The solution provides a consolidated view of:

**Revenue → Orders → Products → Customers → Geography → Sellers → Logistics**

More importantly, the project demonstrates the complete analytics workflow from **raw data and ETL development to business analysis, data validation, and decision-focused Power BI reporting**.
