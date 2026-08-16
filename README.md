# Hi, I'm Rakesh Ramanjulu 👋

### Data Engineer | Python • SQL • PostgreSQL • Airflow • dbt • Docker • Data Platforms

**I build data systems from the source application through ingestion, orchestration, transformation, modeling, and analytics.**

My focus is increasingly on building **production-inspired systems** rather than isolated pipelines—systems that generate data, move it, transform it, monitor it, preserve its history, and make it useful downstream.

---

## 👨‍💻 About Me

I'm a Data Engineer with a background in **production support and operations**, which strongly influences how I approach engineering.

I don't just think about whether a pipeline works.

I think about what happens when it **doesn't**.

That means designing around:

* 🔍 **Observability** — Can I tell what happened?
* 🧾 **Auditability** — Can I reconstruct what happened later?
* 🔄 **Recoverability** — Can the system safely retry or restart?
* 🕒 **History** — Do I preserve enough state to troubleshoot?
* 🧪 **Data Quality** — Can bad data be detected before it spreads?
* 📦 **Reproducibility** — Can the environment be rebuilt consistently?
* ⚙️ **Automation** — Can repetitive operational work be eliminated?

My projects are designed to explore these problems across **OLTP systems, batch pipelines, analytics platforms, and streaming architectures**.

---

# 🏗️ Featured Engineering Projects

## 🛒 E-Commerce Data Platform

### `Python → PostgreSQL → CDC → Kafka → Stream Processing → Databricks`

> **Current flagship project — building the source system and data platform together.**

Rather than starting with a prepared dataset, this project starts at the source.

I'm building a continuously running Python application that simulates an operational e-commerce environment, generates realistic transactional activity, and writes it into a PostgreSQL OLTP database.

The long-term goal is to evolve that operational system into a complete streaming and analytical data platform.

### ⚡ Currently Running

```text
Python Order Generator
        │
        ▼
PostgreSQL OLTP
        │
        ├── Customers
        ├── Products
        ├── Orders
        ├── Order Details
        └── Operational History
```

The workload runs continuously inside Docker, creating transactional data that can serve as the source for downstream engineering.

### 🔜 Platform Evolution

```text
Python Application
       │
       ▼
PostgreSQL OLTP
       │
       ▼
   Debezium CDC
       │
       ▼
     Kafka
       │
       ▼
Spark / Streaming
       │
       ▼
   Databricks
       │
       ▼
Analytics / Monitoring
```

### Engineering Focus

* Continuous synthetic e-commerce transaction generation
* Relational OLTP schema design
* Customer, product, order, and order-line relationships
* Order lifecycle and state-history tracking
* PostgreSQL transaction processing
* Dockerized application deployment
* Long-running workload operation
* Development and production database separation
* Database backup and refresh strategies
* Failure investigation and operational history
* CDC and event-driven architecture
* Streaming data processing
* Lakehouse architecture

**Current:** Python • PostgreSQL • Docker • SQL

**Planned Platform:** Debezium • Apache Kafka • Apache Spark • Databricks

---

## 💱 Currency Exchange Data Platform

### `REST API → Python → Airflow → DuckDB / MotherDuck → dbt → Analytics → Tableau`

A complete batch-oriented data platform built to explore how a scheduled pipeline behaves **operationally**, not just how data moves from A to B.

### Engineering Highlights

* Built a Python ingestion framework supporting **full, scheduled, and backfill processing**
* Orchestrated execution and retries with **Apache Airflow**
* Containerized pipeline components with **Docker Compose**
* Built staging, dimensional, fact, and presentation layers with **dbt**
* Implemented fact and dimension modeling
* Added automated data-quality and relationship tests
* Implemented dbt snapshots for historical dimension tracking
* Built curated analytics views for downstream consumers
* Added pipeline audit information and structured logging
* Integrated success, warning, and failure notifications
* Designed graceful handling for expected no-data scenarios
* Added operational monitoring around pipeline runtime
* Built a Tableau reporting layer
* Designed the project for reproducible deployment

### Architecture

```text
Frankfurter API
      │
      ▼
Python Ingestion
      │
      ▼
DuckDB / MotherDuck
      │
      ▼
     dbt
      │
      ├── Staging
      ├── Dimensions
      ├── Facts
      └── Presentation
              │
              ▼
           Tableau

      ▲
      │
Apache Airflow
Orchestration + Monitoring
```

**Technologies:** Python • SQL • Apache Airflow • Docker • dbt • DuckDB • MotherDuck • Tableau • Git

