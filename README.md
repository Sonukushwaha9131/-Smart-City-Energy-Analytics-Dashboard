# ⚡ Smart City Energy Analytics Dashboard

```{=html}
<p align="center">
```
`<b>`{=html}Interactive Excel Dashboard for City-Wide Energy Monitoring,
Cost Analysis & Operational Alerts`</b>`{=html}
```{=html}
</p>
```
```{=html}
<p align="center">
```
`<img src="https://img.shields.io/badge/Excel-Interactive%20Dashboard-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white" alt="Excel">`{=html}
`<img src="https://img.shields.io/badge/Data-1%2C250%20Energy%20Logs-0f766e?style=for-the-badge" alt="Data">`{=html}
`<img src="https://img.shields.io/badge/KPIs-5-2563eb?style=for-the-badge" alt="KPIs">`{=html}
`<img src="https://img.shields.io/badge/Charts-4-f59e0b?style=for-the-badge" alt="Charts">`{=html}
```{=html}
</p>
```

------------------------------------------------------------------------

## 📌 Project Overview

The **Smart City Energy Analytics Dashboard** is an Excel-based
analytics solution designed to monitor electricity consumption,
generation, energy efficiency, operating cost, peak-demand warnings,
temperature conditions, and energy status across a simulated smart-city
environment.

The workbook processes **1,250 energy records** covering:

-   🏙️ **5 city regions**
-   🏢 **5 facility types**
-   ⚡ **5 power sources**
-   📅 **Full-year 2025 activity**
-   📊 **5 KPI cards**
-   📈 **4 dashboard charts**
-   🎛️ **2 interactive slicers**
-   🔎 Pivot-based analytical summaries

The project focuses not only on visualization, but also on **data
validation, formula correction, dynamic totals, slicer resilience, and
executive-level reporting**.

------------------------------------------------------------------------

## 🎯 Business Problem

City energy planners need a reliable way to answer questions such as:

-   How much energy is being consumed vs. generated?
-   Which facilities have the highest energy demand?
-   What is the total city-wide energy cost?
-   Where are peak-demand conditions occurring?
-   Which periods show energy deficits or surpluses?
-   How does temperature relate to operational conditions?
-   Can management filter the dashboard without breaking calculations?

The original workbook contained several formula, reference, formatting,
and dashboard reliability issues. This project corrected those issues
and converted the workbook into a presentation-ready analytical
dashboard.

------------------------------------------------------------------------

## 🖼️ Dashboard Preview

> Add your final dashboard screenshot here as
> `assets/dashboard-preview.png`.

``` text
assets/
└── dashboard-preview.png
```

![Smart City Energy Dashboard](assets/dashboard-preview.png)

------------------------------------------------------------------------

## 📊 Executive KPI Snapshot

  --------------------------------------------------------------------------
  KPI                                 Verified Value Meaning
  --------------------- ---------------------------- -----------------------
  ⚡ Total Energy               **6,244,204.55 kWh** Total electricity
  Consumed                                           demand

  🔋 Total Energy               **4,114,522.02 kWh** Total energy produced
  Generated                                          

  📉 Net Energy Deficit         **2,129,682.53 kWh** Consumption exceeding
                                                     generation

  💰 Total Energy Cost             **₹1,027,065.30** City-wide consumption
                                                     cost

  🎯 Average Efficiency                   **65.65%** Average
                                                     generated-to-consumed
                                                     performance
  --------------------------------------------------------------------------

### Core KPI Formula

**Energy Efficiency**

``` text
Efficiency = Total Generated Energy / Total Consumed Energy
```

For this dataset:

``` text
4,114,522.02 / 6,244,204.55 ≈ 65.88%
```

> Note: the workbook's row-level `Efficiency_Ratio` average is
> approximately **65.65%**. These are different aggregation methods and
> should not be treated as interchangeable.

------------------------------------------------------------------------

## 🔍 Key Insights

### Energy Balance

-   Total consumption is significantly higher than total generation.
-   The city records approximately **2.13 million kWh of net deficit**.
-   **1,028 logs** are classified as `Deficit`.
-   **222 logs** are classified as `Surplus`.

### Peak Demand

-   **198 logs** trigger a peak-warning condition.
-   **1,052 logs** remain within the normal warning state.
-   These alerts can be used to identify periods requiring operational
    attention.

### Temperature Profile

The corrected temperature classification contains:

  Temperature Tier             Logs
  -------------------------- ------
  🔥 HOT (≥30°C)                202
  🌤️ MODERATE (15--29.9°C)      812
  ❄️ COLD (\<15°C)              236

### Regional Coverage

  Region             Records
  ---------------- ---------
  South District         267
  East District          260
  Central Hub            250
  North District         241
  West District          232

