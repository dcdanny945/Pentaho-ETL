# ICE Entertainment — Dimensional Data Warehouse (Star Schema)

Star schema data warehouse for a global digital retailer, built with Pentaho (ETL) and a MySQL database. Integrates fragmented sales and ERP data into a single source of truth, with all financial reporting standardised to USD.

## Design

- **Star schema:** 2 fact tables (`fact_sales`, `fact_c_subscription`) surrounded by conformed dimensions.
  
- **Dimensions:** `dim_customer` (SCD Type 2), `dim_product`, `dim_store`, `dim_market`, `dim_date` (Sunday flags + Australian public holidays 2022–2026), `dim_currency`.
  
- **ETL:** Pentaho transformations (`.ktr`) handle data cleansing, dimension lookups, monthly currency-rate conversion to USD, and margin calculation.


### Star Schema (ER Diagram)
![Star Schema ER Diagram](images/star_schema.png)


## ETL Pipelines (Pentaho)

### fact_sales Transformation

![fact_sales pipeline](images/fact_sales.png)

### fact_c_subscription Transformation

![fact_c_subscription pipeline](images/fact_c_subscription.png)

### dim_customer — SCD Type 2

![dim_customer SCD Type 2](images/dim_customer_scd.png)

### dim_currency Transformation

![dim_currency pipeline](images/dim_currency.png)

### stg_currency_rate (USD Conversion Lookup)

![stg_currency_rate pipeline](images/stg_currency_rate.png)

## Tech

Pentaho Data Integration (Spoon) · MySQL · SQL

## Files

- `*.ktr` — Pentaho transformations (open in Spoon to run)
- `*.sql` — schema creation scripts
- `images/` — ER diagram and key ETL pipeline screenshots


