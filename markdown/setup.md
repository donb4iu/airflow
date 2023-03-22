# Installation and Setup Airflow in Docker

## References

[Running Airflow in Docker](https://github.com/donb4iu/airflow.git)

## Install

### #( 03/22/23@10:41AM )( donbuddenbaum@donbs-imac ):~/Documents
mkdir airflow
### #( 03/22/23@10:42AM )( donbuddenbaum@donbs-imac ):~/Documents
cd airflow
### #( 03/22/23@10:42AM )( donbuddenbaum@donbs-imac ):~/Documents/airflow
curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.5.2/docker-compose.yaml'
```
% Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
Dload  Upload   Total   Spent    Left  Speed
100 11576  100 11576    0     0  25350      0 --:--:-- --:--:-- --:--:-- 25839
```
### #( 03/22/23@10:42AM )( donbuddenbaum@donbs-imac ):~/Documents/airflow
curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.5.2/airflow.sh'
```
% Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
Dload  Upload   Total   Spent    Left  Speed
100  1271  100  1271    0     0   2242      0 --:--:-- --:--:-- --:--:--  2277
```
### #( 03/22/23@10:45AM )( donbuddenbaum@donbs-imac ):~/Documents/airflow
chmod +x airflow.sh
### #( 03/22/23@10:46AM )( donbuddenbaum@donbs-imac ):~/Documents/airflow
mkdir -p ./dags ./logs ./plugins
#### #( 03/22/23@10:47AM )( donbuddenbaum@donbs-imac ):~/Documents/airflow
echo -e "AIRFLOW_UID=$(id -u)" > .env
### #( 03/22/23@10:47AM )( donbuddenbaum@donbs-imac ):~/Documents/airflow
docker compose up airflow-init

```
Attaching to airflow-airflow-init-1
airflow-airflow-init-1  | The container is run as root user. For security, consider using a regular user account.
airflow-airflow-init-1  |
airflow-airflow-init-1  | /home/airflow/.local/lib/python3.7/site-packages/airflow/models/base.py:49 MovedIn20Warning: Deprecated API features detected! These feature(s) are not compatible with SQLAlchemy 2.0. To prevent incompatible upgrades prior to updating applications, ensure requirements files are pinned to "sqlalchemy<2.0". Set environment variable SQLALCHEMY_WARN_20=1 to show all deprecation warnings.  Set environment variable SQLALCHEMY_SILENCE_UBER_WARNING=1 to silence this message. (Background on SQLAlchemy 2.0 at: https://sqlalche.me/e/b8d9)
airflow-airflow-init-1  | DB: postgresql+psycopg2://airflow:***@postgres/airflow
airflow-airflow-init-1  | Performing upgrade with database postgresql+psycopg2://airflow:***@postgres/airflow
airflow-airflow-init-1  | [2023-03-22 14:51:25,679] {migration.py:205} INFO - Context impl PostgresqlImpl.
airflow-airflow-init-1  | [2023-03-22 14:51:25,680] {migration.py:212} INFO - Will assume transactional DDL.
airflow-airflow-init-1  | [2023-03-22 14:51:25,690] {migration.py:205} INFO - Context impl PostgresqlImpl.
airflow-airflow-init-1  | [2023-03-22 14:51:25,690] {migration.py:212} INFO - Will assume transactional DDL.
airflow-airflow-init-1  | INFO  [alembic.runtime.migration] Context impl PostgresqlImpl.
airflow-airflow-init-1  | INFO  [alembic.runtime.migration] Will assume transactional DDL.
airflow-airflow-init-1  | INFO  [alembic.runtime.migration] Running stamp_revision  -> 290244fb8b83
airflow-airflow-init-1  | Upgrades done
airflow-airflow-init-1  | [2023-03-22 14:51:47,804] {manager.py:243} INFO - Inserted Role: Admin
airflow-airflow-init-1  | [2023-03-22 14:51:47,820] {manager.py:243} INFO - Inserted Role: Public
airflow-airflow-init-1  | [2023-03-22 14:51:47,827] {manager.py:824} WARNING - No user yet created, use flask fab command to do it.
airflow-airflow-init-1  | [2023-03-22 14:51:48,046] {manager.py:504} INFO - Created Permission View: can edit on Passwords
airflow-airflow-init-1  | [2023-03-22 14:51:48,071] {manager.py:562} INFO - Added Permission can edit on Passwords to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:48,146] {manager.py:504} INFO - Created Permission View: can read on Passwords
airflow-airflow-init-1  | [2023-03-22 14:51:48,180] {manager.py:562} INFO - Added Permission can read on Passwords to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:48,599] {manager.py:504} INFO - Created Permission View: can edit on My Password
airflow-airflow-init-1  | [2023-03-22 14:51:48,625] {manager.py:562} INFO - Added Permission can edit on My Password to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:48,689] {manager.py:504} INFO - Created Permission View: can read on My Password
airflow-airflow-init-1  | [2023-03-22 14:51:48,751] {manager.py:562} INFO - Added Permission can read on My Password to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:48,850] {manager.py:504} INFO - Created Permission View: can edit on My Profile
airflow-airflow-init-1  | [2023-03-22 14:51:48,890] {manager.py:562} INFO - Added Permission can edit on My Profile to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:48,931] {manager.py:504} INFO - Created Permission View: can read on My Profile
airflow-airflow-init-1  | [2023-03-22 14:51:48,971] {manager.py:562} INFO - Added Permission can read on My Profile to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:49,387] {manager.py:504} INFO - Created Permission View: can create on Users
airflow-airflow-init-1  | [2023-03-22 14:51:49,424] {manager.py:562} INFO - Added Permission can create on Users to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:49,447] {manager.py:504} INFO - Created Permission View: can read on Users
airflow-airflow-init-1  | [2023-03-22 14:51:49,492] {manager.py:562} INFO - Added Permission can read on Users to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:49,568] {manager.py:504} INFO - Created Permission View: can edit on Users
airflow-airflow-init-1  | [2023-03-22 14:51:49,625] {manager.py:562} INFO - Added Permission can edit on Users to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:49,668] {manager.py:504} INFO - Created Permission View: can delete on Users
airflow-airflow-init-1  | [2023-03-22 14:51:49,717] {manager.py:562} INFO - Added Permission can delete on Users to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:49,779] {manager.py:504} INFO - Created Permission View: menu access on List Users
airflow-airflow-init-1  | [2023-03-22 14:51:49,836] {manager.py:562} INFO - Added Permission menu access on List Users to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:50,001] {manager.py:504} INFO - Created Permission View: menu access on Security
airflow-airflow-init-1  | [2023-03-22 14:51:50,021] {manager.py:562} INFO - Added Permission menu access on Security to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:50,165] {manager.py:504} INFO - Created Permission View: can create on Roles
airflow-airflow-init-1  | [2023-03-22 14:51:50,193] {manager.py:562} INFO - Added Permission can create on Roles to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:50,222] {manager.py:504} INFO - Created Permission View: can read on Roles
airflow-airflow-init-1  | [2023-03-22 14:51:50,239] {manager.py:562} INFO - Added Permission can read on Roles to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:50,279] {manager.py:504} INFO - Created Permission View: can edit on Roles
airflow-airflow-init-1  | [2023-03-22 14:51:50,306] {manager.py:562} INFO - Added Permission can edit on Roles to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:50,343] {manager.py:504} INFO - Created Permission View: can delete on Roles
airflow-airflow-init-1  | [2023-03-22 14:51:50,361] {manager.py:562} INFO - Added Permission can delete on Roles to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:50,470] {manager.py:504} INFO - Created Permission View: menu access on List Roles
airflow-airflow-init-1  | [2023-03-22 14:51:50,505] {manager.py:562} INFO - Added Permission menu access on List Roles to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:50,641] {manager.py:504} INFO - Created Permission View: can read on User Stats Chart
airflow-airflow-init-1  | [2023-03-22 14:51:50,666] {manager.py:562} INFO - Added Permission can read on User Stats Chart to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:50,726] {manager.py:504} INFO - Created Permission View: menu access on User's Statistics
airflow-airflow-init-1  | [2023-03-22 14:51:50,761] {manager.py:562} INFO - Added Permission menu access on User's Statistics to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:51,002] {manager.py:504} INFO - Created Permission View: can read on Permissions
airflow-airflow-init-1  | [2023-03-22 14:51:51,028] {manager.py:562} INFO - Added Permission can read on Permissions to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:51,093] {manager.py:504} INFO - Created Permission View: menu access on Actions
airflow-airflow-init-1  | [2023-03-22 14:51:51,108] {manager.py:562} INFO - Added Permission menu access on Actions to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:51,283] {manager.py:504} INFO - Created Permission View: can read on View Menus
airflow-airflow-init-1  | [2023-03-22 14:51:51,342] {manager.py:562} INFO - Added Permission can read on View Menus to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:51,413] {manager.py:504} INFO - Created Permission View: menu access on Resources
airflow-airflow-init-1  | [2023-03-22 14:51:51,435] {manager.py:562} INFO - Added Permission menu access on Resources to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:51,622] {manager.py:504} INFO - Created Permission View: can read on Permission Views
airflow-airflow-init-1  | [2023-03-22 14:51:51,642] {manager.py:562} INFO - Added Permission can read on Permission Views to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:51,697] {manager.py:504} INFO - Created Permission View: menu access on Permission Pairs
airflow-airflow-init-1  | [2023-03-22 14:51:51,725] {manager.py:562} INFO - Added Permission menu access on Permission Pairs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:53,274] {manager.py:504} INFO - Created Permission View: can create on DAG Runs
airflow-airflow-init-1  | [2023-03-22 14:51:53,304] {manager.py:562} INFO - Added Permission can create on DAG Runs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:53,337] {manager.py:504} INFO - Created Permission View: can read on DAG Runs
airflow-airflow-init-1  | [2023-03-22 14:51:53,359] {manager.py:562} INFO - Added Permission can read on DAG Runs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:53,397] {manager.py:504} INFO - Created Permission View: can edit on DAG Runs
airflow-airflow-init-1  | [2023-03-22 14:51:53,425] {manager.py:562} INFO - Added Permission can edit on DAG Runs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:53,505] {manager.py:504} INFO - Created Permission View: can delete on DAG Runs
airflow-airflow-init-1  | [2023-03-22 14:51:53,523] {manager.py:562} INFO - Added Permission can delete on DAG Runs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:53,556] {manager.py:504} INFO - Created Permission View: menu access on DAG Runs
airflow-airflow-init-1  | [2023-03-22 14:51:53,577] {manager.py:562} INFO - Added Permission menu access on DAG Runs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:53,663] {manager.py:504} INFO - Created Permission View: menu access on Browse
airflow-airflow-init-1  | [2023-03-22 14:51:53,694] {manager.py:562} INFO - Added Permission menu access on Browse to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:53,877] {manager.py:504} INFO - Created Permission View: can read on Jobs
airflow-airflow-init-1  | [2023-03-22 14:51:53,901] {manager.py:562} INFO - Added Permission can read on Jobs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:53,942] {manager.py:504} INFO - Created Permission View: menu access on Jobs
airflow-airflow-init-1  | [2023-03-22 14:51:53,982] {manager.py:562} INFO - Added Permission menu access on Jobs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:54,153] {manager.py:504} INFO - Created Permission View: can read on Audit Logs
airflow-airflow-init-1  | [2023-03-22 14:51:54,177] {manager.py:562} INFO - Added Permission can read on Audit Logs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:54,229] {manager.py:504} INFO - Created Permission View: menu access on Audit Logs
airflow-airflow-init-1  | [2023-03-22 14:51:54,260] {manager.py:562} INFO - Added Permission menu access on Audit Logs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:54,441] {manager.py:504} INFO - Created Permission View: can create on Variables
airflow-airflow-init-1  | [2023-03-22 14:51:54,480] {manager.py:562} INFO - Added Permission can create on Variables to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:54,526] {manager.py:504} INFO - Created Permission View: can read on Variables
airflow-airflow-init-1  | [2023-03-22 14:51:54,568] {manager.py:562} INFO - Added Permission can read on Variables to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:54,611] {manager.py:504} INFO - Created Permission View: can edit on Variables
airflow-airflow-init-1  | [2023-03-22 14:51:54,638] {manager.py:562} INFO - Added Permission can edit on Variables to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:54,664] {manager.py:504} INFO - Created Permission View: can delete on Variables
airflow-airflow-init-1  | [2023-03-22 14:51:54,679] {manager.py:562} INFO - Added Permission can delete on Variables to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:54,700] {manager.py:504} INFO - Created Permission View: menu access on Variables
airflow-airflow-init-1  | [2023-03-22 14:51:54,735] {manager.py:562} INFO - Added Permission menu access on Variables to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:54,855] {manager.py:504} INFO - Created Permission View: menu access on Admin
airflow-airflow-init-1  | [2023-03-22 14:51:54,883] {manager.py:562} INFO - Added Permission menu access on Admin to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:55,052] {manager.py:504} INFO - Created Permission View: can create on Task Instances
airflow-airflow-init-1  | [2023-03-22 14:51:55,133] {manager.py:562} INFO - Added Permission can create on Task Instances to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:55,191] {manager.py:504} INFO - Created Permission View: can read on Task Instances
airflow-airflow-init-1  | [2023-03-22 14:51:55,234] {manager.py:562} INFO - Added Permission can read on Task Instances to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:55,239] {manager.py:504} INFO - Created Permission View: can edit on Task Instances
airflow-airflow-init-1  | [2023-03-22 14:51:55,295] {manager.py:562} INFO - Added Permission can edit on Task Instances to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:55,360] {manager.py:504} INFO - Created Permission View: can delete on Task Instances
airflow-airflow-init-1  | [2023-03-22 14:51:55,389] {manager.py:562} INFO - Added Permission can delete on Task Instances to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:55,439] {manager.py:504} INFO - Created Permission View: menu access on Task Instances
airflow-airflow-init-1  | [2023-03-22 14:51:55,481] {manager.py:562} INFO - Added Permission menu access on Task Instances to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:55,494] {manager.py:504} INFO - Created Permission View: clear on Task Instances
airflow-airflow-init-1  | [2023-03-22 14:51:55,506] {manager.py:562} INFO - Added Permission clear on Task Instances to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:55,534] {manager.py:504} INFO - Created Permission View: set failed on Task Instances
airflow-airflow-init-1  | [2023-03-22 14:51:55,581] {manager.py:562} INFO - Added Permission set failed on Task Instances to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:55,625] {manager.py:504} INFO - Created Permission View: set retry on Task Instances
airflow-airflow-init-1  | [2023-03-22 14:51:55,680] {manager.py:562} INFO - Added Permission set retry on Task Instances to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:55,718] {manager.py:504} INFO - Created Permission View: set running on Task Instances
airflow-airflow-init-1  | [2023-03-22 14:51:55,746] {manager.py:562} INFO - Added Permission set running on Task Instances to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:55,795] {manager.py:504} INFO - Created Permission View: set skipped on Task Instances
airflow-airflow-init-1  | [2023-03-22 14:51:55,820] {manager.py:562} INFO - Added Permission set skipped on Task Instances to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:55,878] {manager.py:504} INFO - Created Permission View: set success on Task Instances
airflow-airflow-init-1  | [2023-03-22 14:51:55,912] {manager.py:562} INFO - Added Permission set success on Task Instances to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:56,215] {manager.py:504} INFO - Created Permission View: can read on Task Reschedules
airflow-airflow-init-1  | [2023-03-22 14:51:56,252] {manager.py:562} INFO - Added Permission can read on Task Reschedules to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:56,314] {manager.py:504} INFO - Created Permission View: menu access on Task Reschedules
airflow-airflow-init-1  | [2023-03-22 14:51:56,362] {manager.py:562} INFO - Added Permission menu access on Task Reschedules to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:56,582] {manager.py:504} INFO - Created Permission View: can read on Triggers
airflow-airflow-init-1  | [2023-03-22 14:51:56,614] {manager.py:562} INFO - Added Permission can read on Triggers to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:56,658] {manager.py:504} INFO - Created Permission View: menu access on Triggers
airflow-airflow-init-1  | [2023-03-22 14:51:56,690] {manager.py:562} INFO - Added Permission menu access on Triggers to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:56,863] {manager.py:504} INFO - Created Permission View: can read on Configurations
airflow-airflow-init-1  | [2023-03-22 14:51:56,898] {manager.py:562} INFO - Added Permission can read on Configurations to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:56,947] {manager.py:504} INFO - Created Permission View: menu access on Configurations
airflow-airflow-init-1  | [2023-03-22 14:51:56,997] {manager.py:562} INFO - Added Permission menu access on Configurations to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:57,246] {manager.py:504} INFO - Created Permission View: can create on Connections
airflow-airflow-init-1  | [2023-03-22 14:51:57,283] {manager.py:562} INFO - Added Permission can create on Connections to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:57,375] {manager.py:504} INFO - Created Permission View: can read on Connections
airflow-airflow-init-1  | [2023-03-22 14:51:57,410] {manager.py:562} INFO - Added Permission can read on Connections to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:57,503] {manager.py:504} INFO - Created Permission View: can edit on Connections
airflow-airflow-init-1  | [2023-03-22 14:51:57,577] {manager.py:562} INFO - Added Permission can edit on Connections to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:57,635] {manager.py:504} INFO - Created Permission View: can delete on Connections
airflow-airflow-init-1  | [2023-03-22 14:51:57,655] {manager.py:562} INFO - Added Permission can delete on Connections to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:57,676] {manager.py:504} INFO - Created Permission View: menu access on Connections
airflow-airflow-init-1  | [2023-03-22 14:51:57,722] {manager.py:562} INFO - Added Permission menu access on Connections to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:57,896] {manager.py:504} INFO - Created Permission View: can read on SLA Misses
airflow-airflow-init-1  | [2023-03-22 14:51:57,943] {manager.py:562} INFO - Added Permission can read on SLA Misses to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:58,038] {manager.py:504} INFO - Created Permission View: menu access on SLA Misses
airflow-airflow-init-1  | [2023-03-22 14:51:58,116] {manager.py:562} INFO - Added Permission menu access on SLA Misses to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:58,143] {manager.py:504} INFO - Created Permission View: muldelete on SLA Misses
airflow-airflow-init-1  | [2023-03-22 14:51:58,183] {manager.py:562} INFO - Added Permission muldelete on SLA Misses to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:58,243] {manager.py:504} INFO - Created Permission View: mulemailsent on SLA Misses
airflow-airflow-init-1  | [2023-03-22 14:51:58,303] {manager.py:562} INFO - Added Permission mulemailsent on SLA Misses to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:58,375] {manager.py:504} INFO - Created Permission View: mulemailsentfalse on SLA Misses
airflow-airflow-init-1  | [2023-03-22 14:51:58,397] {manager.py:562} INFO - Added Permission mulemailsentfalse on SLA Misses to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:58,466] {manager.py:504} INFO - Created Permission View: mulnotificationsent on SLA Misses
airflow-airflow-init-1  | [2023-03-22 14:51:58,521] {manager.py:562} INFO - Added Permission mulnotificationsent on SLA Misses to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:58,553] {manager.py:504} INFO - Created Permission View: mulnotificationsentfalse on SLA Misses
airflow-airflow-init-1  | [2023-03-22 14:51:58,597] {manager.py:562} INFO - Added Permission mulnotificationsentfalse on SLA Misses to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:58,863] {manager.py:504} INFO - Created Permission View: can read on Plugins
airflow-airflow-init-1  | [2023-03-22 14:51:58,881] {manager.py:562} INFO - Added Permission can read on Plugins to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:58,911] {manager.py:504} INFO - Created Permission View: menu access on Plugins
airflow-airflow-init-1  | [2023-03-22 14:51:58,958] {manager.py:562} INFO - Added Permission menu access on Plugins to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:59,106] {manager.py:504} INFO - Created Permission View: can read on Providers
airflow-airflow-init-1  | [2023-03-22 14:51:59,220] {manager.py:562} INFO - Added Permission can read on Providers to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:59,254] {manager.py:504} INFO - Created Permission View: menu access on Providers
airflow-airflow-init-1  | [2023-03-22 14:51:59,310] {manager.py:562} INFO - Added Permission menu access on Providers to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:59,490] {manager.py:504} INFO - Created Permission View: can create on Pools
airflow-airflow-init-1  | [2023-03-22 14:51:59,536] {manager.py:562} INFO - Added Permission can create on Pools to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:59,586] {manager.py:504} INFO - Created Permission View: can read on Pools
airflow-airflow-init-1  | [2023-03-22 14:51:59,612] {manager.py:562} INFO - Added Permission can read on Pools to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:59,630] {manager.py:504} INFO - Created Permission View: can edit on Pools
airflow-airflow-init-1  | [2023-03-22 14:51:59,666] {manager.py:562} INFO - Added Permission can edit on Pools to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:59,724] {manager.py:504} INFO - Created Permission View: can delete on Pools
airflow-airflow-init-1  | [2023-03-22 14:51:59,747] {manager.py:562} INFO - Added Permission can delete on Pools to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:59,793] {manager.py:504} INFO - Created Permission View: menu access on Pools
airflow-airflow-init-1  | [2023-03-22 14:51:59,836] {manager.py:562} INFO - Added Permission menu access on Pools to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:59,941] {manager.py:504} INFO - Created Permission View: can create on XComs
airflow-airflow-init-1  | [2023-03-22 14:51:59,955] {manager.py:562} INFO - Added Permission can create on XComs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:51:59,972] {manager.py:504} INFO - Created Permission View: can read on XComs
airflow-airflow-init-1  | [2023-03-22 14:51:59,998] {manager.py:562} INFO - Added Permission can read on XComs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:00,018] {manager.py:504} INFO - Created Permission View: can delete on XComs
airflow-airflow-init-1  | [2023-03-22 14:52:00,033] {manager.py:562} INFO - Added Permission can delete on XComs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:00,054] {manager.py:504} INFO - Created Permission View: menu access on XComs
airflow-airflow-init-1  | [2023-03-22 14:52:00,088] {manager.py:562} INFO - Added Permission menu access on XComs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:00,216] {manager.py:504} INFO - Created Permission View: menu access on DAG Dependencies
airflow-airflow-init-1  | [2023-03-22 14:52:00,255] {manager.py:562} INFO - Added Permission menu access on DAG Dependencies to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:00,542] {manager.py:504} INFO - Created Permission View: menu access on DAGs
airflow-airflow-init-1  | [2023-03-22 14:52:00,590] {manager.py:562} INFO - Added Permission menu access on DAGs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:00,667] {manager.py:504} INFO - Created Permission View: menu access on Datasets
airflow-airflow-init-1  | [2023-03-22 14:52:00,767] {manager.py:562} INFO - Added Permission menu access on Datasets to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:00,812] {manager.py:504} INFO - Created Permission View: menu access on Documentation
airflow-airflow-init-1  | [2023-03-22 14:52:00,826] {manager.py:562} INFO - Added Permission menu access on Documentation to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:00,854] {manager.py:504} INFO - Created Permission View: menu access on Docs
airflow-airflow-init-1  | [2023-03-22 14:52:00,889] {manager.py:562} INFO - Added Permission menu access on Docs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:14,385] {providers_manager.py:238} INFO - Optional provider feature disabled when importing 'airflow.providers.google.leveldb.hooks.leveldb.LevelDBHook' from 'apache-airflow-providers-google' package
airflow-airflow-init-1  | /home/airflow/.local/lib/python3.7/site-packages/snowflake/connector/options.py:108 UserWarning: You have an incompatible version of 'pyarrow' installed (9.0.0), please install a version that adheres to: 'pyarrow<10.1.0,>=10.0.1; extra == "pandas"'
airflow-airflow-init-1  | [2023-03-22 14:52:28,558] {providers_manager.py:238} INFO - Optional provider feature disabled when importing 'airflow.providers.google.leveldb.hooks.leveldb.LevelDBHook' from 'apache-airflow-providers-google' package
airflow-airflow-init-1  | [2023-03-22 14:52:33,164] {manager.py:504} INFO - Created Permission View: can read on DAGs
airflow-airflow-init-1  | [2023-03-22 14:52:33,202] {manager.py:504} INFO - Created Permission View: can edit on DAGs
airflow-airflow-init-1  | [2023-03-22 14:52:33,226] {manager.py:504} INFO - Created Permission View: can delete on DAGs
airflow-airflow-init-1  | [2023-03-22 14:52:33,891] {manager.py:504} INFO - Created Permission View: can read on Datasets
airflow-airflow-init-1  | [2023-03-22 14:52:34,135] {manager.py:504} INFO - Created Permission View: can read on ImportError
airflow-airflow-init-1  | [2023-03-22 14:52:34,772] {manager.py:504} INFO - Created Permission View: can read on DAG Code
airflow-airflow-init-1  | [2023-03-22 14:52:34,839] {manager.py:504} INFO - Created Permission View: can read on DAG Warnings
airflow-airflow-init-1  | [2023-03-22 14:52:35,614] {manager.py:243} INFO - Inserted Role: Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,630] {manager.py:562} INFO - Added Permission can read on Audit Logs to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,637] {manager.py:562} INFO - Added Permission can read on DAGs to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,651] {manager.py:504} INFO - Created Permission View: can read on DAG Dependencies
airflow-airflow-init-1  | [2023-03-22 14:52:35,657] {manager.py:562} INFO - Added Permission can read on DAG Dependencies to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,663] {manager.py:562} INFO - Added Permission can read on DAG Code to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,668] {manager.py:562} INFO - Added Permission can read on DAG Runs to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,674] {manager.py:562} INFO - Added Permission can read on Datasets to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,680] {manager.py:562} INFO - Added Permission can read on ImportError to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,685] {manager.py:562} INFO - Added Permission can read on DAG Warnings to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,690] {manager.py:562} INFO - Added Permission can read on Jobs to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,695] {manager.py:562} INFO - Added Permission can read on My Password to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,700] {manager.py:562} INFO - Added Permission can edit on My Password to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,705] {manager.py:562} INFO - Added Permission can read on My Profile to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,710] {manager.py:562} INFO - Added Permission can edit on My Profile to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,715] {manager.py:562} INFO - Added Permission can read on Plugins to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,720] {manager.py:562} INFO - Added Permission can read on SLA Misses to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,725] {manager.py:562} INFO - Added Permission can read on Task Instances to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,738] {manager.py:504} INFO - Created Permission View: can read on Task Logs
airflow-airflow-init-1  | [2023-03-22 14:52:35,743] {manager.py:562} INFO - Added Permission can read on Task Logs to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,748] {manager.py:562} INFO - Added Permission can read on XComs to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,766] {manager.py:504} INFO - Created Permission View: can read on Website
airflow-airflow-init-1  | [2023-03-22 14:52:35,772] {manager.py:562} INFO - Added Permission can read on Website to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,778] {manager.py:562} INFO - Added Permission menu access on Browse to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,783] {manager.py:562} INFO - Added Permission menu access on DAGs to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,789] {manager.py:562} INFO - Added Permission menu access on DAG Dependencies to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,794] {manager.py:562} INFO - Added Permission menu access on DAG Runs to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,799] {manager.py:562} INFO - Added Permission menu access on Datasets to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,804] {manager.py:562} INFO - Added Permission menu access on Documentation to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,810] {manager.py:562} INFO - Added Permission menu access on Docs to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,815] {manager.py:562} INFO - Added Permission menu access on Jobs to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,821] {manager.py:562} INFO - Added Permission menu access on Audit Logs to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,826] {manager.py:562} INFO - Added Permission menu access on Plugins to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,831] {manager.py:562} INFO - Added Permission menu access on SLA Misses to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,837] {manager.py:562} INFO - Added Permission menu access on Task Instances to role Viewer
airflow-airflow-init-1  | [2023-03-22 14:52:35,844] {manager.py:243} INFO - Inserted Role: User
airflow-airflow-init-1  | [2023-03-22 14:52:35,851] {manager.py:562} INFO - Added Permission can read on Audit Logs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,857] {manager.py:562} INFO - Added Permission can read on DAGs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,870] {manager.py:562} INFO - Added Permission can read on DAG Dependencies to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,875] {manager.py:562} INFO - Added Permission can read on DAG Code to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,881] {manager.py:562} INFO - Added Permission can read on DAG Runs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,887] {manager.py:562} INFO - Added Permission can read on Datasets to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,893] {manager.py:562} INFO - Added Permission can read on ImportError to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,899] {manager.py:562} INFO - Added Permission can read on DAG Warnings to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,905] {manager.py:562} INFO - Added Permission can read on Jobs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,911] {manager.py:562} INFO - Added Permission can read on My Password to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,916] {manager.py:562} INFO - Added Permission can edit on My Password to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,921] {manager.py:562} INFO - Added Permission can read on My Profile to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,926] {manager.py:562} INFO - Added Permission can edit on My Profile to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,932] {manager.py:562} INFO - Added Permission can read on Plugins to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,947] {manager.py:562} INFO - Added Permission can read on SLA Misses to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,959] {manager.py:562} INFO - Added Permission can read on Task Instances to role User
airflow-airflow-init-1  | [2023-03-22 14:52:35,990] {manager.py:562} INFO - Added Permission can read on Task Logs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,009] {manager.py:562} INFO - Added Permission can read on XComs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,044] {manager.py:562} INFO - Added Permission can read on Website to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,062] {manager.py:562} INFO - Added Permission menu access on Browse to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,067] {manager.py:562} INFO - Added Permission menu access on DAGs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,073] {manager.py:562} INFO - Added Permission menu access on DAG Dependencies to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,078] {manager.py:562} INFO - Added Permission menu access on DAG Runs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,083] {manager.py:562} INFO - Added Permission menu access on Datasets to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,089] {manager.py:562} INFO - Added Permission menu access on Documentation to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,095] {manager.py:562} INFO - Added Permission menu access on Docs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,100] {manager.py:562} INFO - Added Permission menu access on Jobs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,106] {manager.py:562} INFO - Added Permission menu access on Audit Logs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,111] {manager.py:562} INFO - Added Permission menu access on Plugins to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,117] {manager.py:562} INFO - Added Permission menu access on SLA Misses to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,123] {manager.py:562} INFO - Added Permission menu access on Task Instances to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,128] {manager.py:562} INFO - Added Permission can edit on DAGs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,134] {manager.py:562} INFO - Added Permission can delete on DAGs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,139] {manager.py:562} INFO - Added Permission can create on Task Instances to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,145] {manager.py:562} INFO - Added Permission can edit on Task Instances to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,150] {manager.py:562} INFO - Added Permission can delete on Task Instances to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,157] {manager.py:562} INFO - Added Permission can create on DAG Runs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,163] {manager.py:562} INFO - Added Permission can edit on DAG Runs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,168] {manager.py:562} INFO - Added Permission can delete on DAG Runs to role User
airflow-airflow-init-1  | [2023-03-22 14:52:36,175] {manager.py:243} INFO - Inserted Role: Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,189] {manager.py:562} INFO - Added Permission can read on Audit Logs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,207] {manager.py:562} INFO - Added Permission can read on DAGs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,228] {manager.py:562} INFO - Added Permission can read on DAG Dependencies to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,242] {manager.py:562} INFO - Added Permission can read on DAG Code to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,251] {manager.py:562} INFO - Added Permission can read on DAG Runs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,261] {manager.py:562} INFO - Added Permission can read on Datasets to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,289] {manager.py:562} INFO - Added Permission can read on ImportError to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,309] {manager.py:562} INFO - Added Permission can read on DAG Warnings to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,314] {manager.py:562} INFO - Added Permission can read on Jobs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,319] {manager.py:562} INFO - Added Permission can read on My Password to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,325] {manager.py:562} INFO - Added Permission can edit on My Password to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,330] {manager.py:562} INFO - Added Permission can read on My Profile to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,335] {manager.py:562} INFO - Added Permission can edit on My Profile to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,340] {manager.py:562} INFO - Added Permission can read on Plugins to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,345] {manager.py:562} INFO - Added Permission can read on SLA Misses to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,351] {manager.py:562} INFO - Added Permission can read on Task Instances to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,362] {manager.py:562} INFO - Added Permission can read on Task Logs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,367] {manager.py:562} INFO - Added Permission can read on XComs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,379] {manager.py:562} INFO - Added Permission can read on Website to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,384] {manager.py:562} INFO - Added Permission menu access on Browse to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,389] {manager.py:562} INFO - Added Permission menu access on DAGs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,394] {manager.py:562} INFO - Added Permission menu access on DAG Dependencies to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,399] {manager.py:562} INFO - Added Permission menu access on DAG Runs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,404] {manager.py:562} INFO - Added Permission menu access on Datasets to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,410] {manager.py:562} INFO - Added Permission menu access on Documentation to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,415] {manager.py:562} INFO - Added Permission menu access on Docs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,420] {manager.py:562} INFO - Added Permission menu access on Jobs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,426] {manager.py:562} INFO - Added Permission menu access on Audit Logs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,430] {manager.py:562} INFO - Added Permission menu access on Plugins to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,436] {manager.py:562} INFO - Added Permission menu access on SLA Misses to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,443] {manager.py:562} INFO - Added Permission menu access on Task Instances to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,449] {manager.py:562} INFO - Added Permission can edit on DAGs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,454] {manager.py:562} INFO - Added Permission can delete on DAGs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,461] {manager.py:562} INFO - Added Permission can create on Task Instances to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,466] {manager.py:562} INFO - Added Permission can edit on Task Instances to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,472] {manager.py:562} INFO - Added Permission can delete on Task Instances to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,478] {manager.py:562} INFO - Added Permission can create on DAG Runs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,483] {manager.py:562} INFO - Added Permission can edit on DAG Runs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,490] {manager.py:562} INFO - Added Permission can delete on DAG Runs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,495] {manager.py:562} INFO - Added Permission can read on Configurations to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,501] {manager.py:562} INFO - Added Permission menu access on Admin to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,507] {manager.py:562} INFO - Added Permission menu access on Configurations to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,513] {manager.py:562} INFO - Added Permission menu access on Connections to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,518] {manager.py:562} INFO - Added Permission menu access on Pools to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,524] {manager.py:562} INFO - Added Permission menu access on Variables to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,574] {manager.py:562} INFO - Added Permission menu access on XComs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,579] {manager.py:562} INFO - Added Permission can create on Connections to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,585] {manager.py:562} INFO - Added Permission can read on Connections to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,591] {manager.py:562} INFO - Added Permission can edit on Connections to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,596] {manager.py:562} INFO - Added Permission can delete on Connections to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,600] {manager.py:562} INFO - Added Permission can create on Pools to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,605] {manager.py:562} INFO - Added Permission can read on Pools to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,610] {manager.py:562} INFO - Added Permission can edit on Pools to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,615] {manager.py:562} INFO - Added Permission can delete on Pools to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,619] {manager.py:562} INFO - Added Permission can read on Providers to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,625] {manager.py:562} INFO - Added Permission can create on Variables to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,629] {manager.py:562} INFO - Added Permission can read on Variables to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,634] {manager.py:562} INFO - Added Permission can edit on Variables to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,639] {manager.py:562} INFO - Added Permission can delete on Variables to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,644] {manager.py:562} INFO - Added Permission can delete on XComs to role Op
airflow-airflow-init-1  | [2023-03-22 14:52:36,649] {manager.py:562} INFO - Added Permission can read on DAGs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:36,659] {manager.py:562} INFO - Added Permission can read on DAG Dependencies to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:36,664] {manager.py:562} INFO - Added Permission can read on DAG Code to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:36,669] {manager.py:562} INFO - Added Permission can read on Datasets to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:36,674] {manager.py:562} INFO - Added Permission can read on ImportError to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:36,679] {manager.py:562} INFO - Added Permission can read on DAG Warnings to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:36,690] {manager.py:562} INFO - Added Permission can read on Task Logs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:36,702] {manager.py:562} INFO - Added Permission can read on Website to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:36,708] {manager.py:562} INFO - Added Permission can edit on DAGs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:36,713] {manager.py:562} INFO - Added Permission can delete on DAGs to role Admin
airflow-airflow-init-1  | [2023-03-22 14:52:37,546] {manager.py:212} INFO - Added user airflow
airflow-airflow-init-1  | User "airflow" created with role "Admin"
airflow-airflow-init-1  | 2.5.2
airflow-airflow-init-1 exited with code 0
```

## Execution

### #( 03/22/23@ 3:33PM )( donbuddenbaum@donbs-imac ):~/Documents/airflow

docker ps
```
CONTAINER ID   IMAGE                           COMMAND                  CREATED         STATUS                   PORTS                    NAMES
01ba13204297   apache/airflow:2.5.2            "/usr/bin/dumb-init …"   2 minutes ago   Up 2 minutes (healthy)   8080/tcp                 airflow-airflow-scheduler-1
c86cd097943e   apache/airflow:2.5.2            "/usr/bin/dumb-init …"   2 minutes ago   Up 2 minutes (healthy)   0.0.0.0:8080->8080/tcp   airflow-airflow-webserver-1
264ec1245f26   apache/airflow:2.5.2            "/usr/bin/dumb-init …"   2 minutes ago   Up 2 minutes (healthy)   8080/tcp                 airflow-airflow-triggerer-1
db4aeb36a8b1   apache/airflow:2.5.2            "/usr/bin/dumb-init …"   2 minutes ago   Up 2 minutes (healthy)   8080/tcp                 airflow-airflow-worker-1
fa59be37bc46   redis:latest                    "docker-entrypoint.s…"   5 hours ago     Up 5 hours (healthy)     6379/tcp                 airflow-redis-1
aca16b14bec8   postgres:13                     "docker-entrypoint.s…"   5 hours ago     Up 5 hours (healthy)     5432/tcp                 airflow-postgres-1
```
## UI

http://localhost:8080 

![image](img.png)

## Flower

### #( 03/22/23@ 4:00PM )( donbuddenbaum@donbs-imac ):~/Documents/airflow
docker compose up flower

```
[+] Running 4/4
⠿ Container airflow-postgres-1      Created                                                                                                                      0.0s
⠿ Container airflow-redis-1         Created                                                                                                                      0.0s
⠿ Container airflow-airflow-init-1  Created                                                                                                                      0.0s
⠿ Container airflow-flower-1        Created                                                                                                                      0.1s
Attaching to airflow-flower-1
airflow-flower-1  |
airflow-flower-1  | BACKEND=redis
airflow-flower-1  | DB_HOST=redis
airflow-flower-1  | DB_PORT=6379
airflow-flower-1  |
airflow-flower-1  | /home/airflow/.local/lib/python3.7/site-packages/airflow/models/base.py:49 MovedIn20Warning: Deprecated API features detected! These feature(s) are not compatible with SQLAlchemy 2.0. To prevent incompatible upgrades prior to updating applications, ensure requirements files are pinned to "sqlalchemy<2.0". Set environment variable SQLALCHEMY_WARN_20=1 to show all deprecation warnings.  Set environment variable SQLALCHEMY_SILENCE_UBER_WARNING=1 to silence this message. (Background on SQLAlchemy 2.0 at: https://sqlalche.me/e/b8d9)
airflow-flower-1  | [2023-03-22 20:02:06,558] {command.py:165} INFO - Visit me at http://0.0.0.0:5555
airflow-flower-1  | [2023-03-22 20:02:06,602] {command.py:170} INFO - Broker: redis://redis:6379/0
airflow-flower-1  | [2023-03-22 20:02:06,609] {command.py:173} INFO - Registered tasks:
airflow-flower-1  | ['airflow.executors.celery_executor.execute_command',
airflow-flower-1  |  'celery.accumulate',
airflow-flower-1  |  'celery.backend_cleanup',
airflow-flower-1  |  'celery.chain',
airflow-flower-1  |  'celery.chord',
airflow-flower-1  |  'celery.chord_unlock',
airflow-flower-1  |  'celery.chunks',
airflow-flower-1  |  'celery.group',
airflow-flower-1  |  'celery.map',
airflow-flower-1  |  'celery.starmap']
airflow-flower-1  | [2023-03-22 20:02:06,610] {command.py:177} WARNING - Running without authentication
airflow-flower-1  | [2023-03-22 20:02:06,626] {mixins.py:225} INFO - Connected to redis://redis:6379/0
airflow-flower-1  | [2023-03-22 20:02:07,747] {inspector.py:42} WARNING - Inspect method active_queues failed
airflow-flower-1  | [2023-03-22 20:02:07,750] {inspector.py:42} WARNING - Inspect method revoked failed
airflow-flower-1  | [2023-03-22 20:02:07,772] {inspector.py:42} WARNING - Inspect method conf failed
airflow-flower-1  | [2023-03-22 20:02:07,773] {inspector.py:42} WARNING - Inspect method reserved failed
airflow-flower-1  | [2023-03-22 20:02:07,773] {inspector.py:42} WARNING - Inspect method registered failed
airflow-flower-1  | [2023-03-22 20:02:07,779] {inspector.py:42} WARNING - Inspect method active failed
airflow-flower-1  | [2023-03-22 20:02:07,784] {inspector.py:42} WARNING - Inspect method scheduled failed
airflow-flower-1  | [2023-03-22 20:02:07,785] {inspector.py:42} WARNING - Inspect method stats failed
```
![img_1.png](img_1.png)