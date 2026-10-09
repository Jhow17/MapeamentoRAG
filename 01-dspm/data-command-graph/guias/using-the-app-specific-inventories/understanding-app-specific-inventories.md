---
title: "Understanding app-specific inventories"
slug: "understanding-app-specific-inventories"
updated: 2026-02-11T07:25:12Z
published: 2026-02-11T07:25:12Z
canonical: "helpcenter.securiti.ai/understanding-app-specific-inventories"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Understanding app-specific inventories

The app-specific inventories show you the sub-graph for all your app-level entities. The page offers a Circular Graph view and a grid to view the inventory at the bottom of the page. The Circular Graph represents the following information.

- Entities - static metadata for the various nodes
- Metadata respective counts
- Relationship among entities

The Circular Graph view provides a pre-defined graph with curated node selections for exploring the graph. This view automatically traverses every relationship between the entities in the circular graph when you apply property filters.

> [!NOTE]
> **Important**
> 
> The Circular Graph view does not return complete results for all related entities. We recommend you do not use these results for reporting purposes.

You can view entities, their respective count, and relationships among entities in the data command graph based on the applied filters.

![dcg_circulargraph.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ecff6147-1d6b-781d-8063-31910b20465e.png)

The grid view lets you view data and apply filters across entities in the SDI or DAG inventory. You can view metrics and counts for entity and relationship types, and as you apply filters, the counts or metrics adjust for the filtered entity along with all the related entities.

![dcg_sdiinventory_grid.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-73e254f6-bd3f-7edc-eaf0-8a42bc56cbc0.png)

For more information, see [Using grid view in app-specific inventories](/v1/docs/using-grid-view-in-app-specific-inventories).

### Entities

Securiti lets you view the fixed number of entities as circles on the data command graph that best represent the underlying data. For instance, a Data Element entity may have a count of 70.

![dcg_circulargraph_entities.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-14dccc18-782e-6921-c12b-1330d433ee40.png)

To can view the entities on the **Data command Graph in SDI**, access the module and click **Data Command Graph** from the left navigation menu as shown below.

![dcg_sdidcg_access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cb32b49a-f741-2330-bc54-b8ffc9517e03.png)

You can filter data in the form of the following five groups:

| Group 1 (Management) |
| --- |
| Entities | IaaS Cloud | A managed cloud service such as AWS (Amazon Web Services), GCP (Google Cloud Platform) and Microsoft Azure. |
| SaaS | Web-based software applications accessible via the internet on a subscription basis, eliminating the need for local installation such as, Gmail, Salesforce, and Microsoft Office 365. |
| Private Cloud | Dedicated cloud computing environment for a single organization. |
| Account | An account in a managed cloud service. Some services may use the word 'Project'. |
| Region | The geographic location in which the resources offered by the managed service are located. |

| Group 2 (AI) |
| --- |
| Entities | AI Platform | An IaaS based AI platform. |
| AI Model | AI Foundational or custom model deployed on IaaS cloud. |
| AI Agent | AI agents provide the ability to build and configure autonomous agents in your application. |

| Group 3 (Data) |
| --- |
| Entities | Data System | A Securiti abstraction for systems that hold data. These could be relational databases that hold structured data, NoSQL databases, object stores such as AWS S3, unstructured data stores such as file systems or SaaS file sharing services and streaming data systems such as Kafka. |
| Object Storage | A data storage architecture for unstructured data, such as buckets by AWS S3 (Amazon Simple Storage Service), Azure Blob Storage, and Google Cloud Storage. |
| Database Cluster | A group of interconnected databases ensuring high availability and scalability, such as MySQL Cluster, PostgreSQL Cluster, and Oracle Real Application Clusters (RAC). |
| Streaming Service | Real-time data processing systems like Apache Kafka, allowing continuous data flow. |
| Data Warehouse | Centralized repositories for analytics, such as, Google BigQuery, Amazon Redshift, and Snowflake, which store and analyze vast amounts of structured and semi-structured data. |
| InMemory Data Store | High-speed data storage in RAM, such as, Redis (a key-value store). |
| Cloud Service | A service offered by an IaaS, PaaS, or SaaS vendor as a managed service. |
| Files | Individual units of data storage, such as text files (.txt), images (.jpg, .png), and documents (.docx). |
| Folder | Virtual containers in file systems, as seen in cloud services like Google Drive and Dropbox. |
| Database | Structured data systems providing organized storage and retrieval capabilities. |
| Site | A site represents an HTTP website reachable at a URL. |
| Table | Fundamental data structures in relational databases, such as tables in MySQL, PostgreSQL |
| Topic | Messaging channels in systems like Apache Kafka, used to route data streams. |
| Data Element | Basic units of data representation, such as, individual fields like "customer name" |
| Content Profile | Content profiles are sets of rules that Securiti uses to identify types of document content. Securiti comes with a set of system content profiles that can be enabled or disabled. You can also create your custom content profiles. |
| Discovery Scan | A discovery scan is a scan initiated against one or more data systems periodically to detect and classify sensitive data in those data systems. |

| Group 4 (Control) |
| --- |
| Entities | Policy | A Securiti abstraction for specifying the scope of data to which a certain action (e.g. masking, labeling) is applied when the scoped data meets the specified conditions. |
| Regulation | A regulation such as GDPR, CCRA, LGPD. |
| Standard | A standard such as NIST, SOC 2, ISO 27001. |
| Finding | A finding against a data system that violates a compliance regulation or a compliance standard. |
| Rule | A rule (or control) captures specific intentions/expectations that a regulation or standard requires enterprises to comply with. |

