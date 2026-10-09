---
title: "Data Access Governance (DAG) overview"
slug: "data-access-governance-dag-overview"
updated: 2026-09-18T09:36:45Z
published: 2026-09-18T09:38:58Z
canonical: "helpcenter.securiti.ai/data-access-governance-dag-overview"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Data Access Governance (DAG) overview

> [!WARNING]
> Important
> 
> This module is available in Securiti SaaS deployments but is not currently available in Securiti Sovereign deployments. Contact your Customer Success Manager or Account Representative for updates on its availability in your tenant.

Governance on access to data is a core privacy principle that features prominently in all privacy directives and regulations. Data Access Governance (DAG) is a set of capabilities that help you understand and control users’ access to your data estate. DAG lets you analyze, manage, and protect sensitive data via access intelligence and granular access control policies.

To implement appropriate security, privacy, and compliance measures for the data, it is essential to have a clear understanding of the specific sensitive data present within the data systems. Without this context, you may encounter difficulties in determining the level of data access different stakeholders from within your organization should have to the data system and data elements present within these data systems. To achieve governance on the access of your data, organizations must:

- Discover all the data systems they have that may contain sensitive data across multi-cloud environments.
- Discover and classify any sensitive and personal data that exists within these data systems.
- Perform Privilege Analysis: analyze and discover which users, groups, and roles may have access to the sensitive data.
- Track the geographic location of the data, the identities associated with the data, and the location of users accessing the data.
- Interpret the relevant data regulations for the specific location where the data is held, and the individuals using that data.

## Data Access Governance (DAG) solution

Data Access Governance consists of the following sets of capabilities for addressing data access use cases.

#### Access Intelligence

Access Intelligence provides insights into who can and is accessing data within your data estate and consists of the following features. It lets you to accomplish the following security, Privacy, and Compliance objectives.

- Protect sensitive data by easily identifying which users and roles from your organization have access to the sensitive data and information.
- Discover how IAM and RBAC configurations are creating access to the sensitive data.
- Explore the relationship between user identities and the access to data they have.
- Identify orphaned accounts and identities, over-provisioned users, and dormant data.
- Track the geographic location of the data and applicable privacy, security, and data sovereignty regulations.

#### Privilege analysis

**Scenario**

As a Data Security Officer, you need to ensure only authorized users have access to sensitive data across your data systems. Manually tracking permissions and roles is slow and error-prone, risking unauthorized exposure. With Securiti privilege analysis and Data Command Graph, you gain clear visibility into user privileges, policy relationships, and data sources enabling you to enforce least privilege access quickly and accurately.

**Overview**

Privilege analysis ingests the Identity and Access Management (IAM) and Role-Based Access Control (RBAC) metadata within your data systems and presents the data through a normalized knowledge graph allowing you to quickly identify who can access sensitive data, how that access is created, and who can administer that access within a data system.

For more information, see [Data Command Graph](/v1/docs/data-access-governance-data-command-graph).

#### Activity analysis

**Scenario**

As a Data Governance Lead, you need to monitor how users interact with data across your environment. Without clear visibility, it’s hard to spot unusual activity or over-provisioned access. With Activity Analysis, you can see who is accessing databases, files, and sites most often or not at all. This helps you detect risky behavior, remove unused privileges, and keep access aligned with actual usage.

**Overview**

Activity analysis lets you see who is actually interacting on the data within your data systems. Using user activity logs from the source data system, activity analysis provides insights into over provisioned access to data, dormant data, and undesired usage of sensitive and personal data.

Securiti as part of its Activity Analysis functionality, provides visibility into Over-provisioned User Access and Most Active Users.

Over-provisioned users are those with access to data they have not used within a defined time period. This lets your security and IAM teams to minimize unnecessary user access, thereby reducing security risk.

#### Cross border analysis

Cross border analysis lets you identify where your data systems are storing your data and what data sovereignty and privacy regulations that data may be subject to. Using data provided by Securiti’s DAG privilege and activity analysis features you can identify incorrectly provisioned access to data and define Cross-border data transfer policy that identify and alert on access to data that may violate privacy and sovereignty regulations.

