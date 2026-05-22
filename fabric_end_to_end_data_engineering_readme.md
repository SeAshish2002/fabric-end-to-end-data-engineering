# End-to-End Data Engineering Pipeline using Microsoft Fabric

## Project Overview

This project demonstrates an enterprise-style end-to-end Data Engineering solution built using Microsoft Fabric and Medallion Architecture.

The solution processes structured, semi-structured, and API-based datasets through Bronze, Silver, and Gold layers using Fabric Pipelines, Lakehouse, and PySpark notebooks.

The project focuses on scalable ingestion, metadata-driven orchestration, transformation pipelines, and business-ready analytics.

---

# Real-World Business Problem Statement

## Scenario: E-Commerce Business Performance & Customer Engagement Analysis

A mid-sized retail business named "ShoppingMart" is experiencing increasing competition in the e-commerce industry. The business requires deeper insights into:

- Customer purchasing behavior
- Sales trends
- Inventory management
- Customer engagement
- Product-level performance
- Business KPIs

The organization currently receives data from multiple systems and formats including:

- CSV files
- APIs
- Semi-structured datasets
- Structured transactional data

The objective of this project is to build a unified modern analytics platform using Microsoft Fabric that:

- Ingests raw data into a centralized Lakehouse
- Validates and cleanses datasets
- Creates curated analytical datasets
- Enables business reporting and KPI generation
- Supports scalable medallion architecture implementation

---

# Architecture

## Microsoft Fabric Medallion Architecture

```texttext
                +-------------------+
                | API / CSV Sources |
                +-------------------+
                           |
                           v
                +-------------------+
                | Metadata JSON     |
                | Configuration     |
                +-------------------+
                           |
                           v
                +-------------------+
                | Fabric Pipelines  |
                | Copy Activities   |
                +-------------------+
                           |
                           v
                +-------------------+
                | Bronze Lakehouse  |
                | Raw Files         |
                +-------------------+
                           |
                           v
                +-------------------+
                | PySpark Notebook  |
                | Silver Transform  |
                +-------------------+
                           |
                           v
                +-------------------+
                | Silver Delta      |
                | Tables            |
                +-------------------+
                           |
                           v
                +-------------------+
                | Gold Layer        |
                | KPI / Analytics   |
                +-------------------+
```

---

# Medallion Architecture Layers

## Bronze Layer (Raw Zone)

Purpose:
- Store raw source data in original format
- Preserve source-of-truth datasets
- Support auditing and reprocessing

Data Types:
- CSV
- JSON
- API responses
- Structured and semi-structured data

Fabric Components Used:
- Fabric Pipelines
- Copy Activity
- Lakehouse Files

---

## Silver Layer (Validated Zone)

Purpose:
- Clean and standardize datasets
- Remove duplicates
- Validate schemas
- Apply business transformations

Transformations Implemented:
- Null handling
- Data type casting
- Deduplication
- Column standardization
- Data cleansing

Fabric Components Used:
- PySpark Notebook
- Lakehouse Delta Tables

---

## Gold Layer (Curated Zone)

Purpose:
- Generate business-ready analytical datasets
- Build KPI-driven reporting tables
- Support dashboards and business intelligence

Examples:
- Sales KPIs
- Revenue analysis
- Customer analytics
- Aggregated reporting tables

Fabric Components Used:
- PySpark Notebook
- Gold Delta Tables
- Power BI / Semantic Model

---

# Technologies Used

- Microsoft Fabric
- Fabric Pipelines
- Lakehouse
- PySpark
- Medallion Architecture
- Copy Activity
- Delta Tables
- REST API Ingestion
- CSV Ingestion
- Metadata-Driven Pipelines
- Parameterized Pipelines
- GitHub

---

# Enterprise Workflow Architecture

The project follows a complete orchestrated workflow inside Microsoft Fabric:

```text
Structured Data Pipeline
          ↓
Unstructured Data Pipeline
          ↓
Silver Layer PySpark Transformations
          ↓
Gold Layer KPI Aggregations
          ↓
Power BI / Semantic Model
```

The orchestration is implemented using:

- Master Pipelines
- Invoke Pipeline activities
- PySpark Notebook activities
- Metadata-driven ingestion
- Parameterized execution

The workflow handles both:

- Structured datasets (CSV)
- Unstructured/Semi-structured datasets (JSON/API)

---

# Structured and Unstructured Data Processing

## Structured Data

Structured datasets processed:

- Customers
- Orders
- Products

Operations performed:

- Schema standardization
- Null handling
- Data type casting
- Customer-product-order joins
- Curated Silver datasets

---

## Unstructured and Semi-Structured Data

Unstructured datasets processed:

- Reviews
- Social media data
- Web logs

Operations performed:

- JSON ingestion
- Sentiment aggregation
- User engagement analytics
- Product review analysis
- KPI generation

---

# PySpark Transformations Implemented

## Silver Layer Transformations

The Silver notebook performs:

- Bronze layer ingestion
- Data cleansing
- Deduplication
- Date conversion
- Multi-table joins
- Structured and unstructured data integration
- Parquet conversion
- Overwrite handling

