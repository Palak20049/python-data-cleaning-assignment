# SQL Sales Analysis Projects

This repository contains two SQL-based projects that demonstrate database design, SQL query writing, data analysis, and business reporting skills. The projects cover both relational database management using MySQL and sales data analysis using SQLite.

---

# Project 1: ShopEase E-Commerce Database

## Overview

The ShopEase E-Commerce Database project focuses on designing and implementing a relational database for an online shopping platform. The project includes schema creation, data insertion, indexing, constraints, and SQL query solutions covering fundamental to advanced database concepts.

The objective is to demonstrate practical database design skills, efficient query writing, data validation, and business-oriented reporting using MySQL.

---

## Features

* Relational database schema design
* Primary Keys and Foreign Keys
* Constraints and Data Validation
* Index Creation for Query Optimization
* Data Insertion Scripts
* Filtering and Searching Techniques
* Aggregation and Grouping Operations
* Multi-table Joins
* CASE Statements
* Transaction Management
* Business Use Case Analysis
* Data Quality Validation

---

## Project Structure

### Database Setup

* `00_master_run_all.sql` – Executes all scripts in the correct sequence
* `01_schema_setup.sql` – Creates tables, keys, indexes, and constraints
* `02_data_insertion.sql` – Inserts sample records

### SQL Query Sections

* `03_section_A_basics.sql` – Basic SELECT queries
* `04_section_B_filtering.sql` – Filtering and SARGable queries
* `05_section_C_aggregation.sql` – Aggregation and grouping operations
* `06_section_D_joins.sql` – Multi-table join queries
* `07_section_E_advanced.sql` – Advanced SQL concepts and transactions
* `08_use_cases_and_validation.sql` – Business insights and data validation

---

## Technologies Used

* MySQL 8+
* SQL

---

## How to Run

Open MySQL and execute:

```sql
SOURCE 00_master_run_all.sql;
```

This script will automatically create the database schema, insert sample data, and run all assignment queries.

---

## Learning Outcomes

Through this project, the following SQL concepts were practiced:

* Database Design
* Primary & Foreign Keys
* Constraints
* Indexing
* Query Optimization
* Filtering
* Aggregation Functions
* Joins
* CASE Statements
* Transactions and ACID Properties
* Business Reporting

---

# Project 2: Superstore Sales Analysis

## Overview

The Superstore Sales Analysis project focuses on analyzing retail sales data using SQLite. The dataset contains customer orders, sales information, product categories, regions, and shipping details.

The project demonstrates how SQL can be used for data exploration, sales analysis, customer insights, trend identification, and data quality assessment.

---

## Features

* CSV Data Loading
* SQLite Database Creation
* Data Cleaning and Date Standardization
* Sales Analysis
* Customer Analysis
* Product Performance Analysis
* Regional Performance Analysis
* Monthly Trend Analysis
* Duplicate Detection
* Data Quality Checks
* Automated Query Execution

---

## Dataset

The project uses:

`Sample - Superstore.csv`

The dataset contains information about:

* Orders
* Customers
* Products
* Categories
* Regions
* Sales
* Profit
* Shipping Details

---

## Project Structure

### Data Loading

* `load_data.py` – Loads CSV data into SQLite database and converts dates into ISO format (`YYYY-MM-DD`)

### Query Execution

* `run_queries.py` – Executes all SQL analysis queries and generates results

### Notebook Generation

* `create_notebook.py` – Generates the Jupyter Notebook version of the analysis

### Analysis Files

* `Superstore_SQL_Analysis.ipynb` – Interactive notebook
* `Superstore_SQL_Analysis.sql` – Complete SQL query collection
* `Superstore_SQL_Analysis_Report.md` – Findings and business insights
* `query_results.md` – Generated query outputs
* `superstore.db` – SQLite database

---

## Technologies Used

* Python
* SQLite
* Pandas
* Jupyter Notebook
* SQL

---

## How to Run

Navigate to the project folder:

```bash
cd Superstore_Analysis
```

Load the dataset:

```bash
python load_data.py
```

Run all analysis queries:

```bash
python run_queries.py
```

---

## Analysis Performed

The project includes:

### Sales Analysis

* Total Sales
* Regional Sales
* Category-wise Sales
* Sub-category Performance

### Customer Analysis

* Top Customers
* Customer Purchase Trends
* Customer Contribution Analysis

### Product Analysis

* Best Selling Products
* High Revenue Products
* Category Performance

### Time-Series Analysis

* Monthly Sales Trends
* Seasonal Performance
* Order Volume Trends

### Data Quality Checks

* Duplicate Records
* Missing Values
* Data Consistency Validation

---

## Key Learning Outcomes

This project helped strengthen understanding of:

* SQL Query Writing
* Data Exploration
* Data Cleaning
* Business Intelligence Reporting
* Trend Analysis
* Customer Analytics
* Product Performance Evaluation
* SQLite Database Management
* Python-SQL Integration

---

# Conclusion

These two projects collectively demonstrate practical database management and data analysis skills. The ShopEase project focuses on relational database design and SQL fundamentals, while the Superstore project highlights analytical SQL techniques and business intelligence reporting using real-world sales data.

Together, they provide hands-on experience in database development, querying, optimization, reporting, and data-driven decision-making.
