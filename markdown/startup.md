# Starting up Airflow

## References

## Bringing up environment

### Airflow

### #( 03/23/23@ 2:40PM )( donbuddenbaum@donbs-imac ):~/Documents/airflow-work

docker compose up

```+] Running 7/7
⠿ Container airflow-work-redis-1              Created                     0.0s
⠿ Container airflow-work-postgres-1           Recreated                   0.4s
⠿ Container airflow-work-airflow-init-1       Recreated                   0.5s
⠿ Container airflow-work-airflow-webserver-1  Recreated                   0.8s
⠿ Container airflow-work-airflow-worker-1     Recreated                   0.7s
⠿ Container airflow-work-airflow-scheduler-1  Recreated                   0.7s
⠿ Container airflow-work-airflow-triggerer-1  Recreated                   0.7s
Attaching to airflow-work-airflow-init-1, airflow-work-airflow-scheduler-1, airflow-work-airflow-triggerer-1, airflow-work-airflow-webserver-1, airflow-work-airflow-worker-1, airflow-work-postgres-1, airflow-work-redis-1
airflow-work-redis-1              | 1:C 23 Mar 2023 18:41:15.230 # oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
airflow-work-redis-1              | 1:C 23 Mar 2023 18:41:15.230 # Redis version=7.0.10, bits=64, commit=00000000, modified=0, pid=1, just started
airflow-work-redis-1              | 1:C 23 Mar 2023 18:41:15.230 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
airflow-work-redis-1              | 1:M 23 Mar 2023 18:41:15.231 * monotonic clock: POSIX clock_gettime
airflow-work-redis-1              | 1:M 23 Mar 2023 18:41:15.232 * Running mode=standalone, port=6379.
airflow-work-redis-1              | 1:M 23 Mar 2023 18:41:15.232 # Server initialized
airflow-work-redis-1              | 1:M 23 Mar 2023 18:41:15.233 * Loading RDB produced by version 7.0.10
airflow-work-redis-1              | 1:M 23 Mar 2023 18:41:15.233 * RDB age 136 seconds
airflow-work-redis-1              | 1:M 23 Mar 2023 18:41:15.233 * RDB memory usage when created 1.25 Mb
airflow-work-redis-1              | 1:M 23 Mar 2023 18:41:15.233 * Done loading RDB, keys loaded: 2, keys expired: 0.
airflow-work-redis-1              | 1:M 23 Mar 2023 18:41:15.233 * DB loaded from disk: 0.000 seconds
airflow-work-redis-1              | 1:M 23 Mar 2023 18:41:15.233 * Ready to accept connections
airflow-work-postgres-1           | 
airflow-work-postgres-1           | PostgreSQL Database directory appears to contain a database; Skipping initialization
airflow-work-postgres-1           | 
airflow-work-postgres-1           | 2023-03-23 18:41:15.318 UTC [1] LOG:  starting PostgreSQL 13.10 (Debian 13.10-1.pgdg110+1) on x86_64-pc-linux-gnu, compiled by gcc (Debian 10.2.1-6) 10.2.1 20210110, 64-bit
airflow-work-postgres-1           | 2023-03-23 18:41:15.318 UTC [1] LOG:  listening on IPv4 address "0.0.0.0", port 5432
airflow-work-postgres-1           | 2023-03-23 18:41:15.318 UTC [1] LOG:  listening on IPv6 address "::", port 5432
airflow-work-postgres-1           | 2023-03-23 18:41:15.321 UTC [1] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
airflow-work-postgres-1           | 2023-03-23 18:41:15.325 UTC [27] LOG:  database system was shut down at 2023-03-23 18:38:59 UTC
airflow-work-postgres-1           | 2023-03-23 18:41:15.333 UTC [1] LOG:  database system is ready to accept connections
airflow-work-airflow-init-1       | The container is run as root user. For security, consider using a regular user account.
airflow-work-airflow-init-1       | 
airflow-work-airflow-init-1       | /home/airflow/.local/lib/python3.7/site-packages/airflow/models/base.py:49 MovedIn20Warning: Deprecated API features detected! These feature(s) are not compatible with SQLAlchemy 2.0. To prevent incompatible upgrades prior to updating applications, ensure requirements files are pinned to "sqlalchemy<2.0". Set environment variable SQLALCHEMY_WARN_20=1 to show all deprecation warnings.  Set environment variable SQLALCHEMY_SILENCE_UBER_WARNING=1 to silence this message. (Background on SQLAlchemy 2.0 at: https://sqlalche.me/e/b8d9)
airflow-work-airflow-init-1       | DB: postgresql+psycopg2://airflow:***@postgres/airflow
airflow-work-airflow-init-1       | Performing upgrade with database postgresql+psycopg2://airflow:***@postgres/airflow
airflow-work-airflow-init-1       | [2023-03-23 18:41:38,080] {migration.py:205} INFO - Context impl PostgresqlImpl.
airflow-work-airflow-init-1       | [2023-03-23 18:41:38,080] {migration.py:212} INFO - Will assume transactional DDL.
airflow-work-airflow-init-1       | [2023-03-23 18:41:38,090] {db.py:1572} INFO - Creating tables
airflow-work-airflow-init-1       | INFO  [alembic.runtime.migration] Context impl PostgresqlImpl.
airflow-work-airflow-init-1       | INFO  [alembic.runtime.migration] Will assume transactional DDL.
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(_PythonDecoratedOperator): prepare_email>, send_email already registered for DAG: example_dag_decorator
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(EmailOperator): send_email>, prepare_email already registered for DAG: example_dag_decorator
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(BashOperator): create_entry_group>, delete_entry_group already registered for DAG: example_complex
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(BashOperator): delete_entry_group>, create_entry_group already registered for DAG: example_complex
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(BashOperator): create_entry_gcs>, delete_entry already registered for DAG: example_complex
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(BashOperator): delete_entry>, create_entry_gcs already registered for DAG: example_complex
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(BashOperator): create_tag>, delete_tag already registered for DAG: example_complex
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(BashOperator): delete_tag>, create_tag already registered for DAG: example_complex
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(_PythonDecoratedOperator): print_the_context>, log_sql_query already registered for DAG: example_python_operator
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(_PythonDecoratedOperator): log_sql_query>, print_the_context already registered for DAG: example_python_operator
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(_PythonDecoratedOperator): print_the_context>, log_sql_query already registered for DAG: example_python_operator
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(_PythonDecoratedOperator): log_sql_query>, print_the_context already registered for DAG: example_python_operator
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(_PythonDecoratedOperator): print_the_context>, log_sql_query already registered for DAG: example_python_operator
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(_PythonDecoratedOperator): log_sql_query>, print_the_context already registered for DAG: example_python_operator
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(_PythonDecoratedOperator): print_the_context>, log_sql_query already registered for DAG: example_python_operator
airflow-work-airflow-init-1       | WARNI [airflow.task.operators] Dependency <Task(_PythonDecoratedOperator): log_sql_query>, print_the_context already registered for DAG: example_python_operator
airflow-work-airflow-init-1       | Upgrades done
airflow-work-airflow-init-1       | [2023-03-23 18:41:52,370] {providers_manager.py:238} INFO - Optional provider feature disabled when importing 'airflow.providers.google.leveldb.hooks.leveldb.LevelDBHook' from 'apache-airflow-providers-google' package
airflow-work-airflow-init-1       | /home/airflow/.local/lib/python3.7/site-packages/snowflake/connector/options.py:108 UserWarning: You have an incompatible version of 'pyarrow' installed (9.0.0), please install a version that adheres to: 'pyarrow<10.1.0,>=10.0.1; extra == "pandas"'
airflow-work-airflow-init-1       | [2023-03-23 18:41:55,336] {providers_manager.py:238} INFO - Optional provider feature disabled when importing 'airflow.providers.google.leveldb.hooks.leveldb.LevelDBHook' from 'apache-airflow-providers-google' package
airflow-work-airflow-init-1       | airflow already exist in the db
airflow-work-airflow-init-1       | 2.5.2
airflow-work-airflow-init-1 exited with code 0
airflow-work-airflow-triggerer-1  | 
airflow-work-airflow-webserver-1  | 
airflow-work-airflow-scheduler-1  | 
airflow-work-airflow-worker-1     | 
airflow-work-airflow-webserver-1  | /home/airflow/.local/lib/python3.7/site-packages/airflow/models/base.py:49 MovedIn20Warning: Deprecated API features detected! These feature(s) are not compatible with SQLAlchemy 2.0. To prevent incompatible upgrades prior to updating applications, ensure requirements files are pinned to "sqlalchemy<2.0". Set environment variable SQLALCHEMY_WARN_20=1 to show all deprecation warnings.  Set environment variable SQLALCHEMY_SILENCE_UBER_WARNING=1 to silence this message. (Background on SQLAlchemy 2.0 at: https://sqlalche.me/e/b8d9)
airflow-work-airflow-triggerer-1  | /home/airflow/.local/lib/python3.7/site-packages/airflow/models/base.py:49 MovedIn20Warning: Deprecated API features detected! These feature(s) are not compatible with SQLAlchemy 2.0. To prevent incompatible upgrades prior to updating applications, ensure requirements files are pinned to "sqlalchemy<2.0". Set environment variable SQLALCHEMY_WARN_20=1 to show all deprecation warnings.  Set environment variable SQLALCHEMY_SILENCE_UBER_WARNING=1 to silence this message. (Background on SQLAlchemy 2.0 at: https://sqlalche.me/e/b8d9)
airflow-work-airflow-scheduler-1  | BACKEND=redis
airflow-work-airflow-scheduler-1  | DB_HOST=redis
airflow-work-airflow-scheduler-1  | DB_PORT=6379
airflow-work-airflow-worker-1     | BACKEND=redis
airflow-work-airflow-worker-1     | DB_HOST=redis
airflow-work-airflow-worker-1     | DB_PORT=6379
airflow-work-airflow-scheduler-1  | 
airflow-work-airflow-worker-1     | 
airflow-work-airflow-scheduler-1  | /home/airflow/.local/lib/python3.7/site-packages/airflow/models/base.py:49 MovedIn20Warning: Deprecated API features detected! These feature(s) are not compatible with SQLAlchemy 2.0. To prevent incompatible upgrades prior to updating applications, ensure requirements files are pinned to "sqlalchemy<2.0". Set environment variable SQLALCHEMY_WARN_20=1 to show all deprecation warnings.  Set environment variable SQLALCHEMY_SILENCE_UBER_WARNING=1 to silence this message. (Background on SQLAlchemy 2.0 at: https://sqlalche.me/e/b8d9)
airflow-work-airflow-triggerer-1  |   ____________       _____________
airflow-work-airflow-triggerer-1  |  ____    |__( )_________  __/__  /________      __
airflow-work-airflow-triggerer-1  | ____  /| |_  /__  ___/_  /_ __  /_  __ \_ | /| / /
airflow-work-airflow-triggerer-1  | ___  ___ |  / _  /   _  __/ _  / / /_/ /_ |/ |/ /
airflow-work-airflow-triggerer-1  |  _/_/  |_/_/  /_/    /_/    /_/  \____/____/|__/
airflow-work-airflow-triggerer-1  | [2023-03-23 18:42:24,786] {triggerer_job.py:101} INFO - Starting the triggerer
airflow-work-airflow-worker-1     | /home/airflow/.local/lib/python3.7/site-packages/airflow/models/base.py:49 MovedIn20Warning: Deprecated API features detected! These feature(s) are not compatible with SQLAlchemy 2.0. To prevent incompatible upgrades prior to updating applications, ensure requirements files are pinned to "sqlalchemy<2.0". Set environment variable SQLALCHEMY_WARN_20=1 to show all deprecation warnings.  Set environment variable SQLALCHEMY_SILENCE_UBER_WARNING=1 to silence this message. (Background on SQLAlchemy 2.0 at: https://sqlalche.me/e/b8d9)
airflow-work-airflow-scheduler-1  |   ____________       _____________
airflow-work-airflow-scheduler-1  |  ____    |__( )_________  __/__  /________      __
airflow-work-airflow-scheduler-1  | ____  /| |_  /__  ___/_  /_ __  /_  __ \_ | /| / /
airflow-work-airflow-scheduler-1  | ___  ___ |  / _  /   _  __/ _  / / /_/ /_ |/ |/ /
airflow-work-airflow-scheduler-1  |  _/_/  |_/_/  /_/    /_/    /_/  \____/____/|__/
airflow-work-airflow-scheduler-1  | [2023-03-23 18:42:31,398] {scheduler_job.py:714} INFO - Starting the scheduler
airflow-work-airflow-scheduler-1  | [2023-03-23 18:42:31,399] {scheduler_job.py:719} INFO - Processing each file at most -1 times
airflow-work-airflow-scheduler-1  | [2023-03-23 18:42:31,840] {executor_loader.py:107} INFO - Loaded executor: CeleryExecutor
airflow-work-airflow-scheduler-1  | [2023-03-23 18:42:31,854] {manager.py:163} INFO - Launched DagFileProcessorManager with pid: 32
airflow-work-airflow-scheduler-1  | [2023-03-23 18:42:31,870] {scheduler_job.py:1410} INFO - Resetting orphaned tasks for active dag runs
airflow-work-airflow-scheduler-1  | [2023-03-23 18:42:31,897] {settings.py:59} INFO - Configured default timezone Timezone('UTC')
airflow-work-airflow-worker-1     | [2023-03-23 18:42:33 +0000] [38] [INFO] Starting gunicorn 20.1.0
airflow-work-airflow-worker-1     | [2023-03-23 18:42:33 +0000] [38] [INFO] Listening at: http://0.0.0.0:8793 (38)
airflow-work-airflow-worker-1     | [2023-03-23 18:42:33 +0000] [38] [INFO] Using worker: sync
airflow-work-airflow-worker-1     | [2023-03-23 18:42:33 +0000] [39] [INFO] Booting worker with pid: 39
airflow-work-airflow-worker-1     | [2023-03-23 18:42:33 +0000] [40] [INFO] Booting worker with pid: 40
airflow-work-airflow-worker-1     |  
airflow-work-airflow-worker-1     |  -------------- celery@5b7fa166f7ac v5.2.7 (dawn-chorus)
airflow-work-airflow-worker-1     | --- ***** ----- 
airflow-work-airflow-worker-1     | -- ******* ---- Linux-5.15.49-linuxkit-x86_64-with-debian-11.6 2023-03-23 18:42:38
airflow-work-airflow-worker-1     | - *** --- * --- 
airflow-work-airflow-worker-1     | - ** ---------- [config]
airflow-work-airflow-worker-1     | - ** ---------- .> app:         airflow.executors.celery_executor:0x7f58cc2aa250
airflow-work-airflow-worker-1     | - ** ---------- .> transport:   redis://redis:6379/0
airflow-work-airflow-worker-1     | - ** ---------- .> results:     postgresql://airflow:**@postgres/airflow
airflow-work-airflow-worker-1     | - *** --- * --- .> concurrency: 16 (prefork)
airflow-work-airflow-worker-1     | -- ******* ---- .> task events: OFF (enable -E to monitor tasks in this worker)
airflow-work-airflow-worker-1     | --- ***** ----- 
airflow-work-airflow-worker-1     |  -------------- [queues]
airflow-work-airflow-worker-1     |                 .> default          exchange=default(direct) key=default
airflow-work-airflow-worker-1     |                 
airflow-work-airflow-worker-1     | 
airflow-work-airflow-worker-1     | [tasks]
airflow-work-airflow-worker-1     |   . airflow.executors.celery_executor.execute_command
airflow-work-airflow-worker-1     | 
airflow-work-airflow-webserver-1  | [2023-03-23 18:42:47,910] {providers_manager.py:238} INFO - Optional provider feature disabled when importing 'airflow.providers.google.leveldb.hooks.leveldb.LevelDBHook' from 'apache-airflow-providers-google' package
airflow-work-airflow-worker-1     | [2023-03-23 18:42:49,384: INFO/MainProcess] Connected to redis://redis:6379/0
airflow-work-airflow-worker-1     | [2023-03-23 18:42:49,407: INFO/MainProcess] mingle: searching for neighbors
airflow-work-airflow-worker-1     | [2023-03-23 18:42:50,441: INFO/MainProcess] mingle: all alone
airflow-work-airflow-worker-1     | [2023-03-23 18:42:50,474: INFO/MainProcess] celery@5b7fa166f7ac ready.
airflow-work-airflow-webserver-1  | /home/airflow/.local/lib/python3.7/site-packages/snowflake/connector/options.py:108 UserWarning: You have an incompatible version of 'pyarrow' installed (9.0.0), please install a version that adheres to: 'pyarrow<10.1.0,>=10.0.1; extra == "pandas"'
airflow-work-airflow-webserver-1  | [2023-03-23 18:42:51,577] {providers_manager.py:238} INFO - Optional provider feature disabled when importing 'airflow.providers.google.leveldb.hooks.leveldb.LevelDBHook' from 'apache-airflow-providers-google' package
airflow-work-airflow-webserver-1  | [2023-03-23 18:42:53 +0000] [19] [INFO] Starting gunicorn 20.1.0
airflow-work-airflow-webserver-1  | [2023-03-23 18:42:54,306] {providers_manager.py:238} INFO - Optional provider feature disabled when importing 'airflow.providers.google.leveldb.hooks.leveldb.LevelDBHook' from 'apache-airflow-providers-google' package
airflow-work-airflow-webserver-1  | [2023-03-23 18:42:54 +0000] [19] [INFO] Listening at: http://0.0.0.0:8080 (19)
airflow-work-airflow-webserver-1  | [2023-03-23 18:42:54 +0000] [19] [INFO] Using worker: sync
airflow-work-airflow-webserver-1  | [2023-03-23 18:42:54 +0000] [32] [INFO] Booting worker with pid: 32
airflow-work-airflow-webserver-1  | [2023-03-23 18:42:54 +0000] [33] [INFO] Booting worker with pid: 33
airflow-work-airflow-webserver-1  | [2023-03-23 18:42:54 +0000] [34] [INFO] Booting worker with pid: 34
airflow-work-airflow-webserver-1  | [2023-03-23 18:42:54 +0000] [35] [INFO] Booting worker with pid: 35
airflow-work-airflow-webserver-1  | 127.0.0.1 - - [23/Mar/2023:18:43:02 +0000] "GET /health HTTP/1.1" 200 141 "-" "curl/7.74.0"
```

