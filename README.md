# PostgreSQL Data Pipeline with Docker

This project is part of the Data Engineering Zoomcamp by DataTalksClub.

It demonstrates how to build a data ingestion pipeline using Python, SQL and Docker, with PostgreSQL as the main database.

##  Project Overview

The goal of this project is to create a reproducible data pipeline that:

* Downloads a dataset ( NYC Taxi data)
* Loads it into a PostgreSQL database
* Uses Docker to manage the environment
* Allows querying and analysis via SQL tools

## 🛠️ Tech Stack

* Python
* PostgreSQL
* Docker & Docker Compose
* Pandas
* Jupyter Notebook
* pgAdmin / pgcli

##  Architecture

Pipeline flow:

```text
Data Source → Python Script → PostgreSQL (Docker) → SQL Analysis
```

## 📂 Project Structure

```bash
.
├── ingest_data.py        # script to download and load data into Postgres
├── pipeline.py           # pipeline logic
├── upload_data.ipynb     # notebook for testing and exploration
├── Dockerfile
├── docker-compose.yml    # defines Postgres & pgAdmin services
├── scripts/
│   ├── postgres.sh
│   ├── pgadmin.sh
│   └── pgcli.sh
```
## How to Run

### 1. Start Docker services

```bash
docker-compose up
```

This will start:

* PostgreSQL database
* pgAdmin (optional UI)

### 2. Run data ingestion

```bash
python ingest_data.py \
  --user=your_user \
  --password=your_password \
  --host=localhost \
  --port=5432 \
  --db=ny_taxi \
  --table_name=yellow_taxi_data \
  --url=<dataset_url>
```

### 3. Query the data

Use:

* pgAdmin (browser UI)
* pgcli
* or any SQL client

Example:

```sql
SELECT COUNT(*) FROM yellow_taxi_data;
```

## Example Use Cases

* Loading large datasets into a database
* Practicing SQL queries
* Building reproducible data pipelines
* Local data warehouse setup


##  Learning Outcomes

Through this project I learned:

* How to use Docker for data engineering workflows
* How to set up and manage PostgreSQL locally
* How to ingest large datasets efficiently
* Writing and executing SQL queries
* Structuring data pipelines in Python


## Acknowledgments

This project is based on the Data Engineering Zoomcamp by DataTalksClub:
https://github.com/DataTalksClub/data-engineering-zoomcamp


