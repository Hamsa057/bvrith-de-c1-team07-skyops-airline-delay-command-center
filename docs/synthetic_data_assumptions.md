# Synthetic Data Assumptions

**Week:** 2  
**Purpose:** Document the assumptions used to generate synthetic airline operations data for the SkyOps Airline Delay Command Center project.

---

## 1. Synthetic Data Boundary

This project uses **synthetic airline operations data only**. It is created for educational purposes and does not contain any real airline, passenger, airport, or customer information.

---

## 2. Domain Assumptions

| Area | Assumption |
|---|---|
| Geography / Scope | Major airports across the United States |
| Time Period | January 2024 to December 2024 |
| Source Systems | Flight operations, airport reference data, airline reference data, and route reference data |
| Event Types | Flight departure, arrival, delay, cancellation, diversion |
| Reference Data | Airports, airlines (carriers), and flight routes |

---

## 3. Data Volume Assumptions

| File | Approximate Rows | Reason |
|---|---:|---|
| flights.csv | ~150,000 | Main flight operations dataset |
| airports.csv | ~400 | Airport reference information |
| carriers.csv | ~25 | Airline carrier reference data |
| routes.csv | ~5,000 | Route mapping information |
| flight_status_event.json | Small sample | Streaming event simulation |

---

## 4. Controlled Data Quality Issues

| Issue Type | Approx. Share | Why Include It |
|---|---:|---|
| Duplicate flight records | 0.2%–0.5% | Test duplicate detection |
| Missing delay values | 1%–3% | Test completeness checks |
| Invalid airport/carrier codes | 0.5%–1% | Test referential integrity |
| Negative delay values | 0.1%–0.5% | Test range validation |
| Timestamp inconsistencies | 0.1%–0.3% | Test date and time validation |

---

## 5. Manual Verification

Before using the generated data, the team verifies that:

- Row counts are reasonable.
- Primary and foreign keys are valid.
- Flight dates and times are realistic.
- Delay values are within expected ranges.
- Controlled data quality issues are present but limited.
- Source files can be joined correctly using common keys.
