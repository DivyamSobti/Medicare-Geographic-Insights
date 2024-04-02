# Medicare-Geographic-Insights

The project aims to build a single source of true data storage for large healthcare datasets using Spark and S3. Some dashboards are also made in this project for visualization.
Tech Stack

    Data lake: Amazon S3

    Data source: PostgreSQL

    Data read storage: MySQL on Amazone RDS

    Processing layer: Apache Spark on EMR

    Visualization: Power BI

Architecture

The architecture of this project is presented as follows:

architecture_2

    Data is sourced from PostgreSQL and ingested into raw zone of Data Lake hosted on S3.
    Raw data is cleansed and standardized before moving to cleansed zone.
    Cleansed data is transformed into reportable form and loaded into curated zone.
    Publish data from curated zone to Data read storage for higher performance report when connection from BI Tool.
    Reports are created in Power BI from the data in MySQL.

Data Source

    Source of raw data is from CMS. Data used is Medicare Part D.
    Data source in PostgreSQL has 4 tables, total size around 10 GB:
        Prescriber_drug: ~ 25M rows
        Prescriber: ~ 1.1M rows
        Drug: ~115K rows
        State: ~30K rows

Visualization

Some dashboards create from the data from data read storage

    Drug report
