---
title: "Google BigQuery"
slug: "google-bigquery-connectors"
status: "update"
updated: 2026-08-31T21:00:01Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/google-bigquery-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Google BigQuery

BigQuery is Google Cloud's fully managed and completely serverless enterprise data warehouse. BigQuery supports all data types, works across clouds, and has built-in machine learning and business intelligence, all within a unified platform

Google BigQuery falls under the category of [Monitored, Structured data systems.](/latest/docs/managing-data-system-connectors)

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Google BigQuery (Self-hosted) | - Sensitive Data Intelligence - Policies - Discovery Scan - DSR Automation - Data Access Control |
| Google BigQuery (Securiti-Cloud) | DSR Automation |

### Supported Pod types

Following types of Pods are supported only for self-hosted connector:

- Securiti standard pod. For more information, see [Configuring Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).
- Securiti epod is also supported for the Google BigQuery self-hosted connector.

### Supported authentication methods

Google BigQuery supports **Credential file** authentication types for authenticating and integrating with Securiti.

#### Keyring support for self-hosted connector

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **GCP Secret Manager**: For more information, see [GCP Secret Manager credential vault](/latest/docs/configuring-credential-vaults-gcp-secret-manager-credential-vault).

### Supported items for classification scans

Securiti supports the following data entities for the Google BigQuery connector:

- Tables

> [!NOTE]
> Note
> 
> Securiti extracts the last modified time and table owner for each table and view from BigQuery's `INFORMATION_SCHEMA.TABLES` view. Securiti ingests these values as properties of the **Table** entity in the Data Command Graph, as shown below.
> 
> | Property | Description |
> | --- | --- |
> | Table Owner | The user or service account that owns the table. |
> | Last Modified Time | The most recent update timestamp for the table or view. |
> 
> ![Graph Explorer interface displaying tables and their properties in Google BigQuery.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/bigquery_tables.png)
- Schemas
- Rows and columns

**Additional resources**

- For more information, see [Configure discovery scans in Google BigQuery](/latest/docs/configure-discovery-scans-in-google-bigquery).
- For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites for configuring the Google BigQuery connector

#### 1. Pod deployment

> [!NOTE]
> **Important**
> 
> Pod deployment is required for self-hosted connectors only.

You must deploy a Securiti pod in your environment to connect your Google BigQuery with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/latest/docs/elastic-pods-deployment).

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

You must be an administrator to grant permissions to the service account or for custom role creation:

#### 3. Use cases and permissions for Google BigQuery

This section covers use cases and permissions required for Google BigQuery self-hosted and Securiti cloud connectors.

If you are using a custom role, you must assign the additional privileges to the custom role as mentioned below. For more information on custom roles, see [Create a custom role and assign permissions](/latest/docs/create-a-custom-role-and-assign-permissions).

| Permission | Description |
| --- | --- |
| `bigquery.tables.getData` | Lets the actual retrieval of row-level data. |
| `bigquery.tables.get` | Lets the user see the table schema/metadata (required for the query engine to parse the SQL). |
| `bigquery.datasets.get` | Lets access to the dataset metadata. |
| `bigquery.tables.list` | Lets you see the list of tables in the BigQuery sidebar. |
| `bigquery.jobs.get` | Lets you view the status and statistics of your specific jobs. |
| `bigquery.readsessions.getData` | Lets you stream data directly from BigQuery storage using the BigQuery Storage Read API. |
| `bigquery.readsessions.create` | Lets you create a read session, which is required before you can stream data using the BigQuery Storage Read API. |
| `bigquery.jobs.create` | Lets a principal (user, service account, or group) to start a job. |

#### Use case and permissions for service account

Use the table below for use case and permissions to be assigned to the service account:

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (Discovery scan) - Data Subject Rights | Sensitive Data Intelligence (discovery scan) is only supported for the self-hosted connector. | Add the following roles: - `BigQuery Data Viewer` - `BigQuery Job User` - `BigQuery Read Session User` | These permissions let Securiti read the files and metadata in Google BigQuery for classification purposes. These permissions also build the Personal Data Index for DSR Automation. |
| Data Access Control | It is only supported for the self-hosted connector. | These permissions let Securiti leverage these Google BigQuery permissions as part of restricting access of your users and groups to Google BigQuery data sources, such as tables, columns, and schemas. |

### Steps to connect Google BigQuery to Securiti

#### Steps to connect the Google BigQuery (self-hosted) connector with Securiti

To configure the Google BigQuery connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Acquire authentication credentials in Google BigQuery](/latest/docs/acquire-authentication-credentials-in-google-bigquery) or [Create a custom role in Google BigQuery](/latest/docs/create-a-custom-role-and-assign-permissions)
3. [Connecting Google BigQuery (self-hosted) with Securiti](/latest/docs/new-ui-connecting-google-bigquery-self-hosted-with-securiti)
4. [Configuring Access permissions for Google BigQuery (self-hosted)](/latest/docs/configuring-access-permissions-for-google-bigquery-self-hosted)
5. [Configure discovery scans in Google BigQuery](/latest/docs/configure-discovery-scans-in-google-bigquery)

#### Steps to connect the Google BigQuery (Securiti-Cloud) connector with Securiti

To configure the Google BigQuery connector, perform the following procedures in sequence:

1. [Acquire authentication credentials in Google BigQuery](/latest/docs/acquire-authentication-credentials-in-google-bigquery) or [Create a custom role in Google BigQuery](/latest/docs/create-a-custom-role-and-assign-permissions)
2. [Connecting Google BigQuery (Securiti-Cloud) with Securiti](/latest/docs/new-ui-connecting-google-bigquery-securiti-cloud-with-securiti)
3. [Configuring General permissions for Google BigQuery (Securiti-Cloud)](/latest/docs/new-ui-configuring-general-permissions-for-google-bigquery-securiti-cloud)

**Additional Resources**

- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
- [Fulfilling DSR requests for Google BigQuery](/latest/docs/fulfilling-dsr-requests-for-google-bigquery).
