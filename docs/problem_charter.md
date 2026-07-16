# Problem Charter

**Week:** 1
**Owner(s):** [Ms. T. Lakshmi Raja Hamsa, Ms. Mekala.Sowjanya, Ms. G.Dhanalaxmi]
**Project:** SkyOps – Airline Delay Command Center

---

## 1. Problem Context

### Define the Problem

Raw flight data contains information about delays, cancellations, carriers, airports, and routes, but may include duplicates, invalid codes, and inconsistent records. SkyOps converts this data into trusted insights for understanding airline performance, airport congestion, delay causes, and live flight status.

---

## 2. Engineering Problem

Build a Databricks pipeline that converts raw aviation data into trusted **Bronze, Silver, Data Quality, and Gold outputs**, which are then used in Power BI and a simulated streaming workflow.

---

## 3. Users / Stakeholders

| Stakeholder         | Requirement                                        |
| ------------------- | -------------------------------------------------- |
| Operations Director | Identify delayed routes and unreliable carriers    |
| Performance Analyst | Compare airline delay and cancellation performance |
| Airport Manager     | Analyze congestion and delay patterns              |
| Communications Lead | Monitor live flight status                         |

---

## 4. Scope

**Included:** Raw data ingestion, Bronze, Silver, Data Quality, Gold metrics, Power BI dashboard, streaming simulation, and GitHub evidence.

**Excluded:** Flight booking systems, delay prediction models, fare tracking, airline website scraping, and Kafka installation.

---

## 5. Goals and Success Criteria

* Build an explainable end-to-end data pipeline.
* Identify and handle major data quality issues.
* Create reliable Gold metrics and a Power BI dashboard.
* Demonstrate simulated live flight status streaming.
* Maintain complete weekly GitHub evidence.
* Ensure all team members can explain the project.
