# Azure-Odyssey
Azure Odyssey is an end-to-end data engineering project on Azure. It uses Data Factory for ingestion, Databricks (PySpark) for transformation, and Synapse Analytics with Power BI for serving. It implements a medallion (Bronze, Silver, Gold) architecture for real-world data pipelines.

# Azure Odyssey: End-to-End Data Pipeline on Azure

Azure Odyssey is an end-to-end data engineering project built on Microsoft Azure. The solution demonstrates a multi-layered data pipeline using Azure Data Factory, Azure Databricks, and Azure Synapse Analytics, with data visualization in Power BI.

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Technologies Used](#technologies-used)
- [Project Phases](#project-phases)
- [Usage](#usage)
- [Future Enhancements](#future-enhancements)
- [License](#license)

## Overview

This project implements a dynamic data pipeline following a medallion architecture with three layers: Bronze, Silver, and Gold. It ingests raw CSV data from a GitHub repository into Azure Data Lake Storage, transforms the data with PySpark in Azure Databricks, and serves it through Azure Synapse Analytics for reporting in Power BI.

## Architecture

The solution is divided into three main phases:

1. **Bronze Layer (Data Ingestion):**  
   - Use Azure Data Factory to ingest CSV data via HTTP connectors from GitHub.
   - Build both static and dynamic pipelines using parameterization and "For Each" loops to handle multiple files.

2. **Silver Layer (Data Transformation):**  
   - Transform the ingested data using Azure Databricks and PySpark.
   - Apply functions such as date extraction, string concatenation, arithmetic operations, and aggregations.
   - Validate transformations using in-notebook visualizations.

3. **Gold Layer (Data Serving & Reporting):**  
   - Create a Synapse Analytics workspace to build external tables and views over the transformed data.
   - Use the serverless SQL endpoint in Synapse to connect with Power BI for interactive dashboards and reporting.

## Technologies Used

- **Azure Data Factory (ADF)**
- **Azure Databricks (PySpark)**
- **Azure Synapse Analytics**
- **Azure Data Lake Storage Gen2**
- **Power BI Desktop**
- **GitHub** (Source Data Repository)

## Project Phases

### Phase 1: Data Ingestion (Bronze)
- **Setup:** Create a resource group, storage account (with hierarchical namespaces enabled), and ADF linked services.
- **Pipeline:** Develop dynamic pipelines that ingest CSV files from GitHub via an HTTP connector, handling multiple files using iteration.

### Phase 2: Data Transformation (Silver)
- **Databricks Notebooks:**  
  - Create clusters and notebooks to read data from the Bronze layer.
  - Transform data with PySpark (e.g., date and string functions, arithmetic operations).
- **Validation:** Use built-in visualization options in Databricks to verify transformations.

### Phase 3: Data Serving & Reporting (Gold)
- **Synapse Analytics:**  
  - Set up a Synapse workspace and configure SQL pools (serverless preferred).
  - Create SQL views and external tables using CETAS to abstract and serve the data.
- **Reporting:** Connect Synapse Analytics to Power BI Desktop via serverless SQL endpoints to build interactive dashboards and KPIs.

### Usage

- **Data Ingestion:**
   -Launch Azure Data Factory and run the dynamic pipeline that ingests CSV files from GitHub.
- **Data Transformation:**
   -Open the provided Databricks notebooks and run the PySpark scripts to transform and validate data.
- **Data Serving & Reporting:**
   -Log in to your Synapse Analytics workspace to view and query the external tables and views.
Open the provided Power BI Desktop file (report.pbix) and connect using the serverless SQL endpoint to build and view dashboards.
