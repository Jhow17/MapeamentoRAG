---
title: "EDC Health dashboard"
slug: "edc-health-dashboard"
updated: 2026-06-10T15:21:17Z
published: 2026-06-10T15:21:17Z
canonical: "helpcenter.securiti.ai/edc-health-dashboard"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# EDC Health dashboard

**Scenario**

As a Data Governance Officer, you need to ensure that data catalog services are running smoothly so users can access and manage data without disruption. When users report issues with search and dataset access, it is not clear which service is causing the problem. Instead of checking multiple areas, you open the EDC Health Dashboard and filter for degraded services. You notice the Search Service is degraded. This helps you quickly identify the issue, inform the right team, and reduce downtime for users.

The **EDC Health** dashboard provides visibility into the health and availability of key data catalog services within your Securiti tenant. It helps you quickly understand whether services are operating normally or experiencing issues. Instead of relying on environment-level alerts or troubleshooting across multiple areas, you can view service status in one place and identify impacted modules.

The dashboard lets you monitor platform availability, detect the status of services, and take action faster when issues occur.

A service may become degraded due to one or more underlying issues. Examples of conditions that can contribute to service degradation include high GraphQL API latency and failed database transactions.

To access EDC Heath Dashboard:

- Open Securiti, then choose System Settings > **Enterprise Data Catalog > EDC Ingestion**.

![Overview of EDC Health service statuses with timestamps and descriptions of service health.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/EDC health - status descriptions.png)

## Services

The dashboard displays the status of the following predefined services.

| Service | Description |
| --- | --- |
| Container Service | Manages storage containers and organizes datasets within the data catalog. |
| Data Platform Service | Supports core platform operations and data processing workflows. |
| Data Product Service | Handles creation and management of data products within the catalog. |
| Dataset Service | Manages dataset ingestion, updates, and metadata. |
| Deletion Service | Processes deletion requests for datasets and related assets. |
| Domain Service | Organizes data into business domains for easier management and discovery. |
| Entity Service | Manages entities and their relationships within the data model. |
| Export Service | Handles exporting of data and metadata from the platform. |
| Glossary Service | Manages business glossary terms and definitions. |
| Import Service | Supports importing data and metadata into the platform. |
| Ingestion Service | Handles data ingestion from various sources into the catalog. |
| Ownership Service | Manages ownership assignment for datasets and assets. |
| Policy Service | Enforces governance and access control policies. |
| Search Service | Enables search functionality across datasets and metadata. |
| Structured Property Service | Manages structured metadata attributes for datasets. |
| Tag Service | Supports tagging of datasets and assets for classification. |
| User Service | Manages user-related operations and access within the platform. |

## Status

You can choose to view the status of the services as follows.

| Status | Description |
| --- | --- |
| Healthy | View the list of healthy services that are running smoothly with no issues. |
| Failed | View the list of failed services that stopped due to errors and require attention. |
| Degraded | View the list of services that are degraded i.e. partially impacted but still progressing. |

> [!NOTE]
> Important
> 
> In case of failures or degradations, contact your Customer Success Manager or Account Representative for more information.
