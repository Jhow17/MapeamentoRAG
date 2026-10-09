---
title: "Configuring General scan settings for IBM Informix"
slug: "configure-ibm-informix-data-scanning"
updated: 2026-07-20T20:05:00Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/configure-ibm-informix-data-scanning"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring General scan settings for IBM Informix

This article covers the supported general scans settings for IBM Informix after authenticating the connector with Securiti.

## Data Scan Policies

> [!NOTE]
> **Note**
> 
> Securiti supports classification scans for IBM Informix Self-hosted connector through Legacy Data Scan feature. Discovery scan is not supported for IBM Informix.

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

Perform Table training on the IBM Informix data system instance as described in [Table training for structured and hybrid data systems](/latest/docs/table-training-for-structured-and-hybrid-data-systems).
