# Data Dictionary

**Week:** 2  
**Purpose:** Define raw, reference, Silver, and streaming fields.

---

## 1. Source File Catalog

| File Name | Grain | Purpose | Approx. Rows | Notes |
|---|---|---|---:|---|
| `flights.csv` | One row per flight | Stores flight schedule, delay, cancellation, departure and arrival information | ~150,000 | Main source dataset |
| `airports.csv` | One row per airport | Stores airport details such as airport code, name, city and state | ~400 | Reference/master data |
| `carriers.csv` | One row per airline | Stores airline (carrier) codes and names | ~25 | Reference/master data |
| `routes.csv` | One row per route | Stores origin–destination routes and distance information | ~5,000 | Route reference data |
| `flight_status_event.json` | One row per event | Simulated live flight status events | Small sample | JSON streaming events |

---

## 2. Raw File Schema: `flights.csv`

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| source_record_key | String | Yes | FLT000001 | Unique flight record ID |
| flight_date | Date | Yes | 2024-01-01 | Date of the flight |
| reporting_carrier | String | Yes | AA | Airline carrier code |
| flight_number | Integer | Yes | 101 | Flight number |
| tail_number | String | No | N123AA | Aircraft tail number |
| origin_airport_code | String | Yes | JFK | Origin airport code |
| destination_airport_code | String | Yes | LAX | Destination airport code |
| scheduled_departure_hhmm | Integer | Yes | 0830 | Scheduled departure time |
| actual_departure_hhmm | Integer | No | 0845 | Actual departure time |
| departure_delay_signed_minutes | Integer | No | 15 | Departure delay (signed) |
| departure_delay_minutes | Integer | No | 15 | Departure delay in minutes |
| scheduled_arrival_hhmm | Integer | Yes | 1130 | Scheduled arrival time |
| actual_arrival_hhmm | Integer | No | 1145 | Actual arrival time |
| arrival_delay_signed_minutes | Integer | No | 15 | Arrival delay (signed) |
| arrival_delay_minutes | Integer | No | 15 | Arrival delay in minutes |
| cancelled_flag | Integer | Yes | 0 | Flight cancellation flag |
| cancellation_code | String | No | A | Cancellation reason code |
| diverted_flag | Integer | Yes | 0 | Flight diversion flag |
| scheduled_elapsed_minutes | Integer | Yes | 180 | Scheduled flight duration |
| actual_elapsed_minutes | Integer | No | 195 | Actual flight duration |
| air_time_minutes | Integer | No | 170 | Time spent in air |
| taxi_out_minutes | Integer | No | 12 | Taxi-out time |
| taxi_in_minutes | Integer | No | 8 | Taxi-in time |
| distance_miles | Integer | Yes | 2475 | Flight distance in miles |
| carrier_delay_minutes | Integer | No | 5 | Delay due to carrier |
| weather_delay_minutes | Integer | No | 10 | Delay due to weather |
| nas_delay_minutes | Integer | No | 0 | Delay due to NAS |
| security_delay_minutes | Integer | No | 0 | Delay due to security |
| late_aircraft_delay_minutes | Integer | No | 5 | Delay due to late aircraft |
| source_period | String | Yes | 2024-01 | Source data period |
| source_original_filename | String | Yes | flights.csv | Original source file |
| source_row_number | Integer | Yes | 1 | Original row number |

---

## 3. Raw File Schema: `airports.csv`

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| airport_code | String | Yes | JFK | Unique airport code |
| airport_name | String | Yes | John F. Kennedy International Airport | Airport name |
| city | String | Yes | New York | City where the airport is located |
| state_region | String | Yes | NY | State or region of the airport |
| active_flag | Integer | Yes | 1 | Indicates whether the airport is active |

---

## 4. Reference File Schema

### carriers.csv

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| carrier_code | String | Yes | AA | Unique airline carrier code |
| carrier_name | String | Yes | American Airlines | Airline name |
| active_flag | Integer | Yes | 1 | Indicates whether the carrier is active |

### routes.csv

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| route_id | String | Yes | R001 | Unique route ID |
| origin_airport_code | String | Yes | JFK | Origin airport code |
| destination_airport_code | String | Yes | LAX | Destination airport code |
| route_label | String | Yes | JFK-LAX | Route identifier |
| distance_miles | Integer | Yes | 2475 | Distance between airports in miles |
| distance_band | String | Yes | Long Haul | Route distance category |

---

## 5. Canonical Silver Table Design

Final Silver table name:

```text
silver_flight_operations
```

| Silver Field | Data Type | Source Mapping | Business Meaning |
|---|---|---|---|
| record_id | String | source_record_key | Unique flight record ID |
| flight_date | Date | flight_date | Date used for analysis |
| carrier_code | String | reporting_carrier | Airline code |
| origin_airport | String | origin_airport_code | Departure airport |
| destination_airport | String | destination_airport_code | Arrival airport |
| departure_delay | Integer | departure_delay_minutes | Departure delay in minutes |
| arrival_delay | Integer | arrival_delay_minutes | Arrival delay in minutes |
| cancelled | Integer | cancelled_flag | Flight cancellation status |
| distance | Integer | distance_miles | Flight distance |

---

## 6. Streaming Event Schema

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| event_id | String | Yes | EVT-0001 | Unique event ID |
| event_timestamp | Timestamp | Yes | 2026-07-03T10:15:00+05:30 | Time of the event |
| flight_id | String | Yes | FLT000001 | Flight record reference |
| gate | String | Yes | A12 | Departure gate |
| status | String | Yes | Boarding | Current flight status |
| delay_minutes | Integer | No | 20 | Current delay in minutes |
| airport_code | String | Yes | JFK | Airport where the event occurred |

---
---

## 7. Primary Keys and Foreign Keys

### Primary Keys
- flights.csv → source_record_key
- airports.csv → airport_code
- carriers.csv → carrier_code
- routes.csv → route_id

### Foreign Keys
- flights.reporting_carrier → carriers.carrier_code
- flights.origin_airport_code → airports.airport_code
- flights.destination_airport_code → airports.airport_code
- routes.origin_airport_code → airports.airport_code
- routes.destination_airport_code → airports.airport_code
