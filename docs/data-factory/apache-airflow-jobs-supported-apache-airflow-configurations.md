---
title: Supported Apache Airflow configurations
description: This article enumerates the Apache Airflow configurations supported by the Apache Airflow Job.
author: nabhishek
ms.author: abnarain
ms.reviewer: abnarain
ms.topic: conceptual
ms.custom:
  - build-2024
ms.date: 04/24/2024
---

# Supported Apache Airflow configurations

> [!NOTE]
> Apache Airflow job is powered by Apache Airflow. </br> [Apache Airflow](https://airflow.apache.org/) is an open-source platform used to programmatically create, schedule, and monitor complex data workflows. It allows you to define a set of tasks, called operators, that can be combined into directed acyclic graphs (DAGs) to represent data pipelines.

In Apache Airflow Job, Apache Airflow configurations can be integrated with the platform's runtime as key-value pairs. While the `airflow.cfg` isn't directly accessible in the UI, users can override these configurations via the UI's "Airflow Configuration overrides" section, retaining access to other `airflow.cfg` settings. Developers have the flexibility to override most Apache Airflow configurations within Apache Airflow Job, `except for those explicitly outlined in a provided table`.

## Airflow configurations reference

For more information on Apache Airflow configurations, see [Configuration Reference](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html).

The following table contains the list of configurations that don't support overrides.

| Configuration                                                                                                                                                            | Description                                                                                                                                                                                 | Default value                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| [AIRFLOW**CELERY**FLOWER_URL_PREFIX](https://airflow.apache.org/docs/apache-airflow-providers-celery/stable/configurations-ref.html#flower-url-prefix)                   | The root URL for Flower.                                                                                                                                                                    | ""                                                                    |
| [AIRFLOW**CORE**DAGS_FOLDER](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#dags-folder)                                                  | The path of the folder where Airflow pipelines live.                                                                                                                                        | AIRFLOW_DAGS_FOLDER                                                   |
| [AIRFLOW**CORE**DONOT_PICKLE](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#donot-pickle)                                                | Whether to disable pickling DAGs.                                                                                                                                                           | False                                                                 |
| [AIRFLOW**CORE**ENABLE_XCOM_PICKLING](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#enable-xcom-pickling)                                | Whether to enable pickling for xcom.                                                                                                                                                        | False                                                                 |
| [AIRFLOW**CORE**EXECUTOR](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#executor)                                                        | The executor class that Airflow should use.                                                                                                                                                 | CeleryExecutor                                                        |
| [AIRFLOW**CORE**FERNET_KEY](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#fernet-key)                                                    | Secret key to save connection passwords in the database.                                                                                                                                    | AIRFLOW_FERNET_KEY                                                    |
| [AIRFLOW**CORE**DAGS_ARE_PAUSED_AT_CREATION](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#dags-are-paused-at-creation)                  | Are DAGs paused by default at creation?                                                                                                                                                     | False                                                                 |
| [AIRFLOW**CORE**PLUGINS_FOLDER](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#plugins-folder)                                            | Path to the folder that contains Airflow plugins.                                                                                                                                           | AIRFLOW_PLUGINS_FOLDER                                                |
| [AIRFLOW**LOGGING**BASE_LOG_FOLDER](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#base-log-folder)                                       | The folder where Airflow should store its log files.                                                                                                                                        | /opt/airflow/logs                                                     |
| [AIRFLOW**LOGGING**LOG_FILENAME_TEMPLATE](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#log-filename-template)                           | Formatting for how Airflow generates file names or paths for each task run.                                                                                                                 | {{ ti.dag_id }}/{{ ti.task_id }}/{{ ts }}/{{ try_number }}.log        |
| [AIRFLOW**LOGGING**DAG_PROCESSOR_MANAGER_LOG_LOCATION](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#dag-processor-manager-log-location) | Full path of the `dag_processor_manager` log file.                                                                                                                                          | /opt/airflow/logs/dag_processor_manager/dag_processor_manager.log     |
| [AIRFLOW**LOGGING**LOGGING_CONFIG_CLASS](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#logging-config-class)                             | Logging config class specifies the logging configuration. This class has to be on the Python class path.                                                                                    | log_config.LOGGING_CONFIG                                             |
| [AIRFLOW**LOGGING**COLORED_LOG_FORMAT](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#colored-log-format)                                 | Log format for when Colored logs is enabled.                                                                                                                                                | [%(asctime)s] {{%(filename)s:%(lineno)d}} %(levelname)s - %(message)s |
| [AIRFLOW**LOGGING**LOGGING_LEVEL](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#logging-level)                                           | Logging level.                                                                                                                                                                              | INFO                                                                  |
| [AIRFLOW**METRICS**STATSD_ON](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#statsd-on)                                                   | Enables sending metrics to StatsD.                                                                                                                                                          | True                                                                  |
| [AIRFLOW**METRICS**STATSD_HOST](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#statsd-host)                                               | Hostname of the StatsD server.                                                                                                                                                              | geneva-services                                                       |
| [AIRFLOW**METRICS**STATSD_PORT](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#statsd-port)                                               | Port number of the StatsD server.                                                                                                                                                           | 8125                                                                  |
| AIRFLOW**METRICS**STATSD_PREFIX                                                                                                                                          | Prefix for all Airflow metrics sent to StatsD.                                                                                                                                              | AirflowMetrics                                                        |
| [AIRFLOW**SCHEDULER**CHILD_PROCESS_LOG_DIRECTORY](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#child-process-log-directory)             | Path of the directory where the Airflow scheduler writes its child process logs.                                                                                                            | /opt/airflow/logs/scheduler                                           |
| [AIRFLOW**SCHEDULER**DAG_DIR_LIST_INTERVAL](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#dag-dir-list-interval)                         | How often (in seconds) to scan the DAGs' directory for new files. Default to 5 minutes.                                                                                                     | 5                                                                     |
| [AIRFLOW**WEBSERVER**BASE_URL](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#webserver)                                                  | The base URL of your website because Airflow can't guess what domain or cname you're using. This URL is used in automated emails that Airflow sends to point links to the right web server. | https://localhost:8080                                                |
| [AIRFLOW**WEBSERVER**COOKIE_SAMESITE](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#cookie-samesite)                                     | Set samesite policy on session cookie.                                                                                                                                                      | None                                                                  |
| [AIRFLOW**WEBSERVER**COOKIE_SECURE](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#cookie-secure)                                         | Set secure flag on session cookie.                                                                                                                                                          | True                                                                  |
| [AIRFLOW**WEBSERVER**EXPOSE_CONFIG](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#expose-config)                                         | Expose the configuration file in the web server.                                                                                                                                            | False                                                                 |
| AIRFLOW**WEBSERVER**AUTHENTICATE                                                                                                                                         | Authenticate user to sign in to the Airflow UI.                                                                                                                                             | True                                                                  |
| AIRFLOW**WEBSERVER**AUTH_BACKEND                                                                                                                                         |                                                                                                                                                                                             | airflow.api.auth.backend.basic_auth                                   |
| [AIRFLOW**WEBSERVER**RELOAD_ON_PLUGIN_CHANGE](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#reload-on-plugin-change)                     | If set to True, Airflow tracks files in the `plugins_folder` directory. When it detects changes, then reload the gunicorn.                                                                  | True                                                                  |
| [AIRFLOW**WEBSERVER**SECRET_KEY](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#secret-key)                                               | Secret key used to run your flask app.                                                                                                                                                      | AIRFLOW_FERNET_KEY                                                    |
| [AIRFLOW**API**AUTH_BACKEND](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#auth-backends)                                                | Comma-separated list of auth backends to authenticate users of the API.                                                                                                                     | airflow.api.auth.backend.basic_auth                                   |
| [AIRFLOW**API**ENABLE_EXPERIMENTAL_API](https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html#enable-experimental-api)                           |                                                                                                                                                                                             | True                                                                  |

## Related Content

[Quickstart: Create an Apache Airflow Job](../data-factory/create-apache-airflow-jobs.md)