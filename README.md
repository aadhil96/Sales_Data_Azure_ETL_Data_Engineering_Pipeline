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

1. **Data Source: Microsoft AdventureWorks 2019 Dataset (Azure SQL Database)**  
   The AdventureWorks 2019 dataset is a Microsoft sample database simulating a retail business. It includes data on customers, products, sales, purchasing, and employee information.  
   The raw sales and business data are stored in an Azure SQL Database, which serves as the primary data source for this pipeline.

2. **Orchestration: Azure Data Factory (ADF)**  
   Azure Data Factory (ADF) is used for scheduling, orchestrating, and monitoring data movement across the pipeline.  
   The pipeline involves copying data from the AdventureWorks SQL database into Azure Data Lake Storage for preprocessing.

3. **Data Processing: Azure Databricks**  
   Azure Databricks handles data transformation in a multi-stage process:  
   - **Bronze**: Raw data is ingested and stored in its original form.  
   - **Silver**: Data is cleansed and normalized, ensuring consistency and quality.  
   - **Gold**: Aggregated, business-ready data is stored for analysis and reporting.  
   Databricks notebooks are used for transformation logic, enabling scalable, parallel data processing.

4. **Data Lake Storage**  
   Data is stored in Azure Data Lake at each processing stage (Bronze, Silver, Gold).  
   Data is typically stored in formats like Parquet or Delta Lake to optimize storage and querying performance.

5. **Serving Layer**  
   - **Azure Synapse Analytics**: Processed data from the Gold layer is loaded into Azure Synapse Analytics for advanced reporting and analysis.  
   - **Power BI**: The final data is visualized using Power BI to create dashboards and reports for business use.
