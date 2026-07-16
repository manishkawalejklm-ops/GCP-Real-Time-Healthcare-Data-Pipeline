# GCP-Real-Time-Healthcare-Data-Pipeline
Engineered an end-to-end Real-Time Streaming Data Pipeline on Google Cloud Platform (GCP) using Python, Google Cloud Pub/Sub, Apache Beam, and Google Cloud Dataflow, enabling continuous ingestion and processing of simulated patient vital events with 2-second streaming intervals.

image








START
  │
  ▼
1️⃣ Create Google Cloud (GCP) Account
  │
  ├── Create Free Trial Account
  ├── Add Card Details
  └── Receive $300 Free Credits
  │
  ▼
2️⃣ Create New GCP Project
  │
  ├── Click New Project
  ├── Give Project Name
  └── Select Project
  │
  ▼
3️⃣ Open Google Cloud Shell
  │
  ├── Open Terminal
  └── Open Cloud Shell Editor (VS Code-like)
  │
  ▼
4️⃣ Create Project Repository
  │
  ├── mkdir patient-vital-monitor
  ├── cd patient-vital-monitor
  └── Root Project Folder Ready
  │
  ▼
5️⃣ Create Simulator Folder
  │
  ├── mkdir simulator
  ├── cd simulator
  ├── touch patient_vital_simulator.py
  └── touch .env
  │
  ▼
6️⃣ Write Patient Simulator Code
  │
  ├── Load .env
  ├── Generate Patient IDs
  ├── Generate Random Vitals
  ├── Inject Errors
  ├── Convert Dictionary → JSON
  ├── Encode UTF-8
  └── Publish to Pub/Sub
  │
  ▼
7️⃣ Configure Simulator .env
  │
  ├── Project ID
  ├── Topic Name
  ├── Patient Count
  ├── Stream Interval
  └── Error Rate
  │
  ▼
8️⃣ Enable Required APIs
  │
  ├── Pub/Sub API
  ├── Cloud Storage API
  ├── Dataflow API
  └── BigQuery API
  │
  ▼
9️⃣ Create Pub/Sub Resources
  │
  ├── Create Topic
  └── Create Pull Subscription
  │
  ▼
🔟 Configure IAM Permissions
  │
  ├── Pub/Sub Admin
  ├── BigQuery Admin
  ├── Storage Admin
  └── Editor Role (if required)
  │
  ▼
1️⃣1️⃣ Run Simulator
  │
  ├── python patient_vital_simulator.py
  └── Verify Messages in Pub/Sub
  │
  ▼
1️⃣2️⃣ Stop Simulator
  │
  └── Ctrl + C
  │
  ▼
1️⃣3️⃣ Create Dataflow Folder
  │
  ├── cd ..
  ├── mkdir dataflow
  ├── cd dataflow
  ├── touch streaming_medallion_pipeline.py
  └── touch .env
  │
  ▼
1️⃣4️⃣ Write Apache Beam Pipeline
  │
  ├── Import Modules
  ├── Load .env
  ├── Configure Pipeline Options
  ├── Bronze Layer
  ├── Silver Layer
  ├── Gold Layer
  └── BigQuery Output
  │
  ▼
1️⃣5️⃣ Configure Dataflow .env
  │
  ├── Project ID
  ├── Subscription
  ├── Bronze Path
  ├── Silver Path
  ├── BigQuery Table
  ├── Temp Path
  ├── Staging Path
  └── Region
  │
  ▼
1️⃣6️⃣ Create Google Cloud Storage Bucket
  │
  ├── Create Bucket
  └── Beam Creates:
        ├── bronze/
        ├── silver/
        ├── temp/
        └── staging/
  │
  ▼
1️⃣7️⃣ Create BigQuery Resources
  │
  ├── Create Dataset
  ├── Create Gold Table
  └── Define Schema
  │
  ▼
1️⃣8️⃣ Install Dependencies
  │
  ├── Apache Beam
  ├── Beam GCP Libraries
  └── python-dotenv
  │
  ▼
1️⃣9️⃣ Run Dataflow Pipeline
  │
  ├── Execute Beam Pipeline
  ├── Upload to Dataflow
  └── Streaming Job Starts
  │
  ▼
2️⃣0️⃣ Restart Simulator
  │
  ├── Generate Patient Data
  └── Stream to Pub/Sub
  │
  ▼
2️⃣1️⃣ Data Processing Begins
  │
  ├── Pub/Sub
  │
  ▼
  Bronze Layer
  │
  ├── Decode UTF-8
  ├── Store Raw JSON
  └── Write to GCS
  │
  ▼
  Silver Layer
  │
  ├── Parse JSON
  ├── Validate Records
  ├── Remove Invalid Data
  └── Write Clean Data
  │
  ▼
  Gold Layer
  │
  ├── Calculate Risk Score
  ├── Assign Risk Level
  ├── Group by Patient
  ├── Aggregate Records
  └── Write to BigQuery
  │
  ▼
2️⃣2️⃣ Verify Pipeline
  │
  ├── Check Pub/Sub
  ├── Check Bronze Bucket
  ├── Check Silver Bucket
  ├── Check BigQuery Table
  └── Verify Dataflow Graph
  │
  ▼
2️⃣3️⃣ Push Project to GitHub
  │
  ├── Create GitHub Repository
  ├── git init
  ├── git add .
  ├── git commit
  ├── git remote add origin
  ├── Generate Personal Access Token
  └── git push origin main
  │
  ▼
2️⃣4️⃣ Connect Power BI
  │
  ├── Connect BigQuery
  ├── Select Dataset
  ├── Select Gold Table
  └── Use Direct Query
  │
  ▼
2️⃣5️⃣ Build Dashboard
  │
  ├── Patient Slicer
  ├── Heart Rate Gauge
  ├── SPO₂ Gauge
  ├── Temperature Gauge
  ├── Risk Level Card
  └── Conditional Formatting
  │
  ▼
2️⃣6️⃣ Live Dashboard
  │
  ├── Select Patient
  ├── BigQuery Executes Query
  ├── Latest Data Returned
  └── Dashboard Updates Automatically
  │
  ▼
                🎉 PROJECT COMPLETED
