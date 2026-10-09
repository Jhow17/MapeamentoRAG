---
title: "IBM Informix"
slug: "ibm-informix-connectors"
status: "new"
updated: 2026-07-20T17:32:39Z
published: 2026-07-20T21:00:01Z
canonical: "helpcenter.securiti.ai/ibm-informix-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# IBM Informix

IBM Informix is a fast, embeddable relational database server designed for high-availability OLTP workloads, IoT applications, and embedded data management. Originally developed by Informix Corporation and acquired by IBM in 2001, it has a long track record in mission-critical environments across retail, finance, manufacturing, and transportation — valued particularly for its small footprint, self-managing capabilities, and support for extended data types such as time series and spatial data.

The IBM Informix connector lets you integrate your Informix deployments with Securiti to discover and govern structured data stored across your relational and object-relational databases.

IBM Informix falls under the category of monitored, structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| IBM Informix (Self-hosted) | - Sensitive Data Intelligence (Standard data scan) - DSR Automation using SQL queries |

### Supported pod types

Standard Securiti Pod.

### Supported authentication methods

IBM Informix (self-hosted) supports Basic authentication method, using username and password.

### Supported items for classification scans

Securiti supports scanning data items for IBM Informix.

### Prerequisites for configuring IBM Informix Self-hosted connector

#### 1. Admin access

You must have admin access to obtain the required "Connect" permission and Table-level privileges (Alter, Index, References), etc., so you can proceed with the Authentication.

For more information, see [Obtain database credentials for your IBM Informix configuration](/latest/docs/grant-permissions-and-obtain-authentication-credentials-in-informix).

#### 2. Pod deployment

You must deploy a Securiti pod in your environment to connect your IBM Informix (Self-hosted) connector.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 3. Use cases and Permissions

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | N/A | Grant **Connect** permissions and table-level privileges to the relevant table or view. | These permissions let Securiti connect with the database in IBM Informix for table-level privileges for all users or a particular user. These permissions also build the Personal Data Index for DSR Automation and enables PII data search. |

### Connect IBM Informix with Securiti

To configure the IBM Informix (Self-hosted) connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain database credentials for your IBM Informix configuration](/latest/docs/grant-permissions-and-obtain-authentication-credentials-in-informix).
3. [Connecting IBM Informix with Securiti](/latest/docs/connect-ibm-informix-with-securiti).
4. [Configure data scans for IBM Informix](/latest/docs/configure-ibm-informix-data-scanning).

#### Additional resources

- For more information about how Securiti uses the IBM Informix data to respond to DSR requests, see [Fulfilling IBM Informix DSR requests](/latest/docs/fulfilling-dsr-requests-in-informix).
