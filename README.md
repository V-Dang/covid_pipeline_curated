# COVID Pipeline (Curated - Silver Layer)

The purpose of this project is to write a pyspark pipeline to incrementally load JSON data from the raw (bronze) data lake to the curated (silver) data lake as a Delta table.
- Metadata (created, updated timestamps)
- Optimizations (Delta format)
- Merge Upsert
- Normalize nested JSON schema

In part 1, API data is ingested into the raw data lake, orchestrated by Airflow:
    - https://github.com/V-Dang/covid_pipeline

Notes:
https://hub.docker.com/r/jupyter/pyspark-notebook
https://www.youtube.com/watch?v=ISD1RrOdn28

Connecting to S3 bucket:
- Extend pyspark image in Dockerfile
    - To include required jars (aws hadoop, etc.)
- Set environment keys in docker compose
    - Use environment (must paste access keys here directly) or env_file (must create .env file)
    - AWS credentials/secret/region, Jupyter token

Prerequisities:
- Bind the local working directory to docker container directory
- Then connect to the jupyter notebook kernel (from the container)