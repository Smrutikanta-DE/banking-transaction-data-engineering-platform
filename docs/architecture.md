
# Banking Transaction Data Engineering Platform — Architecture

```mermaid
flowchart TD
    A[Banking Source Files<br/>Customers, Accounts, Transactions, Events]

    A --> B[Bronze Layer<br/>Raw Data Ingestion]
    B --> C[Silver Layer<br/>Data Cleaning and Transformation]
    C --> D[Quarantine<br/>Invalid Records and Rejection Reasons]
    C --> E[Gold Layer<br/>Business Aggregations and KPIs]
    E --> F[Power BI<br/>Analytics Dashboard]

    G[Azure Data Factory<br/>Daily Orchestration Design] -.-> H[Bronze to Gold Pipeline Flow]
```

## Technology Stack

- Databricks Free Edition
- PySpark and Spark SQL
- Delta Lake
- Azure Data Factory
- Power BI

## Implementation Note

The Databricks data processing and Azure Data Factory orchestration were implemented separately. The ADF pipeline currently uses placeholder Wait activities and is not natively integrated with Databricks.
