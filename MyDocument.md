# 📌 Job Data Pipeline — Production-Grade Event-Driven PySpark System

This project implements a **production-grade, event-driven PySpark data pipeline** for processing and analyzing job posting data.

It demonstrates the transition from exploratory notebooks to **enterprise-ready data engineering systems**.

---

# 🚀 Overview

The solution follows:

- Layered Architecture  
- Config-driven design  
- Modular packaging using `.whl`  
- Event-driven orchestration  
- Cloud-native deployment strategy  
- Production-level logging & validation  

---

# 🏗 Architecture

## High-Level Flow

S3 File Upload  
↓  
SQS Queue / Lambda Trigger  
↓  
Airflow DAG  
↓  
Spark Job (packaged .whl)  
↓  
Processed Data (Parquet)  
↓  
KPI Outputs & Analytics  

---

## Design Principles

- Layered architecture  
- KISS principle  
- Config-driven implementation  
- Vendor abstraction  
- Event-driven processing  
- Production logging  
- Testable modular components  

---

# 📂 Project Structure

job-data-pipeline/
│
├── config/
│   └── config.yaml
│
├── src/
│   ├── reader.py
│   ├── writer.py
│   ├── cleaning.py
│   ├── feature_engineering.py
│   ├── validation.py
│   ├── kpis.py
│   ├── logging_config.py
│   └── pipeline.py
│
├── tests/
│   └── test_pipeline.py
│
├── setup.py
├── requirements.txt
└── main.py


---

# ⚙️ Core Capabilities

## 🔍 Data Exploration

- Schema detection  
- Numerical vs categorical profiling  
- Null handling  
- Duplicate detection  
- Salary normalization logic  

---

## 🧹 Data Processing

- Modular cleaning functions  
- Column preprocessing  
- Data wrangling  
- Feature removal based on profiling  

---

# KPIs Generated

- Top 10 job postings per category  
- Salary distribution per category  
- Degree vs salary correlation  
- Highest salary per agency  
- Average salary per agency (last 2 years)  
- Highest paid skills in US market  
- Average salary calculation  
- Salary band classification  
- Posting year extraction  
- Skill-based salary aggregation  
- High-cardinality feature removal  

---

# Layered Architecture

Each notebook cell was refactored into independent modules.

### I/O Layer
- Abstracted read/write logic  
- Local / Cloud switchable  

### Processing Layer
- Cleaning and transformation logic  

### Feature Layer
- Derived analytical columns  

### Validation Layer
- Schema & data quality checks  

### KPI Layer
- Business metrics computation  

### Orchestration Layer
- Pipeline execution entry point  

---

# 📦 Packaging Strategy

The entire project is packaged as a `.whl` file.

## Why `.whl`?

- Version-controlled releases  
- Clean deployment  
- Avoids notebook execution in production  
- CI/CD friendly  
- Easy Spark submission  

---

# ☁️ Event-Driven Deployment Architecture

## Trigger Options

### Option 1 — S3 → SQS → Airflow
- Durable  
- Scalable  
- Production safe  

### Option 2 — S3 → Lambda → Airflow
- Low latency  
- Lightweight  
- Suitable for smaller workloads  

---

## Airflow Responsibilities

- DAG orchestration  
- Retry handling  
- Monitoring  
- SLA enforcement  

---

# 📈 Logging & Observability

- Centralized logging configuration  
- Structured logs  
- Error tracking  
- Execution traceability  

---

# 🧪 Testing

- Unit tests for transformation logic  
- Schema validation checks  
- Salary band test cases  
- Feature computation assertions  

## Testing Ensures

- Regression prevention  
- Production reliability  
- CI integration readiness  

---

# 🧩 Challenges Faced

### Salary Inconsistency
Different formats and null values required normalization strategy.

### Correlation Analysis
Education level required encoding before correlation computation.

### Notebook to Production Transition
Refactoring exploratory code into modular, testable components required architectural restructuring.

### Vendor Abstraction
Designing read/write flexibility while keeping implementation simple.

---

# 🎯 Key Learnings

- Production pipelines require strong modularity  
- Logging & validation are critical for maintainability  
- Event-driven orchestration reduces operational complexity  
- Packaging improves deployment maturity  
- Layered architecture simplifies vendor changes  

---

# 🔄 Scalability Considerations

- Partitioned Parquet writes  
- Cloud storage abstraction  
- Idempotent processing  
- Config-driven environment switching  
---

# 🏁 How to Run Locally

```bash
pip install -r requirements.txt
python main.py
```
