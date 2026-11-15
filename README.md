
# Banking Transaction Data Engineering Platform

## Project Overview

The Banking Transaction Data Engineering Platform is an end-to-end data engineering project designed to process, transform, validate, and analyse banking transactions from multiple banking channels.

The platform handles mobile banking, ATM banking, and branch banking transactions using a Medallion Architecture (Bronze, Silver, and Gold).

The processed data is used to generate business insights through interactive Power BI dashboards.

## Business Objectives

- Process banking transactions from multiple sources.
- Validate transaction data and maintain data quality.
- Handle SUCCESS, FAILED, PENDING, and REVERSED transactions.
- Quarantine invalid records with rejection reasons.
- Generate business-level analytics and KPIs.
- Provide interactive dashboards for banking performance analysis.

## Architecture

The project follows the Medallion Architecture:

**Bronze Layer**
- Ingest raw CSV and JSON files.
- Preserve source information.
- Add ingestion timestamps.

**Silver Layer**
- Clean and transform raw data.
- Apply data validation rules.
- Process transaction and event data.
- Separate invalid records into quarantine.

**Gold Layer**
- Generate business-ready analytical datasets.
- Calculate transaction summaries and KPIs.
- Support customer, account, transaction type, and banking source analysis.

**Reporting Layer**
- Connect Power BI to Databricks Gold datasets.
- Build interactive dashboards.
- Analyse transaction trends and business performance.

## Technologies Used

| Technology | Purpose |
|---|---|
| Azure Data Factory | Pipeline orchestration design |
| Azure Databricks Free Edition | Data processing |
| PySpark | Data ingestion and transformation |
| Spark SQL | Analytical transformations |
| Delta Lake | Data storage |
| Power BI | Data visualisation |
| GitHub | Version control and project documentation |

## Key Project Results

- 30 banking transactions processed.
- 3 banking sources: Mobile, ATM, and Branch.
- 4 transaction statuses handled.
- Bronze, Silver, and Gold layers implemented.
- Data validation and quarantine logic implemented.
- 7 Gold analytical datasets created.
- Interactive Power BI report with 3 pages and 6 slicers.

## Power BI Dashboard

The Power BI report includes:

1. Banking Overview
2. Customer and Account Analysis
3. Transaction Analysis

The dashboards provide transaction KPIs, transaction status distribution, banking source analysis, customer segment analysis, and transaction trends.

## Azure Data Factory Orchestration

An Azure Data Factory pipeline was designed to demonstrate daily banking pipeline orchestration, including activity dependencies, parameters, variables, and success/failure paths.

The current ADF implementation uses placeholder Wait activities. Actual execution of Databricks notebooks through ADF is not implemented in this project scope.

## Project Environment

- Databricks Free Edition was used for data engineering implementation.
- Azure Data Factory was developed separately in an Azure Free Trial environment.
- Power BI Desktop was used for reporting.

## Author

Data Engineering Project | Banking Transaction Analytics


## Project Documentation

Explore the detailed project documentation:

| Document | Description |
|---|---|
| [Architecture Diagram](docs/architecture.md) | End-to-end project architecture |
| [Data Dictionary](docs/data_dictionary.md) | Bronze, Silver and Gold datasets |
| [Power BI Dashboard](powerbi/README.md) | Dashboard pages, screenshots and insights |
| [ADF Pipeline](adf/README.md) | Azure Data Factory orchestration design |

## Databricks Notebooks

The project implementation is available in the `notebooks/` directory:

1. [Bronze Ingestion](notebooks/01_bronze_ingestion)
2. [Silver Transformation](notebooks/02_silver_transformation)
3. [Gold Layer](notebooks/03_gold_layer)

## Project Repository Structure

```text
banking-transaction-data-engineering-platform/
│
├── notebooks/
│   ├── 01_bronze_ingestion
│   ├── 02_silver_transformation
│   └── 03_gold_layer
│
├── adf/
│   ├── pl_banking_daily_orchestration.json
│   └── README.md
│
├── powerbi/
│   ├── README.md
│   ├── banking_overview.png
│   ├── customer_account_analysis.png
│   └── Transaction_analysis.png
│
├── docs/
│   ├── architecture.md
│   └── data_dictionary.md
│
├── sample_data/
├── .gitignore
└── README.md
```

