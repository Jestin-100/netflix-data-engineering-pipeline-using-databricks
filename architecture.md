# Medallion Architecture (Bronze → Silver → Gold)

This document explains the medallion architecture used in this pipeline.

Bronze (raw)
- Raw CSV ingestion from the source (Kaggle: netflix titles)
- Store exactly as captured with minimal validation
- Partitioning strategy: ingestion_date, optionally year

Silver (cleaned)
- Parse and standardize columns (dates, types)
- Handle nulls, normalize genre lists, deduplicate on natural keys
- Enforce JSON/Delta schemas (see `data/schemas`)

Gold (aggregated / served)
- Business-ready aggregates and served tables for dashboards and ML
- Example outputs: top genres per year, unique title counts, recommendation features

Best Practices
- Store schemas in repo and validate at ingestion (automated tests).
- Use Delta for ACID and time-travel.
- Track experiments with MLflow.
