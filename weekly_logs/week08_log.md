# Week 08 Log — [PowerBI DashBoards]

**Week:** 8  
**Date range:** [Add dates]  
**Team:** [Team 07]  
**Project:** [SkyOps Airline Delay Command Center]

---

## 1. Sprint Goal

Build the first working Gold-only Power BI dashboard for the SkyOps Airline Delay Command Center.
Validate the approved Gold hand-off, create the Power BI model with safe relationships and measures, build the first dashboard pages, and prepare reconciliation and evidence for review.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Loaded the approved Gold tables into Power BI | T. Lakshmi Raja Hamsa | Done | Power BI model |
| Created and cleaned the Power BI data model | T. Lakshmi Raja Hamsa | Done | `week08_03_powerbi_model.png` |
| Removed incorrect `_bronze_record_hash` relationships | Dhana Laskhmi | Done | Power BI relationship view |
| Created safe business-key relationships | Sowjanya | Done | `week08_03_powerbi_model.png` |
| Created Flight Operations Overview dashboard | sowjanya | Done | `week08_04_dashboard_page_01.png` |
| Added Total Flights, Cancelled Flights, Cancellation Rate and Diverted Flights KPI cards | T. Lakshmi Raja Hamsa | Done | Dashboard Page 1 |
| Added Flight Volume Over Time visual | T. Lakshmi Raja Hamsa | Done | Dashboard Page 1 |
| Added Flights by Carrier visual | Team 07 | Sowjanya | Dashboard Page 1 |
| Added Cancellation Rate by Carrier visual | Dhana lakshmi | Done | Dashboard Page 1 |
| Added and tested Date Range and Carrier slicers | Dhana Lakshmi | Done | Dashboard Page 1 |
| Created Route Performance dashboard | T. Lakshmi Raja Hamsa | Done | `week08_05_dashboard_page_02.png` |
| Added Total Route Flights, Cancelled Flights, Route Cancellation Rate and Avg Arrival Delay KPI cards | T. Lakshmi Raja Hamsa | Done | Dashboard Page 2 |
| Added Flights by Route visual | Sowjanya | Done | Dashboard Page 2 |
| Added Flights by Distance Band visual | Sowjanya | Done | Dashboard Page 2 |
| Added and tested Date Range slicer | T. Lakshmi Raja Hamsa | Done | Dashboard Page 2 |
| Created Cancellation Rate and Route Cancellation Rate DAX measures | Dhana Laskhmi | Done | Power BI measures |
| Tested dashboard filtering and KPI changes | Team 07 | Dhana Lakshmi | Dashboard screenshots |
| Prepared Power BI dashboard README | T. Lakshmi Raja Hamsa | Done | `dashboard/README.md` |

---

## 3. Key Decisions

- Use the approved Gold tables as the data sources for the Power BI dashboards.
- Remove incorrect `_bronze_record_hash` relationships and use meaningful business-key relationships.
- Keep different-grain Gold summary tables independent instead of directly joining them.
- Create two dashboard pages based on business questions: Flight Operations Overview and Route Performance.
- Use KPI cards, comparison visuals, trend visuals and slicers to make the dashboards interactive.
- Use DAX measures for Cancellation Rate and Route Cancellation Rate.
- Keep further dashboard refinement and detailed storytelling for Week 9.

---

## 4. Blockers / Risks


| Blocker | Impact | Help Needed |
|---|---|---|
| Final Gold-to-Power BI reconciliation needs to be completed | Final dashboard validation evidence is pending | Verify selected dashboard values against the corresponding Gold calculations |
| Final dashboard evidence screenshots need to be organized | GitHub evidence package is not yet complete | Capture and organize the required dashboard and validation screenshots |

---

## 5. Evidence Added to GitHub


- `dashboard/powerbi_dashboard.pbix`
- `dashboard/README.md`
- `notebooks/06_powerbi_export.ipynb`
- `screenshots/week08_01_gold_source_register.png`
- `screenshots/week08_02_export_reconciliation.png`
- `screenshots/week08_03_powerbi_model.png`
- `screenshots/week08_04_dashboard_page_01.png`
- `screenshots/week08_05_dashboard_page_02.png`
- `screenshots/week08_06_measure_reconciliation.png`

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI helped with Power BI dashboard planning, selecting suitable visuals and slicers, explaining Power BI relationships, creating DAX measures, and preparing dashboard documentation. |
| What we changed after AI suggestion | We reviewed the suggested relationships and removed the incorrect `_bronze_record_hash` relationships. We also created two business-focused dashboard pages instead of creating separate pages for every Gold table. |
| What we verified manually | We manually checked the Power BI relationships, KPI values, visuals, slicer behaviour, field selections and dashboard layout. The Carrier slicer was tested and confirmed to change the dashboard values. |
| What we can explain without AI | We can explain the dashboard pages, KPI calculations, Power BI relationships, visuals, slicers and the process of validating dashboard values against the Gold data. |

---

## 7. Next Week Preparation

- Refine the Power BI dashboard layout and visual presentation.
- Improve dashboard usability and visual hierarchy.
- Develop deeper dashboard insights and decision-oriented storytelling.
- Complete the remaining Gold-to-Power BI reconciliation and evidence checks.
