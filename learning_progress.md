# Learning Progress

## Implemented (verified in code)
Bronze/Silver/Gold, seeds, ref(), table/view/incremental, Jinja set/for/if, one macro, check-strategy snapshot, SCD2 dim with row_number surrogate key, incremental fact, GMV mart, 2 generic tests on fact_orders.

## Issues found (by reading code; models were not run)
| # | File | Issue | Fix idea |
|---|---|---|---|
| 1 | gold/gold_sales.sql | groups by customer_name, not in silver_orders | join silver/dim customers |
| 2 | gold/macro_demo.sql | selects customer_name from silver_orders | join customers or drop column |
| 3 | gold/mart_city_sales.sql | uses city, not in fact_orders | join dim_customers_scd2 like mart_gmv |
| 4 | gold/fact_orders.sql | joins SCD2 dim on customer_id only → duplicates once history exists | add validity-window join or use current rows |
| 5 | gold/fact_orders.sql | restaurant_sk is just restaurant_id | use a real surrogate key |
| 6 | gold/dim_customers_scd2.sql | row_number() keys not stable | hash of customer_id + dbt_valid_from |
| 7 | fact_orders_incremental.sql | id > max() misses late/updated rows | timestamp watermark |
| 8 | automation/*.py | README overwritten each sync; project repo copy skips dbt_project.yml; README claims CI/CD | keep README manual |
