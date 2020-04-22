# airflow-mariadb
Run Airflow on MariaDB repository

This example reviews installing Apache Airflow and re-configuring it to use MariaDB.

The procedures for setting up the AWS instance and connecting to it are outlined [here](https://github.com/spineo/local-yum-mariadb/blob/master/README.md). For this example, we will install Airflow in the same Linux RHEL 8 AWS instance that is running the master MariaDB node.

First we will need to install/configure Python36 and Pip (the recommended way to install Apache Airflow)

As _root_ user (or using _sudo_) run the following commands:

```
yum install python36
yum install python36-devel
```

Python36 should automatically install _pip3_ which will be used to install Airflow


As self, we will install Apache Airflow as follows (we can subsequently set AIRFLOW_HOME in the ~/.bashrc):

```
export AIRFLOW_HOME=~/airflow
pip3 install --user apache-airflow
```

 By default, Airflow uses the SQLite database so we will run _airflow initdb_ to reconfigure the application to use MariaDB.

