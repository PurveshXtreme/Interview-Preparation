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

# 📘 Data Warehousing Building Blocks (Proper Notes)

A Data Warehouse is designed using a set of core building blocks that help structure data for analysis.  
The four primary building blocks are:

- Fact Tables  
- Dimension Tables  
- Measures (Facts)  
- Schemas  

These form the foundation of dimensional modeling.

---

# 1️⃣ Fact Tables

A **Fact Table** is the central table in a Data Warehouse model. It stores **quantitative, numeric, measurable data** about business processes.

### Purpose:
- Record business events such as sales, transactions, shipments.
- Provide values that analysts want to aggregate and study.

### Characteristics of Fact Tables:
- Contain **numeric measures** (facts).
- Contain **foreign keys** referencing dimension tables.
- Usually very large in size.
- Represent data at a specific **granularity** (e.g., one row per sale).

### Examples:
- Sales Fact → sales_amount, quantity, discount  
- Order Fact → order_count, shipping_cost  

---

# 2️⃣ Dimension Tables

A **Dimension Table** provides the **context** for facts. These tables store **descriptive attributes** that help analyze and group facts.

### Purpose:
Answer questions like:
- Who purchased? (Customer)  
- What was purchased? (Product)  
- When was it purchased? (Time)  
- Where was it purchased? (Location)

### Characteristics of Dimension Tables:
- Contain **textual** or **categorical** data.
- Have a **primary key** (often a surrogate key).
- Smaller compared to fact tables.
- Used to slice and filter data in reports.

### Examples:
- Customer Dimension → name, age, city  
- Product Dimension → name, brand, category  
- Time Dimension → date, month, year  

---

# 3️⃣ Measures (Facts)

**Facts** are the numeric values stored inside fact tables. They represent measurable business data.

### Types of Facts:

#### ✔ Additive Facts
- Can be added across all dimensions.
- Example: sales_amount, quantity_sold.

#### ✔ Semi-Additive Facts
- Can be added across some dimensions, but not all (usually not across time).
- Example: account_balance, inventory_level.

#### ✔ Non-Additive Facts
- Cannot be added at all.
- Example: percentage, ratio.

### Importance:
Facts drive business KPIs and analytical reports.

---

# 4️⃣ Schemas (Model Structures)

Schemas define how fact and dimension tables are organized.

### ⭐ Star Schema
- Most widely used schema in DW.
- Fact table at the center, surrounded by dimension tables.
- Dimensions are **not normalized**.
- Simple and fast for queries.

### ❄ Snowflake Schema
- Dimensions are **normalized** into multiple related tables.
- More complex structure.
- Saves space but slower for analysis.

### Importance:
Choosing the schema affects performance, usability, and maintainability.

---

# 📌 Summary of Building Blocks

- **Fact Tables** store numeric values about business events.  
- **Dimension Tables** store descriptive information that explains the facts.  
- **Facts (Measures)** include numeric data used in analysis (additive, semi-additive, non-additive).  
- **Schemas** (Star, Snowflake) define how fact and dimension tables are linked.

These building blocks together make data in the warehouse **organized**, **analyzable**, and **efficient** for reporting.

---

# 📘 Dimensional Modeling

Dimensional Modeling is a design technique used in Data Warehousing to make data easy to understand and fast for querying.  
It organizes data into:
- **Fact Tables** (measurements)
- **Dimension Tables** (descriptive context)

It is mainly used for analytical processing (OLAP).

---

# ⭐ Core Components of Dimensional Modeling

## 1️⃣ Fact Tables
- Store measurable, numeric data (facts)
- Examples: sales amount, quantity sold
- Contain foreign keys referencing dimensions
- Represent business processes

## 2️⃣ Dimension Tables
- Store descriptive attributes of business entities
- Examples: customer name, product category, time, location
- Contain primary keys (usually surrogate keys)
- Used for slicing, filtering, grouping data

---

# 📌 Star Schema vs Snowflake Schema

## ⭐ Star Schema
- Fact table at the center
- Dimension tables directly connected
- Dimensions are *not normalized*
- Simpler and faster for querying

### Structure:
Fact Table → Dimension Table (1-to-Many)

## ❄ Snowflake Schema
- Dimensions are normalized into multiple related tables
- More complex structure
- Saves storage but slower for analysis

### Structure:
Fact Table → Dimension → Sub-Dimension

### Comparison Table:

| Star Schema | Snowflake Schema |
|-------------|------------------|
| Denormalized dimensions | Normalized dimensions |
| Faster query performance | Slower queries |
| Simple design | Complex design |
| Uses more storage | Uses less storage |
| Best for reporting | Best for complex DW design |

---

# 📌 Facts, Fact Tables, Dimensions, and Dimension Tables

## Facts
- Numerical measurements used for analysis
- Examples: revenue, profit, units sold
- Can be additive, semi-additive, or non-additive

## Fact Tables
- Central tables containing facts and foreign keys
- Usually very large
- Represent business events or processes

## Dimensions
- Textual descriptive data about entities
- Examples: product, customer, time, store

## Dimension Tables
- Contain dimension attributes
- Used for grouping, filtering, slicing data in reports
- Connected to fact tables through keys

---

# 📌 Types of Fact Tables (4 Main Types)

## 1️⃣ Transaction Fact Table
- Records individual business transactions
- Most detailed (lowest granularity)
- Example: each sales transaction

## 2️⃣ Periodic Snapshot Fact Table
- Captures data at fixed intervals (daily, monthly)
- Used for trend analysis
- Example: daily inventory levels, monthly account balances

## 3️⃣ Accumulating Snapshot Fact Table
- Tracks a process with multiple stages
- Updated as process progresses
- Example: order fulfillment lifecycle (order → shipped → delivered)

## 4️⃣ Factless Fact Table
- Contains only foreign keys, no numeric facts
- Used for event tracking or coverage analysis
- Example: student attendance, employee training participation

---

# 📌 Summary

Dimensional modeling organizes data into fact and dimension tables for fast analytical queries.  
Star schema is simpler and faster; snowflake schema is normalized and more complex.  
Fact tables store measurements; dimension tables store descriptive information.  
Four fact table types: Transaction, Periodic Snapshot, Accumulating Snapshot, and Factless Fact Tables.

---


