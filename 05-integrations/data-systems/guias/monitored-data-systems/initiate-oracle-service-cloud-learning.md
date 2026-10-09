---
title: "Configuring general scan settings for Oracle Service Cloud"
slug: "initiate-oracle-service-cloud-learning"
updated: 2026-08-11T11:41:25Z
published: 2026-08-11T11:41:25Z
canonical: "helpcenter.securiti.ai/initiate-oracle-service-cloud-learning"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring general scan settings for Oracle Service Cloud

This article covers the general scan settings supported features of Oracle Service Cloud after authenticating the connector with Securiti.

## Data Scan Policies

> [!NOTE]
> **Note**
> 
> Securiti supports classification scans for Oracle Service Cloud Self-hosted connector through Legacy Data Scan feature. Discovery scan is not supported for Oracle Service Cloud.

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

- After the connector finishes learning the tables and schemas, it redirects you to the **Table Training** tab.
- Perform Table training on the Oracle Service Cloud data system instance. For more information, see [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

## Breach Analysis

In the **Configuration** tab, under the **Breach** section, mark the **Breach Analysis** checkbox to initiate enhanced analysis for any reported incident for your data system and get an automated report for remediation.
