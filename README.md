# 🏥 Disease & Symptoms Analytics Dashboard
### A Full Power BI–Style Dashboard Built in Python

![Full Dashboard](docs/full_dashboard.png)

---

## 📌 Project Overview

An end-to-end interactive analytics dashboard that **mirrors every major Power BI workflow** — built entirely in Python using Pandas and Plotly.

| 🔢 Stat | Value |
|---|---|
| 🦠 Unique Diseases | **773** |
| 🤒 Unique Symptoms | **377** |
| 📋 Total Records | **~246,000 rows** |
| 📊 Charts Built | **7 interactive visuals** |
| 🧰 Tech Stack | Python · Pandas · Plotly · KaggleHub · Jupyter |

---

## ⚡ Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/caroline-2204/disease-symptoms-powerbi-dashboard.git
cd disease-symptoms-powerbi-dashboard

# 2. Install dependencies
pip install kagglehub[pandas-datasets] plotly pandas numpy

# 3. Run the notebook
jupyter notebook Disease_Dashboard_PowerBI_Style.ipynb

# OR open the pre-built dashboard instantly (no Python needed)
open disease_dashboard_FULL.html
```

---

## 🗺️ Power BI Features → Python Equivalents

| Power BI Feature | Python Implementation |
|---|---|
| Get Data / Power Query | `kagglehub.load_dataset` + `pandas` |
| Unpivot Columns | `pd.melt()` |
| Merge Queries | `pd.merge()` |
| Conditional Column | `pd.cut()` / lambda function |
| Star Schema (Model View) | Separate `fact`, `dim_disease`, `dim_symptom` DataFrames |
| COUNTROWS / DISTINCTCOUNT | `len()` / `.nunique()` |
| CALCULATE / ALL | `groupby + agg` with full-scope variables |
| RANKX | `.rank(method="dense", ascending=False)` |
| DIVIDE (% of Total) | `value / total * 100` |
| Card Visual | `go.Indicator` |
| Bar Chart + Top N | `go.Bar` + `.head(10)` |
| Donut Chart | `go.Pie(hole=0.55)` |
| Matrix + Heatmap | `go.Heatmap` with `pivot()` |
| Scatter / Bubble Chart | `px.scatter(size=...)` |
| Treemap | `px.treemap` |
| Drill-Through Page | Filtered sub-dashboard function |
| Slicers | Python variable-based filtering |
| Full Report Layout | `make_subplots` |
| Publish / Share | `.write_html()` — zero dependencies |

---

## 📊 Dashboard Visuals

### 🏆 Top 10 Most Common Diseases
> Bar chart showing disease occurrence ranked by row count — equivalent to Power BI's Top N filter with RANKX measure.

![Top 10 Diseases](docs/top10_diseases.png)

---

### 🩺 Severity Category Distribution
> Donut chart splitting all records by Mild / Moderate / Critical severity — built from a Conditional Column transformation.

![Severity Donut](docs/severity_donut.png)

---

### 💊 Top 20 Most Frequent Symptoms (Coloured by Severity)
> Horizontal bar chart with a continuous colour scale mapped to average severity score per symptom — equivalent to Power BI conditional formatting.

![Top 20 Symptoms](docs/top20_symptoms.png)

---

### 🔥 Symptom Frequency Heatmap — Disease × Position
> Matrix visual showing how often each symptom position appears per disease. Colour intensity = frequency — equivalent to Power BI's Matrix visual with heatmap conditional formatting.

![Heatmap Matrix](docs/heatmap_matrix.png)

---

### ⚠️ Disease Risk Matrix — Frequency vs Severity
> Bubble scatter plot: X = average severity, Y = occurrence count, bubble size = symptom diversity. Equivalent to Power BI's Scatter/Bubble chart with play axis.

![Risk Scatter](docs/risk_scatter.png)

---

### 🗺️ Disease Treemap — Occurrence & Severity
> Treemap where tile size = disease frequency and colour = average severity. Equivalent to Power BI's Treemap visual.

![Treemap](docs/treemap.png)

---

## 🗂️ Repository Structure

```
disease-symptoms-powerbi-dashboard/
│
├── Disease_Dashboard_PowerBI_Style.ipynb   # Main notebook (16 steps)
├── disease_dashboard_FULL.html             # Full interactive dashboard (open in browser)
│
├── chart_top10_diseases.html               # Individual interactive charts
├── chart_severity_donut.html
├── chart_top20_symptoms.html
├── chart_heatmap_matrix.html
├── chart_risk_scatter.html
├── chart_treemap.html
│
├── docs/                                   # README preview images
│   ├── full_dashboard.png
│   ├── top10_diseases.png
│   ├── severity_donut.png
│   ├── top20_symptoms.png
│   ├── heatmap_matrix.png
│   ├── risk_scatter.png
│   └── treemap.png
│
└── README.md
```

---

## 🔎 Notebook Steps (16 Steps)

| Step | Description |
|---|---|
| 0 | Install & import libraries |
| 1 | Load dataset via KaggleHub |
| 2 | Initial exploration (shape, nulls, dtypes) |
| 3 | Power Query transforms — trim, clean, **unpivot** symptom columns |
| 4 | Merge severity lookup + Conditional Column (Mild/Moderate/Critical) |
| 5 | Build Star Schema (Fact + 2 Dimension tables) |
| 6 | DAX-style measures: RANKX, % of Total, CALCULATE/ALL |
| 7 | KPI Cards (4 indicators) |
| 8 | Top 10 Diseases bar chart |
| 9 | Severity donut chart |
| 10 | Top 20 Symptoms coloured bar chart |
| 11 | Heatmap matrix (Disease × Symptom Position) |
| 12 | Risk scatter bubble chart |
| 13 | Treemap — top 25 diseases |
| 14 | **Drill-Through simulation** — change 1 variable to explore any disease |
| 15 | **Slicer simulation** — filter all visuals by severity/symptom |
| 16 | Full combined dashboard + HTML export |

---

## 📦 Dataset

- **Source:** [Kaggle — dhivyeshrk/diseases-and-symptoms-dataset](https://www.kaggle.com/datasets/dhivyeshrk/diseases-and-symptoms-dataset)
- **Description:** 773 diseases × 377 symptoms, artificially generated preserving Symptom Severity and Disease Occurrence Probability
- **Key insight:** A disease with only ONE symptom in a row implies very high correlation between that symptom and the disease

---

## 👩‍💻 Author

**Caroline** — MSc Advanced Data Science & AI, University of Liverpool  
🔗 [GitHub](https://github.com/caroline-2204)

---

*All charts are fully interactive in the HTML exports — hover, zoom, click legend items to filter.*
