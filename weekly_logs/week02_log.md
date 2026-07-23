# Week 02 Log — Dataset Design and Data Dictionary

**Week:** 2  
**Date range:** 21 July 2026 – 27 July 2026  
**Team:** Team 07  
**Project:** SkyOps Airline Delay Command Center

---

## 1. Sprint Goal

The goal of Week 2 was to design the project dataset structure, define source files, prepare a data dictionary, identify primary and foreign keys, and document synthetic data assumptions.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Created data dictionary | Team 07 | Done | docs/data_dictionary.md |
| Defined source files and fields | Team 07 | Done | docs/data_dictionary.md |
| Documented synthetic data assumptions | Team 07 | Done | docs/synthetic_data_assumptions.md |
| Added sample raw datasets | Team 07 | Done | data_sample/raw/ |
| Updated data generator script | Team 07 | Done | src/generate_synthetic_data.py |

---

## 3. Key Decisions

- Selected project source files such as flights, airports, carriers, and routes datasets.
- Defined relationships between datasets using primary keys and foreign keys.
- Used synthetic sample data for testing and development.
- Maintained small raw sample files for GitHub submission.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| Understanding dataset relationships and field mapping | Medium | Discussed with team members and referred project documentation |

---

## 5. Evidence Added to GitHub

- Added data dictionary documentation (docs/data_dictionary.md)
- Added synthetic data assumptions document (docs/synthetic_data_assumptions.md)
- Added raw sample CSV files (data_sample/raw/)
- Updated synthetic data generation script (src/generate_synthetic_data.py)

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI helped understand data dictionary format, dataset documentation, and synthetic data generation approach. |
| What we changed after AI suggestion | Adapted AI suggestions according to SkyOps project requirements and verified them with the actual dataset structure. |
| What we verified manually | Verified file names, fields, keys, and sample data manually before updating GitHub. |
| What we can explain without AI | We can explain dataset design, keys, assumptions, and organization of raw sample data. |

---

## 7. Next Week Preparation

- Perform dataset profiling and schema validation.
- Start preparing data ingestion for the Bronze layer.
