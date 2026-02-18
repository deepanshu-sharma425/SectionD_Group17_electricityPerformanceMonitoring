# Performance & Reliability Audit of NTPC Thermal Power Stations

## 📌 Project Overview
**Sector:** Energy & Power Utilities  
**Institute:** Newton School of Technology  
**Faculty Mentor:** Archit  

This project conducts a comprehensive operational audit of National Thermal Power Corporation (NTPC) stations using a dataset of **7,500 records** spanning **2017–2026**. The analysis reveals a critical efficiency gap where the fleet operates at an average **Daily Capacity Factor (DCF) of 65.9%**, significantly trailing top performers. 

The audit identifies a massive **607,137 MW cumulative outage volume**, translating to a potential revenue loss of over **₹580 Crores**. The project provides a 7-point KPI framework and actionable recommendations to bridge the gap between Monitored and Available Capacity.

### 👥 Team Details (Section-D/G-17)
* **Mansi Agarwal**
* **Aditya Samadhiya**
* **Kapish Rohilla**
* **Deepanshu**
* **Prashant Pandey**
* **Harshit Kudhial**

---

## 📊 KPI Framework & Scorecard
The analysis is anchored on **7 Core KPIs** developed to assess fleet health:

| Metric | Value | Description |
| :--- | :--- | :--- |
| **Total Power Generation** | **49,620.6 MU** | Total energy delivered to the grid. |
| **Avg Daily Capacity Factor** | **65.9%** | Efficiency score (Actual Generation vs. Potential). |
| **Total Outage Volume** | **607,137 MW** | Cumulative capacity lost to technical/maintenance issues. |
| **Monitored Capacity** | **3,033,314 MW** | Theoretical maximum installed capacity. |
| **Available Capacity** | **2,426,176 MW** | Actual capacity ready for generation. |
| **High Capacity Share** | **26.97%** | Fleet reliance on top-performing assets. |
| **Zero Gen Events** | **70** | Critical failure events where units produced 0 MW. |

---

## 📂 Data Dictionary
**Source:** NDAP - Government of India  
**Volume:** 7,500 rows, 16 columns  

| Column | Description |
| :--- | :--- |
| `Station_Clean` | Standardized power station name. |
| `Monitored Capacity` | Total installed capacity (MW). |
| `Available Capacity` | Capacity ready for generation (MW). |
| `Actual Generation` | Energy produced daily (Million Units - MU). |
| `Outage` | Capacity unavailable due to maintenance/faults (MW). |
| `Coal Stock` | Days of fuel inventory available. |
| `Daily_Capacity_Factor` | Calculated KPI: `(Generation / (Monitored * 0.024)) * 100`. |
| `Zero_Gen_Flag` | Categorical flag detecting complete unit failure. |

---

## 🧹 Methodology & Cleaning
The data pipeline was executed entirely in Google Sheets (`RawDataset` -> `Cleaned`):
1.  **Imputation:** Missing `Coal Stock` values were imputed with 0 to maintain calculation integrity.
2.  **Standardization:** Removed underscores from station names and standardized date formats.
3.  **Feature Engineering:** * Created `Capacity_Category` to segment "High" vs "Low" performers.
    * Derived `Zero_Gen_Flag` to isolate the 70 critical failure events.
4.  **Assumptions:** Blank outage values were treated as 0 MW (fully operational).

---

## 💡 Key Insights
1.  **The Efficiency Gap:** There is an **11.8%** performance difference between the "High Capacity" segment and the rest of the fleet.
2.  **Asset Reliance:** Despite their efficiency, "High Capacity" units contribute only **26.97%** of the total generation share.
3.  **Regional Bottleneck:** **Uttar Pradesh** is the primary contributor to the outage volume, showing a disproportionately large "Outage" segment in stacked bar analysis.
4.  **Seasonal Vulnerability:** Generation drops by **~12%** in August, marking the lowest demand/efficiency window.
5.  **Benchmark:** *Talcher (Old) Unit 2* sets the operational standard with a **99.4% DCF**.

---

## 📈 Dashboard Summary
The project includes a dynamic Google Sheets dashboard featuring:

* **Top Line KPI Strip:** Instant view of the 7 core metrics (Gen, DCF, Outage, etc.).
* **Trend Analysis:** Line charts tracking generation growth (2017–2026).
* **Seasonality Analysis:** Bar charts identifying the August dip.
* **State-wise Performance:** **Stacked Bar Chart** comparing Monitored vs. Available Capacity to highlight state-specific inefficiencies.
* **Interactive Slicers:** Filter by Year, Month, State, Station, and Capacity Category.

---

## 🚀 Recommendations & Business Impact

### Proposed Actions
1.  **Performance Turnaround:** Target the bottom 25% "Low Capacity" units for immediate overhaul.
2.  **Technical Task Force:** Deploy a specialist team to **Uttar Pradesh** to address the high outage volume.
3.  **Zero-Gen RCA:** Mandate Root Cause Analysis within 24 hours for any "Zero Generation" event.
4.  **Strategic Maintenance:** Align all major annual overhauls strictly with the **August** low-demand window.

### Estimated Impact
By reducing cumulative outages (607,137 MW) by just **10%**, NTPC can recover **~1,457 Million Units (MU)** of energy. At a rate of ₹40 Lakhs/MU, this translates to:

### **₹582.8 Crores** *Potential Revenue Recovery*

---

## 🔮 Future Scope
* **Predictive ML:** Integration of vibration/sensor data to predict boiler failures before they occur.
* **Logistics Integration:** Incorporating railway supply chain data to model coal stock volatility.

---

## 📜 Repository Structure
* `Power_Generation_Analysis_Report.docx` - Full project report.
* `DVA Capstone - Dashboard.csv` - Dashboard data source.
* `DVA Capstone - clean_data.csv` - The processed dataset used for analysis.
* `DVA Capstone - Calculated_Pivots.csv` - Aggregated data for charts.