### Flower

### #( 03/23/23@ 4:47PM )( donbuddenbaum@donbs-imac ):~/Documents/airflow-work

docker compose up flower   

```[+] Running 4/0
⠿ Container airflow-work-postgres-1      Running                          0.0s
⠿ Container airflow-work-redis-1         Running                          0.0s
⠿ Container airflow-work-airflow-init-1  Created                          0.0s
⠿ Container airflow-work-flower-1        Created                          0.0s
Attaching to airflow-work-flower-1
airflow-work-flower-1  |
airflow-work-flower-1  | BACKEND=redis
airflow-work-flower-1  | DB_HOST=redis
airflow-work-flower-1  | DB_PORT=6379
airflow-work-flower-1  |
airflow-work-flower-1  | /home/airflow/.local/lib/python3.7/site-packages/airflow/models/base.py:49 MovedIn20Warning: Deprecated API features detected! These feature(s) are not compatible with SQLAlchemy 2.0. To prevent incompatible upgrades prior to updating applications, ensure requirements files are pinned to "sqlalchemy<2.0". Set environment variable SQLALCHEMY_WARN_20=1 to show all deprecation warnings.  Set environment variable SQLALCHEMY_SILENCE_UBER_WARNING=1 to silence this message. (Background on SQLAlchemy 2.0 at: https://sqlalche.me/e/b8d9)
airflow-work-flower-1  | [2023-03-23 20:48:31,012] {command.py:165} INFO - Visit me at http://0.0.0.0:5555
airflow-work-flower-1  | [2023-03-23 20:48:31,019] {command.py:170} INFO - Broker: redis://redis:6379/0
airflow-work-flower-1  | [2023-03-23 20:48:31,023] {command.py:173} INFO - Registered tasks:
airflow-work-flower-1  | ['airflow.executors.celery_executor.execute_command',
airflow-work-flower-1  |  'celery.accumulate',
airflow-work-flower-1  |  'celery.backend_cleanup',
airflow-work-flower-1  |  'celery.chain',
airflow-work-flower-1  |  'celery.chord',
airflow-work-flower-1  |  'celery.chord_unlock',
airflow-work-flower-1  |  'celery.chunks',
airflow-work-flower-1  |  'celery.group',
airflow-work-flower-1  |  'celery.map',
airflow-work-flower-1  |  'celery.starmap']
airflow-work-flower-1  | [2023-03-23 20:48:31,024] {command.py:177} WARNING - Running without authentication
airflow-work-flower-1  | [2023-03-23 20:48:31,030] {mixins.py:225} INFO - Connected to redis://redis:6379/0
```
