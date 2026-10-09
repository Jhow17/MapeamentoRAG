---
title: "Data Security dashboards for Public Cloud"
slug: "data-security-dashboards-for-public-cloud"
updated: 2026-04-21T06:18:11Z
published: 2026-04-21T06:18:11Z
canonical: "helpcenter.securiti.ai/data-security-dashboards-for-public-cloud"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Data Security dashboards for Public Cloud

The Data Security dashboard lets you gain insights into your public cloud environment's security posture.

![Dashboard displaying Azure data security metrics and compliance status for various cloud services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datasecurity_dashboards.png)

The tables below show supported widgets in the Data Security system dashboards. The widgets are available in each cloud provider's dashboards.

**AWS widgets**

| Widget title | Widget type | Description |
| --- | --- | --- |
| AWS - Top Cloud Risks | Metric | Shows metric counts for the following information serving as cloud risks in AWS environment. - S3 Buckets with Read Access to Public - S3 Buckets without Encryption at Rest - Publicly Open S3 Buckets with Sensitive Data - Cloud Storage Buckets not encrypted with customer managed keys - S3 Buckets without DNS Compliant Names - S3 Buckets without MFA for Deletion - S3 Buckets Containing PII - Object Storage Buckets with Versioning is disabled |
| AWS - Open Security Findings by Severity | Chart | Provides information about all the open security findings in AWS, Azure, Google Cloud accounts, classified on the basis of their severity such as High, Low, etc. The findings are displayed in the form of a pie chart in their respective dashboards. |
| AWS - High Open Findings by Data System Type | Chart | Provides information about all the high open security findings in AWS, Azure, Google Cloud accounts as a severity count in their respective dashboards. The data is classified on the basis of the asset type in the form of a bar chart. |
| AWS - Critical Open Findings by Data System Type | Chart | Provides information about all the critical open security findings in AWS, Azure, Google Cloud accounts as a severity count in their respective dashboards. The data is classified on the basis of the asset type in the form of a bar chart. |
| AWS - Top 5 High and Critical Security Findings | Chart | Provides an overview of the top 5 high and critical security findings for AWS, Azure, Google Cloud data systems by listing the findings and displaying their counts in their respective dashboards. |
| AWS - Accounts with Most Critical Findings | Chart | Provides information about the most critical security findings in AWS accounts, Azure subscriptions, and GCP projects as a findings count in their respective dashboards. The data is classified on the basis of the account names in the form of a bar chart. |
| AWS - Regions with Most Critical Findings | Chart | Provides information about the most critical security findings in AWS, Azure, Google Cloud accounts as a findings count. The data is classified on the basis of the regions in the form of a bar chart. |
| AWS - Top Publicly Accessible Data Systems | Grid | Provides information such as assets, account name, and data size related to top 5 publicly accessible AWS, Azure, and Google Cloud data systems. |
| AWS - Top Data Systems with Logging Disabled | Grid | Provides information such as assets, account name, and data size related to top 5 AWS, Azure, and Google Cloud data systems with logging disabled. |
| AWS - Top Unencrypted Data System | Grid | Provides information such as assets, account name, and data size related to top 5 unencrypted AWS, Azure, and Google Cloud data systems. |
| AWS - Top Data Systems without Continuous Backups | Grid | Provides information such as assets, account name, and data size related to top 5 AWS, Azure, and Google Cloud data systems without continuous backups. |
| AWS - Top Data Systems with MFA Delete Disabled | Grid | Provides information such as assets, account name, and data size related to top 5 AWS, Azure, and Google Cloud data systems with MFA delete disabled. |
| AWS - Top Data Systems without KMS Encryption | Grid | Provides information such as assets, account name, and data size related to top 5 AWS, Azure, and Google Cloud data systems without KMS encryption. |

**Azure widgets**

