
# Banking Transaction Data Engineering Platform — Data Dictionary

## 1. Project Overview

This document describes the datasets and tables used in the Banking Transaction Data Engineering Platform, including their purpose and role in the Medallion Architecture.

The project processes banking transaction data and produces analytical datasets for reporting.

## 2. Bronze Layer — Raw Data

**Purpose:** Store ingested source data with minimal transformation.

| Source File | Description |
|---|---|
| customers.csv | Customer information |
| accounts.csv | Banking account information |
| mobile_banking_transactions.json | Mobile banking transaction records |
| Mobile banking events | Events associated with mobile banking |
| ATM transaction data | Transactions performed through ATMs |
| ATM events | Events associated with ATM transactions |
| Branch transaction data | Transactions performed through branches |
| Branch events | Events associated with branch transactions |

## 3. Silver Layer — Cleaned and Validated Data

**Purpose:** Clean, standardize, validate and prepare data for analytical processing.

| Dataset | Description |
|---|---|
| Silver Transactions | Standardized banking transaction records |
| Silver Events | Standardized banking event records |
| Silver Customers | Cleaned customer records |
| Silver Accounts | Cleaned account records |
| Quarantine | Invalid records retained with rejection reasons |

Invalid records are separated through validation logic while valid records continue through processing.

## 4. Gold Layer — Business Analytics

**Purpose:** Store aggregated datasets for reporting and business analysis.

| Gold Table | Description |
|---|---|
| gold_daily_transaction_summary | Transaction metrics by date and status |
| gold_daily_transaction_summary_by_source | Transaction metrics by banking source |
| gold_daily_customer_summary | Customer-level transaction metrics |
| gold_daily_segment_summary | Transaction metrics by customer segment |
| gold_daily_account_type_summary | Transaction metrics by account type |
| gold_daily_transaction_type_summary | Transaction metrics by transaction type |
| gold_daily_business_kpis | Daily business performance indicators |

## 5. Business Rules

- Currency: INR
- Transaction types: DEPOSIT, WITHDRAWAL, TRANSFER, PAYMENT
- Transaction statuses: SUCCESS, FAILED, PENDING, REVERSED
- Processing frequency: Daily batch
- Historical data requirement: Six months
- Invalid records: Quarantined with rejection reasons
- Gold datasets: Refreshed after successful daily processing

## 6. Technology Stack

- Azure Data Factory — Pipeline orchestration design
- Databricks Free Edition — Data processing
- PySpark — Data ingestion and transformation
- Spark SQL — Analytical transformations
- Delta Lake — Data storage
- Power BI — Business intelligence and visualization

## 7. Architecture

The project follows the Medallion Architecture:

**Source Data → Bronze → Silver → Gold → Power BI**

Azure Data Factory contains a separate orchestration pipeline design using placeholder Wait activities. Native Databricks integration is not implemented.
