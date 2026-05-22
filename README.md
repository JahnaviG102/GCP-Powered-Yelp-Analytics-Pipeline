# GCP-Powered-Yelp-Analytics-Pipeline
A fully automated GCP pipeline that processes Yelp data using BigQuery, Dataproc, DBT, and Cloud Composer to deliver restaurant insights.

## GCP-Powered Yelp Analytics Pipeline
This project is a scalable, cloud-native data pipeline built on Google Cloud Platform (GCP) that ingests, processes, and analyzes Yelp’s public dataset to uncover insights into restaurant businesses. It leverages modern data engineering tools for efficient ETL orchestration, transformation, and visualization.

## Project Highlights
* End-to-end data pipeline processing over 5 million records
* Automated ETL workflows with Cloud Composer and Dataproc
* Scalable data transformation using DBT on BigQuery
* CI/CD for DBT models using Cloud Build and Cloud Run
* Real-time interactive visualizations via Google Data Studio

## Components & Architecture

 **Data Ingestion**
* Yelp public dataset is downloaded and uploaded to Google Cloud Storage (GCS)
* Cloud Composer DAG triggers ingestion upon file arrival in data/raw/

**Data Processing**
* Raw JSON files are cleaned and transformed using Apache Spark on Dataproc
* Transformed data is ingested into BigQuery raw tables

**Data Modeling**
* DBT is used to transform staging tables into clean, analytical marts
* Over 30 models built for aggregations, business metrics, and trend analysis

**Orchestration**
* Cloud Composer manages DAGs that trigger Dataproc jobs and Cloud Run DBT execution
* DAG ensures dependencies and retries are handled seamlessly

**CI/CD for DBT**
* Cloud Build builds a Docker image for DBT on each push to main
* Cloud Run executes DBT transformations using the latest image
* Eliminates manual deployment and ensures consistent, version-controlled transformations

**Visualization**
* Final transformed datasets are visualized using Google Data Studio
* Dashboards include filters by business type, location, and ratings, with < 2s query latency

## Tech Stack
**Cloud Infrastructure:** Google Cloud Platform, Terraform

**Storage:** Google Cloud Storage (GCS)

**Data Processing:** Apache Spark on Cloud Dataproc

**Data Warehouse:** BigQuery

**Data Modeling:** DBT

**Orchestration:** Cloud Composer (Airflow)

**CI/CD & Containerization:** Cloud Build, Cloud Run

**Visualization:** Google Data Studio

**Programming:** Python

##Sample Dashboard
An interactive dashboard built on top of DBT models in BigQuery enables business stakeholders to explore Yelp restaurant data. It includes filters by city, category, and average rating.

## Conclusion
This project was developed as part of my capstone for the Data Engineering Bootcamp at UT Dallas.
Feel free to connect with me on LinkedIn if you'd like to share feedback or discuss the project further.
