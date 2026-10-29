# 🏗️ SQL Data Warehouse Project — Bronze, Silver & Gold

A SQL Server data warehouse built using the **Medallion Architecture** (Bronze → Silver → Gold), consolidating CRM and ERP source data into a clean, business-ready **star schema** for analytics and reporting.

---

## 📌 Project Overview

Raw CSV exports from two source systems — **CRM** and **ERP** — are progressively cleaned, integrated, and modeled into a single SQL Server database (`DataWarehouse`). The final Gold-layer views are ready to power BI dashboards, ad-hoc SQL analysis, and reporting.

**Includes:** DDL & ETL scripts for all three layers, data quality checks, and full documentation in `docs/` (architecture, data flow, data model, naming conventions, data catalog).

---

## 🏛️ Data Architecture

<img width="1544" height="912" alt="data_architecture" src="https://github.com/user-attachments/assets/b6f0b04f-8e64-460c-96cf-81f92a7eed1e" />

Data flows from CSV files (CRM & ERP) through **Bronze** (raw, as-is) → **Silver** (cleaned & standardized) → **Gold** (business-ready star schema), before being consumed via BI tools, SQL queries, or ML.

---

## 🥉🥈🥇 Data Layers

<img width="1498" height="822" alt="data_layers" src="https://github.com/user-attachments/assets/529dace7-105a-437e-855f-0ab136edb0f5" />


| Layer | Object Type | Transformation |
|---|---|---|
| **Bronze** | Tables | None — raw, as-is load |
| **Silver** | Tables | Cleaning, standardization, derived columns |
| **Gold** | Views | Integration, aggregation, business logic |

---

## ⭐ Gold Layer (Star Schema)

- `gold.dim_customers` — customer demographic & geographic attributes
- `gold.dim_products` — product, category & subcategory attributes
- `gold.fact_sales` — sales transactions linked to both dimensions (`sales_amount = quantity × price`)

---

## 📁 Repository Structure

```
├── datasets/        # Raw CRM & ERP source CSV files
├── docs/            # Architecture, data flow, model & naming docs
├── scripts/
│   ├── init_database.sql
│   ├── bronze/      # DDL + load procedure
│   ├── silver/      # DDL + cleaning/transform procedure
│   └── gold/        # DDL (dim/fact views)
└── tests/           # Data quality checks (silver & gold)
```

---

## 📐 Naming Conventions

All schemas, tables, columns, and stored procedures follow a consistent, source-aware naming standard (e.g., `dim_customers`, `fact_sales`, `customer_key`, `load_bronze`) to keep the warehouse predictable and easy to navigate. See [`docs/naming_conventions.md`](docs/naming_conventions.md) for the full set of rules.

---

## 🛠️ Tech Stack

SQL Server (T-SQL) · Stored Procedures · Views · `BULK INSERT` · Star Schema Modeling · Data Quality Testing

---

## 🚀 Getting Started

1. Run `scripts/init_database.sql` to create the database and schemas.
2. Run Bronze DDL + `EXEC bronze.load_bronze;`
3. Run Silver DDL + `EXEC silver.load_silver;`
4. Run Gold DDL to create the final views.
5. (Optional) Run scripts in `tests/` to validate data quality.

---

## 👤 About Me

Hi, I'm **Dhruv Bansal**, a Data Analytics and Business Intelligence enthusiast with a passion for transforming raw data into meaningful insights. I enjoy working with SQL, Python, Power BI, and data visualization to solve real-world business problems and support data-driven decision-making.

I'm continuously expanding my skills by building hands-on projects that demonstrate practical analytics techniques, problem-solving, and best practices in data analysis.

🔗 LinkedIn: https://www.linkedin.com/in/dhruv-bansal-388501293/

📧 Email: dhruvbansal3922@gmail.com

---

⭐ If you found this project useful, feel free to star the repo!
