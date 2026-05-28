# UAC Care Transition Efficiency & Placement Outcome Analytics

## Project Overview

A Streamlit-based analytics dashboard for the HHS Unaccompanied Alien Children (UAC) Program, 
reframing the dataset from capacity monitoring to process efficiency and outcome evaluation.

## Project Structure

```
uac_dashboard/
├── app.py              ← Main Streamlit dashboard
├── data.csv            ← HHS UAC Program dataset
├── requirements.txt    ← Python dependencies
└── README.md
```

## Features

### Dashboard Modules
- **Care Pipeline Flow** — Volume trends + Sankey diagram of CBP→HHS→Sponsor flow
- **Transfer & Discharge Efficiency** — Ratio-based KPI panels with 30-day moving averages
- **Backlog & Bottleneck Detection** — Inflow vs exit comparison with alert thresholds
- **Temporal Pattern Analysis** — Monthly trends, weekday vs weekend, year-over-year
- **Outcome Stability** — Discharge variability and consistency scoring
- **Pipeline Throughput** — Overall system equilibrium tracking

### KPIs Computed
| KPI | Formula |
|-----|---------|
| Transfer Efficiency Ratio | CBP Transferred ÷ CBP In Custody |
| Discharge Effectiveness Index | HHS Discharged ÷ HHS In Care |
| Pipeline Throughput Rate | Total Exits ÷ Total Entries |
| Backlog Ratio | HHS In Care ÷ Daily Discharges |
| Outcome Stability Score | 1 − (Rolling Std ÷ Rolling Mean) |

## How to Run

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Launch the dashboard
streamlit run app.py
```

The app will open at `http://localhost:8501`

## Data Columns

| Column | Description |
|--------|-------------|
| Date | Reporting date |
| Children apprehended and placed in CBP custody | Daily intake volume |
| Children in CBP custody | Active CBP care load |
| Children transferred out of CBP custody | Flow into HHS system |
| Children in HHS Care | Active HHS care load |
| Children discharged from HHS Care | Successful sponsor placements |

## Sidebar Controls

- **Date Range** — Filter all charts to any date window
- **Alert Thresholds** — Customizable visual alert levels for each KPI
- **Display Options** — Toggle 30-day moving averages, weekday analysis

## Deliverables

- ✅ Streamlit Dashboard (`app.py`)
- 📄 Research paper / EDA — extend from this dashboard's analysis
- 📋 Executive Summary — use KPI summaries and bottleneck findings
