## Data Sources

This project uses publicly available **NYC Yellow Taxi Trip Records** data.

### Data Source
- NYC Taxi & Limousine Commission (TLC)
- Official dataset:
  https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page

### Data Format
- Parquet files
- Monthly partitions
- Large file sizes (>25MB per file)

### Why data is not stored in GitHub
- Parquet files exceed GitHub’s recommended file size limits
- In real-world data engineering, raw data is stored in cloud storage
- This project ingests data directly into **Azure Data Lake Gen2**

### Ingestion Approach
- Data is downloaded from the official source
- Uploaded to Azure Blob Storage (raw landing zone)
- Automatically processed using Microsoft Fabric pipelines

This approach reflects industry best practices for scalable data engineering solutions.
