# Azure Data Engineering Pipeline with Azure Data Factory and Databricks - Sales Data

## Project Overview
This project implements a scalable data pipeline using Azure Data Factory (ADF) for orchestration and Azure Databricks for data preprocessing. The data is sourced from the Microsoft AdventureWorks 2019 dataset, processed in Databricks, and stored in Azure Data Lake. The final data is loaded into Azure Synapse Analytics and visualized using Power BI for reporting.

## Architecture Diagram
![azure_diagram](https://github.com/aadhil96/Sales_Data_Azure_ETL_Data_Engineering_Pipeline/blob/8d6657f52d33d816613bfe594aa8870cc651a313/Azure%20Sales%20Data%20Engineering%20Pipeline-Page-3.drawio.png)

The architecture follows a layered approach, commonly referred to as the Bronze-Silver-Gold pattern in data lakes:

- Bronze Layer: Raw data from the AdventureWorks SQL Database is copied into Azure Data Lake.
- Silver Layer: Data is cleansed and transformed using Databricks notebooks.
- Gold Layer: Final transformation is done, making the data ready for analytics.

## Pipeline Components
1. Data Source: Microsoft AdventureWorks 2019 Dataset (Azure SQL Database)
   The AdventureWorks 2019 dataset is a Microsoft sample database that contains a simulated retail business, including data on customers, products, sales, purchasing, and employee information.
    The raw sales and business data are stored in an Azure SQL Database, which serves as the data source for this pipeline.
2. Orchestration: Azure Data Factory (ADF)
  ADF is used to schedule, orchestrate, and monitor the data movement across the pipeline.
  The pipeline involves copying data from the AdventureWorks SQL database into Azure Data Lake Storage for preprocessing.
3. Data Processing: Azure Databricks
  Azure Databricks handles the data transformation in stages:
  - Bronze: Raw data is ingested and stored in its raw form.
  - Silver: Data cleansing and normalization are performed, ensuring consistency and data quality.
  - Gold: Aggregated, business-ready data is stored for analysis and reporting.
  Databricks notebooks are used for the transformation logic, allowing scalable, parallel data processing.
4. Data Lake Storage
  Data is stored in Azure Data Lake at each processing stage (Bronze, Silver, Gold).
  The data format is typically Parquet or Delta Lake to optimize storage and querying.
5. Serving Layer:
  - Azure Synapse Analytics: Processed data from the Gold layer is loaded into Azure Synapse Analytics for further reporting and analysis.
  - Power BI: The final data is visualized using Power BI, creating dashboards and reports for business users.
