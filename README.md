Ride Sharing Analytics Using Spark Streaming and Spark SQL
Prerequisites

Before starting, ensure the following software is installed:

Python 3.x
Download and Install Python

Verify installation:

python --version
PySpark

Install using pip:

pip install pyspark
Faker (for generating sample data)

Install using pip:

pip install faker
Project Structure
ride-sharing-analytics/
├── outputs/
│   ├── task_1       # CSV files of Task 1
│   ├── task_2       # CSV files of Task 2
│   └── task_3       # CSV files of Task 3
├── task1.py
├── task2.py
├── task3.py
├── data_generator.py
└── README.md
data_generator.py → Continuously generates input data: (trip_id, driver_id, distance_km, fare_amount, timestamp)
outputs/ → Stores processed CSV files for each task
task1.py, task2.py, task3.py → Spark Structured Streaming tasks
Running the Analysis

Start the data generator first:

python data_generator.py

Open a new terminal and run each task:

python task1.py
python task2.py
python task3.py
Check the outputs/ directory to verify batch files are being written.
Sample Console Outputs

Task 1 – Basic Streaming Ingestion:

[Task 1] Batch 6 written → outputs/task_1/batch_6
[Task 1] Batch 7 written → outputs/task_1/batch_7
[Task 1] Batch 8 written → outputs/task_1/batch_8
[Task 1] Batch 9 written → outputs/task_1/batch_9
[Task 1] Batch 10 written → outputs/task_1/batch_10
[Task 1] Batch 11 written → outputs/task_1/batch_11

Task 2 – Real-Time Aggregations (Driver-Level):

[Task 2] Batch 1 written → outputs/task_2/batch_1
[Task 2] Batch 2 written → outputs/task_2/batch_2
[Task 2] Batch 3 written → outputs/task_2/batch_3
[Task 2] Batch 4 written → outputs/task_2/batch_4
[Task 2] Batch 5 written → outputs/task_2/batch_5
[Task 2] Batch 6 written → outputs/task_2/batch_6
[Task 2] Batch 7 written → outputs/task_2/batch_7
[Task 2] Batch 8 written → outputs/task_2/batch_8
[Task 2] Batch 9 written → outputs/task_2/batch_9

Task 3 – Windowed Time-Based Analytics:

[Task 3] Batch 48 written → outputs/task_3/batch_48
[Task 3] Batch 85 written → outputs/task_3/batch_85
[Task 3] Batch 124 written → outputs/task_3/batch_124
[Task 3] Batch 164 written → outputs/task_3/batch_164
[Task 3] Batch 203 written → outputs/task_3/batch_203
[Task 3] Batch 242 written → outputs/task_3/batch_242
[Task 3] Batch 281 written → outputs/task_3/batch_281
[Task 3] Batch 322 written → outputs/task_3/batch_322
Overview

This project builds a real-time analytics pipeline for a ride-sharing platform using Apache Spark Structured Streaming and Spark SQL.

Process streaming ride data
Perform real-time aggregations
Analyze trends over time
Objectives
Task 1: Ingest and parse streaming ride data.
Task 2: Compute driver-level metrics: total fare & average distance.
Task 3: Analyze trends using 5-minute sliding windows.
