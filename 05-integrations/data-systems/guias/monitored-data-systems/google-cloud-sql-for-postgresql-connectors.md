---
title: "Google Cloud SQL for PostgreSQL"
slug: "google-cloud-sql-for-postgresql-connectors"
status: "update"
updated: 2026-04-28T04:14:59Z
published: 2026-04-28T04:15:02Z
canonical: "helpcenter.securiti.ai/google-cloud-sql-for-postgresql-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Google Cloud SQL for PostgreSQL

Google Cloud SQL for PostgreSQL is a fully-managed relational database service that simplifies the setup and management of PostgreSQL instances in the cloud. It offers automatic backups, high availability, and easy scalability, making it ideal for businesses needing a reliable and scalable PostgreSQL solution.

The Google Cloud SQL for PostgreSQL connector falls under the Monitored, Structured data systems category. See [Data systems classification](/v1/docs/managing-data-system-connectors), for more information.

The table below shows a comparison for the three Google Cloud SQL databases supported in Securiti.

|  | Authentication |
| --- | --- |
| **Database** | **Basic** | **SQL Cloud Proxy** | **IAM Authentication Strategy** | **User Credentials Authentication Strategy** |
| Google Cloud SQL for MySQL | Supported | Supported | Supported | Supported |
| Google Cloud SQL for PostgreSQL | Supported | Supported | Supported | Supported |
| Google Cloud SQL for SQL Server | Supported | Supported | Not supported | Supported |

### Supported Pod types

Securiti supports a self hosted pod connector for connecting to Google Cloud for PostgreSQL data system. See [Configuring Securiti pods](/v1/docs/securiti-pods-and-elastic-pods), for more information.

### Supported authentication methods

Google Cloud for PostgreSQL supports the following authentication types for authenticating and integrating with Securiti.

| Authentication Type | Authentication Credentials |
| --- | --- |
| Basic | - Host - Port - User (if keyring is not used) - Password (if keyring is not used) |
| SQL Cloud Proxy | **Authentication Strategy: User Credentials** - User (if keyring is not used) - Password (if keyring is not used) - Credentials File (if keyring is not used) - Connection Identifier **Authentication Strategy: User Credentials** - IAM User - Credentials File (if keyring is not used) - Connection Identifier |

#### Keyring support for Google Cloud SQL for PostgreSQL

You can use a keyring during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/v1/docs/managingcredentials-using-keyrings) for more information.

- **GCP Secrets Manager**. See [Configuring GCP Secrets Manager credential vaults](/v1/docs/configuring-credential-vaults-gcp-secret-manager-credential-vault) for more information.
- **Basic keyring**. See [Managing Keyrings](/v1/docs/managingcredentials-using-keyrings) for more information.

> [!NOTE]
> **Note**
> 
> Basic keyring is not supported for **IAM Authentication** strategy when using the **SQL Cloud Proxy** authentication method.

### Prerequisites for configuring Google Cloud SQL for PostgreSQL connector

You must fulfil the below prerequisites to connect your Google Cloud SQL for PostgreSQL connector with Securiti

- Ensure that SQL Cloud instances are enabled
- *(Skip for SQL Cloud Proxy authentication)* Record user credentials for Basic authentication
- *(Skip for Basic authentication)* Prerequisites for SQL Cloud Proxy authentication
  - Enable cloud proxy on GCP Infrastructure
  - Create IAM User
  - Create and associate Service Account
    - Assign roles or permissions to the service account
  - Enable IAM for your SQL cloud instance
  - Grant DB permissions to IAM user
  - Download service account file

See [Prerequisites for Google Cloud SQL for PostgreSQL](/v1/docs/prerequisites-for-google-cloud-sql-for-postgresql), for more information.

### Use case and permissions for Google Cloud SQL for PostgreSQL

This section covers use cases and permissions required for Google Cloud SQL for PostgreSQL.

Securiti supports the following module features or scans for Google Cloud SQL for PostgreSQL.

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
| **Cloud SQL Instance User** | This role is essential for authenticating the service account with IAM and managing interactions within the database instances. When scanning or managing data within a specific database in a Google Cloud SQL instance, the Cloud SQL Instance User role ensures the service account can authenticate itself via IAM, without requiring traditional PostgreSQL credentials |

### Steps to connect Google Cloud SQL for PostgreSQL with Securiti

**New UI**

To configure the Google Cloud SQL for PostgreSQL self-hosted connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).
3. [Prerequisites for Google Cloud SQL for PostgreSQL](/latest/docs/prerequisites-for-google-cloud-sql-for-postgresql).
4. [(New UI) Connecting Google Cloud SQL for PostgreSQL with Securiti](/latest/docs/new-ui-connecting-google-cloud-sql-for-postgresql-with-securiti).
5. [Configure discovery scans in Google Cloud SQL for PostgreSQL](/latest/docs/configure-discovery-scans-in-google-cloud-sql-for-postgresql).

**Classic UI**

To configure the Google Cloud SQL for PostgreSQL self-hosted connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).
3. [Prerequisites for Google Cloud SQL for PostgreSQL](/latest/docs/prerequisites-for-google-cloud-sql-for-postgresql).
4. [Activate the Google Cloud SQL for PostgreSQL connector in Securiti](/latest/docs/activate-the-google-cloud-sql-for-postgresql-connector-in-securiti).
5. [Configure discovery scans in Google Cloud SQL for PostgreSQL](/latest/docs/configure-discovery-scans-in-google-cloud-sql-for-postgresql).

## Additional resources

- [Troubleshooting for Google Cloud SQL for PostgreSQL connectors](/latest/docs/troubleshooting-for-google-cloud-sql-for-postgresql-connectors)
- [Fulfilling DSR requests for Google Cloud SQL for PostgreSQL](/latest/docs/fulfilling-dsr-requests-for-google-cloud-sql-for-postgresql)
