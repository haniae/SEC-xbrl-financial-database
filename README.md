# SEC XBRL Financial Database & Data Modeling

## Overview
This project implements a relational PostgreSQL database for U.S. SEC XBRL financial data.
The goal was to design a scalable, normalized schema and build a reproducible ingestion
pipeline capable of handling large-scale regulatory filings.

The database supports structured querying of company submissions, financial facts,
taxonomy metadata, and presentation logic—enabling downstream financial analysis,
reporting, and analytics use cases.

---

## Data Sources
- U.S. SEC XBRL Financial Statement Data Sets
- Monthly filings (SUB, TAG, DIM, NUM, PRE tables)

---

## Technical Stack
- **Python** (Jupyter Notebook)
- **PostgreSQL**
- **SQL (DDL & DML)**
- **csvkit**
- **AWS EC2 (execution environment)**

---

## Database Schema
The database follows a normalized design aligned with SEC data structure:

- **SUB** — Filing-level metadata (registrant, form type, filing date)
- **TAG** — XBRL taxonomy definitions
- **DIM** — Dimensional metadata (axes and members)
- **NUM** — Numeric financial facts
- **PRE** — Presentation layer mapping for financial statements

Primary and foreign key constraints are enforced to maintain referential integrity.

---

## Key Features
- End-to-end database creation using SQL DDL
- Automated ingestion of TSV → CSV → PostgreSQL
- Handling of large-scale financial datasets with memory constraints
- Column-level documentation using PostgreSQL comments
- Reproducible execution from database initialization to data load

---

## How to Run
1. Create a PostgreSQL database
2. Open the Jupyter notebook
3. Run cells sequentially to:
   - Create tables
   - Load data
   - Validate schema and constraints

---

## Use Cases
- Financial statement analysis
- Regulatory reporting
- Data engineering pipelines
- Downstream ML / analytics workflows

---

## Notes
Due to data volume constraints, a subset of monthly filings was used during execution.
The pipeline is designed to scale with appropriate compute resources.
