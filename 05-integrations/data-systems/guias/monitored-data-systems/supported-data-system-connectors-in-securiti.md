---
title: "Supported data system connectors in Securiti"
slug: "supported-data-system-connectors-in-securiti"
updated: 2026-08-27T13:13:47Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/supported-data-system-connectors-in-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Supported data system connectors in Securiti

> [!NOTE]
> **Note**
> 
> Securiti connectors employ credential encryption, which means credentials are not only encrypted in a database but remain encrypted over the connector’s lifecycle. Even after credentials are retrieved from the database and decrypted for use, they're stored in the memory, encrypted.

The tables below list all data system connectors supported in Securiti. Use the key definitions to understand the concepts covered in the table.

## Key Definitions

### App type

- **Self-hosted:** The connector is hosted or deployed on your premises instead of being hosted on Securiti cloud.
- **Securiti Cloud:** The connector is hosted on Securiti's environment.

### Connection method

- **API:** Securiti queries the connector for data via APIs.
- **Pods**: Securiti uses pods or appliances to host the data system and query data from there.
- **ePod:** Securiti uses elastic Pods or appliances to host the data system and queries data from there. ePods provide more scalability.

### Scan type

- **Structured**: Connector scans structured data in the form of rows and columns. Securiti performs table training on the data.
- **Unstructured:** Data system contains unstructured data like text, images, or videos. DSR Automation, using full scan and discovery scan, is performed to identify sensitive data. For more information on files that are skipped during scans, see [Viewing skip reasons for documents](/v1/docs/viewing-errors-and-skipped-files-in-discovery-scans).
- **Hybrid:** Data system connector contains a combination of structured and unstructured data. Connector treats most objects as structured data and scans unstructured content within these apps.
- **Scanless:** Securiti does not perform data scanning on these connectors. The scanless connectors are queried with DSR using APIs.
- **Streaming:** Identifies sensitive data upstream in the data pipeline for a data system and optionally protects it via masking.

### Module features support

The column highlights the Securiti module scans supported for each connector.

- **Breach Analysis**: Initiates an enhanced analysis for any reported incident for your data system and generates an automated report for remediation in the **Data Breach Management** module.
- **Data Access Control**: Enables policy creation for your connector in the **Data Access Governance** module.
- **Discovery Scan**: Scans your data system connector for sensitive data discovery. Discovery scan results can be seen in the **Sensitive Data Intelligence** module.
- **DSR Automation using APIs (Smart search):** Scans your data system connector using search APIs, without building or storing an index of primary data elements.
- **DSR Automation using Full Scan**: Scans your self-hosted data system connector and builds an index of primary data elements.
- **DSR Automation using SQL queries**: Performs DSR scan on structured data system connectors using query -based search.
- **Security Posture Scan**: Checks your data system instance for any policy violations and performs automated remediation of misconfigurations in the **Security Posture Management** module.
- **Workflow**: Includes the connector node in workflow in the **Workflows** module.

### Miscellaneous

- **Under Study:** A particular piece of information requires confirmation before it is updated in the table.

### Storage and File Services

