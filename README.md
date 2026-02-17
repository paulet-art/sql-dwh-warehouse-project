# Sales SQL Data Warehouse

## 📌 Project Overview
This project implements a **Sales Data Warehouse** using SQL to support reliable analytics, reporting, and business insights. The warehouse follows modern data-warehousing best practices, including layered data modeling, data quality checks, and analytics-ready schemas.

The goal is to transform raw sales data into a **single source of truth** that can be consumed by BI tools, analysts, and downstream applications.

---

## 🏗️ Architecture Overview
The data warehouse is designed using a **layered (medallion) architecture**:
<img width="1157" height="619" alt="image" src="https://github.com/user-attachments/assets/54032b53-f2d2-4bfd-ac58-73265466fa4c" />


- **Bronze Layer** – Raw, ingested data
- **Silver Layer** – Cleaned, validated, and transformed data
- **Gold Layer** – Business-ready fact and dimension tables for analytics

This approach ensures **data reliability, scalability, and auditability**.

---

## 📂 Data Layers
<img width="1273" height="652" alt="image" src="https://github.com/user-attachments/assets/680de444-f552-436e-85e4-27ac0e64df56" />


### 1️⃣ Bronze Layer (Raw Data)
**Purpose:** Preserve raw source data exactly as received.

- Stores raw sales, customer, product, and transaction data
- Minimal transformations applied
- Acts as a historical record and recovery layer

**Key Characteristics**
- Append-only tables
- No business logic applied
- Used for traceability and debugging

---

### 2️⃣ Silver Layer (Clean & Conformed Data)
**Purpose:** Improve data quality and standardization.

**Transformations Applied**
- Data type standardization
- Deduplication
- Null handling and default values
- Referential integrity checks
- Basic business rules (e.g. valid dates, positive sales values)

**Outcome**
- Clean, trustworthy datasets
- Conformed entities across sources (customers, products, dates)

---

### 3️⃣ Gold Layer (Analytics-Ready Data)
**Purpose:** Enable fast and reliable analytics.

**Modeling Approach**
- Star schema design
- Fact and dimension tables

**Core Tables**
- `fact_sales`
- `dim_customers`
- `dim_products`
- `dim_date`
- `dim_regions`

These tables are optimized for:
- BI dashboards
- Ad-hoc SQL analysis
- KPI tracking and trend analysis

---

## 🧠 Data Modeling
The warehouse uses **dimensional modeling** principles:

- Facts capture measurable business events (e.g. sales amount, quantity)
- Dimensions provide descriptive context (customer, product, time)

This structure improves:
- Query performance
- Business understanding
- Scalability for future metrics

---

## ✅ Data Quality & Validation
To ensure trust in the data, the following checks are implemented:

- Primary key uniqueness checks
- Foreign key consistency between facts and dimensions
- Null and outlier detection
- Duplicate record detection
- Schema validation

These checks help catch data issues early before reaching dashboards.

---

## 📊 Analytics Use Cases
The warehouse supports key sales analytics such as:

- Total and average sales over time
- Top-performing products and customers
- Regional sales performance
- Month-over-month and year-over-year growth
- Sales trends and seasonality analysis

---

## 🛠️ Tools & Technologies
- **SQL** – Core transformation and modeling logic  
- **Relational Database** – Data warehouse storage  
- **BI Tools (Optional)** – Power BI / Tableau for visualization  
- **Version Control** – Git for tracking changes  
