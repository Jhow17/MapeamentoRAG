---
title: "SAP ECC"
slug: "sap-ecc-connectors-1"
status: "new"
updated: 2026-07-31T11:49:09Z
published: 2026-07-31T11:49:15Z
canonical: "helpcenter.securiti.ai/sap-ecc-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# SAP ECC

SAP ERP Central Component (SAP ECC) is an enterprise resource planning system that provides an integrated view of an organization’s core business processes. By integrating SAP ECC with Securiti, users can gain visibility into enterprise data and manage sensitive information in a centralized and compliant manner.

The SAP ECC data system falls under the [Monitored, Structured data systems](/latest/docs/managing-data-system-connectors).

### Supported Connector types and modules

| Connector type | Modules supported |
| --- | --- |
| SAP ECC (Self-hosted) | - Sensitive Data Intelligence (Discovery scan) - Data Subject Rights (DSR) |

### Supported Pod types

- Standard Securiti Pod.

### Supported authentication methods

SAP ECC supports the basic authentication method, including username and password.

### Supported items for the Classification scan

Securiti only scans the tables related to selected modules from:

- Financial Accounting and Controlling
- Human Resources
- Materials Management
- Sales And Distribution
- Project System
- Production Planning
- Plant Maintenance
- Quality Management
- Supply Chain Management

For more information about classifications in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites for configuring the SAP ECC connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your SAP ECC with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. User creation and profile assignment

You must create a user in the SAP ECC and assign the `SAP_ALL` profile.

For more information, see [Acquire authentication credentials in SAP ECC](/latest/docs/acquire-authentication-credentials-in-sap-ecc).

#### 3. Use cases and permissions for SAP ECC

This section covers use cases and permissions required for the SAP ECC connector.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject DSR Automation using SQL queries | SDI only covers the Discovery Scan. | Create custom `Read Table RFC Name` to allow scanning. | These permissions let Securiti read the tables in SAP ECC for classification purposes. These permissions also build the Personal Data Index for DSR Automation. |

### Connecting SAP ECC with Securiti

#### Steps to connect the SAP ECC connector with Securiti

To configure the SAP ECC (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Acquire authentication credentials in SAP ECC](/latest/docs/acquire-authentication-credentials-in-sap-ecc).
3. [Connecting the SAP ECC with Securiti](/latest/docs/connecting-the-sap-ecc-with-securiti).
4. [Configure discovery scans in SAP ECC](/latest/docs/configure-discovery-scans-in-sap-ecc).

#### Additional resources

- [Fulfilling DSR requests for SAP ECC](/latest/docs/fulfilling-dsr-requests-for-sap-ecc-1).
- [Troubleshooting for SAP ECC](/latest/docs/troubleshooting-for-sap-ecc).