---

## ❄️ Snowflake + dbt Analytics Engineering

A modern ELT project demonstrating analytics engineering patterns using Snowflake and dbt.

### Engineering Highlights

* Built an end-to-end ELT workflow on Snowflake
* Developed modular staging and analytics models
* Implemented dimensional data modeling
* Used dbt snapshots for **SCD Type 2 history**
* Added automated data-quality testing
* Created reusable dbt macros
* Generated project documentation
* Implemented CI/CD workflows with GitHub Actions

**Technologies:** Snowflake • dbt • SQL • GitHub Actions • CI/CD

---

## 🏛️ SQL Server Data Warehouse

A traditional relational data warehouse demonstrating foundational warehousing and ETL architecture.

### Engineering Highlights

* Designed a multi-layer warehouse architecture
* Built ETL ingestion and transformation workflows
* Implemented fact and dimension models
* Designed star-schema analytical structures
* Developed stored procedures for transformation workflows
* Applied data-cleaning and validation logic

**Technologies:** SQL Server • T-SQL • ETL • Dimensional Modeling • Star Schema

---

# 🧰 Engineering Toolkit

| Area                    | Technologies                                 |
| ----------------------- | -------------------------------------------- |
| **Languages**           | Python • SQL                                 |
| **Databases**           | PostgreSQL • Snowflake • SQL Server • DuckDB |
| **Transformation**      | dbt Core • Pandas • PySpark                  |
| **Orchestration**       | Apache Airflow                               |
| **Data Processing**     | Apache Spark                                 |
| **Containers**          | Docker • Docker Compose                      |
| **Cloud / Platforms**   | AWS • MotherDuck                             |
| **DevOps**              | Git • GitHub • GitHub Actions • CI/CD        |
| **Analytics**           | Tableau • Matplotlib                         |
| **Integration**         | REST APIs                                    |
| **Currently Exploring** | Kafka • Debezium • Databricks                |

---

# 🧠 How I Approach Data Engineering

I try to build projects around questions that engineers encounter when systems actually have to operate:

**What happens when the source is unavailable?**

**What happens when a task needs to retry?**

**Can I determine how long an order remained in a particular state?**

**Can a failed pipeline safely restart without corrupting data?**

**How would I investigate yesterday's production behavior?**

**What should be logged, audited, tested, or retained?**

**How does transactional data become analytical data?**

**When does batch processing stop being the right architecture?**

Those questions drive my projects more than simply adding another technology to the stack.

---

# 🔬 Currently Building & Exploring

My current work is centered around evolving the e-commerce platform from an operational application into a broader data ecosystem.

```text
OLTP
 │
 ├── PostgreSQL
 │
 ▼
Change Data Capture
 │
 ├── Debezium
 │
 ▼
Event Streaming
 │
 ├── Kafka
 │
 ▼
Stream Processing
 │
 ├── Spark
 │
 ▼
Lakehouse
 │
 └── Databricks
```

Alongside that work, I'm exploring:

* Streaming vs. batch architecture
* Change Data Capture
* Event-driven data systems
* Operational data modeling
* Historical state tracking
* Data observability
* Pipeline performance
* Semi-structured data processing
* Lakehouse architecture

---

# 📚 Additional Projects

My repositories also include smaller projects covering:

**SQL Engineering**

* Window functions
* CTEs
* Query optimization
* Data cleaning
* Analytical SQL

**Python Data Processing**

* Pandas
* NumPy
* File processing
* Data transformation
* Exploratory analysis
* Automation

These projects represent the foundations that eventually evolved into the larger data platforms above.

---

# 🎯 What I'm Building Toward

My goal is to continue progressing beyond individual ETL pipelines toward designing and operating **complete data platforms**.

That means understanding the entire lifecycle:

```text
Source Systems
      ↓
Data Generation
      ↓
Ingestion / CDC
      ↓
Batch & Streaming
      ↓
Storage
      ↓
Transformation
      ↓
Data Modeling
      ↓
Quality & Observability
      ↓
Analytics
```

The technology matters.

**Understanding how the pieces behave together matters more.**

---

## 📫 Connect

I'm always interested in discussing **data engineering, Python, SQL, pipeline architecture, and the operational problems behind reliable data systems.**

Feel free to connect with me on LinkedIn or explore the repositories behind these projects.

---

### Thanks for stopping by 👋

**Build it. Break it. Understand why it broke. Make the next version better.**
