---
title: "Databricks"
slug: "databricks-connectors"
status: "update"
updated: 2026-09-28T08:27:49Z
published: 2026-09-28T08:27:49Z
canonical: "helpcenter.securiti.ai/databricks-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Databricks

Databricks is a cloud-based data engineering tool used for processing and transforming massive quantities of data and exploring the data through machine learning models. You can run Databricks on any Cloud platform including Azure, AWS or GCP. It uses the data lake of the respective Cloud platform for storage while the Databricks Delta Lake layer, sitting atop the data lake, processes the data as it arrives.

Databricks connector falls under the [Monitored, Structured data systems](/latest/docs/managing-data-system-connectors) and scans that data using the SQL data warehouse.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Databricks (Self-hosted) | It supports: - Sensitive Data Intelligence - DSR Automation - Security Posture Management - Data Access Governance - Data Breach Management |

### Supported pods type

- Standard Securiti Pods.
- Elastic Pods (EDSS).

### Supported authentication methods

| Authentication type | Supported credentials |
| --- | --- |
| Personal Access Token | - Access Token |
| OAuth 2.0 | - Client ID - Client Secret |

#### Keyring support

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/using-keyrings).

- **HashiCorp**. For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

HashiCorp is OAuth supported with Databricks Online.
- **CyberArk:** For more information, see [Configuring CyberArk vault](/latest/docs/cyberark-credential-vault).
- **Azure Key Vault:** For more information, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault).

### Supported items for Classification Scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Database
- Schemas
- Tables

### Prerequisites

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Databricks with a Self-hosted connector. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/latest/docs/elastic-pods-1).

For more information on configuring pods, see [Securiti variables: Platform name pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

Before proceeding with the connector configuration process, allowlist the following Databricks URLs in the firewall setting of your machine. For more information, see [cloud partners from Databricks](https://www.databricks.com/company/partners/cloud-partners).

| URL | Documentation |
| --- | --- |
| Azure *<*.azuredatabricks.net>* | [https://learn.microsoft.com/en-us/azure/databricks/security/network/firewall-rules](https://learn.microsoft.com/en-us/azure/databricks/security/network/firewall-rules) |
| GCP *<*.gcp.databricks.com>* | [https://docs.gcp.databricks.com/security/network/firewall-rules.html](/v1/docs/using-firewall-rules-1) |
| AWS *<*.cloud.databricks.com>* | [https://docs.databricks.com/en/security/network/firewall-rules.html](/v1/docs/using-firewall-rules-1) |

#### 2. Admin access in Databricks Workspace

You must have an administrator or create a user role access in Databricks database

- For more information on connecting Databricks to Securiti, see [Grant permissions and obtain credentials in Databricks](/latest/docs/grant-permissions-and-obtain-credentials-in-databricks).

#### 3. Upload JDBC drivers

For successful authentication, you must download JDBC drivers from [Databricks website](https://www.databricks.com/spark/jdbc-drivers-download) and upload them to Securiti

For more information, see [Uploading JDBC driver files in Securiti](/latest/docs/uploading-jdbc-driver-files-in-securiti).

#### 4. Configure cloud object storage permissions

Databricks data system also requires you to configure access to following cloud object storages for Databricks because that's where it stores the metadata.

- Amazon S3
- Google Cloud Storage
- Azure Data Lake Storage
- Azure Blob Storage

For more information, see [Databricks documentation](https://docs.databricks.com/aws/en/connect/storage/) to configure access to cloud object storages.

#### 5. Permissions and use cases

You must assign these permissions to the Databricks user to meet different use cases. See the table below.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector. | **User permission** - **Can use** permission to user in Databricks database - **Data reader** to user in catalogue. **Entitlements** - Workspace access - Databricks SQL access | These permissions let Securiti read the Schemas and tables in Databricks classification purposes. These permissions also build the Personal Data Index for DSR Automation. |
| Security Posture Management Rule Evaluation | N/A | **User permission** - **Can use** permission to user in Databricks database - **Data reader** to user in catalogue. **Entitlements** - Workspace access - Databricks SQL access | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |
| Data Access Intelligence | Data Access Intelligence requires admin access to execute Data Access governance feature. | Admin access to Databricks account. | These permissions let Securiti leverages these permissions as part of determining which users and user groups have access to data in Databricks and what level of permissions they have on that data. |

### Steps to connect Databricks with Securiti

To configure the Databricks self-hosted connector:

1. Deploy and configure pod using [Securiti Pods and Elastic Pods](/latest/docs/securiti-pods-and-elastic-pods).
2. Use one of the following topics depending on the type of authentication method you choose:
  - For Personal Access Token, use [Grant permissions and obtain credentials in Databricks](/latest/docs/grant-permissions-and-obtain-credentials-in-databricks)
  - For OAuth 2.0, use [Create Service Principal and obtaining OAuth 2.0 credentials](/latest/docs/create-service-principal-and-obtain-credential).
3. [Connecting Databricks with Securiti](/latest/docs/new-ui-connecting-databricks-with-securiti).
4. [Configuring General and Access permissions](/latest/docs/new-ui-configuring-general-and-access-permissions-1).
5. [Configuring discovery scans in Databricks](/latest/docs/configuring-discovery-scans-in-databricks).

**Additional resources**

- [Troubleshooting for Databricks](/latest/docs/troubleshooting-for-databricks)
- [Fulfilling DSR requests for Databricks](/latest/docs/fulfilling-dsr-requests-for-databricks)

Permissions refer to the minimum set of access details required to connect a data system with Securiti and allow scanning of data. Permissions could be of an administrative role where the user has all privileges to scan, share and access data, or it can be READ/WRITE only. Without the required permissions, data cannot be discovered or scanned for sensitive information.

An advanced process of enabling data intelligence on a data system before fulfilling a DSR request.
