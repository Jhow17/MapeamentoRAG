---
title: "Microsoft Fabric FAQs"
slug: "microsoft-fabric-faqs"
updated: 2026-08-10T08:02:09Z
published: 2026-08-10T08:02:09Z
canonical: "helpcenter.securiti.ai/microsoft-fabric-faqs"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft Fabric FAQs

This article answers frequently asked questions about the Microsoft Fabric connector.

### Data processing

****Does Microsoft Fabric contain structured data?****

Yes. Microsoft Fabric contains structured data, such as tables.

****How does Securiti process Microsoft Fabric data?****

Although Microsoft Fabric includes structured data, the data is sourced and accessed through files. Because of this ingestion method, Securiti processes Microsoft Fabric data as unstructured data.

### Scan coverage

****What does the Fabric connector scan?****

The connector scans content in the **Files** folder of a Fabric Lakehouse. Securiti processes this content as unstructured data.

****What does the Fabric connector not scan?****

The connector does not scan the following Fabric content:

- Lakehouse Tables
- Warehouses
- Mirrored databases
- KQL databases (Eventhouse)
- Other Fabric item types, including notebooks, data pipelines, eventstreams, semantic models, reports, and dashboards

****Is my data in Lakehouse Tables scanned?****

Securiti does not scan content in the **Tables** folder directly. If a file was placed in the **Files** folder and later used to create a table, the connector scans the original file in the **Files** folder. **Table** content that was not created from a file in the **Files** folder is not scanned.

### Workspace access and permissions

****How does the connector find Lakehouses to scan?****

The connector scans workspaces where the Securiti service principal has been assigned a workspace role. Within each of those workspaces, it scans all Lakehouses, including Lakehouses organized in folders.

****I shared a single Lakehouse with Securiti, but it is not being scanned. Why?****

The connector finds Lakehouses through the workspaces the Securiti service principal can access at the workspace level. If a Lakehouse is shared only at the item level, without a workspace role, the connector does not find it. Assign the service principal a workspace role so the connector can scan the Lakehouse. For more information, see [Microsoft's guidance on workspace roles](https://learn.microsoft.com/en-us/fabric/fundamentals/roles-workspaces).

****Which permissions should I grant?****

Assign the Securiti service principal a workspace role on each workspace you want scanned, and confirm access to the Files folder of the Lakehouse. Grant access based on the location of the data you want scanned.
