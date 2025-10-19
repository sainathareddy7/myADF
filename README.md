# OnPremData2Cloud – Azure Data Factory Pipeline

## 📌 Overview
This project demonstrates an **Azure Data Factory (ADF)** pipeline that dynamically copies all tables from an **on-premises MySQL database** to **Azure SQL Database** using a parameterized and scalable approach.
## 🔍 Pipeline Highlights
- **Lookup Activity**: Fetches all table names from MySQL schema (`amazon_db`).
- **ForEach Activity**: Iterates over each table name.
- **Copy Activity**: Dynamically copies data from MySQL to Azure SQL DB.
- **Linked Services**: MySQL (on-prem) and Azure SQL DB connections.
- **Integration Runtime**: Self-hosted + Azure IR.
## ⚙️ Components
1. **Lookup Query**
   ```sql
   SELECT table_name FROM information_schema.tables 
   WHERE table_schema = 'amazon_db' AND table_type = 'BASE TABLE';
