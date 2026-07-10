# End-to-End-Banking-Data-Engineering-Project-on-Microsoft-Fabric

## Project Overview

This project demonstrates the design and implementation of a complete end-to-end Data Engineering solution using Microsoft Fabric. The project simulates a real-world banking analytics platform by ingesting structured banking data from an on-premises environment, transforming and validating the data, implementing Slowly Changing Dimension (SCD Type 1), building a Lakehouse architecture, and creating a Power BI semantic model for reporting.

The project follows modern Medallion Architecture principles and demonstrates practical experience with Microsoft Fabric, Lakehouse, Delta Tables, Dataflow Gen2, PySpark, Spark SQL, and Power BI.

---

# Project Architecture

```
CSV Files (AI Banking Dataset)        Azure Data Lake Storage Gen2
            │                                      │
            ▼                                      ▼
Azure VM (On-Premises Simulation)           OneLake Shortcut
            │                                      │
            ▼                                      │                                     
On-Premises Data Gateway                           │
            │                                      │
            ▼                                      ▼

                        Dataflow Gen2
                              │
                              ▼
                Lakehouse (Bronze / Staging)
                              │
                              ▼
                  Microsoft Fabric Notebook
                              ├───────────────┐
                              │               │
                              ▼               ▼
                       Dimension Tables   Fact Tables
                       (SCD Type 1)       (Delta Format)
                                      │
                                      ▼
                           Lakehouse (Silver / Gold)
                                      │
                                      ▼
                             Power BI Semantic Model
                                      │
                                      ▼
                               Power BI Dashboard
```

---

# Technologies Used

- Microsoft Fabric
- OneLake
- Lakehouse
- Dataflow Gen2
- PySpark
- Spark SQL
- Delta Lake
- Azure Data Lake Storage Gen2
- On-Premises Data Gateway
- Power BI
- Semantic Model
- Star Schema
- Slowly Changing Dimension (SCD Type 1)
- GitHub

---

# Dataset

AI Banking Dataset (CSV)

Fact Tables

- Transactions
- Daily Account Balance
- Loan Payments

Dimension Tables

- Customer
- Account
- Branch
- Product
- Channel
- Date
- Employee

---

# Project Workflow

## 1. Data Ingestion

- Connected on-premises data using Azure VM and On-Premises Gateway
- Accessed source fact files from on-premises data using Azure VM and On-Premises Gateway
- Accessed dimension data using OneLake Shortcuts from ADLS Gen2
- Loaded data into Microsoft Fabric Lakehouse

---

## 2. Data Transformation

Dataflow Gen2 was used to perform data cleansing including:

- Removing duplicate records
- Filtering null values
- Data type validation
- Data quality checks
- Date validation
- Standardizing column formats

---

## 3. Staging Layer

Created staging tables inside the Lakehouse for all fact datasets.

Example:

- stg_transactions
- stg_daily_account_balance
- stg_loan_payments

---

## 4. Dimension Processing

Dimension tables were loaded from OneLake Shortcuts using Fabric Notebooks.

Implemented:

- Slowly Changing Dimension (SCD Type 1)

Dimension Tables:

- dim_customer
- dim_account
- dim_branch
- dim_product
- dim_channel
- dim_date
- dim_employee

---

## 5. Fact Table Generation

Using Spark SQL, staging tables were joined with dimension tables to generate optimized fact tables.

Created:

- fact_transactions_final
- fact_daily_account_balance_final
- fact_loan_payments_final

The final fact tables retain only:

- Numerical measures
- Foreign keys

All tables were stored in Delta format.

---

## 6. Semantic Model

Created a Power BI Semantic Model including:

- Star Schema relationships
- One-to-Many relationships
- Single-direction filtering

Relationships were established between fact tables and all dimension tables.

---

## 7. Power BI Dashboard

Developed an interactive dashboard including:

- KPI Cards
- Transaction Trend
- Branch-wise Analysis
- Product-wise Analysis
- Channel-wise Analysis
- Customer Transaction Details
- Interactive Slicers

---

# Key Features

- End-to-End ETL Pipeline
- Microsoft Fabric Lakehouse
- Dataflow Gen2
- Delta Tables
- OneLake Shortcuts
- Star Schema
- Semantic Modeling
- Slowly Changing Dimension Type 1
- Power BI Dashboard
- Data Quality Validation

---

# Skills Demonstrated

- Data Engineering
- ETL Pipeline Development
- Microsoft Fabric
- Lakehouse Architecture
- Delta Lake
- Spark SQL
- PySpark
- Data Modeling
- Data Cleansing
- Data Validation
- SCD Type 1
- Power BI
- Azure Data Lake Storage
- Semantic Modeling

---

# Learning Outcomes

This project demonstrates practical implementation of modern cloud-based Data Engineering concepts including:

- Data ingestion from on-premises environments
- Data transformation using Dataflow Gen2
- Lakehouse architecture
- Delta table implementation
- Slowly Changing Dimension (Type 1)
- Semantic modeling
- Business Intelligence reporting
- End-to-End analytics pipeline

---

# Author

**Haripatel**

Aspiring Data Engineer

Microsoft Fabric | Azure | PySpark | SQL | Power BI | Data Engineering
