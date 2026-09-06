# Week 07 Log — Gold Table Design and Build

**Week:** 7  
**Date range:** 6 Sep 2026  
**Team:** Team 07  
**Project:** SkyOps Airline Delay Command Center
---

## 1. Sprint Goal

Close the Week-6 Trusted Silver handoff; define the SkyOps KPI contracts and Gold-table design; build the carrier-level daily Gold metrics table; and validate its grain, scope, joins, measures, reconciliation and controlled rerun behaviour.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Verified Trusted Silver handoff and documented SkyOps KPI register | Team 07 | Done | `notebooks/05_gold_aggregations.ipynb` |
| Defined KPI formulas, grain, eligibility and input scope | Team 07 | Done | `notebooks/05_gold_aggregations.ipynb` |
| Profiled Trusted Silver flight scope and required KPI fields | Team 07 | Done | `notebooks/05_gold_aggregations.ipynb` |
| Validated carrier lookup uniqueness before enrichment | Team 07 | Done | `notebooks/05_gold_aggregations.ipynb` |
| Built safe carrier enrichment using LEFT JOIN | Team 07 | Done | `notebooks/05_gold_aggregations.ipynb` |
| Created carrier-day Gold aggregation | Team 07 | Done | `notebooks/05_gold_aggregations.ipynb` |
| Created `gold_skyops_carrier_daily_metrics` Delta table | Team 07 | Done | `notebooks/05_gold_aggregations.ipynb` |
| Added Gold grain, key and KPI measure validation checks | Team 07 | Done | `notebooks/05_gold_aggregations.ipynb` |
| Added Gold-to-Trusted Silver measure reconciliation checks | Team 07 | Done | `notebooks/05_gold_aggregations.ipynb` |
| Added weighted average-delay reconciliation | Team 07 | Done | `notebooks/05_gold_aggregations.ipynb` |
| Added controlled repeat-run comparison | Team 07 | Done | `notebooks/05_gold_aggregations.ipynb` |
| Updated Gold KPI documentation | Team 07 | Done | `docs/gold_metrics_definition.md` |
| Added Week 7 GitHub activity evidence | Team 07 | Done | `screenshots/week07_*` |
| Completed Week 7 Gold log documentation | Team 07 | Done | `weekly_logs/week07_log.md` |

---

## 3. Key Decisions

- Gold processing reads only from the approved Trusted Silver tables; Silver Candidate and Quarantine are excluded.
- The Week-7 built Gold output is `gold_skyops_carrier_daily_metrics`.
- The declared grain is one row per `reporting_carrier + metric_date`.
- Daily flight volume is calculated over eligible Trusted Silver flight records with a usable flight date.
- Cancellation and diversion rates use their defined Trusted Silver flight populations and KPI eligibility rules.
- The 15-minute departure-delay KPI uses signed departure delay and excludes cancelled and diverted flights from its eligible denominator.
- Average operational delay metrics use the defined operational delay fields and applicable eligibility conditions.
- Carrier enrichment uses a LEFT JOIN so eligible flight records are not silently lost.
- Carrier lookup uniqueness and join effects are checked before aggregation.
- Gold measures are reconciled against the appropriate eligible Trusted Silver populations.
- Changing audit timestamps are excluded from controlled business-row rerun comparison.
- Additional airport, route and delay-cause Gold designs are not treated as completed physical outputs unless separately built and validated.
- Power BI/dashboard implementation is outside the Week-7 Gold build boundary.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| None | No major blocker during Week 7 implementation | Not required |

---

## 5. Evidence Added to GitHub

- `notebooks/05_gold_aggregations.ipynb` - completed SkyOps Week-7 Gold aggregation notebook.
- `docs/gold_metrics_definition.md` - SkyOps KPI definitions and Gold-table documentation.
- `gold_skyops_carrier_daily_metrics` - carrier-day Gold Delta table build.
- Gold KPI definitions covering flight volume, cancellation rate, diversion rate, departure-delay rate and operational delay measures.
- Gold scope, carrier lookup, LEFT JOIN and grain validation logic.
- Gold-to-Trusted Silver measure reconciliation and weighted average-delay validation.
- Controlled repeat-run comparison logic.
- `screenshots/week07_*` - Week-7 execution evidence.
- `weekly_logs/week07_log.md` - completed seven-section Week-7 record.
- Week 7 GitHub activity evidence.

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | Explained the Gold-layer method, KPI contracts, grain and scope definition, safe joins, aggregation and validation approaches. |
| What we changed after AI suggestion | Adapted the suggested method to the actual SkyOps Trusted Silver flight and carrier tables, project-specific delay fields, KPI rules and Gold table name. |
| What we verified manually | Verified the Trusted Silver inputs, KPI fields, eligibility conditions, carrier join key, declared Gold grain, aggregation logic, reconciliation queries and controlled rerun comparison logic. |
| What we can explain without AI | We can explain why the Gold grain is carrier plus date, how each KPI is calculated, why specific flight records are included or excluded, how the LEFT JOIN protects the input population, and how Gold measures are reconciled to Trusted Silver. |

---

## 7. Next Week Preparation

- Confirm the built Gold table and KPI definitions are approved for downstream consumption.
- Review and retain genuine Week-7 execution evidence and validation results.
- Carry the remaining approved Gold-table/KPI designs forward according to mentor direction.
- Prepare the approved Gold outputs for the next Power BI/dashboard stage.
