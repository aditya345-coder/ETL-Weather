# ETL-Weather

This project is an end-to-end data pipeline for extracting, transforming, and loading (ETL) weather data using Apache Airflow, PostgreSQL, and Docker. The goal of this project is to automate the process of fetching weather data from an API, transforming it, and storing it in a PostgreSQL database for analysis.

## Project structure
```bash
├───dags
|   └───etlweather.py
│   └───exampledag.py
|
├───tests
│   └───dags
|       └───test_dag_example.py
|
├───.gitignore
├───airflow_settings.yaml
├───docker-compose.yaml
├───Dockerfile
├───requirements.txt
```

## Prerequisites

Before you get started, ensure that you have the following installed:

- Docker
- Python 3.x

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/weather-etl-airflow.git
   cd weather-etl-airflow
   ```
2. **Create Virtual envionment**
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows use `venv\Scripts\activate`
   ```
3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```
4. **Set up Docker:**
 - Ensure Docker is running.
 - The project includes a docker-compose.yml file to set up a PostgreSQL container and an Airflow instance.
5. **Run Docker Compose**
   ```bash
   docker-compose up
   ```
## Airflow Setup
**Initialize Airflow:**
After running Docker Compose, navigate to the dags folder where your Airflow DAG files are located.
Use the command astro dev init to initialize the Airflow project.
Run Airflow Locally:

To start Airflow:
```bash
astro dev start
```
If you make any changes to the code, restart Airflow:
```bash
astro dev restart
```

## Folder Details
* `dags/`: Contains the DAG files that define the ETL pipeline. The primary file is etlweather.py, which orchestrates the extraction, transformation, and loading of weather data.

* `example_astronauts.py:` This DAG shows a simple ETL pipeline example that queries the list of astronauts currently in space from the Open Notify API and prints a statement for each astronaut. The DAG uses the TaskFlow API to define tasks in Python, and dynamic task mapping to dynamically print a statement for each astronaut.

* `tests/`: Contains test files for verifying the functionality of the DAGs.

* `.gitignore`: Specifies files and directories to be ignored by Git (e.g., virtual environments, Docker files, etc.).

* `airflow_settings.yaml`: Contains Airflow configuration settings.

* `docker-compose.yaml`: Defines the services, networks, and volumes for running PostgreSQL and Airflow using Docker Compose.

* `Dockerfile`: This file contains a versioned Astro Runtime Docker image that provides a differentiated Airflow experience.

* `airflow_settings.yaml`: Use this local-only file to specify Airflow Connections, Variables, and Pools instead of entering them in the Airflow UI as you develop DAGs in this project.

* `requirements.txt`: Lists the Python dependencies for the project, including Airflow and other required libraries.

# License
- This project is licensed under the MIT License - see the LICENSE file for details.
