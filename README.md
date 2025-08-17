# SQL-DATA-WARHOUSE-PROJECT
Building a modern data warhouse using SQL server , including ETL process , DATA MODELING and ANALYTICS .

# 📦 Data Warehouse and Analytics Project

Welcome to the **Data Warehouse and Analytics Project** repository! 🚀  
This project demonstrates a comprehensive data warehousing and analytics solution, from building a data warehouse to generating actionable insights.  
Designed as a portfolio project, it highlights industry best practices in data engineering and analytics.

---

# 🧠 Data Warehouse Development Roadmap

This repository outlines the step-by-step development of a modern data warehouse using SQL Server. Each phase is broken down into epics and tasks to guide implementation and ensure best practices.

---

🏗️ DATA ARCHITECTURE 
- **The data architecture for this project follows Medallion Architecture Bronze, Silver, and Gold layers:**

1. **Bronze Layer**: Stores raw data as-is from the source systems. Data is ingested from CSV Files into SQL Server Database.  
2. **Silver Layer**: This layer includes data cleansing, standardization, and normalization processes to prepare data for analysis.  
3. **Gold Layer**: Houses business-ready data modeled into a star schema required for reporting and analytics.

### 🔹 LAYER BREAKDOWN

- **Bronze Layer**
  - Stores raw data exactly as received from source systems (e.g., CSV files).
  - Preserves original fidelity for traceability and reprocessing.
  - Loaded into SQL Server staging tables using bulk insert scripts with error handling and logging.

- **Silver Layer**
  - Cleanses and standardizes data (e.g., formats, null handling).
  - Normalizes multi-valued fields and applies basic transformation logic.
  - Produces structured, reliable data ready for modeling.

- **Gold Layer**
  - Models data into star schemas (fact and dimension tables).
  - Applies business rules for reporting and analytics.
  - Optimized for BI tools like Power BI or Tableau.
  - Includes execution time tracking and audit logging for performance and traceability.

---

📖 PROJECT OVERVIEW

This project involves:

1. **Data Architecture**: Designing a Modern Data Warehouse Using Medallion Architecture Bronze, Silver, and Gold layers.  
2. **ETL Pipelines**: Extracting, transforming, and loading data from source systems into the warehouse.  
3. **Data Modeling**: Developing fact and dimension tables optimized for analytical queries.  
4. **Analytics & Reporting**: Creating SQL-based reports and dashboards for actionable insights.

---

🚀 PROJECT REQUIRMENTS  
**Building the Data Warehouse (Data Engineering)**

**Objective**  
Develop a modern data warehouse using SQL Server to consolidate sales data, enabling analytical reporting and informed decision-making.

**Specifications**  
1. **Data Sources**: Import data from two source systems (ERP and CRM) provided as CSV files.  
2. **Data Quality**: Cleanse and resolve data quality issues prior to analysis.  
3. **Integration**: Combine both sources into a single, user-friendly data model designed for analytical queries.  
4. **Scope**: Focus on the latest dataset only; historization of data is not required.  
5. **Documentation**: Provide clear documentation of the data model to support both business stakeholders and analytics teams.

---

📊 BI : ANALYTICS & REPORTING (Data Analysis)

**Objective**  
Develop SQL-based analytics to deliver detailed insights into:

- Customer Behavior  
- Product Performance  
- Sales Trends

These insights empower stakeholders with key business metrics, enabling strategic decision-making.

📄 For more details, refer to `docs/requirements.md`.

---

## 📁 REPOSITORY STRUCTURE

| Folder/File                | Description                                                  |
|---------------------------|--------------------------------------------------------------|
| `datasets/`               | Raw datasets used for the project (ERP and other sources)    |
| `docs/`                   | Project documentation and architecture diagrams              |
| ├── `etl.drawio`          | ETL techniques and methods diagram                           |
| ├── `data_architecture.drawio` | Overall project architecture diagram                 |
| ├── `data_catalog.md`     | Dataset catalog with field descriptions                      |
| ├── `data_flow.drawio`    | Data flow diagram                                            |
| ├── `data_models.drawio`  | Star schema data models                                      |
| ├── `naming-conventions.md` | Naming guidelines for tables, columns, and files         |
| `scripts/`                | SQL scripts for ETL and transformations                      |
| ├── `bronze/`             | Extract and load raw data                                    |
| ├── `silver/`             | Clean and transform data                                     |
| ├── `gold/`               | Create analytical models                                     |
| `tests/`                  | Test scripts and data quality checks                         |
| `README.md`               | Project overview and instructions                            |
| `LICENSE`                 | License information                                          |
| `.gitignore`              | Git ignore rules                                             |
| `requirements.txt`        | Project dependencies                                         |



