# Data team ide
- lines between the jobs are blurry
- some companies have 1 person for all roles
- larger companies have jobs more narrow

## Data engineer
- custom data ingestion 
- overall pipeline orchestration
- develop and deploy ML endpoints
- develop and deploy data platform
- data warehouse performance improvement

## Analytics engineer
- clean and ready data for analysis
- apply software engineering practices to analytics code
- data documentation and definitions
- train business users on how to use a data platform data visualization tools

## Data analyst
- deep insights work (Why did churn spike last month? || What are the best acquisition channels?)
- work with business users to understand data reqs
- build critical dashboards
- forecasting

# DBT Fundamentals
- lost of data sources
- move them into data platforms
- use BI tools 

## dbt comes in
- dbt helps with data transformation on top of data platform (data warehouse tools) 
- transformation process in SQL using DAGs (T of ELT)
- dbt connects directly to your data platform to model data and develop, test, document, deploy your data transformations

# 2 ways to run dbt
## dbt Cloud
- online IDE and an interface
## dbt CLI
- locally

> dbt is designed to handle the transformation layer of extract-load-transform framework for data platforms. dbt creates a connection to a data platform and runs a SQL code against the warehouse to transform the data
> version control using git

# DBT Commands
- dbt test
- dbt run or dbt run --select filename
- dbt docs generate
- dbt build contains test and run

# Environments
- develop
- deploy


# Training
Use SQL and jinja

# dbt Models
- models are SQL statements
- by executing a dbt run you execute a SQL (model) against the data warehouse and you can see the warehouse (Redshift) changes
- use preview button which does not make any changes to the warehouse

# Questions
- DDL
- DML
- CTE

# Modular thinking
- imagine building a car - build its parts and then assemble -- do the same with data and tables
- these pre-assembled tables are called STAGING MODELS
- ref function allows me to pull info from materialized tables in data warehouse
- compile button lets the staging models to resolve the dependencies allowing me to work on my own development environment

# Traditional modeling
How should data be organized in the data warehouse was optimized for data redundancy as storage was expensive
With dbt we can focus on agile analytics bc we have cheap storage and strong computation
- Star Schema
- Kimball
- Data Vault

# Naming conventions
- Sources
- Staging
- Intermediate
- Fact
- Dimension

# Sources
- raw sources
- document the raw tables and make it easier to track the sources, use aliases
- use just 1 config .yml file and change only one name instead of all references
- source freshness

# Data reliability and dbt testing
- broken dashboards get fixed
- suddenly something brakes
    - dbt allows you to scale tests and develop when the dashboard is going to break
    - try out everything in the development stage
    - https://www.youtube.com/watch?v=M_cNspn2XsE



Continue here:
https://courses.getdbt.com/courses/take/fundamentals/texts/27962320-learning-objectives

# Documentation
- put together the coding and the documentation in .yml files
- what queries you used to create this dashboard

# Deployment
- deploy your dbt project means running dbt jobs on a schedule
- merge the two branches = development and deployment