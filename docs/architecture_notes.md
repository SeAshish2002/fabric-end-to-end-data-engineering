# Architecture Notes

## Architecture Overview

This project implements an end-to-end modern data engineering architecture using Microsoft Fabric and Medallion Architecture principles.

The architecture is designed to process both structured and semi-structured datasets using scalable pipeline orchestration and PySpark transformations.

---

# Medallion Architecture

The solution follows a layered Medallion Architecture:

```text
Bronze Layer  →  Silver Layer  →  Gold Layer
```

Purpose of each layer:

- Bronze → Raw data ingestion
- Silver → Cleaned and validated datasets
- Gold → Business KPI and analytics datasets

---

# Bronze Layer Design

## Purpose

The Bronze layer stores raw source data in its original format.

## Data Types Processed

- CSV files
- JSON files
- API responses
- Structured datasets
- Semi-structured datasets

## Storage Strategy

Raw datasets are stored inside the Fabric Lakehouse Files section.

## Pipeline Components Used

- Fabric Pipelines
- Copy Activity
- Lookup Activity
- ForEach Activity

---

# Metadata-Driven Ingestion Design

The ingestion framework is metadata-driven and parameterized.

Metadata JSON files dynamically define:

- Source URLs
- Sink folders
- File names
- Ingestion behavior

## Advantages

- Reduced hardcoding
- Reusable pipelines
- Easier scalability
- Dynamic ingestion execution

---

# Pipeline Orchestration Design

The workflow is orchestrated using a master pipeline.

Execution flow:

```text
Structured Ingestion
        ↓
Unstructured Ingestion
        ↓
Silver Transformations
        ↓
Gold Aggregations
```

## Orchestration Components

- Invoke Pipeline activities
- Notebook activities
- Dependency chaining
- Activity monitoring

---

# Silver Layer Design

## Purpose

The Silver layer performs cleansing, validation, and integration of raw datasets.

## Transformations Implemented

- Null handling
- Data cleansing
- Date conversion
- Deduplication
- Multi-table joins
- Schema standardization

## PySpark Functions Used

- dropna()
- withColumn()
- to_date()
- join()
- spark.read.format()

## Storage Format

- Parquet datasets

---

# Gold Layer Design

## Purpose

The Gold layer generates business-ready analytical datasets and KPIs.

## KPI Analytics Implemented

### Product Review Analytics

- Average rating calculation
- Product-level review aggregation

### Social Media Sentiment Analytics

- Platform sentiment aggregation
- Social engagement analysis

### Web Engagement Analytics

- User activity aggregation
- Page interaction tracking

---

# Storage Formats

| Layer  | Storage Format |
|--------|----------------|
| Bronze | CSV / JSON |
| Silver | Parquet |
| Gold | Parquet |

---

# Engineering Concepts Implemented

- Medallion Architecture
- Metadata-driven pipelines
- Parameterized execution
- Structured ingestion
- API ingestion
- PySpark transformations
- Lakehouse architecture
- Pipeline orchestration
- KPI aggregation