## 1. What is a Database?

A database is an organised place to store information on a computer.

Can store text, numbers, images, videos, documents.

Managed using DBMS (Database Management System).

Helps save, update, and retrieve data easily.

# Why databases are important

Run daily operations (customers, orders, inventory).

Handle specialised data (engineering, finance).

Power systems (libraries, travel bookings).

# Key benefits:

Efficient scaling

Data integrity

Data security

Data analytics

## 2. Types of Databases
## Relational (SQL)

Tables: rows + columns.

Uses SQL.

Good for structured data + relationships.

Examples: RDS, Aurora, MySQL, PostgreSQL.

## NoSQL

Flexible structure (documents, key-value).

Handles fast-growing, unstructured data.

Examples: DynamoDB, DocumentDB.

## Graph Databases

Store nodes + relationships.

For connected data (social networks).

Example: Neptune.

## In-Memory

Data stored in RAM for speed.

Examples: ElastiCache (Redis/Memcached), MemoryDB.

## Time Series

Stores data over time (metrics, logs).

Example: Timestream.

## Data Warehouse

Analytics + reporting (large datasets).

Example: Redshift.

## Ledger Databases

Immutable, cryptographically verifiable records.

Example: QLDB.

## 3. AWS Main Database Services
# Amazon RDS (Relational)

Fully managed SQL databases.

Engines: MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Aurora.

## Key features:

Automated backups

Multi-AZ for high availability

Read replicas

Scaling storage + compute

Monitoring (CloudWatch)

Less admin than EC2 or on-premises setups.

## Amazon Aurora

High-performance relational DB (MySQL + PostgreSQL compatible).

Faster than traditional MySQL/Postgres.

Auto-scaling storage (up to 128TB).

Highly available, fault-tolerant.

Works with RDS interface.

Serverless option available.

## Amazon ElastiCache (In-Memory)

Super-fast in-memory caching.

For web sessions, leaderboards, dashboards.

Engines: Redis, Memcached.

Reduces load on databases.

## Amazon DynamoDB (NoSQL)

Fully managed, serverless key-value database.

Very high performance, low latency.

Automatic scaling.

Features:

Global tables

Continuous backups

DynamoDB Accelerator (DAX) for 10x faster reads

## Amazon Redshift (Data Warehouse)

Petabyte-scale analytics service.

Columnar storage + parallel processing.

For BI dashboards, trend analysis, big data insights.

Runs SQL queries on huge datasets.

## Amazon EMR (Big Data Processing)

Managed Hadoop/Spark clusters.

Used for processing large datasets.

Common for ETL, logs, clickstream analysis, ML pipelines.

## Amazon Athena (Serverless Query)

Query data directly in S3 using SQL.

No servers to manage.

Great for ad-hoc queries and data lake analysis.

## Amazon Neptune (Graph Database)

Designed for highly connected data.

Query languages: Gremlin, SPARQL, openCypher.

Used for fraud detection, recommendations, social graphs.

## Amazon QuickSight (BI Visualization)

Serverless dashboard and reporting service.

Uses SPICE in-memory engine.

Integrates with S3, Athena, Redshift, RDS.

Build and share dashboards.

## AWS Glue (ETL)

Fully managed ETL service for preparing data.

Crawlers build Data Catalog.

Transform data using visual or code-based tools.

Supports batch + streaming.

## AWS DMS (Database Migration Service)

Migrates databases to AWS with minimal downtime.

Supports Oracle, SQL Server, MySQL, PostgreSQL, MongoDB, etc.

Used for migration + continuous replication.

## 4. Other AWS Database Services (Good to Know)
Amazon DocumentDB

Document database compatible with MongoDB.

For JSON-style workloads.

## Amazon Timestream

Time series database for metrics, IoT, monitoring.

## Amazon QLDB

Immutable, cryptographically verifiable ledger database.

## Amazon Managed Blockchain

Create blockchain networks (Hyperledger Fabric, Ethereum).
