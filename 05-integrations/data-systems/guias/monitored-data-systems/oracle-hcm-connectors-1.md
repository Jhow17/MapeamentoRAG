---
title: "Oracle HCM"
slug: "oracle-hcm-connectors-1"
status: "new"
updated: 2026-08-11T10:31:33Z
published: 2026-08-11T10:31:42Z
canonical: "helpcenter.securiti.ai/oracle-hcm-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Oracle HCM

Oracle Human Capital Management (HCM), is a cloud-based suite of applications designed to manage the entire employee lifecycle. It encompasses a range of functionalities, from recruitment and onboarding to talent management and workforce analytics. The Oracle HCM connector lets you integrate your Oracle HCM environment with Securiti to discover and govern sensitive people data stored across your human capital management workflows.

Oracle HCM falls under the category of Hybrid data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Oracle HCM (Self-hosted) | - Sensitive Data Intelligence - DSR Automation using Full Scan - Breach Analysis |

### Supported pod types for self-hosted connector

- Standard Securiti pod
- Elastic pods (EDSS)

### Supported authentication types

Oracle HCM (self-hosted) supports the following authentication types:

| Authentication Type | Authentication credentials |
| --- | --- |
| Basic | - Username - Password |

### Supported items for classification scans

The discovery scan supports scanning entities for the Oracle HCM.

### Prerequisites for configuring Oracle HCM in Securiti

You must complete these prerequisites before connecting your Oracle HCM connector with Securiti.

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Oracle HCM with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

You must have access to use minimum API Permissions for the module you want to use and add roles for successful Connector Authentication.

#### 3. Use cases and permissions for Oracle HCM

This section covers use cases and permissions required for Oracle HCM Self-hosted connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing - Breach Analysis | You must grant admin consent to all API permissions. | Minimum **API Permissions** (Use REST Service privileges) based on the module of your choice and **Activation Credentials** for successful Connector authentication. Access to add **Roles** to user accounts. | These permissions let Securiti to read the tables and schema metadata in Oracle for classification purposes and to build the Personal Data Index for DSR Automation. |

### Steps to connect your Oracle HCM with Securiti

To configure the Oracle HCM connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain permission and authentication credentials in Oracle HCM](/latest/docs/obtain-permission-and-authentication-credentials-in-oracle-hcm).
3. [Connect Oracle HCM connector with](/latest/docs/connect-oracle-hcm-connector-with-securiti) Securiti.
4. [Configure discovery scans in Oracle HCM](/latest/docs/configure-discovery-scans-in-oracle-hcm).
5. [Configure general permissions for Oracle HCM](/latest/docs/configuring-general-settings-for-oracle-hcm).

#### Additional resources

- [Fulfilling DSR requests for Oracle HCM](/latest/docs/fulfilling-dsr-requests-for-oracle-hcm)
