# 📈 FP&A Automated Variance Dashboard (BvA)

## 📌 Project Overview
Variance analysis is a fundamental component of corporate finance, used to compare planned financial budgets against realized actuals. This project demonstrates the architecture of an automated Financial Planning and Analysis (FP&A) dashboard that calculates variances across multiple departments, dynamically updating based on user-selected financial periods.

## ⚙️ Core Methodologies & Skills Demonstrated

### 1. Dynamic Period Selection & Data Engineering
Raw financial data rarely arrives perfectly formatted for dashboard ingestion.
* **Helper Column Architecture:** Engineered a unique concatenated identifier (`Department` + `TEXT(Date, "mmm")`) to transform vertical time-series data into a queryable database structure.
* **Data Validation:** Implemented drop-down menus to allow executive end-users to toggle between monthly reporting periods dynamically.

### 2. The INDEX/MATCH Lookup Engine
Replaced static `VLOOKUP` limitations with a robust, two-dimensional `INDEX/MATCH` coordinate system.
* **Application:** As the user changes the reporting month, the engine cross-references the Helper Column to instantly pull the exact Budget and Actual figures for every department simultaneously.

### 3. Variance Mathematics & Error Handling
Executed standard FP&A calculations with built-in structural safeguards.
* Calculated **Absolute Variance ($)** and **Percentage Variance (%)**.
* **Error Handling:** Wrapped percentage formulas in `=IFERROR(..., 0)` to prevent `#DIV/0!` errors when evaluating departments with zero-dollar starting budgets, ensuring uninterrupted dashboard functionality.

### 4. Advanced Visualization & Formatting
* **Conditional Formatting:** Applied automated Red/Green highlighting to variance percentages, allowing for rapid visual identification of cost overruns and revenue successes.
* **Waterfall Charting:** Built a formatted Waterfall "Bridge" chart. Customized the Y-axis bounds to appropriately scale the variance steps between the anchored "Total Budget" and "Total Actual" pillars, providing a clear visual narrative of the month's financial performance.

## 📂 Repository Contents
* `FPA_Variance_Dashboard.xlsx`: The interactive Excel model.
* `FP&A_Variance_Analysis_Model.csv`: The raw Kaggle dataset used for the project.
