# Week 04 Log — Bronze Ingestion

**Week:** 4  
**Date range:** [31-07-2026 to 06-08-2026]  
**Team:** [07]  
**Project:** SkyOps – Airline Delay Command Center

---

## 1. Sprint Goal

Implement the Bronze ingestion layer by reading all approved batch source files and storing them as persistent Bronze Delta tables. Preserve the original source data, add ingestion metadata, and verify that the source and Bronze record counts match.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Created Week 4 Bronze Ingestion notebook (`02_bronze_ingestion.ipynb`) |[T. Lakshmi Raja Hamsa] | Done | notebooks/02_bronze_ingestion.ipynb |
| Configured Unity Catalog, schema, and Volume path | [Dhana Lakshmi] | Done | Notebook output |
| Ingested `airports.csv` into `bronze_airports` | [Sowjanya] | Done | Notebook execution |
| Ingested `carriers.csv` into `bronze_carriers` | [Sowjanya] | Done | Notebook execution |
| Ingested `flights.csv` into `bronze_flights` | [Sowjanya] | Done | Notebook execution |
| Ingested `routes.csv` into `bronze_routes` | [T. Lakshmi Raja Hamsa] | Done | Notebook execution |
| Added ingestion metadata (`ingestion_timestamp`, `source_system`, `source_file_name`, `batch_id`) | [T. Lakshmi Raja Hamsa] | Done | Bronze tables |
| Reconciled source and Bronze row counts for all datasets | [] | Done | Reconciliation output |
| Captured execution screenshots and updated repository | [Dhana Lakshmi] | Done | evidence/week_04/ |

---

## 3. Key Decisions

- Used the approved CSV batch files (`airports.csv`, `carriers.csv`, `flights.csv`, and `routes.csv`) stored in the Unity Catalog Volume for Bronze ingestion.
- Used Delta tables with **overwrite** mode to support safe repeat-run behaviour and prevent duplicate records during reruns.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| Initial data pack contained Excel files, while the project workflow used CSV files in Databricks. | Resolved after confirming the CSV files from Week 3 were the approved batch sources. | No further assistance required. |

---

## 5. Evidence Added to GitHub

- Updated `notebooks/02_bronze_ingestion.ipynb`
- Added screenshots in `evidence/week_04/` (Volume contents, Bronze tables, reconciliation results, Delta history)
- Updated `weekly/week_04_log.md`

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI assisted in organizing the Bronze ingestion notebook, preparing the ingestion workflow, and generating sample code for creating Bronze Delta tables and reconciliation. |
| What we changed after AI suggestion | Updated the notebook to use the SkyOps project configuration, Unity Catalog path, approved CSV source files, and project-specific Bronze table names. |
| What we verified manually | Verified file availability in the Unity Catalog Volume, successful Bronze table creation, metadata columns, record counts, and notebook execution results in Databricks. |
| What we can explain without AI | We can explain the Bronze ingestion workflow, Unity Catalog setup, ingestion metadata, Delta table creation, source-to-Bronze process, and source-versus-Bronze reconciliation. |

---

## 7. Next Week Preparation

- Prepare the Bronze tables for Data Quality validation and Silver layer transformations.
- Review the Bronze ingestion results and project documentation before starting Week 5 implementation.
