## Project Report – Azure Fabric NYC Taxi Medallion Pipeline

This report documents the design, implementation, and outcomes of an end-to-end
data engineering pipeline built using Azure Storage, Microsoft Fabric, and Power BI.

The project demonstrates secure ingestion, medallion architecture processing,
automation, and analytics for large-scale taxi trip data.

---

## Business Context

NYC Taxi trip data is high-volume, time-series data that requires:
- Scalable storage
- Automated ingestion
- Structured transformation
- Analytics-ready datasets

This project simulates a real-world public-sector or transport analytics scenario.

---

## Solution Overview

The solution follows a **Medallion Architecture**:

- **Raw / Bronze**: Ingest raw files from Azure Data Lake
- **Silver**: Clean, validate, and standardize data
- **Gold**: Aggregate data for analytics and reporting

Automation is supported using Azure Event Grid and Microsoft Fabric pipelines.

---

## Key Components

- Azure Data Lake Storage Gen2 (raw landing zone)
- Microsoft Fabric Lakehouse (Bronze / Silver / Gold)
- Fabric notebooks for transformation
- Event-based pipeline trigger
- Power BI dashboard using Direct Lake

---

## Data Processing Flow

1. Data lands in ADLS Gen2 (`raw-landing`)
2. Fabric pipeline ingests raw data (Bronze)
3. Data is cleaned and validated (Silver)
4. Aggregations are created (Gold)
5. Power BI consumes Gold layer for reporting

---

## Analytics & Insights

The Power BI dashboard provides:
- Total trips and revenue
- Borough-level trip distribution
- Daily and monthly trend analysis
- Operational insights for transport planning

---

## Security & Governance

- RBAC-based access control
- Secure storage (no public access)
- Event-driven automation
- Identity managed via Microsoft Entra ID

---

## Outcome

This project demonstrates a production-style data pipeline that is:
- Secure
- Automated
- Scalable
- Analytics-ready

It reflects real-world cloud data engineering best practices.
