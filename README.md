# Building Real-Time Sales Dashboard Using Big Data Components

## Overview
This project implements an end-to-end real-time data pipeline that ingests simulated e-commerce sales events, processes them using Apache Spark Structured Streaming, stores both raw and aggregated data, and visualizes results through a real-time dashboard.

The system demonstrates modern streaming architecture using Apache Kafka, Spark, MySQL, HDFS, Django, and Chart.js.

## Architecture

System Architecture:
<br>
<img width="566" height="223" alt="Architecture" src="https://github.com/user-attachments/assets/56865ca2-dd1b-4490-a023-8483b1e43c26" />
<br>
Data Flow:

Python Sales Simulator 
→ Apache Kafka 
→ Spark Structured Streaming 
→ MySQL (Aggregated Metrics)
→ HDFS (Raw Data Storage)
→ Django + Chart.js Dashboard

## Technologies Used

- Python
- Apache Kafka
- Apache Spark Structured Streaming
- Hadoop HDFS
- MySQL
- Django
- Chart.js
- VirtualBox
- PuTTY
- WinSCP

## Features

- Real-time streaming sales data ingestion
- Kafka-based event messaging pipeline
- Spark streaming aggregation of sales metrics
- Raw event storage in HDFS
- Aggregated metrics storage in MySQL
- Real-time dashboard auto-refreshing every 5 seconds
- Sales analysis by:
  - Card Type
  - Country
- Interactive bar and pie chart visualizations

## Dashboard Preview

<p align="center">
<img src="https://github.com/user-attachments/assets/7dd09b18-96d8-4c9e-a6fc-7dceade7d0b6" width="48%">
</p>
<br>
<p align="center">
<img src="https://github.com/user-attachments/assets/b90b461d-f6a8-43e1-8617-f46f6b71aca0" width="46%">
<img src="https://github.com/user-attachments/assets/c4951789-a43a-420c-bb9e-e7f334376bd9" width="48%">
</p>

---

## Sample Metrics Analyzed

- Sales by Card Type
- Sales by Country
- Transaction Distribution
- Real-Time Batch Updates
- Aggregated Sales Metrics

## Project Structure

```bash
kafka_producer_consumer/
├── kafka_producer.py

realtime_data_processing/
├── realtime_data_processing.py

realtime_charts/
├── Django dashboard
```

## How It Works

### Producer Layer
Simulates online sales events and publishes records into Kafka topics.

### Streaming Layer
Spark Structured Streaming consumes Kafka events and performs:

- Data ingestion
- Real-time aggregation
- Metric calculations

### Storage Layer

MySQL stores:
- Aggregated sales metrics

HDFS stores:
- Raw streaming event data

### Visualization Layer

Django + Chart.js displays:
- Auto-refreshing bar charts
- Interactive pie charts

## Run the Project

### Start Services
```bash
sudo systemctl start zookeeper
sudo systemctl start kafka
start-all.sh
```

### Start Spark Streaming
```bash
spark-submit realtime_data_processing.py
```

### Start Producer
```bash
python3 kafka_producer.py
```

### Start Dashboard
```bash
python3 manage.py runserver
```

Access:
```bash
http://localhost:8000
```

## Key Learnings

This project demonstrates:

- Event-driven architecture
- Streaming data pipelines
- Real-time analytics
- Distributed storage concepts
- Dashboard visualization integration

## Future Enhancements

- Dockerize deployment
- Add schema registry
- Add Spark checkpointing improvements
- Deploy using cloud services (AWS / Azure)
- Add anomaly detection on transaction streams
