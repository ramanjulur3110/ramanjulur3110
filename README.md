# Hi, I'm Rakesh Ramanjulu 👋

### Data Engineer | Python • SQL • PostgreSQL • Airflow • dbt • Docker • Data Platforms

**I build data systems from the source application through ingestion, orchestration, transformation, modeling, and analytics.**

My background in **production support and operations** influences how I approach data engineering: build for failure, preserve history, automate recovery, and make systems observable.

---

## 🚀 Featured Projects

| Project                                                             | Focus                                      | Stack                               |
| ------------------------------------------------------------------- | ------------------------------------------ | ----------------------------------- |
| **[🛒 E-Commerce Data Platform](https://github.com/ramanjulur3110/e-Commerce-Data-Platform)**              | OLTP → CDC → Streaming → Lakehouse         | Python • PostgreSQL • Docker        |
| **[💱 Currency Exchange Data Platform](https://github.com/ramanjulur3110/End_to_End_Currency_Exchange_Rate_ELT_Pipeline)**       | Batch ingestion, orchestration & analytics | Python • Airflow • dbt • MotherDuck |
| **[❄️ Snowflake + dbt Analytics Engineering](https://github.com/ramanjulur3110/dbt-snowflake-airbnb-pipeline)** | ELT, dimensional modeling & CI/CD          | Snowflake • dbt • GitHub Actions    |
| **[🏛️ SQL Server Data Warehouse](https://github.com/ramanjulur3110/SQL_Data_Warehouse_Project)**            | Traditional ETL & dimensional warehousing  | SQL Server • T-SQL                  |

### 🔨 Currently Building

**E-Commerce Data Platform — Phase 1 Complete ✅**

`OLTP → CDC → Kafka → Stream Processing → Lakehouse → Analytics`

I'm currently evolving a continuously running e-commerce source system into an end-to-end streaming data platform.

---

## 👨‍💻 About Me

I'm a Data Engineer with a background in **production support and operations**.

That experience shaped how I think about engineering. A successful pipeline isn't just one that moves data—it should also be possible to understand what happened when something goes wrong.

I design projects around:

* 🔍 **Observability** — Can I determine what happened?
* 🧾 **Auditability** — Can I reconstruct historical behavior?
* 🔄 **Recoverability** — Can processing safely retry or restart?
* 🕒 **History** — Is enough state preserved to investigate problems?
* 🧪 **Data Quality** — Can incorrect data be detected before it propagates?
* 📦 **Reproducibility** — Can the environment be rebuilt consistently?
* ⚙️ **Automation** — Can repetitive operational work be eliminated?

Rather than building isolated demos, I increasingly focus on **production-inspired systems that generate, move, transform, model, monitor, and serve data.**

---

# 🏗️ Engineering Projects

## 🛒 E-Commerce Data Platform

### Phase 1 — OLTP Source System ✅

**Python • PostgreSQL • Docker • SQL**

> **Current flagship project — building an end-to-end data platform from the source system forward.**

Rather than beginning with a prepared dataset, I built the operational system that creates the data.

Phase 1 is a continuously running, containerized **e-commerce OLTP platform** consisting of independent Python services for transaction generation and payment processing backed by PostgreSQL.

The system produces evolving transactional data with realistic state transitions, payment outcomes, retry behavior, and historical records that will become the source for future CDC, streaming, and lakehouse pipelines.

### Current Architecture

```text
                   PostgreSQL OLTP
                         ▲
                         │
             ┌───────────┴───────────┐
             │                       │
      Order Generator         Payment Processor
           Python                  Python
             │                       │
             └───────────┬───────────┘
                         │
                  Docker Compose
```

The two application services operate independently and connect to PostgreSQL using dedicated **least-privilege service accounts**.

### Transaction Lifecycle

```text
Order Created
     │
     ▼
   PENDING
     │
     ▼
Payment INITIATED
     │
     ▼
  PROCESSING
     │
     ├──── APPROVED ────► PAID
     │
     ├──── DECLINED ────► FAILED
     │
     └──── TIMEOUT ─────► RETRY
```

Order and payment state changes are retained historically, allowing transaction behavior to be reconstructed and analyzed over time.

### Engineering Highlights

* Built independent **order-generation and payment-processing services**
* Designed a relational PostgreSQL OLTP model across transactional, historical, and reference tables
* Implemented realistic order and payment state progression
* Added payment approval, decline, timeout, and retry behavior
* Preserved complete order and payment state history
* Implemented shipping-class and state-based sales-tax calculations
* Created weighted distributions for products and payment methods
* Implemented transactional database operations across related tables
* Added graceful shutdown behavior for continuously running services
* Containerized the complete environment using **Docker Compose**
* Created dedicated PostgreSQL service accounts with **least-privilege permissions**
* Externalized credentials and runtime configuration through environment variables
* Created reproducible DDL and static-data deployment scripts
* Added operational SQL for transaction counts and progression validation
* Validated complete schema destruction and reconstruction from source-controlled scripts
* Deployed the platform as a continuously running NAS workload

### Platform Roadmap

```text
PHASE 1                 PHASE 2
OLTP                     CDC / Streaming
  │                            │
  ▼                            ▼
PostgreSQL ─────────────► Debezium
                               │
                               ▼
                             Kafka
                               │
                               ▼
                           PHASE 3
                    Processing / Lakehouse
                               │
                               ▼
                        Spark / PySpark
                               │
                               ▼
                          Databricks
                               │
                               ▼
                           PHASE 4
                  Analytics / Observability
```

**Phase 1:** ✅ Python • PostgreSQL • Docker
**Phase 2:** 🔜 Debezium • Apache Kafka
**Phase 3:** ⏳ Spark / PySpark • Databricks
**Phase 4:** ⏳ Analytics • Data Quality • Observability

The goal is to build the downstream data platform around a source system whose behavior I fully understand because I designed and built it.

**[→ Explore the E-Commerce Data Platform](YOUR_REPOSITORY_URL)**

---

## 💱 Currency Exchange Data Platform

### `REST API → Python → Airflow → MotherDuck → dbt → Analytics → Tableau`

A complete batch-oriented data platform built to explore how scheduled pipelines behave **operationally**, not simply how data moves from A to B.

### Engineering Highlights

* Built a Python ingestion framework supporting **full, scheduled, and backfill processing**
* Orchestrated scheduled execution and retries with **Apache Airflow**
* Containerized pipeline components with **Docker Compose**
* Built staging, dimensional, fact, and presentation layers using **dbt**
* Implemented dimensional data modeling
* Added automated data-quality and relationship testing
* Implemented dbt snapshots for historical dimension tracking
* Created curated analytics views for downstream consumption
* Added pipeline auditing and structured logging
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

**[→ Explore the Currency Exchange Data Platform](YOUR_REPOSITORY_URL)**

---

## ❄️ Snowflake + dbt Analytics Engineering

A modern ELT project demonstrating analytics-engineering patterns using Snowflake and dbt.

### Engineering Highlights

* Built an end-to-end ELT workflow on Snowflake
* Developed modular staging and analytics models
* Implemented dimensional data modeling
* Used dbt snapshots for **SCD Type 2 history**
* Added automated data-quality testing
* Created reusable dbt macros
* Generated project documentation
* Implemented CI/CD workflows using GitHub Actions

**Technologies:** Snowflake • dbt • SQL • GitHub Actions • CI/CD

**[→ Explore the Snowflake + dbt Project](YOUR_REPOSITORY_URL)**

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

**[→ Explore the SQL Server Data Warehouse](YOUR_REPOSITORY_URL)**

---

# 🧰 Engineering Toolkit

| Area                          | Technologies                                 |
| ----------------------------- | -------------------------------------------- |
| **Languages**                 | Python • SQL                                 |
| **Databases / Warehouses**    | PostgreSQL • Snowflake • SQL Server • DuckDB |
| **Transformation**            | dbt Core • Pandas • PySpark                  |
| **Orchestration**             | Apache Airflow                               |
| **Data Processing**           | Apache Spark                                 |
| **Containers**                | Docker • Docker Compose                      |
| **Cloud / Platforms**         | AWS • MotherDuck                             |
| **DevOps**                    | Git • GitHub • GitHub Actions • CI/CD        |
| **Analytics**                 | Tableau • Matplotlib                         |
| **Integration**               | REST APIs                                    |
| **Currently Building Toward** | Kafka • Debezium • Databricks                |

---

# 🧠 Engineering Philosophy

I build projects around questions engineers encounter when systems actually have to operate:

> **What happens when the source is unavailable?**

> **Can a failed pipeline safely restart without corrupting data?**

> **Can I determine how long an order remained in a particular state?**

> **How would I investigate yesterday's production behavior?**

> **What should be logged, audited, tested, or retained?**

> **How does transactional data become analytical data?**

> **When does batch processing stop being the right architecture?**

These questions drive my projects more than simply adding another technology to the stack.

---

# 🎯 What I'm Building Toward

My goal is to continue progressing beyond individual ETL pipelines toward designing and operating **complete data platforms**.

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

I want to understand the complete lifecycle of data—from the operational system where a transaction originates to the analytical platform where that information becomes useful.

**The technology matters. Understanding how the pieces behave together matters more.**

---

# 📚 Additional Projects

My repositories also include smaller projects covering foundational SQL and Python engineering.

**SQL:** Window functions • CTEs • Query optimization • Data cleaning • Analytical SQL

**Python:** Pandas • NumPy • File processing • Data transformation • Exploratory analysis • Automation

These projects represent the foundations that eventually evolved into the larger engineering platforms above.

---

## 📫 Connect

I'm always interested in discussing **data engineering, Python, SQL, pipeline architecture, and the operational challenges behind reliable data systems.**

**[LinkedIn](YOUR_LINKEDIN_URL)** • **[GitHub Projects](YOUR_GITHUB_URL)**

---

### Thanks for stopping by 👋

**Build it. Break it. Understand why it broke. Make the next version better.**
