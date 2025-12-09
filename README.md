# Netflix Movie Recommendation Engine Databricks Lakehouse

End to end collaborative filtering recommendation system built completely on Databricks.

Most recent Netflix movie data (csv files) extracted from Kaggle and ingested in to databricks unity catalog as volume in the landing schema (raw data ingestion). 

Using medallion architecture, the data goes through 3 level bronze, silver and gold. The volume is converted to databricks delta tables (databricks default table) in the bronze layer, cleaned and transformed in the silver layer and ready for business intelligence, AI/ML in the gold layer for end users.

Spark ALS + Delta Lake + MLflow + Databricks SQL Dashboards + Automated Workflows

[![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)](https://databricks.com)
[![Delta Lake](https://img.shields.io/badge/Delta_Lake-00C4B8?style=for-the-badge)](https://delta.io)
[![MLflow](https://img.shields.io/badge/MLflow-0194E5?style=for-the-badge)](https://mlflow.org)

## Architecture
![Architecture](architecture.png)

## Features
- 5 million synthetic ratings (realistic power-law distribution)
- Bronze → Silver → Gold medallion architecture
- MLflow experiment tracking + model registry
- Top-10 recommendations for every user
- Live dashboard in Databricks SQL
- Weekly automated retraining job

Work in progress – come back in a few days for the full code & demo video!
