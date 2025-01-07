# Pipeline built with Reddit, Apache Airflow, PostgreSQL, Celery, and AWS

Comprehensive data pipeline that extracts, transforms, and loads (ETL) Reddit data into a Redshift data-warehouse. This leverages a combination of tools and services including Apache Airflow, Celery, PostgreSQL, Amazon S3, AWS Glue, Amazon Athena, and Amazon Redshift.

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Prereqs](#prereqs)
- [System Setup](#system-setup)

## Overview

The pipeline is designed to:

1. Extract data from Reddit using its API.
2. Store the raw data into a S3 bucket from Apache Airflow.
3. Transform the data using AWS Glue and AWS Athena.
4. Load the transformed data into AWS Redshift for analytics and querying.

## Architecture
![RedditDataEngineering.png](assets%2FRedditDataEngineering.png)
1. **Reddit API**: Source of data.
2. **Apache Airflow & Celery**: Orchestrates the ETL process and manages task distribution.
3. **PostgreSQL**: Temporary storage and metadata management.
4. **Amazon S3**: Raw data storage.
5. **AWS Glue**: Data cataloging and ETL jobs.
6. **Amazon Athena**: SQL-based data transformation.
7. **Amazon Redshift**: Data warehousing and analytics.

## Prereqs
- AWS Account with appropriate permissions for S3, Glue, Athena, and Redshift.
- Reddit API credentials.
- Docker Installation
- Python 3.9 or higher

## System Setup

1. Create a virtual environment.
   ```bash
    python3 -m venv venv
   ```
2. Activate the virtual environment.
   ```bash
    source venv/bin/activate
   ```
3. Install the dependencies.
   ```bash
    pip install -r requirements.txt
   ```
4. Rename the configuration file and the credentials to the file.
   ```bash
    mv config/config.conf.example config/config.conf
   ```
5. Starting the containers
   ```bash
    docker-compose up -d
   ```
6. Launch the Airflow web UI.
   ```bash
    open http://localhost:8080
   ```