Key PySpark concepts used:

- spark.read.format()
- option("header","true")
- dropna()
- withColumn()
- to_date()
- join()
- groupBy()
- agg()
- parquet()
- overwrite mode

---

## Gold Layer Aggregations

The Gold layer generates business KPIs including:

### KPI 1 — Web Log Engagement Analytics

Aggregates web log activity to measure:

- User engagement
- Page interactions
- Action frequency

### KPI 2 — Social Media Sentiment Analytics

Analyzes social media data to identify:

- Platform sentiment trends
- Customer engagement patterns
- Social media activity distribution

### KPI 3 — Product Review Analytics

Calculates:

- Average product ratings
- Review-based performance metrics
- Product-level customer feedback insights

---

# Project Features

## 1. Metadata-Driven and Parameterized Ingestion

The ingestion framework is designed using metadata-driven and parameterized pipeline architecture.

JSON metadata configuration files dynamically control:

- Source paths
- File formats
- API endpoints
- Destination locations
- Load behavior
- Pipeline execution flow
- Dynamic file handling

Parameterized pipelines are used to:

- Reuse ingestion logic across multiple datasets
- Avoid hardcoded values
- Improve scalability and maintainability
- Support dynamic source-to-target execution

This approach closely aligns with enterprise-level modern data engineering practices and significantly reduces hardcoding within pipelines.

---

## 2. Structured and Semi-Structured Data Ingestion

The project ingests:

- CSV files
- API-based data
- Semi-structured datasets

using Fabric Copy Activities.

---

## 3. Bronze Layer

The Bronze layer stores raw ingested data inside the Fabric Lakehouse Files section.

Key characteristics:

- Raw data preservation
- Minimal transformation
- Supports replay/reprocessing
- Handles ingestion conflicts

---

## 4. Silver Layer

PySpark notebooks are used to:

- Clean data
- Remove null values
- Rename columns
- Perform type casting
- Standardize schemas
- Apply transformations
- Create Delta tables

---

## 5. Gold Layer

The Gold layer contains business-ready analytical datasets and KPIs.

Examples:

- Sales KPIs
- Aggregated metrics
- Business reporting tables
- Dashboard-ready datasets

---

# Pipeline Workflow

## Step 1 — Metadata Configuration

JSON metadata files define ingestion behavior.

## Step 2 — Pipeline Execution

Fabric Pipelines orchestrate ingestion activities.

## Step 3 — Data Ingestion

Data is copied from APIs and CSV sources into Bronze Lakehouse storage.

## Step 4 — Silver Transformation

PySpark notebooks clean and transform raw data.

## Step 5 — Gold Analytics

Business-level aggregated datasets are generated.

---

# Folder Structure

```text
fabric-end-to-end-data-engineering/
│
├── README.md
├── screenshots/
├── notebooks/
├── pyspark/
├── metadata/
├── architecture/
├── datasets/
└── pipeline-configs/
```

---

# Project Screenshots

## Medallion Workflow Architecture

The project implements a complete Medallion Architecture workflow in Microsoft Fabric.

Key workflow stages:

- Data Ingestion
- Bronze Layer
- Silver Transformations
- Gold Aggregations
- Data Visualization

## Master Pipeline Orchestration

The master pipeline orchestrates:

- Structured ingestion pipeline
- Unstructured ingestion pipeline
- Silver notebook execution
- Gold notebook execution

with successful end-to-end execution monitoring.

## Metadata-Driven JSON Configuration

JSON metadata files dynamically control:

- Source locations
- Sink folders
- Dynamic ingestion paths
- File names

This enables reusable and scalable ingestion design.

## Silver Layer PySpark Notebook

The Silver notebook demonstrates:

- Bronze data loading
- Data cleaning
- Date standardization
- Multi-table joins
- Structured and unstructured integration
- Parquet write operations

## Gold Layer KPI Notebook

The Gold notebook generates:

- Web engagement KPIs
- Sentiment analysis metrics
- Product review aggregations
- Business reporting datasets

## Power BI / Reporting Layer

The project includes a reporting and semantic model layer for business visualization and analytics.

---

# Screenshots

## Pipeline Architecture

(Add screenshot here)

## Bronze Layer

(Add screenshot here)

## Silver Layer Notebook

(Add screenshot here)

## Gold Layer

(Add screenshot here)

---

# Key Learnings

During this project, the following concepts were implemented and explored:

- End-to-end pipeline orchestration
- Parameterized pipeline design
- Metadata-driven engineering
- API ingestion
- Lakehouse architecture
- Medallion Architecture
- PySpark transformations
- Delta tables
- File path management
- Data pipeline debugging
- Structured and semi-structured data handling

---

# Future Improvements

Potential enhancements for future versions:

- Incremental loading
- Scheduling and triggers
- Monitoring dashboards
- Data quality validation
- CI/CD integration
- Parameterized pipelines
- Logging framework

---

# Author

Ashish Sharma

Microsoft Fabric | PySpark | Data Engineering

