# 📊 SI&OP Executive Forecasting & Variance Console

A comprehensive **Power BI dashboard** developed as part of the **Smith+Nephew SI&OP Reporting Case Study** to analyze forecast snapshots, evaluate forecast performance, and provide executive-level insights into Revenue, Non-Revenue, and CAPEX planning.

---

## 🚀 Project Overview

In **Sales, Inventory & Operations Planning (SI&OP)**, forecasts are generated periodically and stored as monthly snapshots. Business stakeholders often need to compare forecasts from different snapshots to understand how planning assumptions evolve over time.

This project transforms multiple forecast snapshots into a scalable reporting model and provides an interactive executive dashboard for analyzing forecast trends, variance, accuracy, and bias.

---

## 🎯 Business Objective

The primary objectives of this project are:

- Compare forecast values across multiple snapshot periods.
- Track forecast evolution over time.
- Measure forecast performance against actual sales.
- Analyze Revenue, Non-Revenue, and CAPEX forecasts.
- Enable dynamic comparison using Lag-based selections.
- Deliver executive-ready insights through interactive dashboards.

---

## 📌 Business Scenario

Forecasts are generated every month and stored as snapshots.

Example:

| Snapshot Period | Label |
|----------------|-------|
| Latest Snapshot (2023 P12) | Resultant |
| Previous Snapshot (2023 P11) | Lag 0 |
| Snapshot Before Previous (2023 P10) | Lag 1 |

For each future forecast period, the dashboard displays values from different snapshots side-by-side.

Example:

| Country | Period | Resultant Revenue | Lag 0 Revenue | Lag 1 Revenue |
|----------|--------|------------------|--------------|--------------|
| USA | 2024 P01 | 120,000 | 115,000 | 110,000 |

---

# 🏗️ Data Transformation Process

The data transformation layer was built using **Power Query**.

### Key Transformation Steps

✔️ Identified latest forecast snapshot.

✔️ Classified forecast versions into:

- Resultant
- Lag 0
- Lag 1

✔️ Pivoted forecast measures into dedicated columns.

✔️ Created snapshot comparison structure.

✔️ Merged Actual Sales data using:

- Period
- Item
- Country

✔️ Built a scalable data model for future snapshot additions.

---

## 🔄 Data Model

The final dataset integrates:

### Forecast Data

- Revenue Forecast
- Non-Revenue Forecast
- CAPEX Forecast

### Actual Data

- Actual Sales Quantity

### Dimensions

- Country
- Period
- Item
- As-Of Period

---

# 📐 KPI Calculations

## 1️⃣ Forecast Accuracy %

Measures how close forecasted quantities are to actual sales.

### Formula

```text
Forecast Accuracy % =
1 - ABS((Forecast Qty - Actual Qty) / Actual Qty)
```

### DAX

```DAX
Forecast Accuracy % =
1 - ABS(
    DIVIDE(
        [Forecast Qty] - [Actual Qty],
        [Actual Qty]
    )
)
```

---

## 2️⃣ Forecast Bias %

Measures whether forecasts are consistently overestimating or underestimating demand.

### Formula

```text
Forecast Bias % =
(Forecast Qty - Actual Qty) / Actual Qty
```

### DAX

```DAX
Forecast Bias % =
DIVIDE(
    [Forecast Qty] - [Actual Qty],
    [Actual Qty]
)
```

---

# 📊 Dashboard Features

The dashboard provides an executive view of SI&OP performance through the following analyses:

### Executive KPIs

- Total Actual Quantity
- Selected Lag Forecast Quantity
- Forecast Accuracy %
- Forecast Bias %

### Country-Level Forecast Analysis

- Revenue Forecast
- Non-Revenue Forecast
- CAPEX Forecast

### Snapshot Trend Analysis

- Forecast Quantity Trend
- Actual Quantity Trend
- Forecast Accuracy Trend

### Variance Analysis

- Forecast Variance Drivers
- Country Contribution Analysis

### Detailed Performance Matrix

Provides detailed comparison at:

- Country level
- Product level
- Snapshot level

---

# 🎛️ Interactive Features

## Dynamic Lag Selection

Users can dynamically switch between:

- Resultant
- Lag 0
- Lag 1

Based on the selected lag, all visuals automatically update.

Example:

Selecting **Lag 0** displays:

- Lag 0 Revenue Forecast
- Lag 0 Non-Revenue Forecast
- Lag 0 CAPEX Forecast

---

## Available Filters

- As-Of Period
- Lag Selection
- Country
  
---

# 💡 Key Business Insights

This dashboard helps answer questions such as:

- Which countries have the highest forecast accuracy?
- How do forecast snapshots evolve over time?
- Is the business consistently overforecasting or underforecasting?
- Which regions contribute the highest revenue?
- How much variance exists between forecast and actual demand?
- Which snapshot provides the most reliable forecast?

---

# 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| Power BI Desktop | Dashboard Development |
| Power Query | Data Transformation |
| DAX | KPI Calculations |
| Excel/CSV | Data Source |
| Data Modeling | Relationship Management |

---

# 📂 Repository Structure

```bash
Smith-Nephew/
│
├── Smith & Nephew Assignment.pbix
├── README.md
```

---

# ⚙️ How to Run

## Prerequisites

- Microsoft Power BI Desktop

Download Power BI Desktop:

https://powerbi.microsoft.com/desktop/

---

## Steps

### 1. Clone the repository

```bash
git clone https://github.com/KushalZanzari/Smith-Nephew.git
```

### 2. Open the project

Open:

```text
Smith & Nephew Assignment.pbix
```

### 3. Refresh Data

Click:

```text
Home → Refresh
```

if data source paths need to be updated.

---

# 🔮 Future Enhancements

- Drill-through analysis.
- Forecast anomaly detection.
- Scenario simulation analysis.
- Automated refresh pipeline.
- Time intelligence reporting.
- Predictive forecasting integration.

---
