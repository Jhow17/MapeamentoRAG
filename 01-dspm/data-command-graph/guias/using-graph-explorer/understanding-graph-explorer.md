---
title: "Understanding Graph Explorer"
slug: "understanding-graph-explorer"
updated: 2026-07-13T12:47:50Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/understanding-graph-explorer"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Understanding Graph Explorer

The Graph Explorer module opens with a blank page where you can create your queries and save them as views. You can import JSON queries or open existing ones from the **Saved Views**. By default, you are in **Query Builder** mode, where you can begin by adding entities, their properties, and relationships according to your use case and view the results in **Table** view.

See the sections below for supported features in the Graph Explorer.

### Supported modes for queries

You can create and view queries in Graph Explorer using the following modes.

- **Query Builder**: This is the default mode where you add entities and properties from the filter panel.
- **JSON View**: This mode can be used if you have a JSON query. You can see the results by pasting the query in the code window.

### Supported views for query results

After you have created your queries, you can switch between the following views to visualize and analyze your query results.

- **Table**: This the default grid view where query results are displayed in form of rows and columns. The Table view uses 2 panels to displays entities in a query and the instances of the related entities in a grid. The rows represent instances for an entity while each column represent a property for that entity.

For more information, see [Using Table View in Graph Explorer](/v1/docs/using-table-view-in-graph-explorer).

![Overview of data system entities and file findings in a graphical interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Graph Explorer_Findings.png)
- **Relationship**: The Relationship view is used to understand the relationships between entities in a side by side or segmented view.

The Relationship view uses a segmented layout with entities in columns and each row representing a relationship. The layout is effective when working with deep, multi-level queries. You can switch between **List** and **Graph** views, to analyze results, as shown below. For more information, see [Using Relationship view in Graph Explorer](/v1/docs/using-relationship-view-in-graph-explorer).

![Graph Explorer displaying security posture findings for AWS S3 bucket configurations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Relationship tab_Graph Explorer.png)

### Entities and properties

In the Graph Explorer, you create your queries or views by selecting entities and adding relationships with other entities. Moreover, you can filter each entity by its key attributes or properties to view data according to your requirements.

#### Entities

Securiti lets you view data for a module's node such as **Data System** as entities in the Data Command Graph. You can select the entities from the filter panel. Entities belonging to a similar domain in Securiti are placed together in the form of groups.

You can also add more entities to your query as relationships using the **Add relationship** option.

The table below lists the supported entities and their groups.

