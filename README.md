# NYC Taxi ETL Project

## Project Overview

This project demonstrates an end-to-end **ETL pipeline** using **PySpark** to process **NYC Yellow Taxi trip data**. It covers:

- Data ingestion from **parquet files** and **taxi zone lookup CSV**  
- Data cleaning and anomaly detection  
- Enrichment with **pickup and dropoff taxi zones**  
- Preparation of clean, enriched data for database loading  

The pipeline is designed for **real-world ETL scenarios** and can be scaled to large datasets.

---

## Features

1. **Data Cleaning**
   - Removes trips with invalid values (e.g., zero or negative fare, distance, or passenger count)  
   - Detects anomalies such as high fare, long distance, long duration, and excessive passengers  

2. **Data Enrichment**
   - Joins taxi trips with **taxi zone lookup table** for both pickup and dropoff locations  
   - Adds human-readable `Zone`, `Borough`, and `Service Zone` columns  

3. **Anomaly Detection**
   - Flags trips violating multiple rules using a **rule-based system**  
   - Stores all violated rules per trip in an array column  

4. **ETL Flexibility**
   - Reads data directly from **parquet files**  
   - Reads reference datasets from **CSV URLs** or local storage  
   - Fully compatible with Spark workflows, ready for database load  

---

## Technologies Used

- Python 3.x  
- PySpark  
- Pandas (for small reference dataset handling)  
- Requests (for downloading external datasets)  
- Git / GitHub for version control  

---

## Getting Started

### Prerequisites

- Python 3.8+  
- PySpark 3.x installed  
- Optional: Conda or virtualenv for environment management  

### Project Structure

```
nyc-taxi-etl-pyspark/
│
├── docs/                # exploratory analysis, etl workflow and project notes
├── README.md            # project documentation

```

### Notes

The taxi zone lookup table can be downloaded directly from NYC website or fetched programmatically.

Spark cannot read https:// URLs directly for CSVs; use pandas to fetch and then convert to Spark dataframe.

This pipeline is suitable for small to medium datasets; for very large datasets, consider storing reference data in S3/HDFS.