| Application name | App type | Scan type | Connection method | Authentication types | Credential vault types | Module features support |
| --- | --- | --- | --- | --- | --- | --- |
| [Alfresco](/v1/docs/alfresco-connectors) | Self-hosted | Unstructured | Pod | OAuth | - AWS Secrets Manager - CredStash - HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [Alibaba Cloud OSS](/v1/docs/alibaba-cloud-oss-connectors-1) | Self-hosted | Unstructured | Pod | OAuth | - AWS Secrets Manager - CredStash - HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [Amazon S3](/v1/docs/amazon-s3-connectors-1) | Self-hosted | Unstructured | Pod/ePod | - Auto-generate Dynamic Credentials - IAM Keys - IAM Roles - S3 Inventory | - AWS Secrets Manager - CredStash - HashiCorp - CyberArk | - DSR Automation using Full Scan - Access Intelligence Scan (Privilege Analysis) - Workflow - Discovery Scan - Data Inventory Sync - Breach Analysis |
| [Azure Blob Storage](/v1/docs/azure-blob-storage-connectors) | Self-hosted | Unstructured | Pod/ePod | - Storage Account - Service Principal - Service Principal with Certificate | - AWS Secrets Manager - CredStash - HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Data Inventory Sync - Breach Analysis |
| [Azure Data Lake Storage Gen2](/v1/docs/azure-data-lake-storage-adls-gen2-connectors) | Self-hosted | Unstructured | Pod/ePod | - Account Key - Azure Service Principal | - Azure Key Vault - HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Data Inventory Sync - Breach Analysis |
| [Azure Data Lake Storage Gen2](/v1/docs/azure-data-lake-storage-adls-gen2-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | Workflow |
| [Azure Files](/v1/docs/azure-files-connectors) | Self-hosted | Unstructured | Pod/ePod | - Storage Account - Active Directory | - CredStash - HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [Box](/v1/docs/box-connectors) | Securiti Cloud | Unstructured | API | OAuth | Not supported | - DSR Automation using smart search APIs - Workflow - Security Posture Scan - Breach Analysis |
| [Box](/v1/docs/box-connectors) | Self-hosted | Unstructured | Pod/ePod | OAuth | Not supported | - DSR Automation using Full Scan - Workflow - Discovery Scan - Breach Analysis - Access Intelligence Scan (Privilege Analysis) |
| [Citrix ShareFile](/v1/docs/citrix-sharefile-connectors) | Self-hosted | Unstructured | Pod | OAuth | Not supported | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [Clicksign](/v1/docs/clicksign-connectors) | Self-hosted | Unstructured | Pod | API Key | Not supported | - DSR Automation using Full Scan - Breach Analysis |
| DigitalOcean Spaces | Self-hosted | Unstructured | Pod | Access Key | Not supported | - Under Study |
| [Dropbox](/v1/docs/dropbox-connectors) | Securiti Cloud | Unstructured | API | OAuth | Not supported | - Security Posture Scan - Breach Analysis |
| [Dropbox](/v1/docs/dropbox-connectors) | Self-hosted | Unstructured | Pod | OAuth | Hashicorp | - DSR Automation using Full Scan - Workflow - Discovery Scan - Breach Analysis - Data Inventory Sync - Gencore AI Entitlements scan |
| [Files.com](/v1/docs/filescom-connectors) | Securiti Cloud | Unstructured | API | API Key | Not supported | - Breach Analysis - Security Posture Scan - Standard Data Scan |
| [Google Drive (Google Workspace)](/latest/docs/g-suite-google-drive-connectors) | Securiti Cloud | Unstructured | API | OAuth | Not supported | - DSR Automation using smart search APIs - Security Posture Scan - Breach Analysis - Data Labelling Policy - Workflow |
| [Google Drive (Google Workspace)](/latest/docs/g-suite-google-drive-connectors) | Self-hosted | Unstructured | Pod/ePod | OAuth | - HashiCorp - AWS Secret Manager - Azure Key Vault - CyberArk | - Breach Analysis - Discovery Scan - DSR Automation using Full Scan - Security Posture Scan - Data Labelling Policy - Workflow - Data Inventory Sync - Gencore AI Entitlements scan |
| [Go File Room](/v1/docs/go-file-room-connectors) | Self-hosted | Unstructured | Pod/ePod | OAuth | Not supported | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [Google Cloud Storage for Firebase](/v1/docs/google-cloud-storage-for-firebase-and-google-cloud-firestore-connectors-1) | Securiti Cloud | Unstructured | API | OAuth | Not supported | - Breach Analysis - Standard Data Scan |
| [Google Cloud Storage](/v1/docs/google-cloud-storage-connector-1) | Self-hosted | Unstructured | Pod/ePod | - Credentials File - IAM Service Account | - AWS Secrets Manager - CredStash - GCP Secret Manager - HashiCorp - Azure Key Vault - CyberArk | - DSR Automation using Full Scan - Discovery Scan - Data Inventory Sync - Breach Analysis |
| [Microsoft 365 Onedrive](/v1/docs/microsoft-365-onedrive-connectors) | Securiti Cloud | Unstructured | API | OAuth | Not supported | - DSR Automation using smart search APIs - Workflow - Breach Analysis - Security Posture Scan |
| [Microsoft 365 Onedrive](/v1/docs/microsoft-365-onedrive-connectors) | Self-hosted | Unstructured | Pod/ePod | OAuth | - HashiCorp - CyberArk | - Breach Analysis - Discovery Scan - DSR Automation using Full Scan - Data Inventory Sync - Security Posture Scan - Access Intelligence Scan (Privilege Analysis - Gencore AI Entitlements scan |
| [Microsoft 365 SharePoint Online](/v1/docs/microsoft-365-sharepoint-online-connectors) | Securiti Cloud | Unstructured | API | OAuth | Not supported | - DSR Automation using smart search APIs - Standard Data Scan - Security Posture Scan - Breach Analysis - Access Intelligence Scan |
| [Microsoft 365 SharePoint Online](/v1/docs/microsoft-365-sharepoint-online-connectors) | Self-hosted | Unstructured | Pod/ePod | OAuth | - Azure Key vault - CyberArk - HashiCorp | - Discovery Scan - DSR Automation using Full Scan - Security Posture Scan - Access Intelligence Scan - Data Access Control - Data Inventory Sync - Gencore AI Entitlements scan - Breach Analysis |
| [NFS](/v1/docs/nfs-connectors) | Self-hosted | Unstructured | Pod/ePod | Path required. No authentication | Not supported | - DSR Automation using Full Scan - Discovery Scan - Data Inventory Sync - Breach Analysis |
| [OpenText Content Server](/v1/docs/opentext-content-server-connectors) | Self-hosted | Unstructured | Pod | OAuth | HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [Oracle Object Storage](/v1/docs/oracle-object-storage-connectors) | Self-hosted | Unstructured | Pod/ePod | Basic | - CredStash - HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [SFTP](/v1/docs/sftp-connectors) | Self-hosted | Unstructured | Pod | - Key-Based - Password-Based | - AWS Secrets Manager - Basic Keyring - CredStash - HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [SMB](/v1/docs/smb-connectors) | Self-hosted | Unstructured | Pod/ePod | - NTLM (User/Password) - Kerberos - Keytab - Kerberos - Password | - AWS Secrets Manager - Basic Keyring - CredStash - CyberArk - Delinea Secret Server - HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Data Inventory Sync - Access Intelligence Scan (Privilege Analysis) - Breach Analysis |
| [Veeva Vault](/v1/docs/veeva-vault-connectors) | Self-hosted | Unstructured | Pod | OAuth | Not supported | - DSR Automation using Full Scan - Breach Analysis |
| [Wasabi](/v1/docs/wasabi-connectors) | Self-hosted | Scanless | Pod | OAuth | - AWS Secrets Manager - CredStash - HashiCorp | - Not supported |

### API Integrations

| Application name | App type | Scan type | Connection method | Authentication types | Credential vault types | Module features support |
| --- | --- | --- | --- | --- | --- | --- |
| [Alation](/v1/docs/alation-connectors) | Self-hosted (Works as a workflow node) | Scanless | Pod/ePod | Basic Access Token | Not supported | - DSR Automation using APIs - Workflow |
| [Auth0](/v1/docs/auth0-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [Auth0](/v1/docs/auth0-connectors) | Self-hosted | Structured | API | OAuth | Not supported | Discovery Scan |
| [BrainTree Payments](/v1/docs/braintree-payments-connectors) | Securiti Cloud | Scanless | API | Basic | Not supported | DSR Automation using APIs |
| [LDAP Active Directory](/v1/docs/ldap-active-directory-connectors-1) | Self-hosted | Structured | Pod | Basic | Basic Keyring | DSR Automation using SQL queries |
| [Microsoft Compliance Center](/v1/docs/microsoft-compliance-center-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [Microsoft Purview Information Protection](/v1/docs/microsoft-purview-information-protection-connectors-1) | Securiti Cloud | Scanless | API | OAuth | Not supported | Not Supported |
| [Okta](/v1/docs/okta-connectors) | Securiti Cloud | Scanless | API | API Key | Not supported | - DSR Automation using APIs - Workflow |
| [Twilio](/v1/docs/twilio-connectors) | Securiti Cloud | Scanless | API | Basic | Not supported | - DSR Automation using APIs - Workflow |

### Relational Database

| Application name | App type | Scan type | Connection method | Authentication types | Credential vault types | Module features support |
| --- | --- | --- | --- | --- | --- | --- |
| [Airtable](/v1/docs/airtable-connectors-1) | Securiti Cloud | Structured | API | Personal Access Token | Not supported | - DSR Automation using SQL queries - Workflow |
| [Amazon Aurora for PostgreSQL](/v1/docs/amazon-aurora-for-postgresql-connectors) | Self-hosted | Structured | Pod | - Basic - IAM Roles | AWS Secret Manager | DSR Automation using SQL queries |
| [Amazon RDS for MySQL](/v1/docs/amazon-rds-for-mysql-connectors) | Self-hosted | Structured | Pod/ePod | - Basic - IAM Roles | - AWS Secret Manager - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan - Workflow |
| [Amazon RDS for M](/v1/docs/amazon-rds-for-ms-sql-server-connector) | Self-hosted | Structured | Pod | Basic | - AWS Secret Manager - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan |
| [Amazon RDS for PostgreSQL](/v1/docs/amazon-rds-for-postgresql-connectors) | Self-hosted | Structured | Pod | - Basic - IAM Roles | - AWS Secret Manager - Basic Keyring - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan - Workflow |
| [Apache Hive](/v1/docs/apache-hive-connectors) | Self-hosted | Structured | Pod | - Password - Keytab | HashiCorp | - DSR Automation using SQL queries - Discovery Scan - Data Access Control |
| [Btrieve](/v1/docs/btrieve-connectors) | Self-hosted | Structured | API | Basic | Not supported | - DSR Automation using APIs and SQL queries - Data Scan |
| [CockroachDB](/v1/docs/cockroach-connectors-en) | Self-hosted | Structured | Pod/ePod | Basic | HashiCorp | - DSR Automation using SQL queries - Discovery Scan |
| [Cloudera Impala](/v1/docs/cloudera-impala-connectors-1) | Self-hosted | Structured | Pod/ePod | Basic | Not supported | - DSR Automation using SQL queries - Discovery Scan |
| [Databricks](/v1/docs/databricks-connectors) | Self-hosted | Structured | Pod/ePod | - Personal Access Token - OAuth 2.0 | - CyberArk - Hashicorp - Azure Key Vault | - DSR Automation using SQL queries - Discovery Scan - Access Intelligence Scan (Privilege Analysis) - Data Access Control - Security Posture Scan - Breach Analysis |
| [Firebird](/v1/docs/firebird-connectors) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Discovery Scan |
| [Greenplum](/v1/docs/greenplum-connectors) | Self-hosted | Structured | API | Basic | Not supported | - DSR Automation using APIs and SQL queries - Discovery Scan |
| [Google Cloud SQL for MySQL](/v1/docs/google-cloud-sql-for-mysql-connectors) | Self-hosted | Structured | Pod/ePod | - Basic - IAM Roles | - GCP Secret Manager - Basic Keyring | - DSR Automation using SQL queries - Discovery Scan - Workflow |
| [Google Cloud SQL for PostgreSQL](/v1/docs/google-cloud-sql-for-postgresql-connectors) | Self-hosted | Structured | Pod | - Basic - IAM Roles | - GCP Secret Manager - Basic Keyring | - DSR Automation using SQL queries - Discovery Scan - Workflow |
| [Google Cloud SQL for SQL Server](/v1/docs/google-cloud-sql-for-sql-server-connectors-1) | Self-hosted | Structured | Pod/ePod | - SQL Server Authentication - Windows Authentication - Azure AD Authentication | - GCP Secret Manager - Basic Keyring | - DSR Automation using SQL queries - Discovery Scan - Workflow |
| HP NonStop SQL | Self-hosted | Structured | Pod | Basic | - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan - Workflow |
| [IBM Db2](/v1/docs/ibm-db2-and-zos-connectors) | Self-hosted | Structured | API | Basic | - Azure Key Vault - CredStash - CyberArk - HashiCorp | - DSR Automation using smart search APIs - Discovery Scan |
| [IBM Db2 zOS](/v1/docs/ibm-db2-and-zos-connectors) | Self-hosted | Structured | API | Basic | - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan |
| [IBM Informix](/v1/docs/ibm-informix-connectors) | Self-hosted | Structured | Pod | Basic | HashiCorp | - DSR Automation using SQL queries - Data Scan |
| [IBM Netezza](/v1/docs/ibm-netezza-connectors) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Discovery Scan |
| [InterSystems Cache](/v1/docs/intersystems-iris-or-cache-connectors) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Discovery Scan |
| [InterSystems IRIS](/v1/docs/intersystems-iris-or-cache-connectors) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Data Scan |
| [MariaDB](/v1/docs/mariadb-connectors-1) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Discovery Scan |
| [Microsoft Access](/v1/docs/microsoft-access-connectors) | Self-hosted | Structured | Pod | Path required. No authentication | Not supported | - DSR Automation using SQL queries - Data Scan |
| [Microsoft Azure SQL Database](/v1/docs/microsoft-azure-sql-database-connectors) | Self-hosted | Structured | Pod | - Service Principal - Service Principal with Certificate - Basic authentication - Azure AD authentication | - Azure Key Vault - HashiCorp | - DSR Automation using SQL queries - Discovery Scan - Breach Analysis |
| [Microsoft Dynamics 365 Finance & Operations](/v1/docs/microsoft-dynamics-365-finance-and-operations-connectors-en) | Self-hosted | Structured | Pod/ePod | OAth based | Not supported | - Discovery Scan |
| [Microsoft Dataverse](/v1/docs/microsoft-dataverse-connectors-1) | Self-hosted | Structured | Pod/ePod | OAth based | HashiCorp | - DSR Automation using SQL queries - Discovery Scan |
| [Microsoft SQL Server](/v1/docs/microsoft-sql-server-connectors) | Self-hosted | Structured | Pod/ePod | - SQL Server Authentication - Windows Authentication - Azure AD Authentication - Kerberos Authentication | - AWS Secrets Manager - Azure Key Vault - CredStash - CyberArk - Delinea Secret Server - HashiCorp | - DSR Automation using SQL queries - Discovery Scan - Security Posture Management - Workflow - Breach Analysis |
| [MySQL](/v1/docs/mysql-connectors) | Self-hosted | Structured | Pod/ePod | Basic | - AWS Secrets Manager - Azure Key Vault - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan - Workflow - Breach Analysis |
| [MySQL Cloud](/v1/docs/mysql-connectors) | Securiti Cloud | Structured | API | Basic | Not supported | - DSR Automation using APIs - Workflow |
| [Oracle](/v1/docs/oracle-connectors) | Self-hosted | Structured | Pod/ePod | Basic | - AWS Secrets Manager - Azure Key Vault - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan - Security Posture Management - Workflow - Breach Analysis |
| Oracle Autonomous Transactional | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Discovery Scan |
| [PostgreSQL](/v1/docs/postgresql-connectors-1) | Self-hosted | Structured | Pod | Basic | - AWS Secrets Manager - Azure Key Vault - Basic Keyring - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan - Workflow - Breach Analysis |
| [PostgreSQL Cloud](/v1/docs/postgresql-connectors-1) | Securiti Cloud | Structured | API | Basic | Not supported | DSR Automation using SQL queries |
| [Progress OpenEdge DB](/v1/docs/progress-openedge-db-connectors) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Data Scan |
| [SAP HANA](/v1/docs/sap-hana-connectors) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Discovery Scan |
| [Sybase ASE](/v1/docs/sybase-ase-connectors) | Self-hosted | Structured | Pod | Basic | HashiCorp | - DSR Automation using SQL queries - Data Scan |
| [Teradata](/v1/docs/teradata-connectors-1) | Self-hosted | Structured | Pod | - Basic - LDAP | - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan |

### Big Data & NoSQL

| Application name | App type | Scan type | Connection method | Authentication types | Credential vault types | Module features support |
| --- | --- | --- | --- | --- | --- | --- |
| [Amazon Athena](/v1/docs/amazon-athena-connectors) | Self-hosted | Structured | Pod/ePod | - Basic - IAM Roles | AWS Secrets Manager | - DSR Automation using SQL queries - Discovery Scan |
| [Amazon Aurora for PostgreSQL](/v1/docs/amazon-aurora-for-postgresql-connectors) | Self-hosted | Structured | Pod | - Basic - IAM Roles | AWS Secrets Manager | - DSR Automation using SQL queries - Discovery Scan |
| [Amazon DocumentDB](/v1/docs/amazon-documentdb-connectors) | Self-hosted | Structured | Pod | Basic | - AWS Secrets Manager - Azure Key Vault - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan |
| [Amazon DynamoDb](/v1/docs/amazon-dynamodb-connectors-1) | Self-hosted | Structured | Pod/ePod | - Basic - IAM Roles | AWS Secrets Manager | - DSR Automation using SQL queries - Discovery Scan - Access Intelligence Scan (Privilege Analysis) |
| [Amazon DynamoDb Cloud](/v1/docs/amazon-dynamodb-connectors-1) | Securiti Cloud | Structured | API | Access Key | Not supported | DSR Automation using APIs |
| [Amazon Redshift](/v1/docs/amazon-redshift-connectors-1) | Self-hosted | Structured | Pod | - Basic - IAM Roles | - AWS Secrets Manager - CyberArk - CyberArk Conjur - HashiCorp | - DSR Automation using SQL queries - Discovery Scan |
| [Amazon RDS MariaDB](/v1/docs/aws-rds-mariadb-connectors) | Self-hosted | Structured | Pod | - Basic - IAM Roles | - AWS Secrets Manager - Basic Keyring | - DSR Automation using SQL queries - Discovery Scan |
| [Apache HBase](/v1/docs/apache-hbase-connectors) | Self-hosted | Structured | Pod | - Basic - Kerberos Authentication | Not supported | - DSR Automation using SQL queries - Discovery Scan |
| [Apache Phoenix](/v1/docs/apache-phoenix-connectors) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Data Scan |
| [Apache Presto](/v1/docs/apache-presto-connectors) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Data Access Control - Discovery Scan |
| [Apache Trino](/v1/docs/apache-trino-connectors) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Data Access Control - Discovery Scan |
| [Azure Cosmos DB](/v1/docs/azure-cosmos-db-connectors-1) | Self-hosted | Structured | Pod/ePod | - Account key - Azure Service Principal | Not supported | - DSR Automation using SQL queries - Discovery Scan |
| [Azure Cosmos DB for MongoDB](/v1/docs/azure-cosmos-db-for-mongodb-connectors-1) | Self-hosted | Structured | Pod | Basic | - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan |
| [Azure Synapse](/v1/docs/azure-synapse-connectors) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Discovery Scan - Breach Analysis |
| [Cassandra](/v1/docs/cassandra-connectors) | Self-hosted | Structured | Pod | Basic | - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan |
| [Google Cloud Firestore](/v1/docs/google-cloud-storage-for-firebase-and-google-cloud-firestore-connectors-1) | Securiti Cloud | Unstructured | API | Service account key file | Not supported | - Breach Analysis - Standard Data Scan |
| [Couchbase NoSQL](/v1/docs/couchbase-nosql-connectors) | Self-hosted | Structured | Pod | Basic | HashiCorp | - DSR Automation using SQL queries - Data Scan |
| [Elasticsearch](/v1/docs/elasticsearch-connectors) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Discovery Scan |
| [Google BigQuery](/v1/docs/google-bigquery-connectors) | Self-hosted | Structured | Pod/ePod | Credentials file | - GCP Secret Manager - HashiCorp | - DSR Automation using SQL queries - Discovery Scan - Data Access Control |
| [Google BigQuery](/v1/docs/google-bigquery-connectors) | Securiti Cloud | Structured | API | Credentials file | Not supported | - DSR Automation using APIs |
| [Google Bigtable](/v1/docs/google-bigtable-connectors-1) | Self-hosted | Structured | Pod | Credentials file | Not supported | - DSR Automation using SQL queries and APIs - Sensitive Data Intelligence |
| Google Spanner | Securiti Cloud | Structured | API | Credentials file | Not supported | DSR Automation using SQL queries and APIs |
| [HDFS](/v1/docs/hdfs-connectors-1) | Self-hosted | Unstructured | Pod | - Keytab - Password | - AWS Secrets Manager - CredStash - HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Data Access Control (Permissions Management Policies) - Breach Analysis - Data Inventory Sync |
| HDFS Google Dataproc | Self-hosted | Unstructured | Pod | Basic | Not supported | - Data Access Control - Breach Analysis |
| [MongoDB](/v1/docs/mongodb-connectors) | Self-hosted | Structured | Pod | Basic | - Azure Key Vault - CredStash - CyberArk - HashiCorp | - DSR Automation using SQL queries - Discovery Scan |
| [Snowflake](/v1/docs/snowflake-connectors) | Self-hosted | Structured | Pod/ePod | - Basic (deprecated) - OAuth 2.0 - Key Pair Authentication | - CredStash - CyberArk - CyberArk Conjur - HashiCorp - Azure Key Vault | - DSR Automation using SQL queries - Discovery Scan - Security Posture Scan (For OAuth and Key Pair authentication only) - Data Access Control - Access Intelligence Scan (Privilege Analysis) |
| [Snowflake](/v1/docs/snowflake-connectors) | Securiti Cloud | Structured | API | - Basic - OAuth 2.0 - Key Pair Authentication | Not supported | - DSR Automation using APIs - Access Intelligence Scan (Privilege Analysis) - Standard data scan |
| [Starburst](/v1/docs/starburst-connectors) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Discovery Scan - Access Intelligence Sca |
| [Oracle Autonomous Data Warehouse](/v1/docs/oracle-autonomous-data-warehouse-connectors-1) | Self-hosted | Structured | Pod | Basic | Not supported | - DSR Automation using SQL queries - Discovery Scan |

### Marketing and Analytics

| Application name | App type | Scan type | Connection method | Authentication types | Credential vault types | Module features support |
| --- | --- | --- | --- | --- | --- | --- |
| [ActiveCampaign](/v1/docs/activecampaign-connectors) | Securiti Cloud | Scanless | API | API Key | Not supported | - DSR Automation using APIs - Workflow |
| [Ad Butler](/v1/docs/adbutler-connectors) | Securiti Cloud | Scanless | API | API Key | Not supported | DSR Automation using APIs |
| [Amplitude](/v1/docs/amplitude-connectors-1) | Securiti Cloud | Scanless | API | Basic | Not supported | DSR Automation using APIs |
| Branch.io | Securiti Cloud | Scanless | API | API Key | Not supported | - DSR Automation using APIs - Breach Analysis |
| [Facebook Workplace](/v1/docs/facebook-workplace-connectors) | Securiti Cloud | Unstructured | API | API Key | Not supported | - Breach Analysis - Standard Data Scan |
| [HackerRank](/v1/docs/hackerrank-connectors) | Securiti Cloud | Scanless | API | API Key | Not supported | DSR Automation using APIs |
| [HubSpot](/v1/docs/hubspot-connectors) | Securiti Cloud | Structured | API | OAuth | Not supported | - DSR Automation using APIs - Workflow |
| [Loggly](/v1/docs/loggly-connectors) | Securiti Cloud | Scanless | API | API Key | Not supported | DSR Automation using APIs |
| [MailChimp](/v1/docs/mailchimp-connectors) | Securiti Cloud | Structured | API | API Key | Not supported | - DSR Automation using SQL queries - Workflow |
| [Microsoft Fabric](/latest/docs/microsoft-fabric) | Self-hosted | Unstructured | Pod | OAuth | - Azure Key Vault - HashiCorp | - Discovery scan - DSR Automation using Full Scan - Data Inventory Sync |
| [New Relic](/v1/docs/new-relic-connectors) | Securiti Cloud | Scanless | API | API Key | Not supported | DSR Automation using APIs |
| [Power BI Service](/v1/docs/power-bi-service-connectors) | Self-hosted | Structured | Pod/ePod | OAuth | HashiCorp | - DSR Automation using APIs and SQL queries - Discovery Scan |
| [Salesforce Chatter](/v1/docs/salesforce-chatter-connectors-1) | Securiti Cloud | Unstructured | API | OAuth | Not supported | - Breach Analysis - Standard Data Scan |
| [Salesforce Marketing Cloud Account Engagement (Pardot)](/v1/docs/salesforce-marketing-cloud-account-engagement-pardot-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | Universal Consent Management (Privacy Platform Integations) |
| [Segment](/v1/docs/segment-connectors) | Securiti Cloud | Scanless | API | API Key | Not supported | DSR Automation using APIs |
| [SendGrid](/v1/docs/sendgrid-connectors) | Securiti Cloud | Scanless | API | API Key | Not supported | DSR Automation using APIs |
| [Flurry](/v1/docs/flurry-connectors) | Securiti Cloud | Scanless | API | API Key | Not supported | DSR Automation using APIs |
| [MoEngage](/v1/docs/moengage-connectors) | Securiti Cloud | Scanless | API | Basic | Not supported | DSR Automation using APIs |
| [Adobe Marketo Engage](/v1/docs/adobe-marketo-engage-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [Dot Digital](/v1/docs/dot-digital-connectors-1) | Securiti Cloud | Scanless | API | Basic | Not supported | DSR Automation using APIs |
| [Drift](/v1/docs/drift-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [Google Analytics](/v1/docs/google-analytics-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [SurveyMonkey](/v1/docs/surveymonkey-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | Breach Analysis |
| [MixPanel](/v1/docs/mixpanel-connectors) | Securiti Cloud | Scanless | API | API Key | Not supported | DSR Automation using APIs |
| [Oracle Eloqua Marketing Automation](/latest/docs/oracle-eloqua) | Self-hosted | Hybrid | Pod | - Basic - OAuth | - Hashicorp - CyberArk Conjur | - DSR Automation using SQL queries - Discovery scan |
| [Tableau Cloud](/v1/docs/tableau-cloud-connectors-1) | Securiti Cloud | Structured | API | OAuth | Not supported | Standard Data Scan |
| [Tableau Server](/v1/docs/tableau-server-connectors) | Self-hosted | Hybrid | Pod | OAuth | Not supported | - Discovery Scan - Breach Analysis |
| [Salesforce Marketing Cloud (SOAP](/v1/docs/salesforce-marketing-cloud-soap-rest-connectors)) | Securiti Cloud | Structured | API | Basic | Not supported | DSR Automation using SQL queries |
| [Salesforce Marketing Cloud (REST)](/v1/docs/salesforce-marketing-cloud-soap-rest-connectors) | Securiti Cloud | Structured | API | OAuth | Not supported | DSR Automation using SQL queries |
| [Blueconic](/v1/docs/blueconic-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [CleverReach](/v1/docs/cleverreach-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [Treasure Data CDP](/v1/docs/treasure-data-cdp-connectors) | Self-hosted | Structured | Pod | API Key | Not supported | - DSR Automation using SQL queries - Discovery scan |

### ERP and CRM

| Service | App Type | Scan Type | Connection method | Authentication types | Credential Vault Types | Module features support |
| --- | --- | --- | --- | --- | --- | --- |
| [Kintone](/v1/docs/kintone-connectors) | Securiti Cloud | Structured | API | Basic | Not supported | DSR Automation using SQL queries |
| [Microsoft Dynamics CRM](/v1/docs/microsoft-dynamics-365-crm-suite-connectors) | Securiti Cloud | Structured | API | OAuth | Not supported | - DSR Automation using SQL queries - Breach Analysis - Workflow |
| [Microsoft Dynamics CRM](/v1/docs/microsoft-dynamics-365-crm-suite-connectors) | Self-hosted | Structured | API | OAuth | HashiCorp | - DSR Automation using SQL queries - Discovery Scan - Breach Analysis - Workflow |
| [NetSuite](/v1/docs/netsuite-connectors) | Securiti Cloud | Structured | API | - OAuth - Basic | Not supported | - DSR Automation using SQL queries - Data Scan |
| [NetSuite](/v1/docs/netsuite-connectors) | Self-hosted | Structured | API | - OAuth - Basic | - HashiCorp - Basic keyring | - DSR Automation using SQL queries - Data Scan |
| [Odoo ERP](/v1/docs/odoo-erp-connectors) | Securiti Cloud | Structured | API | Basic | Not supported | DSR Automation using SQL queries |
| [Oracle ERP Cloud](/v1/docs/oracle-erp-connectors) | Securiti Cloud | Structured | API | Basic | Not supported | Standard Data Scan |
| [Oracle Sales Cloud](/v1/docs/oracle-sales-cloud-connectors-1) | Securiti Cloud | Scanless | API | Basic | Not supported | DSR Automation using APIs |
| [Quickbase](/v1/docs/quickbase-connectors) | Self-hosted | Unstructured | Pod/ePod | OAuth | Not supported | - DSR Automation using Full Scan - Discovery Scan |
| [Salesforce](/v1/docs/salesforce-connectors-1) | Securiti Cloud | Structured | API | OAuth | Not supported | - DSR Automation using APIs - Workflow - Security Posture Scan - Universal Consent Management (Privacy Platform Integations) |
| [Salesforce (Legacy)](/v1/docs/salesforce-connectors-1) | Self-hosted | Structured | Pod/ePod | OAuth | HashiCorp | - DSR Automation using APIs and SQL queries - Discovery Scan - Workflow |
| [Salesforce CRM](/v1/docs/salesforce-crm-connectors) | Self-hosted | Hybrid | Pod/ePod | OAuth | - HashiCorp - CyberArk | - DSR Automation using Full Scan - Discovery Scan |
| [Oracle HCM](/v1/docs/oracle-hcm-connectors-1) | Self-hosted | Hybrid | Pod/ePod | Basic | Not supported | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [SAP ECC](/v1/docs/sap-ecc-connectors-1) | Self-hosted | Structured | Pod | Basic | Not supported | DSR Automation using SQL queries |
| [ServiceNow](/v1/docs/servicenow-connectors) | Securiti Cloud | Structured | API | Basic | Not supported | - DSR Automation using SQL queries - Security Posture Scan |
| [ServiceNow (Legacy)](/v1/docs/servicenow-connectors) | Securiti Cloud | Structured | API | OAuth | Not supported | Standard Data Scan |
| [ServiceNow Files](/v1/docs/servicenow-files-connectors) | Self-hosted | Unstructured | Pod | OAuth | CredStash | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [ServiceNow Tables](/v1/docs/servicenow-tables-connectors-1) | Self-hosted | Structured | Pod/ePod | OAuth | CredStash | - DSR Automation using SQL queries - Discovery Scan |
| [Zoho CRM](/v1/docs/zoho-crm-connectors) | Securiti Cloud | Structured | API | OAuth | Not supported | - DSR Automation using SQL queries - Security Posture Scan |
| [Zuora](/v1/docs/zuora-connectors) | Securiti Cloud | Unstructured | API | OAuth | Not supported | - Breach Analysis - Security Posture Scan - Standard Data Scan |
| [Oracle Service Cloud](/v1/docs/oracle-service-cloud-connectors) | Self-hosted | Hybrid | Pod | Basic | Not supported | - DSR Automation using APIs and SQL queries - Breach Analysis |
| [Zendesk](/v1/docs/zendesk-self-hosted-connectors) | Self-hosted | Structured | Pod/ePod | OAuth | Not supported | - DSR Automation using APIs and SQL queries - Discovery Scan - Workflow |
| [Zendesk Support](/v1/docs/zendesk-support-connectors) | Securiti Cloud | Hybrid | API | OAuth | Not supported | - DSR Automation using SQL queries - Security Posture Scan - Workflow |
| [Zendesk Support](/v1/docs/zendesk-support-connectors) | Self-hosted | Hybrid | Pod | OAuth | HashiCorp | - DSR Automation using APIs and SQL queries - Discovery Scan - Breach Analysis - Workflow - Data Inventory Sync - Gencore AI Entitlements scan |
| [Salesforce Commerce Cloud](/v1/docs/salesforce-commerce-cloud-connectors-1) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [Capsule CRM](/v1/docs/capsule-crm-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [Zoho Recruit](/v1/docs/zoho-recruit-connectors) | Self-hosted | Hybrid | Pod | OAuth | Not supported | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis - Workflow |
| [Gladly](/v1/docs/gladly-connectors-1) | Self-hosted | Structured | Pod | Basic | Not supported | Discovery Scan |
| [Domo](/v1/docs/domo-connectors) | Self-hosted | Structured | Pod | OAuth | Not supported | - DSR Automation using APIs and SQL queries - Discovery Scan |
| [Braze](/v1/docs/braze-connectors) | Securiti Cloud | Scanless | API | API Key | Not supported | Workflow |
| [Braze](/v1/docs/braze-connectors) | Self-hosted | Structured | Pod | API Key | Not supported | - DSR Automation using APIs and SQL queries - Discovery Scan |
| [Salesforce Customer Data Platform](/v1/docs/salesforce-customer-data-platform-connectors) | Self-hosted | Structured | Pod | OAuth | Not supported | - DSR Automation using APIs and SQL queries - Discovery Scan |

### e-Commerce

| Application name | App type | Scan type | Connection method | Authentication types | Credential Vault Types | Module features support |
| --- | --- | --- | --- | --- | --- | --- |
| [Chargebee](/v1/docs/chargebee-connectors) | Securiti Cloud | Scanless | API | Basic | Not supported | - DSR Automation using APIs - Workflow |
| [Magento](/v1/docs/magento-connectors) | Securiti Cloud | Scanless | API | Basic | Not supported | DSR Automation using APIs |
| [Paypal](/v1/docs/paypal-connectors) | Securiti Cloud | Scanless | API | Basic | Not supported | DSR Automation using APIs |
| [Shopify](/v1/docs/shopify-connectors) | Self-hosted | Hybrid | Pod | API key | CyberArk | Discovery Scan |
| [Shopify](/v1/docs/shopify-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | - DSR Automation using APIs - Workflow |
| [Signifyd](/v1/docs/signifyd-connectors) | Securiti Cloud | Scanless | API | Basic | Not supported | DSR Automation using APIs |
| [Square](/v1/docs/configuring-the-square-connector) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [Stripe](/v1/docs/stripe-connectors-1) | Securiti Cloud | Scanless | API | API Key | Not supported | - DSR Automation using APIs - Workflow |
| [Coupa](/v1/docs/coupa-connectors-1) | Securiti Cloud | Hybrid | API | OAuth | Not supported | Standard Data Scan |
| [Coupa](/v1/docs/coupa-connectors-1) | Self-hosted | Hybrid | Pod/ePod | API Key | - HashiCorp - Basic Keyring | DSR Automation using APIs |
| [Workday](/v1/docs/workday-connectors-1) | Securiti Cloud | Hybrid | API | Basic | Not supported | - DSR Automation using APIs - Security Posture Scan |
| [Workday](/v1/docs/workday-connectors-1) | Self-hosted | Hybrid | Pod | - Basic - OAuth | HashiCorp | - DSR Automation using APIs - Discovery Scan - Breach Analysis - Security Posture Scan |
| [Outreach](/v1/docs/outreach-connectors-1) | Securiti Cloud | Structured | API | OAuth | Not supported | DSR Automation using APIs |

### Collaboration

| Application name | App type | Scan type | Connection method | Authentication types | Credential vault types | Module features support |
| --- | --- | --- | --- | --- | --- | --- |
| [Asana](/v1/docs/asana-and-asana-premium-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | - DSR Automation using APIs - Workflow |
| [Asana Enterprise](/v1/docs/asana-enterprise-connectors) | Self-hosted | Unstructured | Pod/ePod | API Key | Not supported | - DSR Automation using Full Scan - Discovery Scan |
| [Asana Premium](/v1/docs/asana-and-asana-premium-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [Confluence Data Center](/v1/docs/confluence-data-center-connectors) | Self-hosted | Unstructured | Pod/ePod | API Key | HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis - Workflow |
| [Confluence Cloud](/v1/docs/confluence-cloud-connector-1) | Self-hosted | Unstructured | Pod/ePod | OAuth | Not supported | - Discovery Scan - Breach Analysis - DSR Automation using Full Scan - Workflow - Data Inventory Sync - Gencore AI Entitlements scan |
| [DocuSign](/v1/docs/docusign-connectors) | Securiti Cloud | Unstructured | API | OAuth | Not supported | - Breach Analysis - Security Posture Scan - Standard Data Scan |
| [DocuSign](/v1/docs/docusign-connectors) | Self-hosted | Unstructured | Pod | OAuth | Not supported | - DSR Automation using APIs - Breach Analysis - Discovery Scan |
| [Front](/v1/docs/front-connectors) | Self-hosted | Hybrid | Pod/ePod | API Key | Not supported | DSR Automation using Full Scan |
| [G Suite Gmail](/v1/docs/g-suite-gmail-securiti-cloud-connectors) | Securiti Cloud | Unstructured | API | OAuth | Not supported | - DSR Automation using APIs - Breach Analysis - Security Posture Scan |
| [G Suite Gmail (Attachments)](/v1/docs/g-suite-gmail-message-body-attachments-connectors) | Self-hosted | Unstructured | Pod | OAuth | Not supported | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [G Suite Google Calendar](/v1/docs/g-suite-google-calendar-securiti-cloud-connectors-1) | Securiti Cloud | Unstructured | API | OAuth | Not supported | Breach Analysis |
| [G Suite Gmail (Message Body)](/v1/docs/g-suite-gmail-message-body-attachments-connectors) | Self-hosted | Unstructured | Pod/ePod | OAuth | Not supported | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [GitHub](/v1/docs/github-connectors-1) | Self-hosted | Unstructured | Pod/ePod | - OAuth App - GitHub App | Not supported | - Discovery Scan - Breach Analysis - Data Inventory Sync - Gencore AI Entitlements scan |
| [GitLab](/v1/docs/gitlab-connectors-1) | Self-hosted | Unstructured | Pod | Basic | Not supported | - DSR Automation using Full Scan - Discovery Scan - Data Inventory Sync - Gencore AI Entitlements scan |
| [Microsoft Teams](/v1/docs/microsoft-teams-connectors) | Self-hosted | Unstructured | Pod/ePod | OAuth | HashiCorp | - Breach Analysis - Discovery Scan - DSR Automation using Full Scan - Data Inventory Sync - Gencore AI Entitlements scan |
| [HelpScout](/v1/docs/helpscout-connectors-1) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [Intercom](/v1/docs/intercom-connectors) | Securiti Cloud | Scanless | API | OAuth | Not supported | DSR Automation using APIs |
| [Jira Cloud](/v1/docs/jira-cloud-connectors-1) | Securiti Cloud | Unstructured | API | OAuth | Not supported | - Workflow - Breach Analysis - Standard Data Scan |
| [Jira Cloud](/v1/docs/jira-cloud-connectors-1) | Self-hosted | Hybrid | Pod/ePod | OAuth | HashiCorp | - Discovery Scan - Breach Analysis - Data Inventory Sync - Gencore AI Entitlements scan |
| [Jira Software Data Center](/v1/docs/jira-data-center-connectors) | Self-hosted | Hybrid | Pod/ePod | OAuth | HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis - Workflow |
| [Microsoft 365 Calendar](/v1/docs/microsoft-365-calendar-connectors-1) | Securiti Cloud | Unstructured | API | OAuth | Not supported | Breach Analysis |
| [Microsoft 365 Lists](/v1/docs/microsoft-365-lists-connectors-1) | Self-hosted | Unstructured | Pod/ePod | - OAuth - Ceritficates | - HashiCorp - Azure Key Vault - CyberArk Vault | - Discovery Scan - Breach Analysis |
| [Microsoft 365 Outlook](/v1/docs/microsoft-365-outlook-connectors) | Securiti Cloud | Unstructured | API | OAuth | HashiCorp | - DSR Automation using APIs - Workflow - Breach Analysis |
| [Microsoft 365 Outlook](/v1/docs/microsoft-365-outlook-connectors) | Self-hosted | Unstructured | Pod/ePod | OAuth | - HashiCorp - CyberArk | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [Microsoft 365 Outlook (Legacy) (Attachments)](/v1/docs/microsoft-365-outlook-connectors) | Self-hosted | Unstructured | Pod | OAuth | HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [Microsoft 365 Outlook (Legacy) (Message Body)](/v1/docs/microsoft-365-outlook-connectors) | Self-hosted | Unstructured | Pod | OAuth | HashiCorp | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [Slack](/v1/docs/slack-connectors) | Securiti Cloud | Unstructured | API | OAuth | Not supported | - DSR Automation using APIs - Workflow - Breach Analysis - Security Posture Scan |
| [Slack Enterprise Grid](/v1/docs/slack-enterprise-grid-connectors) | Self-hosted | Unstructured | Pod/ePod | OAuth | Not supported | - DSR Automation using Full Scan - Discovery Scan - Data Inventory Sync - Gencore AI Entitlement scan - Breach Analysis |
| [Slack (Self-hosted)](/v1/docs/slack-connectors) | Self-hosted | Unstructured | Pod/ePod | OAuth | Not supported | - DSR Automation using Full Scan - Discovery Scan - Breach Analysis |
| [SAP SuccessFactors](/v1/docs/sap-successfactors-connectors) | Securiti Cloud | Structured | API | Basic | Not supported | DSR Automation using SQL queries |
| [SAP Successfactors](/v1/docs/sap-successfactors-self-hosted-connectors) | Self-hosted | Structured | Pod | OAuth | Not supported | - DSR Automation using SQL queries - Discovery Scan |
| [Smartsheet](/v1/docs/smartsheet-connectors) | Securiti Cloud | Hybrid | API | API Key | Not supported | DSR Automation using APIs |
| [Securiti for Box](/v1/docs/securiti-for-box-connector) | Self-hosted | Unstructured | Pod/ePod | OAuth | Not supported | - DSR Automation using APIs - Discovery Scan - Data Inventory Sync - Gencore AI Entitlements scan |
| [Trello](/v1/docs/trello-connectors) | Securiti Cloud | Scanless | API | API Key | Not supported | DSR Automation using APIs |

### Streaming

| Application name | App type | Scan type | Connection method | Authentication types | Credential vault types | Module features support |
| --- | --- | --- | --- | --- | --- | --- |
| [Kafka](/v1/docs/kafka-connectors-1) | Self-hosted | Streaming | Pod | - Plain Text - SSL Without Client Authentication - SSL With Client Authentication - SASL plain text - SASL SSL | HashiCorp | Discovery Scan |
| [Amazon MSK](/v1/docs/amazon-msk-connectors) | Self-hosted | Streaming | Pod | - Plain Text - SSL Without Client Authentication - SSL With Client Authentication - SASL plain text - SASL SSL | - AWS Secrets Manager - HashiCorp | - Discovery Scan - Access Intelligence Scan (Privilege Analysis) |
| [Confluent Kafka](/v1/docs/confluent-kafka-connectors) | Self-hosted | Streaming | Pod | - Plain Text - SSL Without Client Authentication - SSL With Client Authentication - SASL plain text - SASL SSL | HashiCorp | Discovery Scan |

## Related

- [Configuring connectors for monitored data systems](/configuring-connectors-for-monitored-data-systems.md)
- [Pods deployment](/pods-deployment.md)
- [Credential vaults](/managing-credentials-configuring-credential-vaults.md)
