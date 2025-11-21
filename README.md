# Retail Analytics Project – Azure • Databricks • Power BI
A complete end-to-end Retail Data Engineering & Analytics project built using Azure Data Lake, Azure Databricks, and Power BI. The goal is to transform raw retail data into meaningful business insights following the Medallion Architecture.

***

## Project Architecture
This project follows the Medallion Architecture:

🏗 Bronze Layer (Raw Layer)
- Raw CSV/Parquet files stored in Azure Data Lake Gen2
- No transformations applied

⚙ Silver Layer (Cleaned Layer)
 - Data cleaning
 - Removing duplicates
 - Standardizing schemas
 - Joining all source tables (customers, products, stores, transactions)

✨ Gold Layer (Analytics Layer)
 - Aggregated KPIs
 - Country-level sales
 - Store and product performance
 - Customer behavior metrics
 - Data exported to Unity Catalog for BI tools

***
Architecture Diagram
<img width="2784" height="1536" alt="Image" src="https://github.com/user-attachments/assets/5f5498c5-7b64-41e7-8b05-65408c4f81e8" />
***

### 🛠️ Technologies Used

| Component  | Technology                     |
|-----------|---------------------------------|
| Storage   | Azure Data Lake Gen2            |
| Compute   | Azure Databricks                |
| Processing| PySpark (Medallion Architecture)|
| Analytics | Power BI                        |
| Monitoring| Log Analytics Workspace         |
| Catalog   | Unity Catalog                   |
| Format    | Parquet                         |

*** 

## 🚀 Databricks Workspace & Cluster
- Create Databricks cluster
- Attach notebook
- Connect to ADLS using service principal or SAS
- Process data into Bronze → Silver → Gold
- Save final curated tables to Unity Catalog

<img width="1898" height="679" alt="Image" src="https://github.com/user-attachments/assets/4b9b32b4-ccf8-4997-88ae-04a464ed972c" />

<img width="1695" height="469" alt="Image" src="https://github.com/user-attachments/assets/01a3d87a-510e-4e3d-bca9-a0bb72bc7cb5" />

![Image](https://github.com/user-attachments/assets/acbec8e0-1d02-44f5-bb1c-55dd823bc1bc)
