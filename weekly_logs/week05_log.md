# Week 05 Log — Silver Transformations

**Week:** 5  
**Date range:** 31 August 2026 – 5 September 2026  
**Team:** Team 07  
**Project:** SkyOps Airline Delay Command Center
---

## 1. Sprint Goal

Transform the completed Bronze tables into clean, standardized and typed Silver Candidate tables according to the approved project specification. Preserve Bronze lineage and validate the Candidate outputs through schema, row-count and lineage checks.

---

## 2. Work Completed
| Task                                             | Owner   | Status | Evidence                          |
| ------------------------------------------------ | ------- | ------ | --------------------------------- |
| Verified Bronze tables and schemas               | Team 07 | Done   | `03_silver_transformations.ipynb` |
| Standardized airport data                        | Team 07 | Done   | `silver_airports_candidate`       |
| Standardized carrier data                        | Team 07 | Done   | `silver_carriers_candidate`       |
| Standardized route data                          | Team 07 | Done   | `silver_routes_candidate`         |
| Standardized flight data                         | Team 07 | Done   | `silver_flights_candidate`        |
| Applied safe type conversions using `TRY_CAST()` | Team 07 | Done   | `03_silver_transformations.ipynb` |
| Preserved Bronze lineage fields                  | Team 07 | Done   | `03_silver_transformations.ipynb` |
| Performed row-count reconciliation               | Team 07 | Done   | `03_silver_transformations.ipynb` |
| Performed record-hash lineage validation         | Team 07 | Done   | `03_silver_transformations.ipynb` |
| Created Silver Candidate Delta tables            | Team 07 | Done   | `03_silver_transformations.ipynb` |


---

## 3. Key Decisions

- Used TRIM() and appropriate standardization operations for controlled fields without changing their business meaning.
- Used TRY_CAST() for safe conversion of fields into their required data types while retaining the original physical rows.
- Preserved Bronze lineage information in the Silver Candidate tables for traceability.
- Maintained the Bronze physical-row grain during the Silver transformation.
- Used Delta tables for the Silver Candidate outputs.
- Did not perform filtering, deduplication or quarantine in Week 5.

---

## 4. Blockers / Risks
| Blocker                                                      | Impact                                                         | Help Needed                              |
| ------------------------------------------------------------ | -------------------------------------------------------------- | ---------------------------------------- |
| Invalid values may become `NULL` during safe type conversion | Such records need to be reviewed during the Data Quality stage | Review conversion results in Week 6      |
| No major implementation blocker identified                   | No immediate impact                                            | Continue validation and evidence capture |


---

## 5. Evidence Added to GitHub

- Updated notebooks/03_silver_transformations.ipynb.
- Added Silver Candidate table transformations for airports, carriers, routes and flights.
- Added schema inspection and validation queries.
- Added Bronze vs Silver row-count reconciliation queries.
- Added record-hash lineage validation queries.
- Added Delta Candidate table creation logic.
- Added Week 5 transformation and validation evidence.

---

## 6. AI Transparency Note
| Question                            | Response                                                                                                                                                                                                                                  |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Where AI helped                     | AI helped us understand the Bronze-to-Silver transformation workflow and suggested Spark SQL patterns for standardization, safe type conversion and validation.                                                                           |
| What we changed after AI suggestion | We compared the suggestions with our approved project specification and actual Bronze schemas and modified the transformations to match our project requirements.                                                                         |
| What we verified manually           | We manually verified the Bronze schemas, source and target columns, data types, transformation logic, lineage fields and validation queries in Databricks.                                                                                |
| What we can explain without AI      | We can explain the purpose of Silver Candidate tables, standardization, `TRY_CAST()`, lineage preservation, row-count reconciliation and record-hash validation, as well as how the Bronze data is transformed into the Candidate tables. |


---

## 7. Next Week Preparation
- Review the Silver Candidate tables for data-quality issues such as invalid conversions and null values.
- Prepare for Week 6 Data Quality processing and the Trusted Silver/quarantine stage.
