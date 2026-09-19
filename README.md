# Superstore Sales Analysis — End-to-End Data Analyst Project

An end-to-end data analysis project using **MySQL, Python, Excel, and Power BI** on the classic Sample Superstore dataset, covering the full pipeline from raw data to an interactive dashboard.

---

## 📌 Business Question

The Superstore is generating strong overall sales, but profitability varies widely across regions, categories, and discount levels. This project investigates:

- Which product categories and sub-categories drive the most **sales** — and which drive the most (or least) **profit**?
- Which regions and customer segments are the most profitable?
- How does **discounting** affect profit margins?
- What does the monthly sales trend look like, and is it growing or shrinking?

---

## 🗂️ Project Structure

```
superstore-analyst-project/
├── sql/
│   └── queries.sql              # Exploratory SQL queries (MySQL)
├── python/
│   └── superstore_analysis.ipynb # Data cleaning, EDA, and visualization
├── excel/
│   └── superstore_summary.xlsx   # PivotTables, PivotCharts, quick formulas
├── powerbi/
│   └── superstore_dashboard.pbix # Interactive Power BI dashboard
├── data/
│   └── superstore.csv            # Raw dataset (source: Kaggle)
└── README.md
```

---

## 🛠️ Tools & Skills Used

| Tool | What it was used for |
|---|---|
| **MySQL** | Storing the raw data relationally and writing exploratory SQL (aggregations, `GROUP BY`, window functions like `RANK()`) |
| **Python (pandas, matplotlib, seaborn)** | Connecting to MySQL, cleaning the data, exploratory data analysis, and charting |
| **Excel** | PivotTables, PivotCharts, and formulas (`SUMIFS`, `XLOOKUP`) for quick ad-hoc analysis |
| **Power BI** | Data modeling, DAX measures, and an interactive dashboard with slicers |

---

## 📊 Dataset

**Source:** [Sample Superstore Dataset — Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)

~9,994 rows of order-level data including order/ship dates, customer info, product category/sub-category, sales, quantity, discount, and profit.

---

## 🔍 Process

### 1. SQL (MySQL)
- Imported the raw CSV into a MySQL table (`orders`).
- Wrote exploratory queries to find total sales by category, sales/profit by region, monthly trends, top customers, and the least profitable sub-categories.
- Used a window function (`RANK()`) to rank categories by profit.
- All queries are in [`sql/queries.sql`](sql/queries.sql).

### 2. Python
- Connected to the MySQL database using `sqlalchemy` and `mysql-connector-python`.
- Checked for missing values and duplicates, converted date columns, and cast numeric columns properly.
- Performed exploratory analysis: sales by category, monthly sales trend.
- Visualized trends with `matplotlib` and `seaborn`.
- Exported the cleaned dataset to CSV and pushed it back into MySQL as `orders_cleaned` for Power BI to use directly.
- Full analysis: [`python/superstore_analysis.ipynb`](python/superstore_analysis.ipynb)

### 3. Excel
- Built PivotTables for sales by category, profit by region, and sales by month.
- Used `SUMIFS` and `XLOOKUP` for quick conditional lookups and totals.
- Created a PivotChart to visualize category performance.
- File: [`excel/superstore_summary.xlsx`](excel/superstore_summary.xlsx)

### 4. Power BI
- Connected directly to the `orders_cleaned` MySQL table.
- Built a custom Date table and DAX measures: `Total Sales`, `Total Profit`, `Profit Margin %`, `Sales Growth %` (YoY).
- Designed a single-page dashboard with KPI cards, a monthly sales trend line chart, a category/sub-category breakdown, a regional map, and interactive slicers (Region, Category, Date).
- File: [`powerbi/superstore_dashboard.pbix`](powerbi/superstore_dashboard.pbix)

---

## 💡 Key Insights


- Insight 1:  "The Furniture category has high sales but the lowest profit margin, largely due to the Tables sub-category losing money on nearly every order."
- Insight 2:  "The West region is the most profitable, while the Central region has the weakest margins despite comparable sales volume."
- Insight 3:  "Profit drops sharply once discounts exceed 20%, suggesting a discounting policy that's eating into margins beyond that threshold."

---

## 📷 Dashboard Preview

"D:\data_analyst_projects\superstore-project\superstore-data-analyst-project\powerbi\screenshots\superstore-dashboard-1.png"
"D:\data_analyst_projects\superstore-project\superstore-data-analyst-project\powerbi\screenshots\superstore-dashboard-2.png"


---

## 🚀 How to Reproduce This Project

1. Clone this repo:
   ```bash
   git clone https://github.com/dileeptanikonda/superstore-analyst-project.git
   ```
2. Import `data/superstore.csv` into a local MySQL database (see `sql/queries.sql` for table setup and queries).
3. Open `python/superstore_analysis.ipynb` in Jupyter Notebook, update the database credentials, and run all cells.
4. Open `excel/superstore_summary.xlsx` to view the PivotTable analysis.
5. Open `powerbi/superstore_dashboard.pbix` in Power BI Desktop (update the data source connection to your local MySQL instance if needed).

---

## 👤 Author

DILEEP
