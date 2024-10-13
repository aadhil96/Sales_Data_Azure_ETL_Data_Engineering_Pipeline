# Azure Data Engineering Pipeline with Azure Data Factory and Databricks - Sales Data

## Project Overview
This project implements a scalable data pipeline using Azure Data Factory (ADF) for orchestration and Azure Databricks for data preprocessing. The data is sourced from the Microsoft AdventureWorks 2019 dataset, processed in Databricks, and stored in Azure Data Lake. The final data is loaded into Azure Synapse Analytics and visualized using Power BI for reporting.

## Architecture Diagram
The architecture follows a layered approach, commonly referred to as the Bronze-Silver-Gold pattern in data lakes:

- Bronze Layer: Raw data from the AdventureWorks SQL Database is copied into Azure Data Lake.
- Silver Layer: Data is cleansed and transformed using Databricks notebooks.
- Gold Layer: Final transformation is done, making the data ready for analytics.
