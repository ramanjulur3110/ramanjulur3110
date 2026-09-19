# Hi, I'm Rakesh Ramanjulu 👋

### Data Engineer | Python • SQL • PostgreSQL • Airflow • dbt • Docker • Data Platforms

**I build data systems from the source application through ingestion, orchestration, transformation, modeling, and analytics.**

My background in **production support and operations** influences how I approach data engineering: build for failure, preserve history, automate recovery, and make systems observable.

---

## 🚀 Featured Projects

| Project                                                             | Focus                                      | Stack                               |
| ------------------------------------------------------------------- | ------------------------------------------ | ----------------------------------- |
| **[🛒 E-Commerce Data Platform](https://github.com/ramanjulur3110/e-Commerce-Data-Platform)**              | OLTP → CDC → Streaming → Lakehouse         | Python • PostgreSQL • Kafka • Docker        |
| **[💱 Currency Exchange Data Platform](https://github.com/ramanjulur3110/End_to_End_Currency_Exchange_Rate_ELT_Pipeline)**       | Batch ingestion, orchestration & analytics | Python • Airflow • dbt • MotherDuck |
| **[❄️ Snowflake + dbt Analytics Engineering](https://github.com/ramanjulur3110/dbt-snowflake-airbnb-pipeline)** | ELT, dimensional modeling & CI/CD          | Snowflake • dbt • GitHub Actions    |
| **[🏛️ SQL Server Data Warehouse](https://github.com/ramanjulur3110/SQL_Data_Warehouse_Project)**            | Traditional ETL & dimensional warehousing  | SQL Server • T-SQL                  |

### 🔨 Currently Building

**E-Commerce Data Platform --- Phases 1--3 Complete ✅ \| Phase 4 In
Progress 🚧**

`Source Platform → PostgreSQL → Debezium → Kafka → PySpark → Databricks Bronze → dbt → Silver → Gold`

The operational platform, CDC/event-streaming pipeline, and Databricks
Bronze ingestion layer are running. Current development is focused on
**dbt transformations for the Silver layer**, followed by Gold
analytical models.

------------------------------------------------------------------------

## 👨‍💻 About Me

I'm a Data Engineer with a background in **production support and
operations**.

That experience shaped how I think about engineering. A successful
pipeline isn't just one that moves data---it should also be possible to
understand what happened when something goes wrong.

I design projects around:

-   🔍 **Observability** --- Can I determine what happened?
-   🧾 **Auditability** --- Can I reconstruct historical behavior?
-   🔄 **Recoverability** --- Can processing safely retry or restart?
-   🕒 **History** --- Is enough state preserved to investigate
    problems?
-   🧪 **Data Quality** --- Can incorrect data be detected before it
    propagates?
-   📦 **Reproducibility** --- Can the environment be rebuilt
    consistently?
-   ⚙️ **Automation** --- Can repetitive operational work be eliminated?

Rather than building isolated demos, I increasingly focus on
**production-inspired systems that generate, move, transform, model,
monitor, and serve data.**

------------------------------------------------------------------------

# 🏗️ Engineering Projects

## 🛒 E-Commerce Data Platform

> **Current flagship project --- building and operating an end-to-end,
> production-inspired data platform from the source system forward.**

Rather than starting with a prepared dataset, I built the operational
system that creates the data.

The project runs as a continuously operating e-commerce platform with
independent Python services handling orders, payments, inventory,
fulfillment, shipping, and refunds. The platform is containerized with
Docker, deployed with Kubernetes, dynamically scales processing
workloads, and uses Slack for operational monitoring and alerts.

Changes in PostgreSQL are captured from the WAL using Debezium, streamed
through Apache Kafka, processed by a Python/PySpark consumer, and
written into the Databricks Lakehouse.

### Current Architecture

``` text
E-Commerce Platform
        │
        ▼
   PostgreSQL
        │
        ▼
       WAL
        │
        ▼
    Debezium
        │
        ▼
 Apache Kafka
        │
        ▼
Python / PySpark
        │
        ▼
Databricks Bronze
        │
        ▼
       dbt
        │
        ▼
 Silver → Gold
```

### Project Roadmap

**Phase 1:** ✅ E-Commerce Source Platform\
**Phase 2:** ✅ CDC & Apache Kafka Streaming\
**Phase 3:** ✅ PySpark / Databricks Bronze\
**Phase 4:** 🚧 dbt / Silver & Gold\
**Phase 5:** ⏳ Public Data API\
**Phase 6:** ⏳ Apache Airflow\
**Phase 7:** ⏳ Power BI / Cloud Deployment

### Technologies

**Python • PostgreSQL • SQL • Docker • Kubernetes • Debezium • Apache
Kafka • PySpark • Databricks • Delta Lake • dbt • Slack**

The goal is to understand the entire lifecycle of data --- from the
application that creates it, through CDC and streaming, into the
lakehouse, and eventually to the systems that consume it.

**[→ Explore the E-Commerce Data
Platform](https://github.com/ramanjulur3110/e-Commerce-Data-Platform)**

## **More building. More breaking. More learning. More coffee. ☕**

## 💱 Currency Exchange Data Platform

### `REST API → Python → Airflow → MotherDuck → dbt → Analytics → Tableau`

A complete batch-oriented data platform built to explore how scheduled
pipelines behave **operationally**, not simply how data moves from A to
B.

### Engineering Highlights

-   Built a Python ingestion framework supporting **full, scheduled, and
    backfill processing**
-   Orchestrated scheduled execution and retries with **Apache Airflow**
-   Containerized pipeline components with **Docker Compose**
-   Built staging, dimensional, fact, and presentation layers using
    **dbt**
-   Implemented dimensional data modeling
-   Added automated data-quality and relationship testing
-   Implemented dbt snapshots for historical dimension tracking
-   Created curated analytics views for downstream consumption
-   Added pipeline auditing and structured logging
-   Integrated success, warning, and failure notifications
-   Designed graceful handling for expected no-data scenarios
-   Added operational monitoring around pipeline runtime
-   Built a Tableau reporting layer
-   Designed the project for reproducible deployment

### Architecture

``` text
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

**Technologies:** Python • SQL • Apache Airflow • Docker • dbt • DuckDB
• MotherDuck • Tableau • Git

**[→ Explore the Currency Exchange Data
Platform](https://github.com/ramanjulur3110/End_to_End_Currency_Exchange_Rate_ELT_Pipeline)**

------------------------------------------------------------------------

## ❄️ Snowflake + dbt Analytics Engineering

A modern ELT project demonstrating analytics-engineering patterns using
Snowflake and dbt.

### Engineering Highlights

-   Built an end-to-end ELT workflow on Snowflake
-   Developed modular staging and analytics models
-   Implemented dimensional data modeling
-   Used dbt snapshots for **SCD Type 2 history**
-   Added automated data-quality testing
-   Created reusable dbt macros
-   Generated project documentation
-   Implemented CI/CD workflows using GitHub Actions

**Technologies:** Snowflake • dbt • SQL • GitHub Actions • CI/CD

**[→ Explore the Snowflake + dbt
Project](https://github.com/ramanjulur3110/dbt-snowflake-airbnb-pipeline)**

------------------------------------------------------------------------

## 🏛️ SQL Server Data Warehouse

A traditional relational data warehouse demonstrating foundational
warehousing and ETL architecture.

### Engineering Highlights

-   Designed a multi-layer warehouse architecture
-   Built ETL ingestion and transformation workflows
-   Implemented fact and dimension models
-   Designed star-schema analytical structures
-   Developed stored procedures for transformation workflows
-   Applied data-cleaning and validation logic

**Technologies:** SQL Server • T-SQL • ETL • Dimensional Modeling • Star
Schema

**[→ Explore the SQL Server Data
Warehouse](https://github.com/ramanjulur3110/SQL_Data_Warehouse_Project)**

------------------------------------------------------------------------

# 🧰 Engineering Toolkit

  -----------------------------------------------------------------------
  Area                                Technologies
  ----------------------------------- -----------------------------------
  **Languages**                       Python • SQL

  **Databases / Warehouses**          PostgreSQL • Snowflake • SQL Server
                                      • DuckDB

  **CDC / Streaming**                 Debezium • Apache Kafka •
                                      PostgreSQL Logical Replication

  **Transformation**                  dbt Core • Pandas • PySpark

  **Orchestration**                   Apache Airflow

  **Data Processing / Lakehouse**     Apache Spark • Databricks • Delta
                                      Lake

  **Containers / Infrastructure**     Docker • Docker Compose •
                                      Kubernetes

  **Cloud / Platforms**               AWS • MotherDuck • Databricks

  **DevOps / Operations**             Git • GitHub • GitHub Actions •
                                      CI/CD • Slack

  **Analytics**                       Tableau • Matplotlib

  **Integration**                     REST APIs

  **Currently Building Toward**       Silver / Gold Models • Public API •
                                      Power BI
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 🧠 Engineering Philosophy

I build projects around questions engineers encounter when systems
actually have to operate:

> **What happens when the source is unavailable?**

> **Can a failed pipeline safely restart without corrupting data?**

> **Can I determine how long an order remained in a particular state?**

> **How would I investigate yesterday's production behavior?**

> **What should be logged, audited, tested, or retained?**

> **How does transactional data become analytical data?**

> **When does batch processing stop being the right architecture?**

These questions drive my projects more than simply adding another
technology to the stack.

------------------------------------------------------------------------

# 🎯 What I'm Building Toward

My goal is to continue progressing beyond individual ETL pipelines
toward designing and operating **complete data platforms**.

``` text
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

I want to understand the complete lifecycle of data---from the
operational system where a transaction originates to the analytical
platform where that information becomes useful.

**The technology matters. Understanding how the pieces behave together
matters more.**

------------------------------------------------------------------------

# 📚 Additional Projects

My repositories also include smaller projects covering foundational SQL
and Python engineering.

**SQL:** Window functions • CTEs • Query optimization • Data cleaning •
Analytical SQL

**Python:** Pandas • NumPy • File processing • Data transformation •
Exploratory analysis • Automation

These projects represent the foundations that eventually evolved into
the larger engineering platforms above.

------------------------------------------------------------------------

## 📫 Connect

I'm always interested in discussing **data engineering, Python, SQL,
pipeline architecture, and the operational challenges behind reliable
data systems.**

**LinkedIn: [Rakesh Ramanjulu](https://www.linkedin.com/in/rakesh-ramanjulu-81ab7858/)** • **[GitHub
Projects](https://github.com/ramanjulur3110)**

------------------------------------------------------------------------

### Thanks for stopping by 👋

**Build it. Break it. Understand why it broke. Make the next version
better.**
