# Week 06 Log — Data Quality and Trusted/Quarantine Routing

**Week:** 6  
**Date range:** 6 Sep 2026 
**Team:**  Team 07  
**Project:** SkyOps Airline Delay Command Center
---

## 1. Sprint Goal

Evaluate the completed Silver Candidate tables against the approved SkyOps Data Quality rules; retain all applicable failure reasons; create Trusted Silver and Quarantine Delta outputs; and prove complete routing, lineage and controlled replay behaviour.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Verified Silver Candidate handoff for airports, carriers, routes and flights | Team 07 | Done | `notebooks/04_data_quality_checks.ipynb` |
| Created Silver Candidate delay components from flight delay-cause fields | Team 07 | Done | `notebooks/04_data_quality_checks.ipynb` |
| Implemented flight identity and duplicate checks | Team 07 | Done | `notebooks/04_data_quality_checks.ipynb` |
| Implemented carrier, airport and route reference checks | Team 07 | Done | `notebooks/04_data_quality_checks.ipynb` |
| Implemented time, duration, cancellation and diversion checks | Team 07 | Done | `notebooks/04_data_quality_checks.ipynb` |
| Implemented delay semantics and delay-cause reconciliation | Team 07 | Done | `notebooks/04_data_quality_checks.ipynb` |
| Implemented route and distance validation | Team 07 | Done | `notebooks/04_data_quality_checks.ipynb` |
| Created Trusted Silver and Quarantine outputs with DQ metadata | Team 07 | Done | `notebooks/04_data_quality_checks.ipynb` |
| Added rule scorecard, routing reconciliation and membership checks | Team 07 | Done | `notebooks/04_data_quality_checks.ipynb` |
| Added controlled replay and Delta history validation | Team 07 | Done | `notebooks/04_data_quality_checks.ipynb` |
| Added Week 6 GitHub activity evidence | Team 07 | Done | GitHub Week 6 evidence |
---

## 3. Key Decisions

- Only approved SkyOps DQ rules are used to determine Trusted Silver versus Quarantine.
- Every Candidate physical record is retained exactly once in either Trusted Silver or Quarantine; no silent deletion or arbitrary deduplication is performed.
- All applicable failure rule IDs and readable failure reasons are retained for a quarantined record.
- Bronze/source lineage is preserved through the DQ process.
- Trusted Silver is the approved input boundary for Week 7 Gold processing.
- Quarantine records are not manually edited; corrections follow the upstream correction and controlled replay process.
- Numeric thresholds not explicitly specified in the project material are kept configurable rather than invented.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| Some numeric DQ thresholds were not explicitly specified in the supplied project material | Risk of applying an incorrect business threshold | Confirm project-specific thresholds with the approved specification/mentor |
| Final DQ counts depend on actual Databricks execution | Evidence must contain genuine execution results | Verify final notebook outputs and screenshots before submission |


---

## 5. Evidence Added to GitHub

- `notebooks/04_data_quality_checks.ipynb` - completed Week-6 Data Quality and Trusted/Quarantine implementation.
- Trusted Silver and Quarantine Delta routing logic.
- DQ rule evaluation, failure metadata and lineage handling.
- Rule scorecard, reconciliation and physical-record membership checks.
- Controlled replay and Delta history validation.
- Week 6 GitHub activity evidence.
- `weekly_logs/week06_log.md` - completed Week-6 weekly record.

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | Explained Spark SQL patterns, reference joins, multi-rule DQ evaluation, routing and reconciliation logic. |
| What we changed | Adapted the suggested logic to the actual SkyOps tables, columns, DQ rules and project requirements. |
| What we verified manually | Verified Candidate schemas, DQ conditions, reference joins, routing destinations, metadata, reconciliation and replay logic in Databricks. |
| What we can explain | We can explain why each DQ rule exists, how PASS/FAIL routing works, how multiple failures are retained, and how Candidate-to-Trusted/Quarantine reconciliation works. |


---

## 7. Next Week Preparation

- Confirm Week 7 reads only from the approved Trusted Silver tables.
- Carry unresolved Quarantine findings and required upstream correction/replay actions forward.
