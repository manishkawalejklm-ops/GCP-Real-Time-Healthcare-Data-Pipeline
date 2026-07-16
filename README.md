# GCP-Real-Time-Healthcare-Data-Pipeline
Engineered an end-to-end Real-Time Streaming Data Pipeline on Google Cloud Platform (GCP) using Python, Google Cloud Pub/Sub, Apache Beam, and Google Cloud Dataflow, enabling continuous ingestion and processing of simulated patient vital events with 2-second streaming intervals.


# 🏥 Real-Time Patient Vital Monitoring Pipeline on Google Cloud

A production-style real-time streaming Data Engineering project built using **Google Cloud Platform**, **Apache Beam**, **Dataflow**, **Pub/Sub**, **BigQuery**, **Google Cloud Storage**, and **Power BI**.

The project simulates patient vital signs, processes streaming data using the Medallion Architecture (Bronze → Silver → Gold), stores curated datasets, and provides a live analytics dashboard.

---

# 📌 Project Architecture

```
Patient Simulator
       │
       ▼
 Google Cloud Pub/Sub
       │
       ▼
 Apache Beam Pipeline
       │
 ┌─────┼───────────┐
 │     │           │
 ▼     ▼           ▼
Bronze Silver     Gold
 GCS    GCS     BigQuery
                    │
                    ▼
               Power BI
```

---

# 🚀 Technologies Used

- Google Cloud Platform (GCP)
- Google Cloud Pub/Sub
- Apache Beam
- Google Cloud Dataflow
- Google Cloud Storage
- BigQuery
- Python
- Power BI
- Git & GitHub

---

# 📂 Project Structure

```
patient-vital-monitor/
│
├── simulator/
│   ├── patient_vital_simulator.py
│   └── .env
│
├── dataflow/
│   ├── streaming_medallion_pipeline.py
│   └── .env
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

# 🔄 End-to-End Workflow

---

## Step 1 – Create Google Cloud Account

- Create a GCP Free Trial Account
- Add Billing Details
- Receive $300 Free Credits

---

## Step 2 – Create a New GCP Project

- Create a new project
- Select the project
- Copy the Project ID

---

## Step 3 – Open Cloud Shell

Launch:

- Cloud Shell Terminal
- Cloud Shell Editor (VS Code)

---

## Step 4 – Create Project

```bash
mkdir patient-vital-monitor
cd patient-vital-monitor
```

---

## Step 5 – Create Simulator

```bash
mkdir simulator
cd simulator

touch patient_vital_simulator.py
touch .env
```

---

## Step 6 – Develop Patient Simulator

The simulator performs the following:

- Loads environment variables
- Generates Patient IDs
- Simulates:
  - Heart Rate
  - SPO₂
  - Temperature
  - Blood Pressure
- Injects random faulty records
- Converts records to JSON
- Publishes messages to Pub/Sub

---

## Step 7 – Configure Simulator

Example `.env`

```text
PROJECT_ID=my-project
TOPIC_NAME=patient-vitals
PATIENT_COUNT=100
STREAM_INTERVAL=2
ERROR_RATE=0.05
```

---

## Step 8 – Enable Required APIs

Enable:

- Pub/Sub API
- Cloud Storage API
- Dataflow API
- BigQuery API

---

## Step 9 – Create Pub/Sub Resources

Create

- Topic
- Pull Subscription

---

## Step 10 – Configure IAM

Grant:

- Pub/Sub Admin
- BigQuery Admin
- Storage Admin
- Editor (Optional)

---

## Step 11 – Run Simulator

```bash
python patient_vital_simulator.py
```

Verify messages are arriving in Pub/Sub.

---

## Step 12 – Stop Simulator

```
Ctrl + C
```

---

## Step 13 – Create Dataflow Module

```bash
cd ..

mkdir dataflow

cd dataflow

touch streaming_medallion_pipeline.py

touch .env
```

---

## Step 14 – Develop Apache Beam Pipeline

Pipeline stages:

- Read Pub/Sub
- Bronze Processing
- Silver Processing
- Gold Processing
- BigQuery Output

---

## Step 15 – Configure Dataflow

Example `.env`

```text
PROJECT_ID=my-project

SUBSCRIPTION=patient-sub

BRONZE_PATH=gs://bucket/bronze

