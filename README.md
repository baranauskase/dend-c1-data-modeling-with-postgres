# Introduction
A startup called Sparkify wants to analyze the data they've been collecting on 
songs and user activity on their new music streaming app. The analytics team is 
particularly interested in understanding what songs users are listening to. 
Currently, they don't have an easy way to query their data, which resides in a 
directory of JSON logs on user activity on the app, as well as a directory with 
JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed 
to optimize queries on song play analysis, and bring you on the project. My role 
is to create a database schema and ETL pipeline for this analysis. I'll be able 
to test my database and ETL pipeline by running queries given to me by the 
analytics team from Sparkify and compare my results with their expected results.

# Project Description
In this project, I'll apply what I've learned on data modeling with Postgres and 
build an ETL pipeline using Python. To complete the project, I will need to 
define fact and dimension tables for a star schema for a particular analytic 
focus, and write an ETL pipeline that transfers data from files in two local 
directories into these tables in Postgres using Python and SQL.

# Setting up development environment
This project can be implemented on a local machine using Python3 and Docker. The 
instructions here assume that VS Code is used as a development environment,
especially the way `ipython` kernel is setup instead of using `jupyter notebook`.
It is good practice not to contaminate your global Python installation by
installing dependencies that are specific to this project. The first step 
therefore is to create a virtual Python environment. We will utilise the most
basic approach by creating an environment using `venv` module. At the root of 
the project run the following commands:

```
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
ipython kernel install --user --name=dend-c1-data-modeling-with-postgres
```

Now that the virtual environment is ready. The next step is spin a `PostgresSQL`
server. The cleanest way is to run an official `Docker` container and you can do
so by deploying the stack.

```
docker stack deploy -c postgres-stack.yml postgres
```
If your `Docker` engine is not running in `swarm` mode then it is also possible
use `docker-compose` to deploy this stack.