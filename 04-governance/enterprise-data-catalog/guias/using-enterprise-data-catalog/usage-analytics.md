---
title: "Usage analytics"
slug: "usage-analytics"
updated: 2026-07-19T19:36:08Z
published: 2026-07-19T19:36:08Z
canonical: "helpcenter.securiti.ai/usage-analytics"
stale: true
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Usage analytics

**Scenario**

As an Executive, you need to assess how effectively your teams are leveraging the Enterprise Data Catalog to guide strategic initiatives. Without visibility, it is difficult to spot underutilized assets or measure adoption. By opening the usage analytics dashboard, you instantly view weekly active users, top searched queries, and dataset engagement. This helps you identify trends, drive data adoption, and make informed decisions with confidence.

The usage analytics page provides various metrics and statistics that help you understand how often and in what ways the Enterprise Data Catalog is being accessed and used.

### Prerequisites

To perform actions on Usage Analytics, enable the **View Dataset Usage** permission for the your account. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

### Exploring Usage Analytics

To start:

- Open **Enterprise Data Catalog**, then on the top right corner of the page, choose **Usage Analytics**.

![usage_analytics_-_main.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-53575ac0-6693-d7e2-f042-135ecbf513e2.png)

At the top of the page, you can see the search bar that lets you discover data assets in the Enterprise Data Catalog. Simply type in the term and press enter.

It also shows you the stats for:

| Tile | Description |
| --- | --- |
| Weekly active users | Number of unique users actively engaging with the data catalog in a week. |
| Datasets | Count for registered datasets in the Enterprise Data Catalog. |
| Domains | Indicate how many distinct domains are available for exploration and analysis within the data catalog. |
| Charts | Refers to the number of graphs available to analyze data within the data catalog. |

It shows you the graphical representation for:

- Entities per domain
- Entities per platform
- Entities per term
- Entities per environment

You can choose any domain from the second search menu to see the following stats of the selected domain in easy-to-understand graphs:

- Weekly active users
- Searches last week
- Section views across entity types
- Actions by entity type

> [!NOTE]
> **Note**
> 
> You can enter the specific data asset in the search bar to view the graphical representation of the search asset.

The dashboard also lets you view the stats for:

| Tile | Description |
| --- | --- |
| Top searched queries | Click on any query to redirect to the search page and see the query result. |
| Top viewed datasets | Click on any dataset to open to access its dedicated page and explore comprehensive details. |

## FAQs

#### Why is the stats tab grayed out?

The stats tab is grayed out if there are no usage statistics for that dataset or there were no ingestion with usage extraction run before.
