---
title: "Viewing entitlements for hyperdrive data systems"
slug: "viewing-entitlements-for-hyperdrive-mode"
updated: 2026-07-21T10:30:27Z
published: 2026-07-21T10:30:27Z
canonical: "helpcenter.securiti.ai/viewing-entitlements-for-hyperdrive-mode"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Viewing entitlements for hyperdrive data systems

Securiti lets you view user entitlements in the Graph Explorer, so you can see who has access to data used in your Gencore AI pipelines before you finalize scope. This helps you validate access and reduces the risk of unintended data exposure.

You can view users and user groups discovered through entitlement scans run on your data systems, and discover their relationships to files. Once an entitlement scan runs successfully on your data system, you can visualize the access paths using direct entitlement relationships between users, user groups, and files.

Securiti supports granular entitlement permissions in Graph Explorer. You can view Read, Write, and Full Control access separately for both **Files** and **Data System** entities. This lets you understand who has access, what level of access they have, and where that access applies.

> [!WARNING]
> Important
> 
> - User entitlements are published in Graph Explorer only for tenants with Hyperdrive mode enabled. If this update is not available in your tenant, contact your Customer Success Manager or Account Representative to determine if this feature is included in your subscription and if your tenant meets the requirements to use this functionality.
> - You must have Entitlement scans configured for your data system connector to view

The following table lists the entities you can use to view entitlements in Graph Explorer, along with their related entities. Each of these entities can have separate Read, Write, and Full Control relationships with Files, Objects, and Data Systems. For each entity, you can view the following granular permission relationships:

- Has Full Read Access
- Has Full Write Access
- Has Full Control Access

| Entitlement entity | Related entities |
| --- | --- |
| User Principal | Files |
| M365 User Group Partition | Files |
| M365 AI Agent | - Data System - Object Storage - Database Cluster - Streaming Service - Data Warehouse - In Memory Data store - File Storage - Cold Storage - Cloud Service - Data Analytics - Structured - Files |
| M365 Application | - Data System - Object Storage - Database Cluster - Streaming Service - Data Warehouse - In Memory Data store - File Storage - Cold Storage - Cloud Service - Data Analytics - Structured - Files |
| M365 Channel | Files |
| M365 Team | Files |
| Organization | Files |
| SMB Computer | - Data System - Object Storage - Database Cluster - Streaming Service - Data Warehouse - In Memory Data store - File Storage - Cold Storage - Cloud Service - Data Analytics - Structured - Files |

Additionally, you can also view the relationships with **Site**, **Data Element**, and **Content Profile** entities in the Instance Explorer, as shown below.

![Overview of onboarding process with details on user groups and data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/entitlement_relationship.png)
