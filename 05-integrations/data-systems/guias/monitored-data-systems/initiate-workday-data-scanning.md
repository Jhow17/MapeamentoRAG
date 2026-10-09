---
title: "Initiate Workday data scanning"
slug: "initiate-workday-data-scanning"
updated: 2026-08-05T11:21:11Z
published: 2026-08-05T11:21:11Z
canonical: "helpcenter.securiti.ai/initiate-workday-data-scanning"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Initiate Workday data scanning

> [!NOTE]
> Note
> 
> For Securiti-Cloud connectors, the first scheduled scan after activation must be initiated manually by clicking the Initiate Data Scan. This requirement does not apply to connector reconfigurations. After the initial scan, all subsequent scheduled scans run automatically according to the configured schedule.

1. On the **Permissions** tab, configure the Connector scan policy as follows:

Since your Workday users are constantly adding, editing, and deleting files from their respective drives, the Securiti Connector must regularly rescan your Workday Data system to discover new and updated tables.

> [!NOTE]
> **Note**
> 
> You can change scan policy settings (if any) during a scan instead of waiting for the scan to complete. New changes take effect when the current scan finishes.
  - Mark the **Auto Scan** checkbox to enable automatic re-scans of your Workday Data system Instance.
  - Mark the **Track Schema Changes Only** checkbox to configure the Connector to only look for Schema changes. If a new Table gets added, it will learn that Table, and it will learn any new columns added to existing tables. But, if new data is inserted into one or more of existing tables, that data won't be scanned.
  - Use the **Scan Interval** tools to configure how often Securiti does the re-scan.
2. Near the upper right corner of the page, click **Save** to save any scan policy changes.
3. Near the bottom of the Connector tab, click **Initiate Data Scanning**.

Securiti scans your Workday Data system to learn its tables and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects.
4. Wait while the Connector transitions through the following states:

After the Connector finishes Learning the tables and schemas, it redirects you to the Table Training tab.
  - Scheduled for Learning
  - Learning Schemas
5. Do Table training on the Workday Data system Instance as described in [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
