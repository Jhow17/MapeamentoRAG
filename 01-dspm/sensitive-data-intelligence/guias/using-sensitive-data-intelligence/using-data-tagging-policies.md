---
title: "Using Data Tagging Policies"
slug: "using-data-tagging-policies"
updated: 2026-09-22T12:02:45Z
published: 2026-09-22T12:02:45Z
canonical: "helpcenter.securiti.ai/using-data-tagging-policies"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using Data Tagging Policies

**Scenario**

As a Data Governance Officer, you need every dataset across your organization classified consistently, whether it lives in cloud storage, a data warehouse, or a SaaS app. Manually reviewing files and applying labels doesn't scale once data spans dozens of systems, and inconsistent tagging leaves gaps in governance and reporting. Data Tagging policies let you define conditions once and apply tags such as "PII" or "Confidential" automatically across all matching data assets. For instance, you can tag every dataset containing financial records as "Sensitive" the moment it's discovered, giving you a single, reliable view of where sensitive data lives.

## Overview

Data Tagging policies apply or remove tags on data assets based on defined conditions, letting you automatically classify and manage data across your connected systems.

Tags are labels or metadata attributes that help categorize data based on sensitivity, business context, ownership, or other criteria, such as "PII," "Financial Data," "Confidential," or "Public."

These policies use metadata from the Data Command Graph. Securiti populates this metadata through the following scans configured for your data system connectors:

| Scans | Description |
| --- | --- |
| Data Inventory Sync | Retrieves metadata and inventory details, including file metadata and inventories of groups, sites, libraries, files, and folders. |
| Discovery Scan | Retrieves sensitive data by identifying structured, unstructured, streaming, personal, and regulated data, including shadow data and associated risks. |
| Access Intelligence | Retrieves entitlement insights, including identity principals and file or document access permissions. |

Using this metadata, you can define scopes through graph queries to identify relevant data objects, such as, including files, tables, columns, datasets, and other nodes in the graph. Once you define a scope, you can apply tagging actions to the matched objects.

## Prerequisites

- Data Tagging policies do not work with the Securiti Sovereign, as it requires integration with the Data Command Graph.
- Data Tagging policies support multi-org feature. For more information, see [Changing your Organization.](/latest/docs/system-settings-managing-organizations)
- The Data Inventory Sync for data system connectors must be enabled for your tenant.
- For Data Tagging policies that include FileExt entities, your tenant must have completed the inventory metadata migration to support policy execution.
- Ensure the required permissions are enabled for your role. For more information, see [Sensitive Data Intelligence Roles and Permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions).

## Key capabilities of Data Tagging policy

| Capabilities | Description |
| --- | --- |
| Platform-level Data Tagging | Apply meaningful tags to data to describe its status, sensitivity, or purpose. For instance, mark a data asset as "Sensitive," "Obsolete," "PII," or "Deprecated." |
| Data categorization | Tag data by organization (Org: Securiti), team (Team: Policy), owner (Owner: John), or project phase. |
| Policy creation from filters | Use tags to define data scopes for policies. For instance, filter all assets tagged **Classification: Sensitive** and create targeted policies, such as retention rules and quarantine actions. |

## Interactive demos

These click-through demos show how to perform actions step by step. Click the **Start Demo** button to begin. Then, click the **Next** button or use the **right arrow** key on your keyboard to proceed, and the **left arrow** key to go back. These demos may include screens from multiple features to illustrate the complete procedure.

### Data Tagging policy for SharePoint Online files

See how Securiti lets you create a Data Tagging policy to tag sensitive data discovered in Microsoft 365 SharePoint Online files, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/lqgtfmp2y78x?embed=inline)

## Using the Data Tagging Policies page

The Data Tagging Policies page lets you manage and analyze your Data Tagging policies:

- Use the top filters to view policies by the following properties:
  - Date Created
  - Data Modified
  - Policy ID
  - Policy Name
  - Owner
  - Status

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-A9Q56CHJ.png)
- Use the search bar to find a Data Tagging policy by its name, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-MMENMQ8D.png)
- View the total number of created policies and also the active policies out of them, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TT8BOTRT.png)
- Use the **Column Selector** to add or remove columns, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-L0CQA19L.png)
- Use the toggle to activate or deactivate the Data Tagging policy, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-T0NC5X1W.png)
- From the options menu (three dots) on the right side of a policy entry, you can **View**, **Edit**, **Clone**, **Delete** or **View Run History** of the policy, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ODS0QEXO.png)
