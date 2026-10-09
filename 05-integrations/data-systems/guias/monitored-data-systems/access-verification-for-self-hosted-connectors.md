---
title: "Access verification for self-hosted connectors"
slug: "access-verification-for-self-hosted-connectors"
updated: 2026-08-03T05:01:27Z
published: 2026-08-03T05:01:27Z
canonical: "helpcenter.securiti.ai/access-verification-for-self-hosted-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Access verification for self-hosted connectors

Securiti runs access verification service every 24 hours for each Connector to assess the validity. Additionally, the feature verifies whether or not the consent still applies, that the keys are valid, and that no change in Permissions has occurred.

Access verification runs with the following conditions:

- It runs every 24 hours for connectors that have either:
  - Never been verified before, or
  - Had a successful verification in the last run.
- It doesn't retry for 7 days if a Connector fails verification.

### Access verification failures notification

Securiti lets you monitor errors that might surface at the time of DSR scanning or discovery scans. In the case of a failed health check, Securiti notifies you by generating data source audit trails and emails.

- An audit trail entry is generated each time access verification runs and fails for that connector. You can view access verification messages in the **Audit Trail/Activity Log** tab of your data system connector.
- Email notifications are sent every 15 days, starting from the first notification, and are grouped by the following ways:

| Group | Explanation |
| --- | --- |
| Tenant ID and Appliance ID | Failure email notifications are grouped by this combination to consolidate related issues into a single report. |
| Customer Services (CS) Team | Receives these grouped failure reports bi-weekly to monitor access issues effectively. |

> [!NOTE]
> **Note**
> 
> Data system owners receive a one-time email notification for each Connector they own, but only if it fails verification, no follow-up emails are sent for the same failure.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PCNC01O4.png)

### Supported connectors for access verification

- **SAAS**:
  - Asana Premium
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
  - Gladly
  - G Suite Google Drive
  - G Suite Gmail (Message Body)
  - G Suite Gmail (Attachments)
  - Jira Software Data Center
  - Jira Software
  - Microsoft Dynamics 365 CRM (Suite)
  - Microsoft Dynamics 365 Finance & Operations
  - Microsoft 365 Lists
  - Microsoft Teams
  - NetSuite
  - Office 365 OneDrive
  - Office 365 Outlook (Attachments)
  - Office 365 Outlook (Message Body)
  - Office 365 SharePoint Online
  - OpenText Content Server
  - Oracle HCM
  - Power BI
  - SAP SuccessFactors
  - ServiceNow Tables
  - Salesforce
  - Salesforce CDP
  - Salesforce CRM
  - Slack Enterprise
  - Slack Pro
  - Shopify
  - Securiti for Box
  - QuickBase
  - Tableau Server
  - Treasure Data CDP
  - Workday
  - Zendesk
  - Zendesk Support
  - Zoho Recruit
- **SQL**:
  - Amazon Aurora Postgres
  - Amazon DocumentDB
  - Amazon DynamoDB
  - Amazon Redshift
  - AWS RDS MariaDB
  - AWS RDS MySQL
  - AWS RDS Postgres
  - Azure Cosmos DB
  - Azure Cosmos MongoDB
  - Cassandra
  - CockroachDB
  - Databricks Self-hosted
  - Elasticsearch
  - GCP MySQL
  - GCP Postgres
  - GCP SQL Server
  - Google BigQuery
  - Microsoft Azure SQL Database
  - MongoDB
  - MySQL
  - Oracle
  - PostgreSQL
  - Snowflake
  - SQL Server
  - Starburst
  - Trino
- **IaaS**
  - Alibaba OSS
  - Azure Blob
  - Google Cloud Storage
  - HDFS
  - LDAP
  - NFS
  - Oracle Object Storage
  - S3
  - SFTP
  - SMB
