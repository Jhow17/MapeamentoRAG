---
title: "HashiCorp credential vault"
slug: "configuring-credential-vaults-hashicorp-credential-vault"
status: "update"
updated: 2026-06-08T08:31:00Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/configuring-credential-vaults-hashicorp-credential-vault"
stale: true
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# HashiCorp credential vault

Securiti supports credential vaults that you use to manage privileged account access securely and SSH keys for Data systems that you integrate with Securiti.

HashiCorp Vault secures, stores, and tightly controls access to tokens, passwords, certificates, API keys, and other sensitive data, in the form of "secrets". When a data system connector is set up for HashiCorp-based authentication, Securiti requests credentials from HashiCorp through a mutual authentication mechanism. HashiCorp then provides Securiti with the "secrets" such as the username and password of a data system, and Securiti uses these credentials to authenticate to that data system.

> [!NOTE]
> **Note**
> 
> - The **Credential Vaults** feature is available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your Securiti tenant.
> - You can only activate HashiCorp vault instances through Securiti pods. When you activate a HashiCorp vault instance, Securiti automatically ensures that the necessary HashiCorp packages are activated on every active pod cluster within your Securiti instance.
> - Securiti supports self-hosted HashiCorp Vault, and it is officially tested with version 1.15. The cloud-based HashiCorp Cloud Platform (HCP) Vault is not currently supported. While minor version updates beyond 1.15 should work as expected, we recommend using the certified version.
> - Securiti does not support keyrings for Securiti Cloud-hosted data system connectors.

Some data systems store credentials using an OAuth plugin with HashiCorp, where Securiti dynamically queries the specified credential path in the HashiCorp Vault and uses these credentials to request an OAuth token.

## Roles and permissions

Securiti implements role-based access control on actions that can be performed for credential vaults and keyrings, such as keyring creation. For more information on roles and their permissions, see [Data Systems RBAC permissions](/v1/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-default-roles).

### Supported data systems for HashiCorp

The following table lists the self-hosted data systems that support HashiCorp Vault, including those that require an OAuth plugin with vault.

| Data System | OAuth Plugin Support |
| --- | --- |
| Alfresco | ❌ |
| Alibaba Cloud OSS | ❌ |
| Amazon DocumentDB | ❌ |
| Amazon MSK | ❌ |
| Amazon RDS for MySQL | ❌ |
| Amazon RDS for PostgreSQL | ❌ |
| Amazon Redshift | ❌ |
| Amazon S3 | ❌ |
| Apache Hive | ❌ |
| Azure Blob Storage | ❌ |
| Azure Cosmos DB for MongoDB | ❌ |
| Azure Data Lake Storage Gen2 | ❌ |
| Azure Files | ❌ |
| Cassandra | ❌ |
| Confluence Data Center | ❌ |
| Confluent Kafka | ❌ |
| Couchbase NoSQL | ❌ |
| Coupa | ✅ |
| Databricks | ❌ |
| Dropbox | ✅ |
| G Suite Google Drive | ❌ |
| Google BigQuery | ❌ |
| Google Cloud Storage | ❌ |
| HDFS | ❌ |
| HP NonStopSQL | ❌ |
| IBM Db2 | ❌ |
| IBM Db2 zOS | ❌ |
| IBM Informix | ❌ |
| Jira Software | ✅ |
| Jira Software Data Center | ✅ |
| Kafka | ✅ |
| Microsoft Azure SQL Database | ❌ |
| Microsoft 365 OneDrive | ✅ |
| Microsoft 365 Outlook (Attachments) | ✅ |
| Microsoft 365 Outlook (Message Body) | ✅ |
| Microsoft 365 SharePoint Online | ✅ |
| Microsoft Dynamics 365 CRM (Suite) | ✅ |
| Microsoft Dataverse | ✅ |
| Microsoft Teams | ✅ |
| MongoDB | ❌ |
| MySQL | ❌ |
| NetSuite | ❌ |
| OpenText Content Server | ❌ |
| Oracle | ❌ |
| Oracle Eloqua | ❌ |
| Oracle Object Storage | ❌ |
| PostgreSQL | ❌ |
| Power BI Service | ✅ |
| S3 Compatible Storage | ❌ |
| Salesforce (Legacy) | ✅ |
| Salesforce CRM | ✅ |
| SFTP | ❌ |
| Slack | ✅ |
| SMB | ❌ |
| Snowflake | ❌ |
| SQL Server | ❌ |
| Sybase ASE | ❌ |
| Teradata | ❌ |
| Wasabi | ❌ |
| Workday | ❌ |
| Zendesk Support | ✅ |

### Using HashiCorp vault for your data system

To use the HashiCorp vault for your data system credentials, follow the procedures as listed below:

1. [Installing and setting up the OAuth 2.0 secrets engine plugin with HashiCorp](/latest/docs/installing-and-setting-up-oauth2-secrets-engine)

> [!NOTE]
> Note
> 
> This procedure is required only for data systems requiring OAuth plugin with HashiCorp. Skip this step if your data system does not support OAuth plugin.
2. [Setting up HashiCorp vault and acquiring authentication credentials](/latest/docs/hashicorp-credential-vault-authentication-methods-in-hashicorp-vault)
3. [Storing data system credentials in HashiCorp vault](/latest/docs/storing-data-system-credentials-in-hashicorp-vault)
  1. [Configuring the OAuth token for data system](/latest/docs/storing-data-system-credentials-in-hashicorp-vault)
4. [Creating credential read policies for credential paths](/latest/docs/creating-credential-read-policies-1)
5. [Configuring HashiCorp vault instance in Securiti](/latest/docs/hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti)
6. [Creating keyrings for HashiCorp](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp)

For dynamic credentials, see the below topics:
  - For Amazon S3 data system, see [Using AWS Secrets Engine for dynamic credentials](/latest/docs/using-aws-secrets-engine-for-dynamic-credentials)
  - For SQL data systems, see [Using Database Secrets Engine for dynamic credentials](/latest/docs/using-database-secrets-engine-for-dynamic-credentials)

Data systems refer to the system where your data is stored. That can be in the form of files (text, audio, video), databases (tables and schemas), and streaming data (data in motion). Securiti supported most of the structured, unstructured, and streaming data systems.

## Related

- [Setting up HashiCorp vault and acquiring authentication credentials](/hashicorp-credential-vault-authentication-methods-in-hashicorp-vault.md)
- [Configuring HashiCorp vault instance in Securiti](/hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti.md)
