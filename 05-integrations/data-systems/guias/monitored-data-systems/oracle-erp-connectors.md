---
title: "Oracle ERP"
slug: "oracle-erp-connectors"
status: "new"
updated: 2026-07-25T14:56:23Z
published: 2026-07-28T21:00:00Z
canonical: "helpcenter.securiti.ai/oracle-erp-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Oracle ERP

Oracle ERP is a cloud-native SaaS suite that connects and centralizes core enterprise functions, including financial management, procurement, supply chain, and project management. into a single unified system.

The Oracle ERP connector lets you integrate your Oracle ERP environment with Securiti to discover and govern structured financial and operational data stored across your enterprise resource planning modules.

Oracle ERP falls under the category of Monitored, Structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Oracle ERP (Securiti Cloud) | - Sensitive Data Intelligence (Standard Data Scan) |

### Supported authentication methods

- For Securiti Cloud connector:
  - Basic authentication

### Supported items for classification scans

Securiti scans the standard data items for Oracle ERP (Securiti Cloud) connectors.

- Databases
- Files
- Apps

### Prerequisites for configuring Oracle ERP connector

#### 1. Admin access

You must have admin access in Oracle ERP to obtain credentials to authenticate your connector.

For more information, see [Acquire authentication credentials in Oracle ERP](/latest/docs/acquire-authentication-credentials-in-oracle-erp).

#### 2. Use cases and permissions for Oracle ERP

This table covers use cases and permissions required for Oracle ERP (Securiti Cloud) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Sensitive Data Intelligence (SDI) | N/A | - Access to obtain params**:** - **Base URL** - **User Name** - **Password** | These permissions let Securiti to read files and schema metadata in Oracle ERP Cloud for data scan purposes. |

### Steps to connect Oracle ERP (Securiti Cloud) connector with Securiti

To configure the Oracle ERP connector, perform the procedures in the following topics:

1. [Acquire authentication credentials in Oracle ERP](/latest/docs/acquire-authentication-credentials-in-oracle-erp).
2. [Connect Oracle ERP Cloud connector with Securiti](/latest/docs/connect-oracle-erp-cloud-connector-with-securiti).
3. [Initiate Oracle ERP data scanning](/latest/docs/initiate-oracle-erp-learning).

#### Additional resources

- [Fulfilling DSR requests for Oracle ERP](/latest/docs/fulfilling-dsr-requests-for-oracle-erp).
