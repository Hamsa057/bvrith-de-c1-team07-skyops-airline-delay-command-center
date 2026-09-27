# Dashboard Insights

**Week:** 9  
**Purpose:** Explain what the Power BI dashboard shows.

---

## 1. Dashboard Pages

| Page | Purpose | Main Visuals |
|---|---|---|
| Page 1: Flight Operations Overview | High-level summary of flight operations, cancellations and carrier performance | KPI cards, Flight Volume Over Time, Flights by Carrier, Cancellation Rate by Carrier, filters |
| Page 2: Route Performance | Analyze flight activity and cancellation performance across routes and distance bands | KPI cards, Flights by Route, Flights by Distance Band, filter |
| Page 3: Quality / Exceptions | Not included in the Week 9 dashboard | Not created |
| Page 4: Streaming / Live View | Not included in the Week 9 dashboard | Not created |

---

## 2. Key Insights

Write 5–8 insights from the dashboard.

1. The Flight Operations Overview page provides a high-level view of total flights, cancelled flights, cancellation rate and diverted flights.
2. Flight volume can be examined over time using the Flight Volume Over Time visual.
3. The Flights by Carrier visual allows comparison of flight activity across carriers.
4. The Cancellation Rate by Carrier visual shows that cancellation performance can vary across carriers within the selected reporting scope.
5. The Carrier slicer allows the dashboard to be filtered for a specific carrier and updates the relevant KPI values and visuals.
6. The Route Performance page provides a route-level view of total flights and cancelled flights.
7. Flights by Distance Band provides a comparison of flight activity across different distance categories.
8. The dashboard uses Gold-level data and KPI measures so that the displayed results can be traced back to their corresponding Gold tables.

---

## 3. How the Dashboard Uses Gold Tables

| Dashboard Page | Gold Table Used | Important Fields |
|---|---|---|
| Page 1: Flight Operations Overview | `Gold_Flight_Delay` | `origin_airport_code`, `reporting_carrier`, flight-level fields |
| Page 1: Flight Operations Overview | `Gold_Carrier_Delay` | `carrier_name`, `metric_date`, `total_flights`, `cancelled_flights` |
| Page 1: Flight Operations Overview | `Gold_Carriers` | `carrier_code`, `carrier_name` |
| Page 1: Flight Operations Overview | `Gold_Airports` | `airport_code` |
| Page 2: Route Performance | `Gold_Route_Daily` | `route_id`, `metric_date`, `total_flights`, `cancelled_flights`, route performance fields |
| Page 2: Route Performance | `Gold_Routes` | `route_id`, route reference fields |

---

## 4. Power BI Validation

- [x] Dashboard connects to Gold outputs only.
- [x] Filters work correctly.
- [x] KPI totals match Gold table checks.
- [x] Screenshots are saved in `screenshots/`.
- [x] Dashboard story is explainable by all students.
