---
title: "IBM Netezza"
slug: "ibm-netezza-connectors"
status: "new"
updated: 2026-07-16T06:23:02Z
published: 2026-07-16T06:23:06Z
canonical: "helpcenter.securiti.ai/ibm-netezza-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# IBM Netezza

IBM Netezza is a high-performance data warehouse platform designed for large-scale analytics and business intelligence workloads. By connecting IBM Netezza with Securiti, organizations can discover and classify sensitive data through Discovery Scan and automate Data Subject Requests (DSR) using SQL queries, helping improve data governance and streamline privacy compliance.

IBM Netezza data system falls under the [Monitored, Unstructured data systems](/latest/docs/getting-started-with-data-system-connectors) category.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| IBM Netezza (Self-hosted) | - DSR Automation - Sensitive Data Intelligence (Discovery Scan) |

### Supported Pod types

Securiti supports standard pod for IBM Netezza. For more information, see [Configuring Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

### Supported authentication method

Securiti supports Basic authentication method for IBM Netezza:

### Prerequisites for configuring IBM Netezza connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your IBM Netezza with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. IBM Netezza instance

You must have access to a running IBM Netezza instance to activate the connector. If you do not manage the instance, coordinate with your IBM Netezza administrator to obtain the required access and configuration details.

#### 3. Use cases and Permissions

Use the table below for permissions and use cases for IBM Netezza.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (Discovery Scan) - DSR automation using SQL queries | N/A | Grant **Select** Privileges to database. | These permissions let Securiti read the files IBM Netezza for classification purposes and to build the Personal Data Index for DSR Automation. |

### Connect IBM Netezza connectors with Securiti

This section covers the methods to integrate your IBM Netezza with Securiti.

#### Steps to connect the IBM Netezza connector with Securiti

To configure the IBM Netezza (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain permissions and authentication credentials in IBM Netezza](/latest/docs/obtain-permissions-and-authentication-credentials-in-ibm-netezza).
3. [Connecting IBM Netezza with Securiti](/latest/docs/connecting-ibm-netezza-with-securiti).
4. [Configure discovery scans in IBM Netezza](/latest/docs/configure-discovery-scans-in-ibm-netezza).

**Additional resources**

- [Fulfilling DSR requests in IBM Netezza](/latest/docs/fulfilling-dsr-requests-in-ibm-netezza).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
