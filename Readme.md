# Operational Efficiency & Power Generation Performance Analysis of NTPC Stations

## 1. Project Overview
**Sector:** Energy & Power Utilities  
**Analysis Period:** 2017–2026  
**Dataset Size:** 7,500 Records  

This project analyzes the power generation efficiency of National Thermal Power Corporation (NTPC) stations. The analysis identifies significant variances in Daily Capacity Factor (DCF) across different power stations, specifically isolating a "Low Capacity" segment that underperforms by approximately 12% compared to high-performing peers. The project aims to provide actionable business intelligence to recover lost revenue opportunities and enhance grid reliability.

### Team Details (Section-D/G-17)
* **Mentor:** Archit (Newton School of Technology)
* **Team Members:**
  * Mansi Agarwal
  * Aditya Samadhiya
  * Kapish Rohilla
  * Deepanshu
  * Prashant Pandey
  * Harshit Kudhial

---

## 2. Data Dictionary
The analysis utilizes a cleaned dataset (`DVA Capstone - clean_data.csv`) derived from raw operational logs.

| Column Name | Description |
| :--- | :--- |
| `Year`, `Month`, `Date` | Temporal attributes of the record. |
| `State_Clean` | Standardized state name where the power station is located. |
| `Station_Clean` | Standardized name of the power station unit. |
| `Monitored` | The monitored capacity of the station (MW). |
| `Available` | The actual available capacity for generation (MW). |
| `Power generation... (Dated)` | Scheduled/Programmed power generation for the date. |
| `Power generation... actual` | Actual power generated on the date. |
| `Outage` | Capacity under outage (MW). Cleaned to handle missing/zero values. |
| `Daily_Capacity_Factor` | **Key KPI:** `(Generation / (Monitored * 0.024)) * 100`. |
| `Zero_Gen_Flag` | Categorical flag (`OK` / `Check`) indicating zero-generation events. |
| `Capacity_Category` | Segmentation of stations into "High Capacity" or "Low Capacity". |

---

## 3. Cleaning Notes
Raw data was transformed to ensure accuracy and consistency:
* **Standardization:** Corrected spelling variations in `State` and `Station` names (e.g., standardizing "Uttar Pradesh" and station unit names).
* **Missing Values:** Imputed missing values in the `Outage` column (assumed zero where not reported).
* **Feature Engineering:**
    * Calculated `Daily_Capacity_Factor` to normalize performance comparisons.
    * Created `Capacity_Category` to segment stations based on performance thresholds.
    * Derived `Zero_Gen_Check_Count` to quantify frequency of zero-generation events.

---

## 4. Key Insights
The analysis yielded three critical insights driving operational strategy:

1.  **Performance Gap:** A distinct divide exists between segments. "High Capacity" stations operate at an average DCF of **79.3%**, whereas "Low Capacity" stations average only **67.5%**, representing a ~12% efficiency gap.
2.  **Outage Impact:** A massive cumulative capacity of **607,138 MW** was reported under outage, translating to an estimated generation loss of ~14,500 Million Units (MU).
3.  **Regional Disparity:** **Uttar Pradesh** serves as a critical bottleneck, recording the highest total outage capacity (~140k MW cumulative), significantly higher than better-performing states like Odisha.

---

## 5. Dashboard Summaries
The project dashboard visualizes these metrics to track station health:

* **Executive Scorecard:** * **Total Outage:** ~607,000 MW (Cumulative)
    * **Avg Daily Capacity Factor:** 65.90%
    * **Total Zero Generation Events:** 70

* **Station Performance Summary:** * Detailed ranking of individual units by efficiency.
    * **Top Performer:** *Talcher (Old) TPS Unit 2* (99.43% DCF).
    * **High Performers:** *Korba STPS Unit 2* (93.44%) and *Singrauli STPS Unit 4* (93.33%).
    * Tracks Monitored vs. Available capacity to pinpoint specific unit failures.

* **Capacity Category Analysis:** * Comparative pivot showing the DCF split (79.32% High vs 67.51% Low).
    * Highlights disproportionate outage volume in the Low Capacity segment (605,988 MW vs 1,148 MW for High Capacity).

* **State-wise Performance:** * Geographic breakdown highlighting high outage rates in Uttar Pradesh compared to consistent performers in other regions.

* **Trend Analysis:** * Time-series views tracking `Daily_Capacity_Factor` (2017–2026) to identify seasonal dips and long-term degradation patterns.
