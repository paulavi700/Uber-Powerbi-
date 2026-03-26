## 📊 Project Overview

This dashboard analyzes thousands of Uber trips to help understand:
- When and where rides are most in demand
- How surge pricing correlates with peak hours
- Which vehicle types and payment methods dominate
- Revenue distribution across pickup/drop-off zones

---

## 🗂️ Dataset Structure

The project uses two relational tables connected via `LocationID`.

### 🚕 Trip Details Table
Contains granular information about each individual Uber ride.

| Column | Description |
|---|---|
| `Trip ID` | Unique identifier for each trip |
| `Pickup Time` | Date & time passenger was picked up |
| `Drop Off Time` | Date & time passenger was dropped off |
| `Passenger Count` | Number of passengers in the trip |
| `Trip Distance` | Distance covered (in miles) |
| `PULocationID` | Numeric code for pickup location |
| `DOLocationID` | Numeric code for drop-off location |
| `Payment Type` | Mode of payment (credit card, cash, wallet) |
| `Fare Amount` | Base fare before additional fees |
| `Surge Fee` | Extra charge applied during high-demand periods |
| `Vehicle` | Uber service type (UberX, UberXL, Uber Black) |

### 📍 Location Table
Maps numeric LocationIDs to real area names and cities.

| Column | Description |
|---|---|
| `LocationID` | Unique identifier — key to link with trip data |
| `Location` | Area or neighborhood name |
| `City` | City where the location exists |

---

## 🔍 Key Insights

- **Surge pricing** spikes strongly align with late-night and early-morning demand windows
- **UberX** dominates overall ride share, while **UberXL** records higher average passenger counts
- Specific **pickup zones** consistently generate disproportionately high revenue
- **Credit card** remains the most preferred payment method across cities
- Trip duration and distance patterns reveal clear **short-trip vs long-trip** corridors

---

## 📐 Data Model

```
Trip Details Table
    |
    |--- PULocationID ──→ Location Table (LocationID)
    |--- DOLocationID ──→ Location Table (LocationID)
```

Star schema design with the Location Table acting as a shared dimension for both pickup and drop-off analysis.

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|---|---|
| **Power BI Desktop** | Dashboard design, data modeling, visuals |
| **DAX** | Custom measures, KPIs, calculated columns |
| **Power Query (M)** | Data transformation and cleaning |
| **Star Schema** | Optimized relational data model |

---

## 📈 Dashboard Features

- **KPI Cards** — Total Trips, Total Revenue, Average Fare, Average Distance
- **Time Intelligence** — Trip trends by hour, day, and month
- **Geographic Map** — Pickup & drop-off hotspot visualization
- **Vehicle Analysis** — Ride share breakdown by vehicle type
- **Surge Pricing Heatmap** — Demand vs surge correlation
- **Payment Analysis** — Revenue split by payment method
- **Dynamic Slicers** — Filter by city, vehicle type, date range, and payment type

---

## 🚀 How to Use

1. Clone or download this repository
2. Open `Uber.pbix` in **Power BI Desktop** (free download from [Microsoft](https://powerbi.microsoft.com/))
3. Explore the dashboard using the interactive slicers and filters
4. Optionally connect your own dataset matching the schema above

```bash
git clone https://github.com/YOUR_USERNAME/uber-powerbi-dashboard.git
```

---

## 📁 Repository Structure

```
uber-powerbi-dashboard/
│
├── Uber.pbix                  # Main Power BI project file
├── README.md                  # Project documentation
├── dataset/
│   ├── trip_details.csv       # (optional) Raw trip data
│   └── location_table.csv     # (optional) Location mapping data
└── screenshots/
    ├── overview.png
    ├── map_view.png
    └── vehicle_analysis.png
```

---

## 🎯 Skills Demonstrated

- Data modeling with star schema in Power BI
- Writing DAX measures for time intelligence and KPIs
- Building interactive, drill-through dashboards
- Geographic data visualization
- Translating raw ride data into actionable business insights

---

## 🙋 About the Author

Built as part of a data analytics portfolio project to demonstrate real-world Power BI skills using ride-sharing domain data.

📬 Connect with me on [LinkedIn](https://www.linkedin.com/in/avipriya-paul-4897a9208/)

---

