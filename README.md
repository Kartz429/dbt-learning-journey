# 📚 dbt Learning Journey

![dbt](https://img.shields.io/badge/dbt-Core-FF694B?logo=dbt&logoColor=white)
![Level](https://img.shields.io/badge/level-beginner→intermediate-orange)
![License](https://img.shields.io/badge/license-MIT-green)

Structured dbt study notes, interview prep and runnable examples, built while developing a food-delivery analytics project (dbt + DuckDB).

**Companion repo:** [food-delivery-dbt-project](https://github.com/Kartz429/food-delivery-dbt-project)

## Learning Path

| # | Topic | Status |
|---|---|---|
| 01 | [dbt Basics](notes/01_DBT_Basics.md) | ✅ |
| 02 | [Project Structure](notes/02_Project_Structure.md) | ✅ |
| 03 | [Medallion Architecture](notes/03_Medallion_Architecture.md) | ✅ |
| 04 | [source() vs ref()](notes/04_Source_vs_Ref.md) | 🟡 ref() practiced, source() not yet |
| 05 | [Materialization](notes/05_Materialization.md) | ✅ |
| 06 | [Data Tests](notes/06_Data_Tests.md) | 🟡 basic generic tests |
| 07 | [Jinja](notes/07_Jinja.md) | ✅ |
| 08 | [Macros](notes/08_Macros.md) | ✅ |
| 09 | [Seeds](notes/09_Seeds.md) | ✅ |
| 10 | [Snapshots](notes/10_Snapshots.md) | ✅ |
| 11 | [SCD Type 1 vs 2](notes/11_SCD_Type_1_vs_Type_2.md) | ✅ |
| 12 | [Incremental Models](notes/12_Incremental_Models.md) | ✅ |
| 13 | [Dimension Tables](notes/13_Dimension_Tables.md) | ✅ |
| 14 | [Fact Tables](notes/14_Fact_Tables.md) | ✅ |
| 15 | [Star Schema](notes/15_Star_Schema.md) | ✅ |
| 16 | [Surrogate Keys](notes/16_Surrogate_Keys.md) | ✅ |
| 17 | [DAG and Lineage](notes/17_DAG_and_Lineage.md) | ✅ |
| 18 | [Environment Management](notes/18_Environment_Management.md) | 🟡 dev/prod DBs exist, config not documented |
| 19 | [CI/CD](notes/19_CI_CD.md) | ⬜ concept only |
| 20 | [Project Summary](notes/20_Project_Summary.md) | ✅ |

## Repository Contents

```
├── notes/        20 concept notes (same template) + index
├── examples/     working code copied from the project
├── interview_questions.md
├── command_cheatsheet.md
├── learning_progress.md   progress + issues found in own code
├── roadmap.md
├── daily_learning_log.md
└── archive/      earlier notes, kept for reference
```

## Current Skill Level
Beginner → early intermediate: solid on modeling concepts (medallion, SCD2, incremental, star schema); next focus is testing depth, `source()` and CI/CD.

## Interview Readiness
- [x] ELT and dbt's role
- [x] Bronze / Silver / Gold
- [x] SCD Type 1 vs 2 and snapshots
- [x] Incremental models
- [x] Facts, dimensions, star schema
- [ ] `source()` and freshness
- [ ] Custom singular and relationships tests
- [ ] CI/CD demo

## Next Steps
See [roadmap.md](roadmap.md).

## License
MIT — see [LICENSE](LICENSE).
