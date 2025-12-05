# 📑 Table of Contents (TOC)

- [1️⃣ What is a Data Warehouse?](#1️⃣-what-is-a-data-warehouse)
  - [Properties](#properties)
  - [Simple Example](#simple-example)

- [2️⃣ Difference Between OLTP and OLAP](#2️⃣-difference-between-oltp-and-olap)

- [3️⃣ Introduction to Data Warehouse Architecture](#3️⃣-introduction-to-data-warehousing-architecture)
  - [Architecture Diagram](#data-warehouse-architecture-descriptive-diagram)

- [4️⃣ Introduction to ETL](#1️⃣-introduction-to-etl-and-data-movement-for-data-warehousing)

- [5️⃣ ETL Design Basics](#2️⃣-introduction-to-etl-design)

- [6️⃣ Core Building Blocks of a Data Warehouse](#🧱-core-building-blocks-of-a-data-warehouse)

- [7️⃣ Fact Tables](#1️⃣-fact-tables)
  - [Purpose](#🎯-purpose)
  - [Characteristics](#🧩-characteristics)
  - [Examples](#📌-examples)

- [8️⃣ Types of Fact Tables](#📌-types-of-fact-tables-4-important-types)
  - [Transaction Fact Table](#1️⃣-transaction-fact-table)
  - [Periodic Snapshot Fact Table](#2️⃣-periodic-snapshot-fact-table)
  - [Accumulating Snapshot Fact Table](#3️⃣-accumulating-snapshot-fact-table)
  - [Factless Fact Table](#4️⃣-factless-fact-table)

- [9️⃣ Dimension Tables](#2️⃣-dimension-tables)
  - [Purpose](#🎯-purpose-1)
  - [Characteristics](#🧩-characteristics-1)
  - [Examples](#📌-examples-1)

- [🔟 Measures (Facts)](#3️⃣-measures-facts)

- [1️⃣1️⃣ Types of Facts](#🔢-types-of-facts-very-important-interview-topic)
  - [Additive Facts](#1️⃣-additive-facts)
  - [Semi-Additive Facts](#2️⃣-semi-additive-facts)
  - [Non-Additive Facts](#3️⃣-non-additive-facts)

- [1️⃣2️⃣ Schemas in Data Warehousing](#📘-schemas-in-data-warehousing-proper-explanation)

- [1️⃣3️⃣ Star Schema](#⭐-1️⃣-star-schema-most-common-schema)

- [1️⃣4️⃣ Snowflake Schema](#❄-2️⃣-snowflake-schema-normalized-schema)

- - [1️⃣ Slowly Changing Dimensions (SCD)](#1️⃣-slowly-changing-dimensions-scd)
  - [What is SCD?](#what-is-scd)
  - [Types of SCD](#⭐-types-of-slowly-changing-dimensions)
  - [SCD Type 0 — Fixed Dimension](#1️⃣-scd-type-0--fixed-dimension)
  - [SCD Type 1 — Overwrite](#2️⃣-scd-type-1--overwrite-no-history)
  - [SCD Type 2 — Full History Tracking](#3️⃣-scd-type-2--full-history-tracking-most-important)
  - [SCD Type 3 — Limited History](#4️⃣-scd-type-3--limited-history-tracking)



# 1️⃣ What is a Data Warehouse? (Simple + Interview Answer)

A **Data Warehouse (DW)** is a centralized storage system that collects data from multiple sources, cleans it, integrates it, and stores it for reporting and analysis.

## **Properties:**

### **1. Subject-oriented**  
Data is categorized and stored by business subject rather than by application.(Sales, HR, Finance)

### **2. Integrated**  
Data is collected from different sources and combined into one place.

### **3. Time-variant**  
Data is stored as a series of snapshots, each representing a period of time.(stores historical data)

### **4. Nonvolatile**  
Typically, data in the data warehouse is not updated or deleted.
once data is loaded, it rarely changes

---

## **Simple example:**

If a company has data in websites, apps, Excel files, CRM…  
→ A Data Warehouse collects everything in one place so business teams can analyze it.

---

# Difference Between OLTP and OLAP

| OLTP (Online Transaction Processing) | OLAP (Online Analytical Processing) |
|--------------------------------------|--------------------------------------|
| Handles day-to-day transactions | Used for reporting and analysis |
| Contains current data | Contains historical data |
| Based on Entity Relationship (ER) Model | Based on Star, Snowflake, and Fact Constellation schemas |
| Used for writing data into the database | Used for reading data from the data warehouse |
| Database size ranges from 100 MB to 1 GB | Data warehouse size ranges from 100 GB to 1 TB |
| Fast; provides high performance | Highly flexible, but not fast |

---

# 📌 1️⃣ Introduction to Data Warehousing Architecture

A **Data Warehouse Architecture** defines how data flows from source systems to the warehouse and then to reporting tools.  
It shows the **layers, components, and processes** involved.

Think of it as the **blueprint** of how a data warehouse works.

---

# Data Warehouse Architecture (Descriptive Diagram)

                     +--------------------------------------+
                     |            SOURCE SYSTEMS             |
                     |--------------------------------------|
                     | OLTP Databases • CRM • ERP • APIs    |
                     | Excel/CSV Files • Logs • Web Apps    |
                     +------------------+-------------------+
                                        |
                                        v
                     +--------------------------------------+
                     |             STAGING AREA              |
                     |--------------------------------------|
                     | Temporary storage for RAW data        |
                     | No cleaning or validation yet         |
                     | Used to collect data from all sources |
                     +------------------+-------------------+
                                        |
                                        v
                     +--------------------------------------+
                     |                  ETL                  |
                     |--------------------------------------|
                     | EXTRACT → from staging                |
                     | TRANSFORM → clean, validate, format   |
                     | handle SCDs, business rules           |
                     | LOAD → into DW tables                 |
                     +------------------+-------------------+
                                        |
                                        v
                     +--------------------------------------+
                     |           DATA WAREHOUSE              |
                     |--------------------------------------|
                     | Central repository with:              |
                     | • Fact Tables (measures)              |
                     | • Dimension Tables (descriptions)     |
                     | Stores historical, integrated data    |
                     +------------------+-------------------+
                                        |
                                        v
                     +--------------------------------------+
                     |              DATA MARTS               |
                     | (Optional, Subject-Specific Areas)    |
                     |--------------------------------------|
                     | Examples: Sales Mart, Finance Mart    |
                     | Provide faster, focused analysis      |
                     +------------------+-------------------+
                                        |
                                        v
                     +--------------------------------------+
                     |          BI & REPORTING LAYER         |
                     |--------------------------------------|
                     | Dashboards • Reports • Analytics      |
                     | Tools: Power BI, Tableau, Excel       |
                     +--------------------------------------+

---

# ✅ 1️⃣ Introduction to ETL and Data Movement for Data Warehousing

ETL stands for:

- **Extract** → Pull data from source systems  
- **Transform** → Clean, validate, format, apply rules  
- **Load** → Store data into the Data Warehouse  

ETL is the *heart* of data warehousing because it moves data from **OLTP → Data Warehouse**.

**Simple Flow:**  
Sources → Staging → ETL → Data Warehouse


# 2️⃣ Introduction to ETL Design

ETL Design defines **how** data will be extracted, transformed, and loaded.

Good ETL design ensures:
- Correct and clean data  
- Fast and efficient processing  
- Easy maintenance  
- Proper handling of data history (SCD)


---

🧱 Core Building Blocks of a Data Warehouse  
The four primary components are:

- Fact Tables  
- Dimension Tables  
- Measures (Facts)  
- Schemas (Star & Snowflake)  


# 1️⃣ Fact Tables

A Fact Table is the central table in a data warehouse.  
It stores quantitative, numeric, measurable business data.

## 🎯 Purpose
- Store numerical measures (sales, profit, quantity).  
- Record business events (transactions, payments).  
- Provide values for aggregation (SUM, AVG, MAX).

## 🧩 Characteristics
- Contains foreign keys referencing dimension tables.  
- Usually very large compared to dimensions.  
- Represents a defined granularity (e.g., each sale).  
- Always numeric facts.

## 📌 Examples

### Sales Fact Table:
- sales_amount  
- quantity_sold  
- discount  
- product_key, customer_key, date_key  


---

# 📌 Types of Fact Tables (4 Important Types)

## 1️⃣ Transaction Fact Table
- Most detailed  
- Records individual transactions  
- Example: Each sale event  

## 2️⃣ Periodic Snapshot Fact Table
- Captures data at fixed intervals (daily, monthly)  
- Useful for trends  
- Example: Daily inventory levels  

## 3️⃣ Accumulating Snapshot Fact Table
- Tracks lifecycle-based processes  
- Updates as each stage completes  
- Example: Order lifecycle → Ordered → Packed → Shipped → Delivered  

## 4️⃣ Factless Fact Table
Contains only foreign keys, no numeric facts.  
Used for:
- Event tracking (attendance)  
- Coverage analysis (promotion applied or not)  


---

# 2️⃣ Dimension Tables

A Dimension Table provides descriptive information that gives meaning to facts.

## 🎯 Purpose
Dimensions answer business questions such as:

- Who made the purchase? → Customer Dimension  
- What was purchased? → Product Dimension  
- When was it purchased? → Time Dimension  
- Where was it purchased? → Location Dimension  

## 🧩 Characteristics
- Contain textual, descriptive, or categorical attributes.  
- Have a primary key (usually surrogate).  
- Smaller in size than fact tables.  
- Used for grouping, filtering, slicing, dicing in reports.

## 📌 Examples
- Customer Dimension: name, age, gender, city  
- Product Dimension: name, brand, category  
- Time Dimension: date, month, quarter, year  


---

# 3️⃣ Measures (Facts)

Measures are the numeric values inside fact tables.  
They are the core of business analysis.

---

# 🔢 Types of Facts (Very Important Interview Topic)

Facts can behave differently when we try to aggregate (SUM, AVG, MAX, MIN) them.  
That’s why we classify them into 3 categories:

---

# 1️⃣ Additive Facts

## ✔ Definition
These facts can be summed (added) across **all dimensions** in the data warehouse.

Meaning:  
No matter how you slice the data (by time, product, customer, region),  
the total is meaningful.

## ✔ Examples
- sales_amount  
- quantity_sold  
- revenue  
- cost  

## ✔ Why additive?
If you sum:

- sales_amount for a day  
- then sum again for a month  
- and again for a year  

➡ The totals remain valid and correct.

## ✔ Example Scenario
| Date | Product | Sales Amount |
|------|---------|--------------|
| 1 Jan | TV | 20,000 |
| 1 Jan | Laptop | 30,000 |

Total Sales = 20,000 + 30,000 = **50,000**  
(Valid across any dimension)

👉 These are the easiest facts to work with.

---

# 2️⃣ Semi-Additive Facts

## ✔ Definition
These facts can be added across some dimensions,  
but **NOT across the time dimension**.

### Why not across time?  
Because these facts represent a **state at a point in time**, not a quantity.

## ✔ Examples
- account_balance  
- inventory_level  
- stock_on_hand  

## ✔ Explanation
If your bank balance is:

- 1 Jan → ₹50,000  
- 2 Jan → ₹55,000  
- 3 Jan → ₹60,000  

👉 You **cannot** add them:  
50k + 55k + 60k = **165k** ❌ (Meaningless)

But you *can* aggregate across other dimensions (e.g., customers or accounts).

## ✔ Correct usage
For semi-additive facts, we typically use:

- MAX(balance)  
- MIN(balance)  
- Ending balance  
- Average inventory  

---

# 3️⃣ Non-Additive Facts

## ✔ Definition
These facts **cannot be added across any dimension**.

Because adding them makes no sense mathematically.

## ✔ Examples
- percentage (conversion rate)  
- ratios (profit margin)  
- percent_growth  

## ✔ Why not additive?
If profit margin is:

- Product A: 20%  
- Product B: 30%  

You cannot do:  
20% + 30% = 50% ❌ (Wrong)

Instead, you must calculate a weighted metric:

```
Profit Margin = Total Profit / Total Sales
```

## ✔ Best way to use non-additive facts
Recompute them using **additive fields**.

---

# 📘 Schemas in Data Warehousing (Proper Explanation)

A Schema defines how tables (Fact + Dimension) are structured and connected in a Data Warehouse.

Schemas are part of Dimensional Modeling, and they determine:

- How fast queries run  
- How easy reporting becomes  
- How clean and organized the structure is  

There are two most important schemas:

- Star Schema  
- Snowflake Schema  

(These are the ones asked in interviews.)

---

# ⭐ 1️⃣ Star Schema (Most Common Schema)

The Star Schema is the simplest and most widely used schema in Data Warehousing.

It is called a *star* because the diagram looks like a star:

```
            Dim_Customer
                 |
Dim_Product — Fact_Sales — Dim_Time
                 |
            Dim_Store
```

## ✔ Structure
- One central Fact Table  
- Multiple Dimension Tables directly connected to it  
- Dimensions are **NOT normalized** (no sub-tables)

## ✔ Example

### Fact Table: Fact_Sales
- sales_amount  
- quantity  
- date_key  
- product_key  
- customer_key  

### Dimension Tables:
- Dim_Product (product_name, category, brand)  
- Dim_Customer (name, city, age)  
- Dim_Time (day, month, year)  
- Dim_Store (store_name, location)  


---

# ❄ 2️⃣ Snowflake Schema (Normalized Schema)

A Snowflake Schema is an extension of the Star Schema.

In this schema, **dimension tables are normalized** into multiple related tables.  
The structure looks like a snowflake because dimensions further branch out:

```
                 Dim_Product
                     |
                Sub_Dim_Category
                     |
Dim_Customer — Fact_Sales — Dim_Time
                     |
                 Sub_Dim_Region
```

## ✔ Structure
- Fact table in the center  
- Dimension tables connected  
- Dimensions have **sub-dimensions** (normalized)


## ✔ Example

### Star Schema Dimension:
```
Dim_Product
(product_id, product_name, category_name)
```

### Snowflake Schema Dimensions:
```
Dim_Product
(product_id, product_name, category_id)

Dim_Category
(category_id, category_name)
```


---

# 🧩 1️⃣ Slowly Changing Dimensions (SCD)

## What is SCD?
A **Slowly Changing Dimension (SCD)** is used in Data Warehousing to **manage and track changes** in dimension table attributes over time.

Dimension data changes slowly — such as:
- Customer address  
- Employee department  
- Product category  

We use SCD techniques to **store historical changes correctly**.

---

# ⭐ Types of Slowly Changing Dimensions

There are **3 major SCD Types** used in the industry + **1 additional type** that stores limited history.

---

# 1️⃣ SCD Type 0 — Fixed Dimension

No changes are allowed.  
Once data is inserted, it remains **unchanged forever**.

### ✔ Use Case:
- **Date Dimension**  
- **Time Dimension**

These values never change.

---

# 2️⃣ SCD Type 1 — Overwrite (No History)

Old values are **overwritten** with new values.  
No historical record is kept.

### ✔ Example  
Customer moves from **Pune → Mumbai**

| Customer | City (Before) | City (After Update) |
|----------|---------------|----------------------|
| John     | Pune          | Mumbai               |

After update → **City = Mumbai** (Old value lost)

---

# 3️⃣ SCD Type 2 — Full History Tracking (Most Important)

Stores **complete history** by creating a **new row** for every change.

### SCD Type 2 typically includes:
- Surrogate key  
- Business key  
- Start date  
- End date  
- Current flag (Y/N)  

### ✔ Example  
Customer moves from **Pune → Mumbai**

| SK | Cust_ID | City   | Start_Date   | End_Date     | Current_Flag |
|----|---------|--------|--------------|--------------|--------------|
| 1  | 1001    | Pune   | 2019-01-01   | 2024-05-01   | N            |
| 2  | 1001    | Mumbai | 2024-05-02   | NULL         | Y            |

---

# 4️⃣ SCD Type 3 — Limited History Tracking

Stores **only limited history**, usually only the **previous value**.

### ✔ Example

| Customer | Current_City | Previous_City |
|----------|--------------|----------------|
| John     | Mumbai       | Pune           |

---




