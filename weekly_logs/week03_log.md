# Week 03 Log — Databricks Setup + Data Exploration

**Week:** 3

**Date range:** 24 July 2026 – 30 July 2026

**Team:** Team 07

**Project:** SkyOps – Airline Delay Command Center

---

## 1. Sprint Goal

This week's objective was to set up the Databricks workspace and perform initial exploration of the project datasets. The team loaded the sample raw data, examined the schema, verified row counts, displayed sample records, and identified basic data quality signals to prepare the data for the Bronze layer.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|------|--------|--------|----------|
| Created Databricks workspace | Team 07 | Done | Databricks workspace |
| Loaded sample raw datasets into Databricks | Team 07 | Done | notebooks/01_data_exploration.ipynb |
| Displayed sample records | Team 07 | Done | Notebook output |
| Verified dataset schema | Team 07 | Done | week03_schema_and_row_count.png |
| Checked row counts | Team 07 | Done | week03_schema_and_row_count.png |
| Performed basic profiling (null values and data quality checks) | Team 07 | Done | Notebook profiling queries |
| Updated Week 03 log | Team 07 | Done | weekly_logs/week03_log.md |

---

## 3. Key Decisions

- Used Databricks Free Edition as the primary development environment.
- Performed schema validation and data profiling before implementing the Bronze layer.
- Used sample datasets for exploration to improve execution speed.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|----------|--------|-------------|
| Learning the Databricks environment | Initial setup required additional time | Mentor guidance and documentation |
| Understanding Spark SQL profiling | Slower progress during exploration | Practice with sample queries |

---

## 5. Evidence Added to GitHub

- notebooks/01_data_exploration.ipynb
- screenshots/week03_databricks_data_loaded.png
- screenshots/week03_schema_and_row_count.png
- weekly_logs/week03_log.md

---

## 6. AI Transparency Note

| Question | Response |
|----------|----------|
| **Where AI helped** | AI assisted in understanding Databricks, Spark SQL commands, schema inspection, and basic data exploration techniques. |
| **What we changed after AI suggestion** | We modified the suggested SQL queries to match our project datasets and added additional schema and row count verification. |
| **What we verified manually** | We manually confirmed successful data loading, verified schema, checked row counts, reviewed notebook outputs, and captured screenshots as evidence. |
| **What we can explain without AI** | We can explain how data was loaded into Databricks, how schema and row counts were verified, and why data profiling is required before Bronze ingestion. |

---

## 7. Next Week Preparation

- Create Bronze tables from the raw datasets.
- Preserve raw data along with ingestion metadata.
- Validate that raw record counts match Bronze table counts.
- Capture screenshots and update the Week 04 log.

---