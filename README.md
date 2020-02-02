This is [Airflow](https://airflow.apache.org/) setup POC based on Docker.

Ressources:

- [ETL best practices with Airflow documentation site](https://gtoonstra.github.io/etl-with-airflow/index.html)

```
$ docker-compose pull
```

```
$ docker-compose up -d
```

How to enter in Airflow shell:

```
$ docker-compose exec webserver /entrypoint.sh bash
airflow list_dags -r
[2020-02-02 18:07:03,162] {{settings.py:254}} INFO - settings.configure_orm(): Using pool settings. pool_size=5, max_overflow=10, pool_recycle=1800, pid=15883
[2020-02-02 18:07:03,684] {{__init__.py:51}} INFO - Using executor LocalExecutor
[2020-02-02 18:07:03,684] {{dagbag.py:403}} INFO - Filling up the DagBag from /usr/local/airflow/dags


-------------------------------------------------------------------
DAGS
-------------------------------------------------------------------
tutorial



-------------------------------------------------------------------
DagBag loading stats for /usr/local/airflow/dags
-------------------------------------------------------------------
Number of DAGs: 1
Total task number: 3
DagBag parsing time: 0.02192
---------+----------+---------+----------+-------------
file     | duration | dag_num | task_num | dags
---------+----------+---------+----------+-------------
/tuto.py | 0.02192  |       1 |        3 | ['tutorial']
---------+----------+---------+----------+-------------
```

```
$ airflow list_tasks tutorial
[2020-02-02 18:07:22,762] {{settings.py:254}} INFO - settings.configure_orm(): Using pool settings. pool_size=5, max_overflow=10, pool_recycle=1800, pid=15996
[2020-02-02 18:07:23,224] {{__init__.py:51}} INFO - Using executor LocalExecutor
[2020-02-02 18:07:23,224] {{dagbag.py:403}} INFO - Filling up the DagBag from /usr/local/airflow/dags
print_date
sleep
templated
```