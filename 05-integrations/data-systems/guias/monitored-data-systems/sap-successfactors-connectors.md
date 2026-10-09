---
title: "SAP SuccessFactors"
slug: "sap-successfactors-connectors"
status: "new"
updated: 2026-07-28T08:57:04Z
published: 2026-07-28T21:00:00Z
canonical: "helpcenter.securiti.ai/sap-successfactors-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# SAP SuccessFactors

SAP SuccessFactors is a cloud-based Human Capital Management (HCM) suite that supports the full employee lifecycle. It is built on a unified data model and enables organizations to automate HR processes, standardize workforce management across global operations. It makes data-driven people decisions through embedded analytics and AI-powered insights.

The SAP SuccessFactors connector lets you integrate Securiti to discover and govern sensitive employee and workforce data stored across your human capital management modules.

SAP SuccessFactors (Self-hosted) and SAP SuccessFactors (Securiti Cloud), both fall under the category of monitored, structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| SAP SuccessFactors (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence (Discovery scan) - DSR Automation using SQL queries |
| SAP SuccessFactors (Securiti Cloud) | Securiti Cloud connector supports: - DSR Automation using SQL queries |

### Supported pod types for self-hosted connector

- Standard Securiti Pods.

### Supported authentication methods

- For Self-hosted connector:
  - SAP SuccessFactors application-based authentication
    - OAuth-based authentication using certificate.
- For Securiti Cloud connector:
  - SAP SuccessFactors application-based authentication
    - Basic authentication

### Supported items for classification scans

Securiti supports following items for classification. For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Databases
- Schema
- Views

### Prerequisites for configuring SAP SuccessFactors connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your SAP SuccessFactors with a Self-hosted connector. For more information on configuring pods, see [Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

You must have admin access to user, API key, and private key file, and grant required permissions for generating APIs.

- For more information on connecting SAP SuccessFactors (Self-hosted) application to Securiti, see [Acquire authentication credentials in SAP SuccessFactors (Self-hosted)](/latest/docs/acquire-authentication-credentials-in-sap-successfactors-self-hosted).
- For more information on connecting SAP SuccessFactors (Securiti Cloud) application to Securiti, see [Acquire authentication credentials in SAP SuccessFactors (Securiti Cloud)](/latest/docs/acquire-authentication-credentials-in-sap-successfactors-securiti-cloud).

#### 3. Use cases and permissions for SAP SuccessFactors

This table covers use cases and permissions required for SAP SuccessFactors Self-hosted and Securiti Cloud connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Sensitive Data Intelligence (SDI) | SDI Discovery Scans and DSR Automation Indexing are only available on the self-hosted connector. | - Access in SAP SuccessFactors required to obtain: - **Datacenter URL** - **Username** - **API Key** - **Company ID** - **Certificate (.pem) file** - SAP SuccessFactors **API Application permissions.** | These permissions let Securiti read the files and file metadata in SAP SuccessFactors for PII scanning. |
| Data Subject Request (DSR) | N/A | This permission lets Securiti read all of the data within your SAP SuccessFactors instance for DSR searches. |

### Connect SAP SuccessFactors connectors with Securiti

#### Steps to connect SAP SuccessFactors (Self-hosted) connector with Securiti

To configure the SAP SuccessFactors (Self-Hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Acquire authentication credentials in SAP SuccessFactors (Self-hosted)](/latest/docs/acquire-authentication-credentials-in-sap-successfactors-self-hosted).
3. [Connect SAP SuccessFactors (Self-Hosted) connector with Securiti](/latest/docs/activate-the-sap-successfactors-self-hosted-connector-in-securiti).
4. [Configure discovery scans in SAP SuccessFactors (Self-hosted)](/latest/docs/configure-discovery-scans-in-sap-successfactors-self-hosted).

#### Additional resources

- [Fulfilling DSR requests for SAP SuccessFactors (Self-Hosted)](/latest/docs/fulfilling-dsr-requests-for-sap-successfactors-self-hosted).
- [Troubleshooting for SAP SuccessFactors](/latest/docs/troubleshooting-for-sap-successfactors).

#### Steps to connect SAP SuccessFactors (Securiti Cloud) connector with Securiti

To configure the SAP SuccessFactors connector, perform the procedures in the following topics:

1. [Acquire authentication credentials in SAP SuccessFactors (Securiti Cloud)](/latest/docs/acquire-authentication-credentials-in-sap-successfactors-securiti-cloud).
2. [Connect SAP SuccessFactors (Securiti Cloud) connector with Securiti](/latest/docs/activate-the-sap-successfactors-securiti-cloud-connector-in-securiti).

#### Additional resources

- [Fulfilling DSR requests for SAP SuccessFactors (Securiti Cloud)](/latest/docs/fulfilling-dsr-requests-for-sap-successfactors-securiti-cloud).

Self-hosted systems refer to computer systems or software applications that are hosted and operated by organizations or individuals who use them, rather than being hosted and operated by service providers or third parties. It becomes the responsibility of the organization to host, maintain, and manage the system or software.

Securiti’s sensitive data scanning feature which lets you target specific locations by looking for specific data elements, on specific schedules and by specific owners. These settings are configured when creating a discovery scan for a data system. Discovery scan is used when a data system containing sensitive information is shared by multiple teams. Each user can create a scan job for the portion of the data system they manage. See Understanding discovery scans for more information.
