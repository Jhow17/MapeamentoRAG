---
title: "Data Access Governance release notes"
slug: "data-access-governance-release-notes"
updated: 2026-09-23T05:39:48Z
published: 2026-09-23T05:39:48Z
canonical: "helpcenter.securiti.ai/data-access-governance-release-notes"
area: dspm
modulo: data-access-governance
tipo: release
data_captura: 2026-10-06
---

# Data Access Governance release notes

## 1.151

### Release updates - September 2026

No updates

---

## 1.150

### Release updates - August 2026

#### Introducing Role Collection node in Data Command Graph

Securiti now resolves Snowflake Role hierarchies in an optimized fashion in **Data Command Graph** to present the results faster. Securiti has added a new Role Collection node for every Role in the graph. It encapsulates all the Roles that the associated Role can in turn assume, by providing precomputed relationships to all the inherited Roles. The **Role** and **User Principal** nodes in the graph now connect to the Role Collection nodes. This connection lets you query inherited Roles and their associated grants and privileges faster from the respective nodes. Use this node only in queries where inherited roles are necessary to obtain the complete access picture.

In conjunction with this addition, Securiti has modified the behavior for recursion on Role nodes. When traversing into and out of a Snowflake Role node, the query no longer applies recursion to fetch connected Roles in the hierarchy. It only fetches the directly connected Role nodes. Use the Role Collection node if you want a **listing of all the roles** in the hierarchy.

> [!NOTE]
> Note
> 
> Search is not supported for Role Collection nodes in this release. Access these nodes by traversing from a connected Role or User Principal node.

The new **Role Collection** node requires a new access scan to run.

> [!NOTE]
> **Note**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements.

For more information, see [Data Access Governance for Snowflake](/latest/docs/data-access-governance-snowflake).

---

## 1.149

### Release updates - August 2026

No updates

---

## 1.148

### Release updates - July 2026

No updates

---

## 1.147

### Release updates - June 2026

#### Updating the graph schema for non-hyperdrive SharePoint Access Intelligence

To improve the performance of scan normalization and graph queries, Securiti has updated the graph schema for non-hyperdrive SharePoint Access Intelligence. Securiti has replaced the **Policy Element** and **Resource Scope** graph nodes with the **Resource Access Node**. This update also introduces **Sharing Link Resource Access Node**, which replaces the **Sharing Link Node**.

To adopt the new model, contact your Customer Success Manager or Account Representative to apply the required tenant configuration change. Once applied, complete the following steps:

1. Reset your Access Scan Definitions and wait for the reset to complete.
2. Execute the scan using the Access Scan Definition.

Your existing access scans continue to work if you do not reconfigure your tenant.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

For more information, see [Data Access Governance for Sharepoint Online](/latest/docs/microsoft-365-sharepoint-online).

  

#### Configuring Access Scan Definitions scope using Discovery Scans for M365 SharePoint Online

Securiti now lets you scope **SharePoint Sites** for access scans directly from the Access Scan Definition (ASD) page. While creating an ASD for **SharePoint Online (Self-Hosted)**, navigate to **Privilege Analysis Configuration** and select one or more discovery scans from the **Site Selection** based on **Discovery Scans** field. The dropdown shows only discovery scans that match the ASD's provider type.

Securiti uses the selected scan IDs to limit the access scan to the relevant **SharePoint Online (Self-Hosted)** sites. If you do not select a discovery scan, Securiti scans all top-level **SharePoint** **Sites** by default. This lets you define and control the scope of each scan more efficiently.

For more information, see [Data Access Governance for Sharepoint Online](/latest/docs/microsoft-365-sharepoint-online).

---
