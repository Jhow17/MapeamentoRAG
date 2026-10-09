---
title: "Cloudera Impala"
slug: "cloudera-impala-connectors-1"
status: "new"
updated: 2026-07-16T05:46:18Z
published: 2026-07-16T05:46:18Z
canonical: "helpcenter.securiti.ai/cloudera-impala-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Cloudera Impala

Cloudera Impala is an open-source, interactive, distributed SQL query engine that enables users to conduct real-time queries on data stored in Hadoop Distributed File System (HDFS), Apache HBase, and Amazon Simple Storage Service (S3).

Cloudera Impala falls under the category of Monitored, Structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors#data-systems-classification).

### Supported Pod types

- Securiti connects to Cloudera Impala using a customer self hosted pod connector. For more information, see [Configuring Securiti pods](/v1/docs/securiti-pods-and-elastic-pods).

### Supported authentication methods

Cloudera Impala supports **Basic** authentication type for authenticating and integrating with Securiti. The basic authentication method uses:

- Username
- Password

### Prerequisites for configuring Cloudera Impala connector

You must have an active database instance of Cloudera Impala available with admin access before connector activation.

#### Use case and permission for Cloudera Impala connector

You need **read access** permission to the Cloudera Impala database for the following Securiti modules

- Sensitive Data Intelligence (Discovery scan)
- Data Subject Rights
- Data Scan Policy

You must provide **read access** for these module features and scans that are supported for the following data entities.

- Tables
- Columns

For more information, see [Create a user in Cloudera Impala database instance](/v1/docs/create-a-user-in-cloudera-impala-database-instance) to assign **read access** permission to the Cloudera Impala user.

### Steps to connect Cloudera Impala with Securiti

To configure the Cloudera Impala connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Create a user in Cloudera Impala database instance](/latest/docs/create-a-user-in-cloudera-impala-database-instance).
3. [Connecting Cloudera Impala with Securiti](/latest/docs/activate-the-cloudera-impala-connector-in-securiti).
4. [Configure discovery scans in Cloudera Impala](/latest/docs/configure-discovery-scans-in-cloudera-impala).
5. Do [Table Training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) for your Cloudera Impala data system connector.

For more information, see [Fulfilling DSR requests in Cloudera Impala](/v1/docs/fulfilling-dsr-requests-in-cloudera-impala) about how Securiti uses the Cloudera Impala data to respond to DSR requests.

The cloud term typically refers to cloud computing. Cloud computing is a technology that allows users to access and use computing resources and services over the internet, often from remote data centers.