| Group | Entities |
| --- | --- |
| AI | AI Agent |
| AI Assistant |
| AI Knowledge Base |
| AI Model |
| AI Platform |
| AI Utility |
| Vector DB |
| Access Intelligence | Activity Log |
| M365 Application |
| M365 Channel |
| SMB Computer |
| Organization |
| M365 Team |
| Identity Provider |
| Active Directory Provider |
| Policy Element |
| Sharing Link |
| Policy Object |
| Policy Privilege Bundle |
| Role |
| Service Account |
| User Principal |
| User Group Principal |
| Active Directory User Group |
| MSFT 365 User Group Partition |
| Active Directory User Identity |
| Resource Access |
| Sharing Link Resource Access |
| Resource Scope |
| Assets | Cloud Asset |
| Cloud | Hosting |
| IaaS Cloud |
| Private Cloud |
| SaaS |
| Compliance | Category |
| Compliance Documents |
| Control |
| Test |
| Framework |
| Project |
| Subcategory |
| Compute | Compute Instance |
| Container Image |
| Kubernetes Cluster |
| Kubernetes Deployment |
| Kubernetes Service |
| Serverless Compute |
| Control | Data Access Control |
| Cross Border Applicability |
| Automation |
| Data Labeling |
| Test Finding |
| Cross Border Finding |
| Cross Border Transfer |
| Security Posture |
| File Findings |
| Finding |
| Gencore AI Firewall Finding |
| Firewall |
| Gencore AI Firewall Rule |
| File Insights |
| Metadata Registration |
| Policy |
| Security Posture Finding |
| File Quarantine |
| File ROT |
| Rule |
| Security Posture Rule |
| Structured Data Findings |
| Structured Data Insights |
| Data | Data Analytics |
| Block Storage |
| Block Storage Snapshot |
| Cloud Service |
| DB Cluster Nodes |
| Cold Storage |
| Collection |
| Column |
| Database |
| Database Cluster |
| Database Schema |
| Data Object |
| Data System |
| Data Warehouse |
| Data Field |
| Discovery Scan |
| Discovery Scan Files |
| Discovery Scan Jobs |
| Files |
| File Storage |
| Folders |
| InMemory Data Store |
| Inventory Scan Job |
| Location |
| Object Storage |
| Package |
| Sampler Group |
| Sampler Super Group |
| Schema Namespace |
| Site |
| Streaming Service |
| Streaming Field |
| Structured |
| Structured Database |
| Table |
| Topic |
| Data Classification | Content Profile |
| Data Element |
| Document Type |
| Exact Data Profile |
| File Cluster |
| File Format |
| Data Map | Assessment |
| Data Transfer |
| Institution |
| Process |
| Risk |
| Vendor |
| Enterprise Data Catalog | Assertion |
| Chart |
| Checkpoint |
| Checkpoint Execution |
| Dashboard |
| Data Domain |
| Data Flow |
| Data Job |
| Data Process |
| Data Product |
| Data Quality Finding |
| Expectation |
| Expectation Execution |
| Expectation Template |
| Glossary Node |
| Glossary Term |
| Responsibility |
| Tags |
| GenAI Pipeline | Data Loader |
| Embeddings Generator |
| Embeddings Generator/Retriever |
| Embeddings Retriever |
| Prompt Firewall |
| Prompt/Response Firewall |
| Query Agent |
| Response Firewall |
| Retrieval Firewall |
| Data Sanitizer |
| Gencore AI | AI Artifact |
| Gencore AI Model |
| API Client |
| Chat Bot |
| Embeddings Model |
| Gencore AI Firewall Profile |
| User Interface |
| LLM Model Provider |
| Messaging App |
| GenAI Pipeline |
| Vector Database |
| Vector DB Provider |
| Widget |
| Management | Account |
| Audit Logging |
| Backup Server Name |
| Database Account |
| Region |
| Secret Management |
| Storage Account |
| Network | ACL |
| API Gateway |
| Content Delivery Network |
| DNS |
| Firewall |
| Security Group IP Rule |
| Load Balancer |
| Network |
| Security Group |
| Subnetwork |
| Policy | Classification Label |
| Policy Classification Labels |
| Scanned Classification Labels |
| Protected | Protected OneDrive |
| Protected Outlook Mailbox |
| Protected M365 Site |
| Protected M365 Team |
| Protected Resource |
| Restore Point |
| VDC Data System |
| Securiti RBAC | Securiti Data User |
| Securiti Tenant User |
| Securiti User |
| Securiti User Group |
| Workflow | Workflow |
| Workflow Execution |

#### Properties

Each entity or node has a number of properties related to it that you can use to view your required data. The properties help you optimize and tailor your search to suit your requirement. These properties also represent key attributes or elements and define the type of an information you can get for an entity.

For example, you can set the **Hosting** property to **AWS** for **Data System** entity to return all AWS data systems in Securiti.

As you select an entity, the properties are also shown in columns in the grid such as for **Data System** entity, you see columns like **Data System Owner**, **Account**, **Content Profile** etc as shown in the screenshot below. You can add or remove properties you see on the Graph Explorer page using the column selector.

![Graph Explorer interface displaying various data system entities and their attributes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Graph Explorer_Columns View.png)

A graph modeling term. Relationships represent a meaningful connection between nodes in graph data modeling. It defines how instances of one node are related to instances of another node within the graph. For example, **Account** node is related to nodes like **Region** and **Data System** in the following manner: Account *has* Data System, Account *belongs to* Region. Here, *has* and *belongs to* are the relationships. Also used interchangeably with the term, *Edge*.

## Related

- [Managing queries in the Graph Explorer](/managing-queries-in-the-graph-explorer.md)
- [Using Table View in Graph Explorer](/using-table-view-in-graph-explorer.md)
- [Using Relationship view in Graph Explorer](/using-relationship-view-in-graph-explorer.md)
