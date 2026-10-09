---
title: "Initiate Tableau Cloud data scanning"
slug: "initiate-tableau-cloud-data-scanning"
updated: 2026-03-10T07:51:22Z
published: 2026-03-10T07:51:22Z
canonical: "helpcenter.securiti.ai/initiate-tableau-cloud-data-scanning"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Initiate Tableau Cloud data scanning

> [!NOTE]
> Note
> 
> For Securiti-Cloud connectors, the first scheduled scan after activation must be initiated manually by clicking the Initiate Data Scan. This requirement does not apply to connector reconfigurations. After the initial scan, all subsequent scheduled scans run automatically according to the configured schedule.

After you configure the Tableau Cloud Connector, configure its scan policy, then initiate data scanning:

1. On the **Permisions** tab, configure the Connector scan policy as follows:

Since your Tableau users are constantly adding, editing, and deleting files from their respective drives, the Securiti Connector must regularly rescan your Tableau Data system to discover the new and updated user Table.

> [!NOTE]
> **Note**
> 
> You can change scan policy settings (if any) during a scan instead of waiting for the scan to complete. New changes take effect when the current scan finishes.
  - Mark the **Auto Scan** checkbox to enable automatic re-scans of your Tableau Data system Instance.
  - Mark the **Track Schema Changes Only** checkbox to configure the Connector to only look for Schema changes. If a new user Table gets added, it will learn that Table, and it will learn any new columns added to it. But, if new data is inserted into the existing Table, that data won't be scanned.
  - Use the **Scan Interval** tools to configure how often Securiti does the re-scan.
2. Near the upper right corner of the page, click **Save** to save any scan policy changes.
3. Near the bottom of the Connector tab, click **Initiate Data scan**.

Securiti scans your Tableau Data system to learn the user Table and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects.
4. Wait while the Connector transitions through the following states:

After the Connector finishes Learning the user Table and schemas, it redirects you to the Table Training tab.

In cases where the Connector or Pod encounters an error during the Learning process, you can click the **Retry Learning** link.

Use the subsequent popup to configure whether or not to discard the current Table training data.
  - Scheduled for Learning
  - Learning Schemas
5. Do Table training on the Tableau Data system Instance as described in [Table training for structured and hybrid data systems](/v1/docs/table-training-for-structured-and-hybrid-data-systems).
