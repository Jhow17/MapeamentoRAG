---
title: "Oracle Sales Cloud"
slug: "oracle-sales-cloud-connectors-1"
status: "new"
updated: 2026-08-10T13:53:34Z
published: 2026-08-10T20:09:39Z
canonical: "helpcenter.securiti.ai/oracle-sales-cloud-connectors-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Oracle Sales Cloud

Oracle Sales Cloud is a cloud-based CRM and sales force automation platform designed to help mid-sized to large enterprises streamline and manage the full sales cycle. It integrates natively with Oracle ERP, HCM, and SCM, giving sales teams and managers a unified view of customer data, AI-driven insights, and real-time forecasting without reliance on third-party integrations.

The Oracle Sales Cloud connector lets you integrate with Securiti to discover and govern sales and customer relationship data processed across your leads, opportunities, contacts, and accounts.

Oracle Sales Cloud falls under the category of monitored, scanless data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Oracle Sales Cloud (Securiti Cloud) | - DSR Automation using APIs |

### Supported authentication methods

- For Securiti Cloud connector:
  - Basic authentication

### Prerequisites for configuring Oracle Sales Cloud connector

#### 1. Admin access

You must have admin access in **Oracle Cloud > Sales and Service Login** to obtain credentials to authenticate your connector.

For more information, see [Acquire authentication credentials in Oracle Sales Cloud](/latest/docs/acquire-authentication-credentials-in-oracle-sales-cloud).

#### 2. Use cases and permissions for Oracle Sales Cloud

This table covers use cases and permissions required for Oracle Sales Cloud connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Data Subject Request (DSR) | N/A | - Access to **Sales and Service Login** in Oracle Cloud application. - Access to obtain: - Base URL - User Name - Password | These permissions let Securiti read the files and databases. These permissions also build the Personal Data Index for DSR Automation. |

### Steps to connect Oracle Sales Cloud connector with Securiti

To configure the Oracle Sales Cloud connector, perform the procedures in the following topics:

1. [Acquire authentication credentials in Oracle Sales Cloud](/latest/docs/acquire-authentication-credentials-in-oracle-sales-cloud).
2. [Connect Oracle Sales Cloud connector with Securiti](/latest/docs/connect-oracle-sales-cloud-connector-with-securiti).

#### Additional resources

- [Fulfilling DSR requests for Oracle Sales Cloud](/latest/docs/fulfilling-dsr-requests-for-oracle-sales-cloud).
- [Understanding enhanced DSR request processing](https://helpcenter.securiti.ai/docs/understanding-identifiers-for-dsr-request-processing)
- [Oracle Sales Cloud data element types for enhanced DSR processing](/latest/docs/oracle-sales-cloud-data-element-types-for-enhanced-dsr-processing).
