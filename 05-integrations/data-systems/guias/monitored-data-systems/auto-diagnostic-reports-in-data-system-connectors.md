---
title: "Auto-diagnostic reports in data system connectors"
slug: "auto-diagnostic-reports-in-data-system-connectors"
updated: 2026-06-18T08:09:41Z
published: 2026-06-18T08:09:41Z
canonical: "helpcenter.securiti.ai/auto-diagnostic-reports-in-data-system-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Auto-diagnostic reports in data system connectors

Securiti performs automatic diagnosis of connector-dependent operations for IaaS, SaaS, and SQL self-hosted connectors with its auto-diagnostics report. You can access a detailed report for all steps after connector activation or reconfiguration.

The auto-diagnostic report helps you identify problematic areas in the connector configuration, including invalid credentials, expired tokens, connectivity issues, or any specific error messages returned by the data source. This feature also validates all the permissions for a connector.

Observe these caveats:

- The auto-diagnostic report only runs after the connector activation or reconfiguration process.
- For connectors previously activated prior to the introduction of the diagnostic utility, the routine executes on the next reconfiguration.
- The number of steps and checks varies for each connector.

> [!NOTE]
> **Note**
> 
> - This utility operates independently of a Connector's Authentication result i.e. it is completely normal for a Connector to have successful Activation but still result in a failed diagnosis. This is because the diagnostic utility thoroughly covers and validates almost all areas that a Connector interacts with, not just Authentication.
> - The SQL Server connector runs a comprehensive diagnostic report covering connectivity, authentication, database access, permissions, and scan readiness across all supported authentication methods, such as SQL, Kerberos, Windows, and Azure AD.
> 
> When a step fails, Securiti displays a specific reason to help you resolve the issue. For a full list of failure scenarios and resolutions, see [Troubleshooting for Microsoft SQL Server connector](/latest/docs/troubleshooting-for-microsoft-sql-server-connector).

## Supported data systems

Securiti provides the diagnostic utility for these Self-hosted connectors:

**IaaS**:

- Alibaba Cloud OSS
- Amazon S3
- Azure Files
- Azure Blob Storage
- Google Cloud Storage
- HDFS
- LDAP Active Directory
- NFS
- Oracle Object Storage
- SFTP
- SMB
- Kafka

**SaaS**:

- Asana Enterprise
- Azure Data Lake Gen2
- Box
- Braze
- Citrix Sharefile
- Confluence Cloud
- Confluence Data Center
- Domo
- DocuSign
- Dropbox
- GitHub
- GitLab
- G Suite Gmail (Attachments)
- G Suite Gmail (Message Body)
- G Suite Google Drive
- Gladly
- Jira Software
- Microsoft Dynamics 365 CRM (Suite)
- Microsoft Dynamics 365 Finance & Operations
- Microsoft 365 Lists
- Microsoft 365 Teams
- NetSuite
- Microsoft 365 OneDrive
- Microsoft 365 Outlook (Attachments)
- Microsoft 365 Outlook (Message Body)
- Microsoft 365 SharePoint Online
- OpenText Content Server
- Oracle HCM
- Power BI Service
- Quickbase
- Salesforce
- Salesforce CDP
- Salesforce CRM
- SAP SuccessFactors
- Securiti for Box
- ServiceNow Tables
- Slack Enterprise Grid
- Shopify
- Tableau Server
- Treasure Data CDP
- Workday
- Zendesk
- Zoho Recruit

**SQL**:

- Amazon Athena
- Amazon Aurora Postgres
- Amazon DocumentDB
- Amazon DynamoDb
- Amazon RDS MySQL
- Amazon RDS PostgreSQL
- Apache Trino
- Cassandra
- Couchbase NoSQL
- CockroachDB
- Databricks
- Elasticsearch
- Firebird
- Google Cloud SQL for MySQL
- IBM Db2
- Microsoft Azure SQL Database
- MongoDB
- MySQL
- Oracle
- PostgreSQL
- SAP HANA
- Snowflake
- Starburst
- SQL Server

## Procedure

To view the report:

1. On the Securiti dashboard view, near the bottom of the page, click **Settings**.
2. In the left sidebar, select **Integrations > Data Systems > Monitored**.
3. On the **Authentication** screen of your data system, you can see **Feature Permission Statuses**. To view the details of each permission, hover over the icon next to it.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Report HS(1).png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Report Detail(1).png)

## Related

- [Configuring connectors for monitored data systems](/configuring-connectors-for-monitored-data-systems.md)
