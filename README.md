# Weather ETL Pipeline using Apache Airflow

An end-to-end **ETL (Extract, Transform, Load) pipeline built with Apache Airflow** that fetches weather data from the **Open-Meteo API**, transforms the required weather information, and stores the processed data in **PostgreSQL**.

## 🚀 Project Overview

This project demonstrates how to build and orchestrate a simple data engineering pipeline using Airflow's TaskFlow API.

The pipeline performs three main steps:

1. **Extract** – Fetches current weather data from the Open-Meteo API using Airflow's `HttpHook`.
2. **Transform** – Extracts and structures relevant weather fields such as temperature, wind speed, wind direction, and weather code.
3. **Load** – Creates a PostgreSQL table if it doesn't exist and inserts the transformed weather data using `PostgresHook`.

## 🔄 Pipeline Architecture

**Open-Meteo API → Extract → Transform → Load → PostgreSQL**

### Tasks

* `extract_weather_data()` – Retrieves weather data from the API.
* `transform_weather_data()` – Processes the API response and extracts required fields.
* `load_weather_data()` – Stores the processed data in PostgreSQL.

## 🛠️ Technologies Used

* **Python**
* **Apache Airflow**
* **PostgreSQL**
* **Open-Meteo API**
* **Airflow HTTP Hook**
* **Airflow PostgreSQL Hook**
* **Airflow TaskFlow API**
* **Pendulum**

## 📊 Data Stored

The PostgreSQL table `weather_data` stores:

* Latitude
* Longitude
* Temperature
* Wind Speed
* Wind Direction
* Weather Code
* Timestamp

## ⏰ Scheduling

The DAG is configured to run **daily** using Airflow's `@daily` schedule with `catchup=False`.

## 🎯 Learning Objectives

This project helped me understand:

* Creating and configuring Airflow DAGs
* Using Airflow's TaskFlow API
* Working with Airflow Connections
* Using `HttpHook` for API integration
* Using `PostgresHook` for database operations
* Building an ETL workflow
* Passing data between Airflow tasks using XComs
* Creating database tables and inserting processed data
* Scheduling and monitoring workflows through the Airflow UI

## 📁 Project Structure

```text
weather-etl-pipeline/
│
├── dags/
│   └── weather_etl_pipeline.py
│
├── README.md
└── requirements.txt
```

## 🔗 Workflow

```text
        Open-Meteo API
               ↓
       Extract Weather Data
               ↓
       Transform Weather Data
               ↓
       Load into PostgreSQL
               ↓
          weather_data
             table
```

This project is a practical implementation of an **API-to-Database ETL pipeline using Apache Airflow**, designed to strengthen my understanding of workflow orchestration and data engineering fundamentals.
