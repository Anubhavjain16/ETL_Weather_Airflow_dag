# ⛅ ETL Weather Data Pipeline

## 📌 Project Overview
This project is an **ETL (Extract, Transform, Load) pipeline** built using **Apache Airflow** to fetch real-time weather data from the Open-Meteo API, process it, and store it in a **PostgreSQL database**. The pipeline is fully automated and scheduled to run **daily**.

## 🏗️ Project Components
- **Airflow DAG** (`etl_weather.py`): Orchestrates the ETL process.
- **PostgreSQL Database**: Stores the transformed weather data.
- **Docker Compose Setup** (`docker-compose.yaml`): Deploys PostgreSQL for local testing.
- **Open-Meteo API**: Provides real-time weather data.

## 🚀 Technologies Used
- **Apache Airflow** (DAG scheduling & task management)
- **PostgreSQL** (Data storage)
- **Docker & Docker Compose** (Containerization)
- **Python** (ETL scripting)
- **Open-Meteo API** (Data source)

## 🛠️ Installation & Setup
### 1️⃣ Clone the Repository
```sh
git clone https://github.com/your-repo/etl-weather-pipeline.git
cd etl-weather-pipeline
```

### 2️⃣ Start PostgreSQL Using Docker
```sh
docker-compose up -d
```

### 3️⃣ Set Up Airflow
Make sure you have **Airflow** installed. If not, install it using:
```sh
pip install apache-airflow
```

### 4️⃣ Start Airflow Scheduler & Web Server
```sh
airflow db init
airflow scheduler & airflow webserver
```

### 5️⃣ Run the DAG
Navigate to **Airflow UI** (http://localhost:8080) and trigger the `weather_etl_pipeline` DAG.

## 🔄 ETL Process
1. **Extract**: Fetches weather data (temperature, wind speed, direction, etc.) from Open-Meteo API.
2. **Transform**: Cleans and structures the data into a well-defined schema.
3. **Load**: Inserts the transformed data into **PostgreSQL**.

## 📊 Database Schema
The **weather_data** table stores processed weather data:
```sql
CREATE TABLE weather_data (
    latitude FLOAT,
    longitude FLOAT,
    temperature FLOAT,
    windspeed FLOAT,
    winddirection FLOAT,
    weathercode INT,
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## ⚠️ Limitations & Future Enhancements
- 🔍 **Add error handling** for API failures.
- 📈 **Optimize Airflow DAG** with retries & logging.
- 🌎 **Expand to multiple locations** dynamically.

---
📌 **Feel free to contribute!** 🚀

