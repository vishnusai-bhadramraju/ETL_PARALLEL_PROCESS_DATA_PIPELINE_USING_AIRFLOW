# Data Pipeline Automation with Apache Airflow

## Project Overview

This project aims to build and automate a data pipeline using Apache Airflow. The project consists of two parallel pipelines:

1. **Pipeline 1**:
   - Extracts data from an S3 bucket.
   - Creates a table in PostgreSQL.
   - Uploads the processed data back to the S3 bucket.

2. **Pipeline 2**:
   - Extracts data from a weather API.
   - Transforms the data using Python.
   - Uploads the transformed data to a PostgreSQL table.

Finally, data from both pipelines are joined and ingested back into the S3 bucket.

## Project Structure

```
.
├── dags
│   ├── pipeline_1.py
│   ├── pipeline_2.py
│   └── final_ingestion.py
├── scripts
│   ├── transform_weather_data.py
│   └── helpers.py
├── configs
│   └── airflow_config.py
├── requirements.txt
└── README.md
```

## Technologies Used

- **Apache Airflow**: For orchestrating the data pipelines.
- **Amazon S3**: For data storage and retrieval.
- **Amazon RDS (PostgreSQL)**: For relational database management.
- **Python**: For data transformation.
- **Weather API**: For extracting weather data.

## Setup Instructions

### Prerequisites

- Docker
- Docker Compose
- AWS Account
- PostgreSQL Instance (Amazon RDS)

### Steps

1. **Clone the Repository**

    ```bash
    gh repo clone vishnusai-bhadramraju/ETL_PARALLEL_PROCESS_DATA_PIPELINE_USING_AIRFLOW
    cd airflow-data-pipeline
    ```

2. **Configure AWS Credentials**

    Ensure your AWS credentials are set up on your local machine. You can use the AWS CLI to configure them.

    ```bash
    aws configure
    ```
    ```

4. **Configure Airflow Variables**

    Set up the necessary Airflow variables for S3 bucket names, PostgreSQL connection details, and Weather API keys using the Airflow web interface.

    - `s3_bucket`: Name of your S3 bucket.
    - `postgres_conn_id`: PostgreSQL connection details.
    - `weather_api_key`: Your Weather API key.

5. **Trigger the Pipelines**

    Trigger the data pipelines from the Airflow web interface.

## Pipeline Details

### Pipeline 1: S3 to PostgreSQL to S3

1. **Extract**: Fetch data from the specified S3 bucket.
2. **Transform**: Create a PostgreSQL table.
3. **Load**: Insert the data into the PostgreSQL table.
4. **Upload**: Export the processed data back to the S3 bucket.

### Pipeline 2: Weather API to PostgreSQL

1. **Extract**: Fetch data from the Weather API.
2. **Transform**: Process and clean the data using Python.
3. **Load**: Insert the transformed data into a PostgreSQL table.

### Final Ingestion

1. **Join Data**: Combine data from both PostgreSQL tables.
2. **Upload**: Export the joined data to the S3 bucket.

## Directory Structure

- **dags**: Contains the DAG files for the pipelines.
- **scripts**: Contains Python scripts for data transformation and helper functions.



## Contact

For any questions or suggestions, please contact Vishnusai Bhadramraju at [vishnusaibhadramraju1@gmail.com](mailto:vishnusaibhadramraju1@gmail.com).