### Facility Coverage

  Facility                Records
  --------------------- ---------
  Educational Campus          259
  Residential Complex         258
  Corporate Office            251
  Medical Center              247
  Industrial Park             235

------------------------------------------------------------------------

## 📈 Dashboard Components

### 1. KPI Cards

The executive header presents the most important metrics at a glance:

-   Total Energy Consumed
-   Total Energy Generated
-   Net Energy Balance / Deficit
-   Total Energy Cost
-   Efficiency

### 2. Energy Volume Analysis

Compares consumption and generation to expose demand-generation gaps.

### 3. Energy Status

Shows the distribution of `Deficit` vs. `Surplus` records.

### 4. Regional / Facility Analysis

Provides comparative analysis across city regions and facility
categories.

### 5. Consumption Trend

Displays the time-series movement of energy consumption across the 2025
reporting period.

### 6. Interactive Filters

Slicers allow the dashboard to be explored dynamically without manually
editing formulas.

------------------------------------------------------------------------

## 🧮 Data & Calculations

### Main Dataset Fields

  Field                      Description
  -------------------------- ----------------------------------
  `Transaction_ID`           Unique energy log identifier
  `Log_Timestamp`            Date and time of the measurement
  `City_Region`              City district / region
  `Facility_Type`            Type of consuming facility
  `Power_Source`             Energy source
  `Avg_Temp_C`               Average temperature in Celsius
  `Consumed_kWh`             Energy consumed
  `Generated_kWh`            Energy generated
  `Unit_Cost`                Cost per kWh
  `Peak_Warning`             Peak-demand warning flag
  `Net_Energy_kWh`           Consumption minus generation
  `Energy_Status`            Deficit / Surplus classification
  `Total_Consumption_Cost`   Transaction-level energy cost
  `Efficiency_Ratio`         Generated / Consumed ratio
  `Log_Date`                 Date extracted for analysis
  `Log_HOUR`                 Hour extracted from timestamp
  `Shift_Time`               Morning / Afternoon / Night
  `Temperature_Category`     Hot / Moderate / Cold
  `Critical_Alert`           Normal / Action required

### Important Calculations

``` text
Net Energy
= Consumed_kWh - Generated_kWh
```

``` text
Energy Cost
= Consumed_kWh × Unit_Cost
```

``` text
Efficiency Ratio
= Generated_kWh / Consumed_kWh
```

``` text
Energy Status
= IF(Net_Energy_kWh < 0, "Surplus", "Deficit")
```

``` text
Peak Alert
= Based on the workbook's Peak_Warning condition
```

------------------------------------------------------------------------

## 🛠️ Technical Audit & Improvements

One of the strongest parts of this project is the **technical correction
work** performed on the original workbook.

### 01 --- Energy Cost Inflation Bug

**Problem:**\
The dashboard originally produced an impossible total energy cost
because total consumption was multiplied by the sum of all unit rates.

**Correction:**\
The calculation was changed to use the actual transaction-level cost
total and filter-aware subtotal logic.

**Verified result:**

``` text
₹1,027,065.30
```

------------------------------------------------------------------------

### 02 --- Temperature Classification Error

**Problem:**\
The temperature category formula referenced the previous/header row
instead of the current record, causing incorrect temperature labels.

**Correction:**\
The calculation was replaced with a structured table reference using the
current row's `Avg_Temp_C`.

**Result:**

``` text
HOT       = 202
MODERATE  = 812
COLD      = 236
```

------------------------------------------------------------------------

### 03 --- Peak Alert Text Standardization

**Problem:**\
High-load records contained inconsistent alert text such as:

``` text
Action requried
```

**Correction:**

``` text
Action required
```

The corrected label is now consistent across the dataset and analytical
outputs.

------------------------------------------------------------------------

### 04 --- Dynamic Totals

The workbook was upgraded so important totals respond correctly to
filtering.

Key dynamic measures include:

-   Consumed Energy
-   Generated Energy
-   Net Energy
-   Total Cost

This makes the dashboard more reliable when slicers are used.

------------------------------------------------------------------------

### 05 --- Slicer Resilience

**Problem:**\
Certain slicer selections could cause dashboard formulas to return
`#REF!`.

**Correction:**\
Error-safe logic was introduced so filtered states remain stable.

------------------------------------------------------------------------

### 06 --- Date Axis Correction

**Problem:**\
The consumption trend chart could display raw Excel serial numbers
instead of readable dates.

**Correction:**\
The date field and chart axis were standardized to calendar-date
formatting.

**Expected display:**

``` text
01-01-25 → 12-31-25
```

------------------------------------------------------------------------

### 07 --- Dashboard Presentation Cleanup

Additional improvements included:

-   Corrected dashboard title typos
-   Standardized chart titles
-   Improved totals-row behavior
-   Corrected freeze-pane positioning
-   Preserved PivotTables and Slicers
-   Verified KPI and chart outputs