| Group 5 (Network) |
| --- |
| Entities | Network | The name of a network, such as the VPC in an Amazon AWS account. |
| Compute Instance | A compute instance such as a virtual machine or a container in managed cloud service. |
| Block Storage | Block Storage service offered by IaaS clouds (e.g. AWS EBS, GCP Compute Disk, Azure Managed Disk etc). |

For **Data Access Governance Inventory**, following three groups are available for entities.

- Management nodes, see the table above.
- Data nodes, see the table above.
- Access management nodes, see the table below.

| Group (Access Management) |
| --- |
| Entities | Identity Provider | An IAM identity provider. This represents a provider of identity information, such as Active Directory (AD), SSO, etc or even data system providers such as Snowflake or AWS. |
| User Principal | An IAM user principal. This represents a user present in the data system or account, and has some permissions to access data therein. |
| Usergroup Principal | An IAM usergroup. This is a group of users or service accounts as configured in the identity provider. |
| Role Principal | An IAM role. A role is a quasi-identity that is in turn assigned to users and has permissions to access resources on the user's behalf. |
| Service Account Principal | A service account. A service account is typically a user account provisioned for use by automated jobs, scripts etc. |
| Policy Object | A normalised IAM Policy object. This represents any access control object ranging from simple grants to complex policy definitions. |
| Policy Privilege bundle | The group of permission bundle (role definition in case of SPO) which holds granular permissions i.e View, Delete, Modify etc for the IAM Policy. |

Each node has a number of attributes related to it that you can use to filter the scope of the data command graph. For example, **Data Element** may have the attribute **Name**.

For **Enterprise Data Catalog**, following entities can be viewed and filtered in the Inventory.

| Group 1 (Management) |
| --- |
| Entities | IaaS Cloud | A managed cloud service such as AWS (Amazon Web Services), GCP (Google Cloud Platform) and Microsoft Azure. |
| SaaS | Web-based software applications accessible via the internet on a subscription basis, eliminating the need for local installation such as, Gmail, Salesforce, and Microsoft Office 365. |
| Private Cloud | Dedicated cloud computing environment for a single organization. |
| Account | An account in a managed cloud service. Some services may use the word 'Project'. |
| Region | The geographic location in which the resources offered by the managed service are located. |

| Group 2 (Data) |
| --- |
| Entities | Object Storage | A data storage architecture for unstructured data, such as buckets by AWS S3 (Amazon Simple Storage Service), Azure Blob Storage, and Google Cloud Storage. |
| Database Cluster | A group of interconnected databases ensuring high availability and scalability, such as MySQL Cluster, PostgreSQL Cluster, and Oracle Real Application Clusters (RAC). |
| Streaming Service | Real-time data processing systems like Apache Kafka, allowing continuous data flow. |
| Cloud Service | A service offered by an IaaS, PaaS, or SaaS vendor as a managed service. |
| Database | Structured data systems providing organized storage and retrieval capabilities. |
| Database Schema | Database Schema is a named collection of logical structures of data (such as tables, views, functions, constraints, indexes etc). |
| Site | A site represents an HTTP website reachable at a URL. |
| Table | Fundamental data structures in relational databases, such as tables in MySQL, PostgreSQL |
| Topic | Messaging channels in systems like Apache Kafka, used to route data streams. |
| Schema Namespace | The namespace that governs the structure of topics exchanged through a streaming datasystem such as Kafka. |
| Data Element | Basic units of data representation, such as, individual fields like "customer name" |
| Content Profile | Content profiles are sets of rules that Securiti uses to identify types of document content. Securiti comes with a set of system content profiles that can be enabled or disabled. You can also create your custom content profiles. |
| Column | A column of a SQL table containing structured data. |
| Streaming Field | A field in streaming data for eg, a message or event produced into or consumed from a topic of a streaming data system. |
| Location | A geographic location where a data system is physically located such as an AWS region in which a managed service such as RDS is located. |
| Discovery Scan | A discovery scan is a scan initiated against one or more data systems periodically to detect and classify sensitive data in those data systems. |

| Group 3 (Users) |
| --- |
| Entities | Tenant User | A user that can access Securiti's Data Command Center. |
| User Group | A group of user identities. A user may belong to multiple groups and groups may contain other groups. |

| Group 4 (Enterprise Data Catalog) |
| --- |
| Entities | Glossary Node | Glossary nodes are used to build taxonomies or hierarchies and contain groupings of glossary terms. |
| Glossary Term | Glossary terms represent business metadata and are used to aggregate business context for technical metadata. |
| Chart | A chart is a widget such as a pie chart, bar chart or a data table and is used to illustrate important characteristics of a data set. |
| Dashboard | A dashboard is a collection of chart objects. |
| Data Process | The execution states and results of an instance of a data job or job flow. |
| Assertion | An assertion is a data quality rule on a data object or data field. |
| Data Flow | Documents the orchestration of a data flows. |
| Data Job | An instance of a job execution within a data flow. It captures the metadata of a job such as data transformation. |
| Tags | Tags are free-form text labels that allow users to group objects for search, filtering, and use. |
| Data Domain | Data domains are used to group metadata from an organizational point of view. Data domains help to expedite ownership assignment as well as to find SMEs. |

### Viewing entities and their relationships

You can view your entities in circular form on the graph. The relationships between entities is represented as connecting lines between the circles.

1. In Securiti, open **Sensitive Data Intelligence** and from the left panel and choose **Dashboard** **> DataCommand Graph.**
2. On the data command graph dashboard, click any entity on the data command graph.

The graph shows you the selected entity highlighted in the entity’s respective group color and the connecting line between the entities shows you the relationship with other entities.

![dcg_circulargraph_relationship.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fb9956f1-0a1a-b7bd-3957-4f9b4cceaba4.png)

## Related

- [Using the Universal Data Explorer](/using-the-universal-data-explorer.md)