| Widget title | Widget type | Description |
| --- | --- | --- |
| Azure - Top Cloud Risks | Metric | Shows metric counts for the following information serving as cloud risks in Azure environment. - Azure Storage Blobs with Read Access to Public - Azure Storage Blobs with Immutability disabled - Azure Storage Blobs publicly open with Sensitive Data - Azure Storage Blobs not encrypted with customer managed keys - Azure Storage Accounts without latest version of TLS Encryption - Azure Storage Blobs without Infrastructure Encryption - Azure Storage Blobs with PII - Azure Storage Accounts with Network Access |
| Azure - Open Security Findings by Severity | Chart | Provides information about all the open security findings in AWS, Azure, Google Cloud accounts, classified on the basis of their severity such as High, Low, etc. The findings are displayed in the form of a pie chart in their respective dashboards. |
| Azure - High Open Findings by Data System Type | Chart | Provides information about all the high open security findings in AWS, Azure, Google Cloud accounts as a severity count in their respective dashboards. The data is classified on the basis of the asset type in the form of a bar chart. |
| Azure - Critical Open Findings by Data System Type | Chart | Provides information about all the critical open security findings in AWS, Azure, Google Cloud accounts as a severity count in their respective dashboards. The data is classified on the basis of the asset type in the form of a bar chart. |
| Azure - Top 5 High and Critical Security Findings | Chart | Provides an overview of the top 5 high and critical security findings for AWS, Azure, Google Cloud data systems by listing the findings and displaying their counts in their respective dashboards. |
| Azure - Subscriptions with Most Critical Findings | Chart | Provides information about the most critical security findings in AWS accounts, Azure subscriptions, and GCP projects as a findings count in their respective dashboards. The data is classified on the basis of the account names in the form of a bar chart. |
| Azure - Regions with Most Critical Findings | Chart | Provides information about the most critical security findings in AWS, Azure, Google Cloud accounts as a findings count. The data is classified on the basis of the regions in the form of a bar chart. |
| Azure - Top Publicly Accessible Data Systems | Grid | Provides information such as assets, account name, and data size related to top 5 publicly accessible AWS, Azure, and Google Cloud data systems. |
| Azure - Top Data Systems with Logging Disabled | Grid | Provides information such as assets, account name, and data size related to top 5 AWS, Azure, and Google Cloud data systems with logging disabled. |
| Azure - Top Unencrypted Data System | Grid | Provides information such as assets, account name, and data size related to top 5 unencrypted AWS, Azure, and Google Cloud data systems. |
| Azure - Top Data Systems without Continuous Backups | Grid | Provides information such as assets, account name, and data size related to top 5 AWS, Azure, and Google Cloud data systems without continuous backups. |
| Azure - Top Data Systems with MFA Delete Disabled | Grid | Provides information such as assets, account name, and data size related to top 5 AWS, Azure, and Google Cloud data systems with MFA delete disabled. |
| Azure - Top Data Systems without KMS Encryption | Grid | Provides information such as assets, account name, and data size related to top 5 AWS, Azure, and Google Cloud data systems without KMS encryption. |

**GCP widgets**

| Widget title | Widget type | Description |
| --- | --- | --- |
| Google Cloud - Top Cloud Risks | Metric | Shows metric counts for the following information serving as cloud risks in GCP environment. - GCP Cloud Storage Buckets with Read Access to Public - GCP Cloud Storage Buckets with Logging disabled - GCP Cloud Storage Buckets publicly open with Sensitive Data - GCP Cloud Storage Buckets not encrypted with customer managed keys - GCP Cloud Storage Buckets with Retention Policy disabled - GCP Cloud Storage Buckets without default event-based hold on Objects - GCP Cloud Storage Buckets with PII - GCP Cloud Storage Buckets with versioning disabled |
| Google Cloud - Open Security Findings by Severity | Chart | Provides information about all the open security findings in AWS, Azure, Google Cloud accounts, classified on the basis of their severity such as High, Low, etc. The findings are displayed in the form of a pie chart in their respective dashboards. |
| Google Cloud - High Open Findings by Data System Type | Chart | Provides information about all the high open security findings in AWS, Azure, Google Cloud accounts as a severity count in their respective dashboards. The data is classified on the basis of the asset type in the form of a bar chart. |
| Google Cloud - Critical Open Findings by Data System Type | Chart | Provides information about all the critical open security findings in AWS, Azure, Google Cloud accounts as a severity count in their respective dashboards. The data is classified on the basis of the asset type in the form of a bar chart. |
| Google Cloud - Top 5 High and Critical Security Findings | Chart | Provides an overview of the top 5 high and critical security findings for AWS, Azure, Google Cloud data systems by listing the findings and displaying their counts in their respective dashboards. |
| Google Cloud - Projects with Most Critical Findings | Chart | Provides information about the most critical security findings in AWS accounts, Azure subscriptions, and GCP projects as a findings count in their respective dashboards. The data is classified on the basis of the account names in the form of a bar chart. |
| Google Cloud - Regions with Most Critical Findings | Chart | Provides information about the most critical security findings in AWS, Azure, Google Cloud accounts as a findings count. The data is classified on the basis of the regions in the form of a bar chart. |
| Google Cloud - Top Publicly Accessible Data Systems | Grid | Provides information such as assets, account name, and data size related to top 5 publicly accessible AWS, Azure, and Google Cloud data systems. |
| Google Cloud - Top Data Systems with Logging Disabled | Grid | Provides information such as assets, account name, and data size related to top 5 AWS, Azure, and Google Cloud data systems with logging disabled. |
| Google Cloud - Top Unencrypted Data System | Grid | Provides information such as assets, account name, and data size related to top 5 unencrypted AWS, Azure, and Google Cloud data systems. |
| Google Cloud - Top Data Systems without Continuous Backups | Grid | Provides information such as assets, account name, and data size related to top 5 AWS, Azure, and Google Cloud data systems without continuous backups. |
| Google Cloud - Top Data Systems with MFA Delete Disabled | Grid | Provides information such as assets, account name, and data size related to top 5 AWS, Azure, and Google Cloud data systems with MFA delete disabled. |
| Google Cloud - Top Data Systems without KMS Encryption | Grid | Provides information such as assets, account name, and data size related to top 5 AWS, Azure, and Google Cloud data systems without KMS encryption. |
