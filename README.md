# Formula 1 Data Engineering Pipeline

## Project Overview

This project is an end-to-end Formula 1 Data Engineering Pipeline built using Microsoft Azure cloud services and Medallion Architecture.

The project processes Formula 1 racing data containing information related to:
- Drivers
- Constructors
- Circuits
- Races
- Race Results
- Sprint Results

The pipeline uses Azure Data Factory for orchestration and Azure Databricks for implementing ETL and data transformation logic. The processed data is stored in Azure Data Lake Storage using Delta Lake format.

The project demonstrates concepts like:
- Data Ingestion
- Incremental Batch Processing
- Medallion Architecture
- ETL Pipeline Development
- Delta Lake Implementation
- Data Transformation using PySpark
- Fact and Dimension Modeling
- Cloud-based Data Processing using Azure Services

---

# Architecture Diagram

_Add your architecture image here_

```md
![Architecture Diagram](architecture/project_architecture.png)
```

---

# Tech Stack Used

- Azure Data Factory
- Azure Databricks
- Azure Data Lake Storage Gen2
- PySpark
- SQL
- Delta Lake
- CSV Files
- JSON Files

---

# Project Flow / Pipeline Flow

### 1. Batch Processing Initialization

The pipeline execution starts with batch processing logic.

Using Azure Databricks notebooks:
- Next Batch ID is identified
- A new batch entry is created for tracking pipeline execution

This helps in maintaining proper batch-level processing and monitoring.

---

### 2. Bronze Layer (Raw Ingestion Layer)

The Bronze layer is responsible for raw data ingestion.

The pipeline reads Formula 1 data from:
- CSV files
- JSON files

Datasets include:
- Circuits Data
- Constructors Data
- Drivers Data
- Races Data
- Results Data
- Sprint Results Data

The raw data is then stored in Azure Data Lake Storage in Delta Table format.

Purpose of Bronze Layer:
- Store raw historical data
- Maintain source-level backup
- Support scalable ingestion

---

### 3. Silver Layer (Transformation Layer)

The Silver layer performs data transformation and cleansing.

In this layer:
- Bronze layer data is processed
- Data cleaning is performed
- Schema corrections are applied
- Required transformations are implemented
- Standardized datasets are generated

The transformed data is then stored in Delta Table format.

---

### 4. Gold Layer (Business Layer)

The Gold layer contains analytics-ready business datasets.

In this layer:
- Data from Silver layer is processed
- Fact and Dimension tables are created
- Data modeling is implemented
- Curated datasets are generated for analytics and reporting

Example tables:
- Fact_Race_Results
- Dim_Drivers
- Dim_Constructors
- Dim_Circuits
- Dim_Races

The Gold layer data can be used for reporting and analytical purposes.

---

# Medallion Architecture

This project follows Medallion Architecture:

| Layer | Purpose |
|---|---|
| Bronze | Stores raw Formula 1 data |
| Silver | Stores cleaned and transformed data |
| Gold | Stores analytics-ready business data |

---

# Data Sources

The project processes multiple Formula 1 datasets in CSV and JSON formats.

### Sample Datasets

#### Circuits Data
Contains information about Formula 1 circuits:
- Circuit ID
- Circuit Name
- Location
- Country
- Coordinates

#### Constructors Data
Contains information about Formula 1 constructors:
- Constructor ID
- Constructor Name
- Nationality

#### Drivers Data
Contains information about Formula 1 drivers:
- Driver Name
- Nationality
- Date of Birth

#### Races Data
Contains race-related information:
- Season
- Round
- Race Name
- Race Date
- Circuit ID

#### Results Data
Contains Formula 1 race results:
- Driver ID
- Constructor ID
- Position
- Points
- Laps
- Race Details

#### Sprint Results Data
Contains Formula 1 sprint race information:
- Sprint Results
- Driver Position
- Points
- Race Information

---

# Features Implemented

- End-to-End Azure Data Engineering Pipeline
- Formula 1 Data Processing
- Batch Processing using Databricks
- Azure Data Factory Orchestration
- Medallion Architecture
- Bronze, Silver, and Gold Layer Implementation
- Data Transformation using PySpark
- Fact and Dimension Modeling
- Delta Lake Implementation
- CSV and JSON Data Processing
- Cloud Data Storage using ADLS Gen2
- Analytics-ready Data Processing
