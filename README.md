# 🏥 Disease & Symptoms Analytics Dashboard

Interactive analytics dashboard built in Python that mirrors a full Power BI workflow.

## Dataset
- 773 unique diseases · 377 symptoms · ~246,000 rows
- Source: [Kaggle — dhivyeshrk/diseases-and-symptoms-dataset](https://www.kaggle.com/datasets/dhivyeshrk/diseases-and-symptoms-dataset)

## Features Covered
- Power Query-style transforms (unpivot, merge, conditional column)
- Star schema data modelling
- DAX-equivalent measures (RANKX, CALCULATE, % of Total)
- 7 interactive Plotly charts: KPI cards, bar, donut, heatmap, scatter, treemap
- Drill-through and slicer simulation
- Full dashboard layout + HTML export

## Tech Stack
Python · Pandas · Plotly · KaggleHub · Jupyter Notebook

## How to Run
```bash
pip install kagglehub[pandas-datasets] plotly pandas numpy
jupyter notebook Disease_Dashboard_PowerBI_Style.ipynb
```

## Live Dashboard
Open `disease_dashboard_FULL.html` in any browser — no Python needed.
