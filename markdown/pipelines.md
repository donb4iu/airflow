# Airflow Pipelines

## References

- [13. Connecting Airflow to a local Postgres Database](https://medium.com/@thehippieandtheboss/13-connecting-airflow-to-a-local-postgres-database-21f5bc849344)
- [Command Line Interface and Environment Variables Reference](https://airflow.apache.org/docs/apache-airflow/stable/cli-and-env-variables-ref.html)

## DAGs

### Test 

```
from datetime import datetime

from airflow import DAG
from airflow.decorators import task

with DAG(
    dag_id="demo_dag",
    start_date=datetime(2022, 1, 1),
    schedule="0 0 * * *"
    ) as dag:

    @task()
    def test_airflow():
        print("Executed using Apache Airflow ✨")

    test_airflow()
```