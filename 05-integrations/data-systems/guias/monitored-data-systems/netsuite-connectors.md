---
title: "NetSuite"
slug: "netsuite-connectors"
status: "update"
updated: 2026-09-21T08:03:25Z
published: 2026-09-21T08:03:59Z
canonical: "helpcenter.securiti.ai/netsuite-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# NetSuite

NetSuite is a cloud-based enterprise resource planning (ERP) platform that helps organizations manage financials, customer relationships, and business operations. By connecting NetSuite with Securiti, organizations can discover and classify sensitive data across NetSuite records through Data Scan, while DSR Automation enables efficient identification and management of personal data associated with data subjects, helping streamline privacy request fulfillment and strengthen compliance with data protection regulations.

NetSuite falls under the [Monitored, structured data systems](/latest/docs/managing-data-system-connectors) category.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| NetSuite (Self-hosted) | - DSR Automation - Sensitive Data Intelligence (Standard Data Scan) |
| NetSuite (Securiti-Cloud) | - DSR Automation - Sensitive Data Intelligence (Standard Data Scan) |

### Supported pod types

Securiti supports standard Securiti Pod for NetSuite (self-hosted) connector.

### Supported authentication methods

Securiti supports following authentication methods for NetSuite connector:

- OAuth
- Basic

#### Keyring support for NetSuite (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings) for more information.

- **HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **Basic**.

### Prerequisites for configuring NetSuite (self-hosted) connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your NetSuite with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Admin access in NetSuite

You must be Admin in the NetSuite application to generate and record credentials for connector activation.

#### 3. Grant token access to the role

Grant Token access to the role created in NetSuite application. For more information, see [Acquire the API access token in NetSuite](/latest/docs/acquire-the-api-access-token-in-netsuite).

#### 3. Use cases and permissions for NetSuite

This section covers use cases and permissions required for Netsuite self-hosted and cloud connectors.

> [!NOTE]
> Note
> 
> In case you are using **Customer Center** and **SuiteCommerce** user roles, see the updated role access in [NetSuite file permissions](/latest/docs/netsuite-file-permissions).

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Data Subject Request (DSR) Automation Indexing - Data Scan | N/A | Grant **Full** access permissions to the role created in NetSuite application: - `Log in using OAuth 2.0 Access Tokens` - `Rest Web Services` - `OAuth 2.0 Authorized Applications Management` - `Integration Application` | These permissions let Securiti read the files and file metadata in NetSuite to build the Personal Data Index for DSR Automation. |

### Connect NetSuite with Securiti

#### Steps to connect NetSuite (Self-hosted) connector with Securiti

To configure the NetSuite (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain credentials in NetSuite (Self-hosted) for OAuth 2.0 authentication](/latest/docs/obtain-credentials-in-netsuite-for-oauth-20-authentication).
3. [Acquire the API access token in NetSuite (Self-hosted)](/latest/docs/acquire-the-api-access-token-in-netsuite).

If you are using Customer Center and SuiteCommerce user roles, see [NetSuite (Self-hosted) file permissions](/latest/docs/netsuite-file-permissions).
4. [Connecting NetSuite (Self-hosted) with Securiti](/latest/docs/connecting-netsuite-self-hosted-with-securiti).
5. [Configuring General permissions for NetSuite (Self-hosted)](/latest/docs/configuring-general-permissions-for-netsuite-self-hosted).

#### Steps to connect NetSuite (Securiti-Cloud) connector with Securiti

To configure the NetSuite Securiti-Cloud connector, perform the procedures in the following topics:

1. [Obtain credentials in NetSuite (Securiti-Cloud) for OAuth 2.0 authentication](/latest/docs/obtain-credentials-in-netsuite-securiti-cloud-for-oauth-2-0-authentication).
2. [Acquire the API access token in NetSuite (Securiti-Cloud)](/latest/docs/acquire-the-api-access-token-in-netsuite-securiti-cloud)

If you are using Customer Center and SuiteCommerce user roles, see [NetSuite (Securiti-Cloud) file permissions](/latest/docs/netsuite-securiti-cloud-file-permissions).
3. [Connecting NetSuite (Securiti-Cloud) with Securiti](/latest/docs/connecting-netsuite-securiti-cloud-with-securiti).
4. [Configuring General permissions for NetSuite (Securiti-Cloud)](/latest/docs/clone-configuring-general-permissions-for-netsuite-self-hosted)

#### Additional resources

1. [Fulfilling DSR requests for NetSuite](/latest/docs/fulfilling-dsr-requests-for-netsuite).
2. [Troubleshooting for NetSuite](/latest/docs/troubleshooting-for-netsuite).
3. [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

> [!NOTE]
> Note
> 
> Row counting for the NetSuite data system is not supported either due to the data system's inability to provide this data or the performance impact Securiti would cause on the data system by counting rows.
