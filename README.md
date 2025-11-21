# Retail Analytics Project – Azure • Databricks • Power BI
A complete end-to-end Retail Data Engineering & Analytics project built using Azure Data Lake, Azure Databricks, and Power BI. The goal is to transform raw retail data into meaningful business insights following the Medallion Architecture.

***

## Project Architecture
This project follows the Medallion Architecture:

🏗 Bronze Layer (Raw Layer)
 Raw CSV/Parquet files stored in Azure Data Lake Gen2
 No transformations applied

⚙ Silver Layer (Cleaned Layer)
 Data cleaning
 Removing duplicates
 Standardizing schemas
 Joining all source tables (customers, products, stores, transactions)

✨ Gold Layer (Analytics Layer)
 Aggregated KPIs
 Country-level sales
 Store and product performance
 Customer behavior metrics
 Data exported to Unity Catalog for BI tools
