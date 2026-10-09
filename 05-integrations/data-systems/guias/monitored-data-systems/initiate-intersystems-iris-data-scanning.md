---
title: "Configuring General scan settings for InterSystems IRIS"
slug: "initiate-intersystems-iris-data-scanning"
updated: 2026-07-01T15:20:42Z
published: 2026-07-01T15:20:42Z
canonical: "helpcenter.securiti.ai/initiate-intersystems-iris-data-scanning"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring General scan settings for InterSystems IRIS

This article covers the General scans settings supported features of InterSystems IRIS after authenticating the connector with Securiti.

## Data Scan Policies

> [!NOTE]
> **Note**
> 
> Securiti supports classification scans for InterSystems IRIS Self-hosted connector through Legacy Data Scan feature. Discovery scan is not supported for InterSystems IRIS.

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

After the connector finishes learning the tables and schemas, it redirects you to the **Table Training** tab.

Do Table training on the Salesforce Data system Instance as described in [Table training for structured and hybrid data systems](/v1/docs/table-training-for-structured-and-hybrid-data-systems).
