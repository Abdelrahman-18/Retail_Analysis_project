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

***

## 📊 Power BI Dashboard

The dashboard serves as the final consumption layer, transforming the curated Gold data into actionable business intelligence. Designed with a focus on user experience (UX), it provides a clear narrative from high-level KPIs to granular product performance.

### 🔹 Key Features
- 📈 Core Performance KPIs: High-level metrics calculated using robust DAX measures, including Total Orders (via DISTINCTCOUNT), Total Revenue (row-level accuracy via SUMX), and Average Order Value (AOV).

- 🏆 Product Deep Dive: A dynamic ranking system highlighting Top Products Sold and a Category Breakdown, allowing stakeholders to instantly identify revenue drivers.

- 🌍 Geographical Analysis: A Revenue Map showing sales distribution across regions, utilizing the optimized data model to ensure accurate filtering by location.

- 📉 Market Efficiency Scatter: A strategic visualization comparing Transaction Count vs. Total Sales, helping identify markets driven by high volume versus high ticket value.

### ⚙️ Data Modeling & Optimization
The primary goal of the Power BI optimization phase was to convert the complex, engineering-focused Medallion Architecture structure into a high-performance Star Schema suitable for analytics.

#### 🔧 Model Structure & Integrity Fixes
- Star Schema Enforcement: The model was optimized by isolating Fact Tables (Transactions) from Dimension Tables (Products, Customers, Stores) to simplify relationships and enhance query speed.

- Ambiguity Resolution: Systematically deactivated redundant relationships (particularly between the Silver and Gold layers) to eliminate 
circular dependencies and resolve "Ambiguous Path" errors.

- Filter Bridging: The core filter blockage was resolved by utilizing the Product dimension as a bridge. A Bi-Directional Filter was implemented on the Product $\leftrightarrow$ Transaction relationship to successfully propagate date and store filters to the highly aggregated Gold tables.

#### Analytical Logic & DAX Optimization

- Robust Calculations: Created centralized, dynamic DAX measures. Revenue was calculated using the SUMX iterator function for row-level accuracy (quantity * price), ensuring correct aggregation across all filters.

- Time Intelligence: Built a dedicated Calendar Table to act as the sole source of time context, enabling stable time-series analysis for metrics like Total Revenue and Average Order Value.


![Image](https://github.com/user-attachments/assets/240294a8-97df-4fe6-8277-2e283a47070e)

![Image](https://github.com/user-attachments/assets/b56e64fd-d49d-42d9-83cf-87f0b1c510bb)

 ***

## 🧑‍💻 Authors

**Abdelrahman Mohamed – Power BI Analyst** 📊
*(Project Owner & Dashboard Design)*
* **Data Modeling:** Optimized the engineering output into a high-performance **Star Schema**, resolving circular dependencies and data ambiguity.
* **Advanced DAX:** Implemented complex measures using iterator functions (`SUMX`) and Time Intelligence for accurate historical analysis.
* **Technical Solutions:** Engineered a **Bi-Directional Filter Bridge** to ensure accurate filtering between granular transaction data and aggregated Gold layers.
* **UI/UX Design:** Designed a custom, user-centric layout using external tools (PowerPoint) for a polished, professional aesthetic.

**Sabry Tarek – Data Engineer** 🔧
*(Data Pipeline & Architecture)*
* **Architecture:** Designed and implemented the **Medallion Architecture** (Bronze, Silver, Gold) using Azure Databricks.
* **Data Engineering:** Built PySpark pipelines for data cleaning, schema enforcement, and transformation.
* **Cloud Infrastructure:** Managed Azure Data Lake Gen2 storage and Unity Catalog integration for seamless BI consumption.