------------------------------------------------------------------------

## 🗂️ Workbook Structure

``` text
Smart_City_Energy_Log.xlsx
│
├── Dataset
│   ├── Raw energy records
│   ├── Calculated columns
│   ├── Alerts
│   └── Energy classifications
│
├── 02_Pivot_Calculations
│   ├── Pivot summaries
│   ├── Facility analysis
│   ├── Energy totals
│   └── Dashboard support calculations
│
├── 03_Main_Dashboard
│   ├── KPI Cards
│   ├── Charts
│   ├── Slicers
│   └── Executive summary
│
└── Problem Statement
    ├── Identified issues
    ├── Technical fixes
    └── Verified outcomes
```

------------------------------------------------------------------------

## 🧰 Tools & Technologies

  Tool                         Purpose
  ---------------------------- -------------------------------------------
  **Microsoft Excel**          Data processing and dashboard development
  **Excel Tables**             Structured data and dynamic calculations
  **PivotTables**              Aggregation and analytical summaries
  **PivotCharts**              Interactive visual analysis
  **Slicers**                  Interactive filtering
  **Excel Formulas**           KPI and calculated-column logic
  **Conditional Formatting**   Alert and status visualization

------------------------------------------------------------------------

## 🔄 Project Workflow

``` text
Raw Energy Logs
      ↓
Data Validation
      ↓
Calculated Columns
      ↓
Formula & Reference Audit
      ↓
Pivot Calculations
      ↓
KPI Development
      ↓
Charts & Slicers
      ↓
Dashboard Validation
      ↓
Executive Energy Dashboard
```

------------------------------------------------------------------------

## 🚀 How to Use

### 1. Download the workbook

Open:

``` text
Smart_City_Energy_Log.xlsx
```

### 2. Start with the Dataset sheet

Review:

-   Energy consumption
-   Energy generation
-   Facility
-   Region
-   Power source
-   Temperature
-   Cost
-   Alerts

### 3. Explore Pivot Calculations

Open:

``` text
02_Pivot_Calculations
```

Use this sheet to understand the analytical summaries behind the
dashboard.

### 4. Open the Dashboard

Navigate to:

``` text
03_Main_Dashboard
```

Use the available slicers to filter the dashboard and observe how the
KPIs and charts respond.

### 5. Validate the results

Check that:

-   KPI totals remain logical
-   Charts display readable dates
-   Filters do not create formula errors
-   Alert labels remain standardized
-   Cost totals remain accurate

------------------------------------------------------------------------

## 📌 Recommended GitHub Repository Structure

``` text
Smart-City-Energy-Analytics/
│
├── README.md
├── Smart_City_Energy_Log.xlsx
│
├── assets/
│   ├── dashboard-preview.png
│   ├── kpi-preview.png
│   └── workflow.png
│
├── documentation/
│   ├── project-report.pdf
│   └── data-dictionary.md
│
└── screenshots/
    ├── dashboard.png
    ├── pivot-analysis.png
    └── dataset.png
```

------------------------------------------------------------------------

## 🌟 Project Highlights

-   ✅ 1,250 validated energy logs
-   ✅ 5 city regions
-   ✅ 5 facility categories
-   ✅ 5 energy sources
-   ✅ 5 executive KPIs
-   ✅ 4 dashboard charts
-   ✅ 2 interactive slicers
-   ✅ Dynamic filter-aware totals
-   ✅ Corrected energy-cost calculation
-   ✅ Corrected temperature classification
-   ✅ Standardized operational alerts
-   ✅ Date-axis correction
-   ✅ Slicer error resilience
-   ✅ Executive-ready Excel dashboard

------------------------------------------------------------------------

## 💡 Future Enhancements

The project can be extended beyond Excel with:

-   🌐 Power BI implementation
-   🐍 Python-based automated data cleaning
-   🗄️ SQL database integration
-   ☁️ Cloud-hosted energy monitoring
-   📡 Real-time IoT energy readings
-   🤖 Energy-demand forecasting
-   🚨 Automated anomaly detection
-   📊 Predictive peak-load alerts
-   💰 Cost optimization recommendations
-   🏙️ District-level energy benchmarking

------------------------------------------------------------------------

## 👨‍💻 Author

**Smart City Energy Analytics Project**

> Built as an end-to-end data analytics and dashboarding project focused
> on transforming raw energy logs into reliable, decision-ready
> insights.

------------------------------------------------------------------------

## ⭐ Support the Project

If this project helped you understand Excel analytics, KPI design,
PivotTables, dashboard development, or data-quality correction:

**⭐ Star the repository and feel free to explore, improve, and reuse
the project.**

------------------------------------------------------------------------

```{=html}
<p align="center">
```
`<b>`{=html}⚡ Turning Energy Data into Smarter City
Decisions`</b>`{=html}
```{=html}
</p>
```
