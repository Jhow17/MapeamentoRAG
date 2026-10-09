---
title: "Initiate Azure Synapse learning"
slug: "initiate-azure-synapse-learning"
updated: 2026-07-02T20:42:29Z
published: 2026-07-02T20:42:29Z
canonical: "helpcenter.securiti.ai/initiate-azure-synapse-learning"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Initiate Azure Synapse learning

This article covers the general scan settings and supported features of Azure Synapse after authenticating the connector with Securiti.

## Data Scan Policies

If you constantly add, edit, and delete files from their respective drives, the Securiti Connector must regularly rescan your data systems to discover new and updated files.

1. To discover new and updated files, on the **General** tab, under the **Data Scan Policies** section, configure the following settings :

> [!NOTE]
> Note
> 
> You can change scan policy settings (if any) during a scan instead of waiting for the scan to complete. New changes take effect when the current scan finishes.
2. Apply the following settings under Data Scan Policies section:

| Setting | Description |
| --- | --- |
| **Auto Scan** | Mark the **Auto Scan** checkbox to enable automatic re-scans of your data systems Instance. |
| **Scan Interval** | Use the **Scan Interval** tools to configure how often Securiti does the re-scan. It gives the following options: - Day - Week - Month |
3. Once you have updated the configurations, click **Initiate Data Scan** or **Save**. Wait while the connector transitions through the data scanning states.

> [!NOTE]
> **Note**
> 
> To perform table training on the Azure Synapse data system instance, you must establish connectivity by enabling firewalls and NSG (Network Security Groups) to allow access on ports **1433** and **11000–11999**.

After the connector finishes learning the tables and schemas, it redirects you to the **Table Training** tab.

Do table training on the Azure Synapse data system instance as described in [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
