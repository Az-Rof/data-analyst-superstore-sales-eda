# Superstore Sales EDA

Exploratory Data Analysis (EDA) on the [Superstore Sales Forecasting](https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting) dataset — 9,800 transactions (2015–2018, USD 2.26M) — covering data quality checks, feature engineering, statistical profiling, and 10+ visualizations. Outputs a text report and aggregated CSV tables automatically.

## Stack

Python · Pandas · NumPy · Matplotlib · Seaborn · kagglehub · Jupyter Notebook

## Quick start

```bash
git clone https://github.com/Az-Rof/superstore-eda.git
cd superstore-eda
python -m venv .venv
.venv\Scripts\activate        # Windows; macOS/Linux: source .venv/bin/activate
pip install pandas numpy matplotlib seaborn kagglehub
python eda_superstore.py
```

`train.csv` is downloaded automatically from Kaggle on first run (place it in the project root to skip the download).

## Project structure

```
eda_superstore.py        # end-to-end EDA pipeline (single script)
ipynb/Analysis.ipynb     # interactive notebook version
eda_output/              # generated results
├── eda_summary.txt      # full text report + insights
├── agg_*.csv            # 5 aggregated tables (yearly, monthly, category, region, top customers/products)
└── *.png                # 10+ charts
```

## Key findings

| Insight | Value |
|---|---|
| YoY growth (2017 → 2018) | +20.3% |
| Peak season | November (best: Nov 2018, USD 117,938) |
| Top category / sub-category | Technology / Phones |
| Top region / state | West / California |
| Customer concentration | Top-10 customers = only 6.8% of sales |
| Sales distribution | Strongly right-skewed (median USD 54 vs mean USD 231) |

## What the pipeline does

1. Download dataset via `kagglehub` (or use local `train.csv`)
2. Parse dates + engineer features (year, quarter, month, shipping days)
3. Data quality audit — missing values, duplicates, impossible dates
4. Descriptive stats (numeric + categorical)
5. Visualizations — distribution, category breakdown, geography, customers/products, time series, month × year heatmap, shipping
6. Write `eda_summary.txt` + aggregated CSVs to `eda_output/`
