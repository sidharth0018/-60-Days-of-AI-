# 🚙 Fuel Analytics Dashboard

An AI-generated interactive dashboard created using Claude AI to analyze fuel economics, emissions, maintenance costs, and E85 viability for a Mahindra Bolero 2021 BS6 Diesel vehicle.

## Overview

This dashboard was generated from a custom prompt that instructed Claude AI to:

- Read a CSV dataset
- Calculate fuel-wise analytics
- Compare Diesel, Petrol, E85, CNG, and EV
- Compute emissions and maintenance metrics
- Analyze E85 fuel economics
- Generate a complete responsive dashboard in pure HTML/CSS/JS

## Vehicle Details

| Parameter | Value |
|------------|---------|
| Vehicle | Mahindra Bolero 2021 (BS6) |
| Fuel | Diesel |
| Usage | Mixed |
| Age | 4.5 Years |
| Monthly Running | 400–500 KM |

## Metrics Computed

### Fuel-wise Analysis

- Average Cost per KM
- Average CO₂ Emission per KM
- Average Maintenance Cost per KM
- Average Refuel/Recharging Time

### Age-Based Analysis

Vehicle grouped into:

- New (0–2 Years)
- Mid-life (3–5 Years)
- Aged (6–9 Years)
- Old (10+ Years)

Metrics:

- Cost/KM
- Maintenance/KM

### E85 Paradox Analysis

Calculated:

- Pump Savings %
- Running Penalty %
- Break-even Fuel Price

### E85 Score

Scoring Model:

| Factor | Weight |
|----------|----------|
| Cost | 4 Points |
| CO₂ | 3 Points |
| Refuel Time | 2 Points |
| Maintenance | 1 Point |

Total Score = 10

## Dashboard Features

### KPI Cards

- Diesel Cost/KM
- E85 Cost/KM
- E85 Running Penalty
- Break-even Price
- Monthly Fuel Cost

### SVG Visualizations

- Bar Chart (Cost/KM)
- Doughnut Chart (CO₂/KM)
- Line Chart (Cost vs Vehicle Age)
- Animated E85 Gauge Score

### Fuel Recommendation Cards

For every fuel type:

- Pros
- Cons
- Best Use Case

## Tech Stack

- HTML5
- CSS3
- Vanilla JavaScript
- SVG Charts
- Glassmorphism UI

No external libraries or CDNs used.

## Screenshot

Add a screenshot inside:

screenshots/dashboard-preview.png

## How to Run

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/fuel-analytics-dashboard.git
```

Open:

```bash
fuel_dashboard.html
```

in any modern browser.

## AI Prompt Used

This project was generated using Claude AI with a structured prompt focused on vehicle fuel economics and E85 feasibility analysis.

## Author

Sidharth Kumar

B.Tech ECE | ABES Engineering College

GitHub: https://github.com/sidharth0018

LinkedIn: https://www.linkedin.com/in/sidharth-kumar-501768287

---

Part of the **60 Days Claude AI Challenge by AB Talks**
