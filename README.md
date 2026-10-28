# Databricks Sales Analytics

A Databricks project that turns flat sales records into reporting-ready tables. The workflow separates ingestion, data preparation, and business summaries into Bronze, Silver, and Gold layers using Python with PySpark and Spark SQL.

## Analytical and engineering workflow

1. **Ingest to Bronze.** Read the source sales CSV and land the raw records in a Databricks table.
2. **Prepare Silver tables.** Standardize transaction dates and timestamps, retain transaction-level fields, and create distinct product and customer tables.
3. **Build Gold reporting tables.** Aggregate sales into regional, customer, and product summaries, including revenue, quantities, transaction counts, and average-order measures where defined in the notebook.
4. **Inspect outputs.** Query the summary tables to review top-performing regions, customers, and products.

## Tools and languages

- **Python and PySpark** for reading and ingesting the source file.
- **Spark SQL** for schema creation, transformations, and analytical aggregations.
- **Databricks** for execution and managed tables.

## Project files

- `databricks_sales_analytics.ipynb` — end-to-end layered workflow.

## Requirements and setup

Use a Databricks workspace with Spark and SQL support, access to the sales CSV, and permission to create or replace the catalog, schemas, and tables used by the notebook. Upload the notebook, configure the expected input file location in the ingestion step, and run the cells in sequence.

## Data model

The Bronze layer preserves source records. The Silver layer separates transactions from product and customer attributes. The Gold layer contains denormalized aggregates intended for business reporting. The notebook uses a configured catalog and schema namespace; adjust that namespace in Databricks if needed.
