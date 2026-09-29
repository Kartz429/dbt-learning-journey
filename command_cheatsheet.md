# dbt Command Cheatsheet
| Command | Use |
|---|---|
| dbt debug | check connection |
| dbt seed | load CSV seeds |
| dbt run | build models |
| dbt run --select fact_orders+ | model and downstream |
| dbt snapshot | capture history |
| dbt test | run tests |
| dbt build | seed+run+snapshot+test in DAG order |
| dbt run --full-refresh | rebuild incremental |
| dbt compile | render Jinja |
| dbt docs generate / serve | docs + lineage |
| dbt ls | list resources |
