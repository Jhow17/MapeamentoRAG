---
title: "Google Cloud SQL for SQL Server"
slug: "google-cloud-sql-for-sql-server-connectors-1"
status: "new"
updated: 2026-04-28T04:22:44Z
published: 2026-04-28T04:22:44Z
canonical: "helpcenter.securiti.ai/google-cloud-sql-for-sql-server-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Google Cloud SQL for SQL Server

Google Cloud SQL for SQL Server is a fully-managed database service that lets you run Microsoft SQL Server databases in the cloud without the overhead of manual administration. It provides automatic backups, patch management, and high availability, enabling businesses to focus on scaling and optimizing their workloads.

The Google Cloud SQL for SQL Server connector falls under the Monitored, Structured data systems category. See [Data systems classification](/v1/docs/managing-data-system-connectors), for more information.

The table below shows a comparison for the three Google Cloud SQL databases supported in Securiti.

|  | Authentication |
| --- | --- |
| **Database** | **Basic** | **SQL Cloud Proxy** | **IAM Authentication Strategy** | **User Credentials Authentication Strategy** |
| Google Cloud SQL for MySQL | Supported | Supported | Supported | Supported |
| Google Cloud SQL for PostgreSQL | Supported | Supported | Supported | Supported |
| Google Cloud SQL for SQL Server | Supported | Supported | Not supported | Supported |

### Supported Pod types

Securiti supports a self hosted pod connector for connecting to Google Cloud for SQL Server data system. See [Configuring Securiti pods](/v1/docs/securiti-pods-and-elastic-pods), for more information.

### Supported authentication methods

Google Cloud for SQL Server supports the following authentication types for authenticating and integrating with Securiti.

| Authentication Type | Authentication Method | Authentication Credentials |
| --- | --- | --- |
| SQL Server Authentication | Basic | - Host - Port - User (if keyring is not used) - Password (if keyring is not used) |
| SQL Cloud Proxy | - User (if keyring is not used) - Password (if keyring is not used) - Credentials File (if keyring is not used) - Connection Identifier |
| Windows Authentication | Basic | - Host - Port - User (if keyring is not used) - Password (if keyring is not used) - Domain |
| SQL Cloud Proxy | - User (if keyring is not used) - Password (if keyring is not used) - Credentials File (if keyring is not used) - Connection Identifier - Domain |
| Azure AD Authentication | Basic | - Host - Port - User (if keyring is not used) - Password (if keyring is not used) |
| SQL Cloud Proxy | - User (if keyring is not used) - Password (if keyring is not used) - Credentials File (if keyring is not used) - Connection Identifier |

#### Keyring support for Google Cloud SQL for SQL Server

You can use a keyring during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/v1/docs/managingcredentials-using-keyrings) for more information.

- **GCP Secrets Manager**. See [Configuring GCP Secrets Manager credential vaults](/v1/docs/configuring-credential-vaults-gcp-secret-manager-credential-vault) for more information.
- **Basic keyring**. See [Managing Keyrings](/v1/docs/managingcredentials-using-keyrings) for more information.

### Prerequisites for configuring Google Cloud SQL for SQL Server connector

You must fulfil the below prerequisites to connect your Google Cloud SQL for SQL Server connector with Securiti

- Ensure that SQL Cloud instances are enabled
- *(Skip for SQL Cloud Proxy authentication)* Record user credentials for Basic authentication
- *(Skip for Basic authentication)* Prerequisites for SQL Cloud Proxy authentication
  - Enable cloud proxy on GCP Infrastructure
  - Create IAM User
  - Create and associate Service Account
    - Assign roles or permissions to the service account
  - Grant DB permissions to IAM user
  - Download service account file

See [Prerequisites for Google Cloud SQL for SQL Server](/v1/docs/prerequisites-for-google-cloud-sql-for-sql-server), for more information.

### Use case and permissions for Google Cloud SQL for SQL Server

This section covers use cases and permissions required for Google Cloud SQL for SQL Server.

Securiti supports the following module features or scans for Google Cloud SQL for SQL Server.

- Sensitive Data Intelligence (Discovery scan)
- Data Subject Rights

You must provide the necessary permissions for these module features and scans that are supported for the following data entities.

- Databases
- Schemas within databases
- Tables and Views within schemas

> [!NOTE]
> **Note**
> 
> No additional permissions are required for accessing data when using **Basic** authentication.

For **SQL Cloud Proxy** authentication, provide the following roles or permissions.

| Modules | Permissions | Use case |
| --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | **Cloud SQL Client** | Lets Securiti connect and access your Cloud SQL instances. This role is primarily used for connecting and listing SQL instances. |
| **Cloud SQL Instance User** | This role is essential for authenticating the service account with IAM and managing interactions within the database instances. When scanning or managing data within a specific database in a Google Cloud SQL instance, the Cloud SQL Instance User role ensures the service account can authenticate itself via IAM, without requiring traditional SQL Server credentials. |

### Steps to connect Google Cloud SQL for SQL Server with Securiti

**New UI**

To configure the Google Cloud SQL for SQL Server self-hosted connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).
3. [Prerequisites for Google Cloud SQL for SQL Server](/latest/docs/prerequisites-for-google-cloud-sql-for-sql-server).
4. [(New UI) Connecting Google Cloud SQL for SQL Server with Securiti](/latest/docs/new-ui-connecting-google-cloud-sql-for-sql-server-with-securiti).
5. [Configure discovery scans in Google Cloud SQL for SQL Server](/latest/docs/configure-discovery-scans-in-google-cloud-sql-for-sql-server).

See [Fulfilling DSR requests for Google Cloud SQL for SQL Server](/latest/docs/fulfilling-dsr-requests-for-google-cloud-sql-for-sql-server) for more information about how Securiti uses the data to respond to DSR requests.

**Classic UI**

To configure the Google Cloud SQL for SQL Server self-hosted connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).
3. [Prerequisites for Google Cloud SQL for SQL Server](/latest/docs/prerequisites-for-google-cloud-sql-for-sql-server).
4. [Activate the Google Cloud SQL for SQL Server connector in Securiti](/latest/docs/activate-the-google-cloud-sql-for-sql-server-connector-in-securiti).
5. [Configure discovery scans in Google Cloud SQL for SQL Server](/latest/docs/configure-discovery-scans-in-google-cloud-sql-for-sql-server).

See [Fulfilling DSR requests for Google Cloud SQL for SQL Server](/latest/docs/fulfilling-dsr-requests-for-google-cloud-sql-for-sql-server) for more information about how Securiti uses the data to respond to DSR requests.
