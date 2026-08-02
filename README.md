# Food Rescue Operational & Donor Intelligence Dashboard

An end-to-end **Power BI Analytics Solution** designed to track, analyze, and optimize regional food rescue operations. This dashboard provides executive stakeholders and logistics managers with real-time operational KPIs, dynamic donor concentration analysis, multi-year volume trends, and food category distribution insights.

---

## 📌 Executive Summary
Food insecurity and supply chain waste require data-driven intervention. This Power BI report consolidates donor metrics, rescue logistics, and inventory distributions into an interactive analytical suite. 

Key operational achievements tracked:
* **28.93 Million Pounds** of total food volume rescued.
* **59.43 Thousand** discrete rescue collection operations.
* **59 Thousand** active donors participating across regional networks.
* **6.92 Thousand** registered volunteer hours enabling distribution.

---

## 🛠 Analytics Architecture & Features

### 1. Executive KPI Header Bar
* High-impact summary cards providing instant macro-level insights across core operational metrics (*Total Rescues, Total Pounds Rescued, Total Boxes, Total Donors, Total Volunteers*).

### 2. Dynamic Top N Donor Concentration Treemap
* **DAX Parameter Integration**: Interactive Numeric Range Slider allowing dynamic filtering from Top 1 to Top 50 donors.
* **Pareto / Risk Analysis**: Visualizes supply concentration, identifying key donor dependencies (e.g., *Farmlink, One Gen Away, Forestwood Farms*).
* **Enhanced Tooltips**: Comprehensive hover cards detailing precise donor ranking, exact poundage, and full organizational names without visual truncation.

### 3. Food Category Breakdown
* Proportionate distribution analysis highlighting key food categories:
  * **Produce**: 36.05% (10.43M lbs) — Largest volume share.
  * **Baked Goods**: 13.79% (3.99M lbs)
  * **Beverages**: 15.20% (4.40M lbs)
  * **Meat & Dairy**: Remaining high-protein yield volume.

### 4. Multi-Year Growth & Temporal Velocity
* Annual collection trajectory tracking volume acceleration across historic collection windows (2024–2026), highlighting peak growth periods and operational shifts.

---

## 📐 DAX Calculations & Parameter Modeling

### Dynamic Top N Donor Filter
```dax
DEFINE
    MEASURE 'Top 25 Donor Summary (3)'[Dynamic Top Donors] = 
        VAR SelectedTopN = COALESCE([Top N Donors Value], 25)
        RETURN
            IF(
                SELECTEDVALUE('Top 25 Donor Summary (3)'[Rank]) <= SelectedTopN, 
                AVERAGE('Top 25 Donor Summary (3)'[Total Pounds]), 
                BLANK()
            )
```

---

## 🚀 Getting Started

### Prerequisites
* **Power BI Desktop** (Version: 2024 or later recommended)
* Dataset Connections: PostgreSQL / DirectQuery or CSV Data Model

### Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/food-rescue-dashboard.git
   ```
2. Open `Food_Rescue_Dashboard.pbip` or `.pbix` in Power BI Desktop.
3. Refresh data connections or update local dataset paths under `Transform Data` -> `Data Source Settings`.

---

## 👥 Stakeholders & Impact
* **Operations Team**: Optimizes driver routing and volunteer scheduling based on category volume peaks.
* **Donor Relations**: Identifies high-value donor partners and addresses donor retention risks.
* **Community Leadership**: Quantifies environmental impact and regional hunger relief metrics.