SILVER_PATH=gs://bucket/silver

BQ_TABLE=patient_dataset.gold_patient_vitals

TEMP_PATH=gs://bucket/temp

STAGING_PATH=gs://bucket/staging

REGION=asia-south1
```

---

## Step 16 – Create Storage Bucket

Create bucket

```
gs://patient-vital-monitor
```

Directory structure

```
bronze/

silver/

temp/

staging/
```

---

## Step 17 – Create BigQuery Resources

Create

Dataset

```
patient_dataset
```

Create Gold Table

```
gold_patient_vitals
```

---

## Step 18 – Install Dependencies

```bash
pip install apache-beam

pip install apache-beam[gcp]

pip install python-dotenv

pip install google-cloud-pubsub
```

---

## Step 19 – Run Dataflow Pipeline

Execute Beam pipeline.

The streaming Dataflow job starts and continuously processes incoming patient data.

---

## Step 20 – Restart Simulator

```bash
python patient_vital_simulator.py
```

Patient events begin streaming to Pub/Sub.

---

# 📊 Streaming Data Flow

```
Patient Simulator

        │

        ▼

Google Cloud Pub/Sub

        │

        ▼

Apache Beam Pipeline

        │

        ▼

──────── Bronze ────────

Decode UTF-8

Store Raw JSON

Write to GCS

        │

        ▼

──────── Silver ────────

Parse JSON

Validate Records

Remove Invalid Data

Standardize Schema

Write Clean Data

        │

        ▼

──────── Gold ─────────

Calculate Risk Score

Assign Risk Category

Aggregate by Patient

Generate Analytics

Write to BigQuery
```

---

# 🥉 Bronze Layer

Stores raw streaming data exactly as received.

Operations:

- Decode bytes
- Preserve raw JSON
- Archive to Cloud Storage

---

# 🥈 Silver Layer

Performs data cleaning.

Operations:

- Parse JSON
- Validate schema
- Remove invalid records
- Handle missing values
- Standardize formats

---

# 🥇 Gold Layer

Creates business-ready analytics.

Calculates:

- Risk Score
- Risk Level
- Average Heart Rate
- Latest Temperature
- Latest SPO₂
- Latest Blood Pressure

Stores curated data in BigQuery.

---

# 📈 Verify Pipeline

Verify:

- Pub/Sub Messages
- Bronze Bucket
- Silver Bucket
- Dataflow Monitoring
- BigQuery Tables

---

# 🔗 Push to GitHub

```bash
git init

git add .

git commit -m "Initial Commit"

git branch -M main

git remote add origin <repo-url>

git push -u origin main
```

---

# 📊 Connect Power BI

Connect using:

```
Power BI

↓

BigQuery Connector

↓

Dataset

↓

Gold Table

↓

Direct Query
```

---

# 📉 Dashboard

Dashboard Components

- Patient Filter
- Heart Rate Gauge
- Temperature Gauge
- SPO₂ Gauge
- Blood Pressure Card
- Risk Level Indicator
- Live Patient Table
- Trend Charts
- Conditional Formatting

---

# 🔴 Live Dashboard Flow

```
User Selects Patient

        │

        ▼

Power BI

        │

        ▼

BigQuery Direct Query

        │

        ▼

Latest Patient Record

        │

        ▼

Dashboard Refreshes Automatically
```

---

# 🎯 Key Features

- Real-time patient vital simulation
- Streaming ingestion with Pub/Sub
- Apache Beam streaming pipeline
- Google Cloud Dataflow execution
- Medallion Architecture (Bronze, Silver, Gold)
- Cloud Storage data lake
- BigQuery analytics layer
- Live Power BI dashboard
- Modular project structure
- Environment-based configuration
- Fault injection for testing
- GitHub-ready project

---

# 📌 Future Enhancements

- Add Apache Airflow orchestration
- Dockerize the application
- CI/CD with GitHub Actions
- Data quality monitoring
- Cloud Logging & Monitoring
- Slack/Email alerts for critical patients
- Machine Learning-based patient risk prediction

---

# 👨‍💻 Author

**Manish Kawale**

**Data Engineer**

Skills:
- Python
- Apache Beam
- Google Cloud Platform
- Pub/Sub
- Dataflow
- BigQuery
- Cloud Storage
- SQL
- Power BI
- Git & GitHub






