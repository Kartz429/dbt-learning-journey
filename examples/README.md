# Code examples (copied unchanged from my_first_project)
| Topic | File |
|---|---|
| Seeds | seeds/*.csv |
| Bronze / Silver | models/bronze_orders.sql, silver_orders.sql |
| Jinja | models/jinja_demo.sql, loop_demo.sql |
| Macro | macros/customer_type.sql, models/macro_demo.sql |
| Snapshot / SCD2 | snapshots/customers_snapshot.sql, models/dim_customers_scd2.sql, scd_type*_demo.sql |
| Incremental | models/fact_orders_incremental.sql |
| Fact / Mart | models/fact_orders.sql, mart_gmv.sql |
| Tests | models/schema.yml |
The full runnable project is in `food-delivery-dbt-project`. Note: macro_demo.sql has a known column issue (see learning_progress.md).
