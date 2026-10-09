---
title: "Understanding database connections and query management in SQL connectors"
slug: "understanding-database-connections-and-query-management-in-sql-connectors"
updated: 2025-11-02T10:51:56Z
published: 2025-11-03T06:08:21Z
canonical: "helpcenter.securiti.ai/understanding-database-connections-and-query-management-in-sql-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Understanding database connections and query management in SQL connectors

When integrating your SQL-based Data systems with Securiti for data classification, learning, or discovery, it’s important to understand how the platform uses database connection and query execution, especially if your environment has limits on simultaneous connections

This document explains how Securiti uses simple and multiple connections.

## Using simple connections

For every database operation, such as fetching metadata, counting rows, or sampling data, Securiti uses a stateless connection pattern, as follows:

1. Opens a new connection
2. Executes the query
3. And closes it immediately after

> [!WARNING]
> Important
> 
> Since each operation creates its own connection, the total number of database queries can quickly add up, especially when multiple tables are involved. In the case of scanning a table, you see multiple connections against multiple queries using the parallel execution method, as described below.

## Using multiple connections in parallel threads

Securiti scans tables in parallel rather than one at a time. This parallelism is enabled by a two-tier worker model inside each pod, which manages connections and executes queries efficiently at scale.

Use the following table to understand the two-tier worker model in pods that handles connections and query executions:

| Component | Explanation |
| --- | --- |
| Threads Manager | Threads Manager organizes scanning by allocating and supervising multiple Worker Threads across tables within a pod. It also controls Worker Threads concurrency to balance load and respect connection limits. |
| Worker Thread | Each Worker Thread handles one table at a time, enabling simultaneous connections and faster scans. Worker Thread performs per-table operations in parallel, such as: - Get columns - Count rows - Sample data - Fetch constraints > [!NOTE] > Note > > Worker threads run simultaneously, and multiple connections can be opened at once. |

## Worker Threads scalability

To efficiently scan large datasets and multiple tables, Securiti uses a scalable worker-thread model. Understanding how this scales helps you estimate the number of parallel database operations and manage load effectively, especially in environments with limited database connection capacity.

Use the following table to understand the process of scaling the pod worker thread model:

| Component | Description |
| --- | --- |
| Threads Managers per pod | Shows you how many Thread Manager processes are running inside each pod. See the example below. *2 Threads Manager per pod* |
| Concurrency per Thread Manager | Shows you the number of Worker Threads each Thread manager can handle for scanning tables. See the example below. *3 Worker Threads inside each Thread Manager* |
| Total Worker Threads | Shows you the total Worker Threads available in all Threads Managers per pod. See the example below. *6 Worker Threads* > [!NOTE] > Note > > The maximum limit for Total Worker Threads is 16. If Total Thread Worker is higher than 16, Securiti falls back to the maximum limit of 16. See the example below: > > For 3 Threads Manager per Pod and 6 Worker Threads, Securiti creates 16 Total Worker Threads because the upper limit is 16 Worker Threads. |

## Connections and query execution estimates

Each of these threads might open separate connections simultaneously, depending on the workload, increasing the total concurrent connections.

> [!NOTE]
> Note
> 
> The number of connections and queries in the table below are the best estimates. Actual numbers can vary based on the scan task, such as column discovery, row counts, sampling, and constraint fetches; table size; retries; and configured maximum limits, such as the 16 Worker Threads mentioned in the table.

The table below shows the estimated number of queries and connections:

| Operation | Detailed Description | Estimated Database Connections | Estimated query executions |
| --- | --- | --- | --- |
| Authentication | Performs the initial access check to verify the connection and fetch accessible table names. This step includes: - 1 database connection - 1 query execution to retrieve table metadata | 1 database connection | 1 query execution |
| Connector Scoped Sync | Fetches the metadata for the connector, which includes databases, schemas, and table names. - 1 Connection and 1 query for getting valid databases - 1 connection for each Database, and: - 1 query for getting Schemas - 1 query for getting Tables > [!NOTE] > Note > > The exact number of connections and queries may vary by connector. This estimate is based on 1 database. | 2 database connections | 3 queries execution |
| Diagnostic reports | Ensures that the data system is accessible and that the connector operations (fetching metadata and querying the data) can be performed. It requires the same number of connections and query execution to check as it does in the overall connection, plus scanning. Diagnostic report requires: - 3 connections and 5 query executions for the connection test - 35 connections and 35 query executions for the scanning test for each schema. > [!NOTE] > Note > > Connector diagnostics performs all operations, including authentication and scanning. | 38 connections per schema | 40 queries per schema |
| Constraint Queries | Fetches constraints in chunks (groups of tables), requiring 2 connections per chunk. It creates connections and executes queries in two parts: - 1 query and connection from the JDBC driver for **Primary Keys (PK)** - 1 query and connection from the database for other constraints, such as Foreign Key (FK) and Unique Key (UK). | 2 database connections | 2 queries execution |
| Fetch Table Columns | Retrieves metadata about table columns, such as names and types. It executes 1 dedicated query with 1 separate connection per table. | 1 database connection | 1 query execution |
| Fetch Row Count (Basic) | Executes a COUNT(*) or equivalent query to determine the number of rows. It is a basic and fast estimate in most connectors. > [!NOTE] > Note > > Fetch Row Count applies to each table being scanned. | 1 database connection | 1 query execution |
| Fetch Row Count (Alternate) | Works if the basic query fails or is not supported, a fallback query is used to count rows, typically more complex and requiring another database hit. | 1 database connections | 1 query execution |
| Fetch Indexes | Retrieves information about existing indexes on the table, such as primary, secondary, and composite. This helps classification and identity matching. It executes 1 query with 1 separate connection. | 1 database connections | 1 query execution |
| Fetch View Definition | If the table is a view, this query fetches the SQL definition using metadata. It executes 1 query with 1 separate connection. | 1 database connections | 1 query execution |
| First x rows Sampling | Executes a *LIMIT* query to fetch a small dataset. This limit value is configurable in the Discovery Scan Configuration. See the example below. *SELECT * FROM table LIMIT X* | 1 database connections | 1 query execution |
| Sampling – Random (worst case) | Performs random sampling queries repeatedly to avoid rows with null values. Each retry creates a new connection. Retries continue until a valid sample is found, up to a default limit of 25. | Up to 25 database connections | 25 query executions |
| CLOB Scanning (If selected) | Queries large text or blob columns for analysis. If selected, each CLOB-related operation uses a new connection. | 1 database connections | 1 query execution |
| Full Scan or Unique Identity (if selected) | Executes a full table scan to identify unique fields, such as candidate keys. Data is processed in chunks for scalability, and each scan uses its own connection. | 1 database connections | 1 query execution |
| EDM Scanning (if selected) | If Entity Data Matching (EDM) is enabled, the full table is fetched where EDM profiles match. The table is then scanned in chunks. Each scan involves a separate connection. | 1 database connections | 1 query execution |
| Total connections (All operations selected) | Estimated maximum number of database hits when all operations (standard plus optional) are selected. This also includes a worst-case sampling scenario with retries. | 76 database connections | 80 query executions |

> [!NOTE]
> Tip
> 
> Since the number of simultaneous connections can grow rapidly depending on:
> 
> - Number of threads
> - Number of tables
> - Number of operations per table
> 
> It’s important to tune concurrency and table limits based on your database’s capacity to handle concurrent sessions.

Data systems refer to the system where your data is stored. That can be in the form of files (text, audio, video), databases (tables and schemas), and streaming data (data in motion). Securiti supported most of the structured, unstructured, and streaming data systems.
