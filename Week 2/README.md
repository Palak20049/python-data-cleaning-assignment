# SQL Sales Analysis - Two Projects

This workspace contains two separate deliverables.

## 1. ShopEase E-Commerce Database  -  [ShopEase_Assignment/](ShopEase_Assignment/)

Relational database task (the PDF assignment). Covers schema design with primary
keys, foreign keys, indexes and constraints, plus the Section A-E question set
(SELECT, filtering & SARGability, aggregation, joins, CASE/ACID/transactions) and
business use cases.

- [00_master_run_all.sql](ShopEase_Assignment/00_master_run_all.sql) - runs everything in order
- [01_schema_setup.sql](ShopEase_Assignment/01_schema_setup.sql) - 4 tables, keys, indexes, constraints
- [02_data_insertion.sql](ShopEase_Assignment/02_data_insertion.sql) - sample data
- [03_section_A_basics.sql](ShopEase_Assignment/03_section_A_basics.sql) - Q1-Q6
- [04_section_B_filtering.sql](ShopEase_Assignment/04_section_B_filtering.sql) - Q7-Q12
- [05_section_C_aggregation.sql](ShopEase_Assignment/05_section_C_aggregation.sql) - Q13-Q18
- [06_section_D_joins.sql](ShopEase_Assignment/06_section_D_joins.sql) - Q19-Q23
- [07_section_E_advanced.sql](ShopEase_Assignment/07_section_E_advanced.sql) - Q24-Q27
- [08_use_cases_and_validation.sql](ShopEase_Assignment/08_use_cases_and_validation.sql) - trends, top customers, duplicates, validation

Run it (MySQL 8+):

```sql
SOURCE 00_master_run_all.sql;
```

## 2. Superstore Sales Analysis  -  [Superstore_Analysis/](Superstore_Analysis/)

Analyzes the `Sample - Superstore.csv` order history in SQLite: load, explore,
filter (region/category/date/sales), aggregate, find top products/customers,
monthly trends, duplicates and data-quality checks.

- [load_data.py](Superstore_Analysis/load_data.py) - loads the CSV into `superstore.db` (dates normalised to ISO `YYYY-MM-DD`)
- [run_queries.py](Superstore_Analysis/run_queries.py) - runs all analysis queries and writes `query_results.md`
- [create_notebook.py](Superstore_Analysis/create_notebook.py) - regenerates the notebook
- [Superstore_SQL_Analysis.ipynb](Superstore_Analysis/Superstore_SQL_Analysis.ipynb) - runnable notebook
- [Superstore_SQL_Analysis.sql](Superstore_Analysis/Superstore_SQL_Analysis.sql) - the queries as plain SQL
- [Superstore_SQL_Analysis_Report.md](Superstore_Analysis/Superstore_SQL_Analysis_Report.md) - results + insights
- [query_results.md](Superstore_Analysis/query_results.md) - generated query output
- [superstore.db](Superstore_Analysis/superstore.db) - the loaded SQLite database

Run it:

```bash
cd Superstore_Analysis
python load_data.py
python run_queries.py
```

All scripts use paths relative to their own folder, so they run from anywhere.
