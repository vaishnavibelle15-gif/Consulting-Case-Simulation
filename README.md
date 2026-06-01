# Profitability Improvement Strategy — Zomato Food Delivery

> **Consulting Case Simulation** | Data Analytics & Business Strategy Portfolio Project

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://python.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen)]()

---

##  Business Problem

**"Orders grew +25% YoY, but profits declined by 12%."**

As a consultant hired by a food delivery startup (modeled on Zomato), I was tasked with:

- Diagnosing **WHY profits are falling** despite revenue growth
- Identifying **WHERE cost inefficiencies** exist across cities and segments
- Recommending **HOW to restore and improve profitability**

---

##  Project Objectives

| # | Objective |
|---|-----------|
| 1 | Analyze revenue and cost structure across 10 Indian cities |
| 2 | Identify loss-making areas (cities, customer segments, discount bands) |
| 3 | Study customer behavior and segmentation (Budget / Regular / Premium) |
| 4 | Evaluate delivery efficiency and SLA performance |
| 5 | Deliver data-backed profitability recommendations |

---

# Project Structure

```
Consulting-Case-Simulation/
│
├── data/
│   ├── zomato_consulting_dataset.csv   ← 5,000 order records (synthetic)
│   └── dashboard_data.json            ← Aggregated KPIs for dashboard
│
├── analysis/
│   └── 01_business_analysis.py        ← Full Python analysis script
│
├── dashboard/
│   └── index.html                     ← Interactive 5-page consulting dashboard
│
├── report/
│   └── (charts auto-saved here when analysis.py is run)
│
└── README.md
```

---

 Key Findings

1. Discount Spiral — Root Cause of Profit Decline
- Avg discount grew from **15% (Jan)** → **35.9% (Dec)**
- Orders with **>35% discount** have only **28.7% profit margin** vs 61.2% at low discounts
- Discount cost now represents **~35% of total revenue** — unsustainable

2. Tier-1 City Delivery Cost Inefficiency
- Mumbai avg delivery cost: **₹79/order** vs ₹51 in Jaipur (55% higher)
- 75% of Mumbai & Delhi orders **exceed the 38-minute SLA**
- Higher delivery time directly correlates with lower ratings (r = −0.82)

3. Premium Customers Are Underserved
- Premium segment: **2.3× higher profit/order** than Budget
- Premium repeat rate: **65%** vs Budget's 25%
- Only **20% of order volume** comes from this highly profitable segment

4. Tier-2 Cities Show Better Unit Economics
- Jaipur, Surat, Ahmedabad: **57–61% profit margins**
- Mumbai, Delhi: **47–50% margins** due to cost pressure
- Strategic opportunity: Tier-2 city expansion

---

# Dashboard

Open `dashboard/index.html` in any browser for the interactive 5-page dashboard:

| Page | Content |
|------|---------|
| Executive Overview | KPIs, trend alerts, city summary |
| Profitability Analysis | City margins, discount impact matrix |
| Operations | Delivery time by city, SLA tracking |
| Customer Segments | Budget / Regular / Premium breakdown |
| Strategy & Recommendations | 4 action plans + SWOT + Porter's 5 Forces |

---

# Strategic Recommendations

| Priority | Action | Expected Impact |
|----------|--------|----------------|
| 🔴 Urgent | Cap discounts at 25% max | +8–12% margin uplift |
| 🟡 High | Optimize Mumbai/Delhi delivery zones | −18% delivery cost |
| 🟢 Growth | Invest in Premium customer retention | 2.3× profit multiplier |
| 🔵 Strategic | Expand in Jaipur, Surat, Ahmedabad | +18% margin advantage |

---

##  How to Run

```bash
# 1. Clone the repo
git clone https://github.com/yourusername/Consulting-Case-Simulation.git
cd Consulting-Case-Simulation

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn faker

# 3. Run analysis
cd analysis
python 01_business_analysis.py

# 4. Open dashboard
open dashboard/index.html   # macOS
# or just double-click index.html in your browser
```

---

 Tech Stack

| Tool | Purpose |
|------|---------|
| Python (Pandas, NumPy) | Data wrangling & KPI computation |
| Matplotlib / Seaborn | Static chart generation |
| HTML / Chart.js | Interactive web dashboard |
| Faker | Synthetic dataset generation |

---

 Consulting Frameworks Applied

- **SWOT Analysis** — Strategic situation mapping
- **Porter's Five Forces** — Competitive intensity assessment
- **Unit Economics Analysis** — Revenue / Cost / Margin per order
- **Customer Segmentation** — RFM-style segment profitability
- **Sensitivity Analysis** — Discount impact on margins

---

 About This Project

This is a **consulting case simulation** built as part of a data analytics portfolio.  
It demonstrates business problem-solving, end-to-end analysis, and data storytelling skills — modeled after real consulting engagements.

**Dataset Note:** The dataset is synthetically generated to reflect realistic food delivery business dynamics (not actual Zomato data).

---


