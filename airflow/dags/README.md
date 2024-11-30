@'
# Airflow DAGs

Folder ini berisi workflow Airflow:
- scraping_dag.py: Workflow pengambilan data
- processing_dag.py: Workflow pemrosesan data
- analytics_dag.py: Workflow analisis data
'@ | Set-Content -Path airflow/dags/README.md