---



## 📄 LICENSE

This project is licensed under the MIT License. You are free to use, modify, and share this project with proper attribution.

---

🌟 ABOUT ME
---

# **Naming Conventions**

This document outlines the naming conventions used for schemas, tables, views, columns, and other objects in the data warehouse.

## **Table of Contents**

1. [General Principles](#general-principles)
2. [Table Naming Conventions](#table-naming-conventions)
   - [Bronze Rules](#bronze-rules)
   - [Silver Rules](#silver-rules)
   - [Gold Rules](#gold-rules)
3. [Column Naming Conventions](#column-naming-conventions)
   - [Surrogate Keys](#surrogate-keys)
   - [Technical Columns](#technical-columns)
4. [Stored Procedure](#stored-procedure-naming-conventions)
---

## **General Principles**

- **Naming Conventions**: Use snake_case, with lowercase letters and underscores (`_`) to separate words.
- **Language**: Use English for all names.
- **Avoid Reserved Words**: Do not use SQL reserved words as object names.

## **Table Naming Conventions**

### **Bronze Rules**
- All names must start with the source system name, and table names must match their original names without renaming.
- **`<sourcesystem>_<entity>`**  
  - `<sourcesystem>`: Name of the source system (e.g., `crm`, `erp`).  
  - `<entity>`: Exact table name from the source system.  
  - Example: `crm_customer_info` → Customer information from the CRM system.

### **Silver Rules**
- All names must start with the source system name, and table names must match their original names without renaming.
- **`<sourcesystem>_<entity>`**  
  - `<sourcesystem>`: Name of the source system (e.g., `crm`, `erp`).  
  - `<entity>`: Exact table name from the source system.  
  - Example: `crm_customer_info` → Customer information from the CRM system.

### **Gold Rules**
- All names must use meaningful, business-aligned names for tables, starting with the category prefix.
- **`<category>_<entity>`**  
  - `<category>`: Describes the role of the table, such as `dim` (dimension) or `fact` (fact table).  
  - `<entity>`: Descriptive name of the table, aligned with the business domain (e.g., `customers`, `products`, `sales`).  
  - Examples:
    - `dim_customers` → Dimension table for customer data.  
    - `fact_sales` → Fact table containing sales transactions.  

#### **Glossary of Category Patterns**

| Pattern     | Meaning                           | Example(s)                              |
|-------------|-----------------------------------|-----------------------------------------|
| `dim_`      | Dimension table                  | `dim_customer`, `dim_product`           |
| `fact_`     | Fact table                       | `fact_sales`                            |
| `report_`   | Report table                     | `report_customers`, `report_sales_monthly`   |

## **Column Naming Conventions**

### **Surrogate Keys**  
- All primary keys in dimension tables must use the suffix `_key`.
- **`<table_name>_key`**  
  - `<table_name>`: Refers to the name of the table or entity the key belongs to.  
  - `_key`: A suffix indicating that this column is a surrogate key.  
  - Example: `customer_key` → Surrogate key in the `dim_customers` table.
  
### **Technical Columns**
- All technical columns must start with the prefix `dwh_`, followed by a descriptive name indicating the column's purpose.
- **`dwh_<column_name>`**  
  - `dwh`: Prefix exclusively for system-generated metadata.  
  - `<column_name>`: Descriptive name indicating the column's purpose.  
  - Example: `dwh_load_date` → System-generated column used to store the date when the record was loaded.
 
## **Stored Procedure**

- All stored procedures used for loading data must follow the naming pattern:
- **`load_<layer>`**.
  
  - `<layer>`: Represents the layer being loaded, such as `bronze`, `silver`, or `gold`.
  - Example: 
    - `load_bronze` → Stored procedure for loading data into the Bronze layer.
    - `load_silver` → Stored procedure for loading data into the Silver layer.


