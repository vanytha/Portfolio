# Data Pipeline Architecture for Reporting and Analytics

This document describes the **data pipeline architecture used for reporting and analytics**, including data extraction, ETL processing, storage, and visualization layers.

---
## Data Pipeline Architecture Diagram
<img width="638" height="1321" alt="mermaid-diagram" src="https://github.com/user-attachments/assets/3a5ab25a-002a-44a7-b792-16c2d2d96ecd" />

## 1. Data Extraction (Sources)

Data is collected from multiple **SQL Server instances** and **network file shares**.

### SQL Server Sources

Data is pulled from the following SQL Server instances:

- `dbprodus08\us08` – United States
- `dbprodca08\ca08` – Canada

Within these servers, data is stored across multiple schemas, such as:

- `sc_rca_xxxx`
- `sc_rca_yyyy`
- `sc_rca_zzzz`

These schemas contain operational data used for analytics and reporting.

### File-Based Sources

Additional data is sourced from **network file shares**, such as:

- `JDE_orders`
 
---

## 2. Data Preparation (ETL – Tableau Prep)

Data preparation and transformation are performed using **Tableau Prep**.

ETL flows use **SQL views** to transform and prepare the data before it is loaded into the reporting warehouse.

### Key ETL Activities

- Joining multiple tables and file-based datasets
- Applying business rules
- Performing calculated transformations

### Views Used in the ETL Process

**Source Views**

- These views are created in the `tableauprep` schema.
- They reference data from various `sa_rca` variants for both **U.S. and Canada**.

**Staging Views**

- Staging views are created in the **`Tableau_Config` database**.
- These views **UNION the sa_rca variants** into a unified dataset.
- Separate staging views exist for **U.S. and Canadian datasets**.

---

## 3. Data Storage (Destination Warehouse)

The ETL outputs are stored in two formats for reporting and analysis.

### SQL Server Data Warehouse

- Data is stored in the **`dw_Tableau` database** on SQL Server.
- This warehouse serves as the central data source for reporting systems.

### Tableau Extract Storage

Data is also stored as **Tableau Hyper Extracts**, which enable faster query performance for dashboards.

- Tableau Server location:  
  `https://bi.cxs.com/#/projects/46`

Hyper extracts allow dashboards to run high-performance analytical queries without directly querying the operational database.

---

## 4. Data Visualization (Reports and Dashboards)

**Tableau Server** hosts multiple dashboard projects aligned with different business functions.

### Dashboard Projects

| Project | Description |
|-------|-------------|
| Client Services | Customer insights and service metrics |
| Clients | Client-specific performance metrics |
| CXS | Metrics for the SaaS-based recognition platform |
| Leadership | Strategic KPIs and executive-level reporting |
| Operations | Operational efficiency and workflow monitoring |
| Sales | Sales pipeline, targets, and performance tracking |
 
These dashboards provide real-time insights and business intelligence to various organizational teams.

 
