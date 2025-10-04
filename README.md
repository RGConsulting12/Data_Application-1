---

# Flight and Airport Data Project

This project will collect and combine **flight data** and **airport location data** so it can be used for future analysis and visualizations.

Right now, this is a starting point — the data will be added later.

---

## Project Goal

The goal is to:
1. Find open data on **commercial flights** and **airport locations**
2. Combine both datasets into one file
3. Use the data for analysis, charts, or dashboards in the future

---

## Project Structure

| Folder | Description |
|--------|--------------|
| `data/` | This is where flight and airport data files will go |
| `scripts/` | Python scripts for cleaning or merging data |
| `notebooks/` | Jupyter notebooks for data exploration |
| `README.md` | This file that explains the project |

---

## Planned Data Sources

I will look at these open datasets:

- [OpenFlights](https://openflights.org/data.html) – routes and airport coordinates  
- [OurAirports](https://ourairports.com/data/) – airport information  
- [OpenSky Network](https://opensky-network.org) – live flight data (optional)

---

## Planned Data Files

**airports.csv**
| Column | Description |
|--------|--------------|
| airport_id | Unique ID (IATA or ICAO) |
| name | Airport name |
| city | City |
| country | Country |
| latitude | Latitude |
| longitude | Longitude |

**flights.csv**
| Column | Description |
|--------|--------------|
| origin_id | Departure airport code |
| destination_id | Arrival airport code |
| airline | Airline name |
| distance_km | Distance between airports (optional) |

---

## Example Plan

Once data is added, a basic Python script might look like this:

```python
import pandas as pd

airports = pd.read_csv("data/airports.csv")
flights = pd.read_csv("data/flights.csv")

merged = flights.merge(
    airports, left_on="origin_id", right_on="airport_id", how="left"
)

print(merged.head())