For more information, see [Cross border transfer policies](/v1/docs/cross-border-transfer-policies).

#### Access Control

**Scenario**

As a Data Security Officer, you're responsible for limiting access to sensitive data across multiple systems. Manually updating user permissions in each system is inefficient and increases the risk of exposure. With Access Control Policies, you centrally enforce fine-grained restrictions based on data classification across all connected data systems. This ensures only the right users access sensitive data, saving time and reducing security risks.

#### Overview

Access Control lets you restrict the access of users and roles to the data resources. You can also define policy-driven access controls on data objects like tables, views, and columns. Policies can be object-level or more fine-grained as in the case of Row-Level Filtering and dynamic column masking. Policy decisions use classifications or tags from data discovery as well as other query contexts such as user attributes and location data. A centralized policy engine translates policies into native enforcement constructs for each supported platform. You must connect the data systems to Securiti’s platform and configure and activate the built-in connectors for these data assets, to create the data access control, cross-border data transfer, and data masking policies for your data systems.

## Data System Coverage for Data Access Governance

| **Data System** | **Access Intelligence** | **Access Control** |
| --- | --- | --- |
| **Privilege Analysis** | **Activity Analysis** | **Cross-Border Data Transfer Policies** |
| **Column Masking Policies** | **Row Level Filtering Policies** | **Permissions Management Policies** |
| Active Directory |  |  |  |  |  | ✓ |
| Amazon S3 | ✓ |  |  | N/A | N/A |  |
| Amazon Bedrock | ✓ |  |  | N/A | N/A |  |
| Amazon DynamoDb | ✓ |  |  |  |  |  |
| Amazon Redshift Cluster | ✓ |  |  |  |  |  |
| Amazon MSK (Amazon Managed Streaming for Apache Kafka) | ✓ |  |  |  |  |  |
| Amazon RDS Instance | ✓ |  |  |  |  |  |
| Apache Hive |  |  |  | ✓ | ✓ | ✓ |
| Apache Trino |  |  |  | ✓ | ✓ | ✓ |
| Apache Presto |  |  |  | ✓ | ✓ | ✓ |
| HDFS |  |  |  | N/A | N/A | ✓ |
| HDFS Google Data proc |  |  |  | N/A | N/A | ✓ |
| Box | ✓ |  |  | N/A | N/A |  |
| Databricks | ✓ |  |  | ✓ | ✓ | ✓ |
| Dropbox | ✓ |  |  | N/A | N/A |  |
| Microsoft Sharepoint Online | ✓ | ✓ | ✓ | N/A | N/A | ✓ |
| OneDrive | ✓ |  |  | N/A | N/A |  |
| SMB | ✓ |  |  | N/A | N/A |  |
| SMB NetApp | ✓ | ✓ |  | N/A | N/A |  |
| SMB Dell Isilon | ✓ |  |  | N/A | N/A |  |
| Snowflake | ✓ |  |  | ✓ | ✓ | ✓ |
| Starburst (Apache Ranger Driven Policies) | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Google BigQuery |  |  |  | ✓ | ✓ | ✓ |

Privilege Analysis is a feature set of DAG Access Intelligence which ingests the Identity and Access Management (IAM) and Role Based Access Control (RBAC) metadata within your data systems and presents the data through a normalized knowledge graph allowing you to quickly identify who can access sensitive data, how that access is created, and who can administer that access within a data system.

Access Intelligence is the insight into the users’ access to applications and data. This includes permissions and activity perfromed on data sources.

Data accessed by a user or role over a filtered time period.

It is a set of definitions related to the movement and access of data across national borders to comply with privacy regulations. It aims to mitigate the risk of unauthorized access, providing a framework for managing and remediating such risks through governance workflows.

A fine-grained access control method that restricts access to specific rows of data in the table in the data system.

## Related

- [Using Data Command Graph](/data-access-governance-data-command-graph.md)
- [Supported Data Systems for Data Access Governance](/supported-data-systems-for-data-access-governance.md)
- [Microsoft 365 SharePoint Online](/microsoft-365-sharepoint-online.md)
- [Windows SMB](/smb.md)
