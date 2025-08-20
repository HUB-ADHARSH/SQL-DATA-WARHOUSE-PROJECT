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

![Dashboard Screenshot](docs/DATA ARCHITECTURE.png)


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


