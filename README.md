# Weather Data ETL Pipeline

## Overview
This project automates the extraction, transformation, and loading (ETL) of weather data from the OpenWeather API into Snowflake. The entire pipeline is orchestrated using Apache Airflow on an AWS EC2 instance.

---

## Architecture

![Project Architecture](https://github.com/Usama00004/Open-Weather-API/blob/main/Images/Image_1.png)



---

## Features
- **Data Extraction**: Fetches real-time weather data from the OpenWeather API.
- **Data Transformation**: Cleans, processes, and structures the data using Python (Pandas).
- **Data Loading**: Stores the transformed data into a Snowflake database.
- **Automation**: Uses Apache Airflow to automate and schedule the ETL pipeline.
- **Deployment**: Hosted on an AWS EC2 instance for continuous execution.

---

## Tech Stack
- **Programming Language**: Python
- **ETL Orchestration**: Apache Airflow
- **Data Storage**: Snowflake
- **Infrastructure**: AWS EC2
- **API Provider**: OpenWeather API
- **Libraries Used**: Pandas, Requests, SQLAlchemy, Snowflake Connector for Python

---

## Project Structure
```
weather_etl_pipeline/
│-- dags/
│   ├── weather_etl.py  # Main ETL DAG
│-- scripts/
│   ├── fetch_data.py  # Fetch data from OpenWeather API
│   ├── transform_data.py  # Clean and structure data
│   ├── load_to_snowflake.py  # Load data into Snowflake
│-- config/
│   ├── config.yaml  # API keys and database credentials
│-- requirements.txt  # Python dependencies
│-- README.md  # Project documentation
```

---

## Setup Instructions

### Clone the Repository
```bash
git clone https://github.com/yourusername/weather-etl.git
cd weather-etl
```

### Install Dependencies
```bash
pip install -r requirements.txt
```

### Configure Environment Variables
Update `config/config.yaml` with:
- OpenWeather API key
- Snowflake credentials

### Set Up Apache Airflow
```bash
export AIRFLOW_HOME=~/airflow
pip install apache-airflow
airflow db init
```

### Deploy on AWS EC2
- Launch an EC2 instance with the required security groups.
- Install dependencies and Airflow.
- Set up cron jobs or Airflow scheduler.

---

## Running the Pipeline
1. Start Airflow Web Server and Scheduler:
```bash
airflow webserver -p 8080
airflow scheduler
```
2. Access Airflow UI at `http://<your-ec2-ip>:8080`
3. Trigger the DAG manually or set a schedule.

---

## Future Enhancements
- Add data validation checks before loading into Snowflake.
- Implement real-time monitoring and alerting.
- Store raw data in S3 for backup and historical analysis.

---

## License
MIT License

---

## Author
[Usama Tahir](https://github.com/usama00004)
