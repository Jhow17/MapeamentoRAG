---
title: "Initiate Oracle ERP data scanning"
slug: "initiate-oracle-erp-learning"
updated: 2026-07-30T07:02:43Z
published: 2026-07-30T07:02:43Z
canonical: "helpcenter.securiti.ai/initiate-oracle-erp-learning"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Initiate Oracle ERP data scanning

> [!NOTE]
> Note
> 
> For Securiti-Cloud connectors, the first scheduled scan after activation must be initiated manually by clicking the Initiate Data Scan. This requirement does not apply to connector reconfigurations. After the initial scan, all subsequent scheduled scans run automatically according to the configured schedule.

After you configure the Oracle ERP Connector, configure its scan policy, then initiate Learning:

1. In the **Privacy** tab , configure the following settings for the Connector scan policy:

Since your Oracle ERP tables are constantly updated, the Securiti Connector must regularly rescan your Oracle ERP data system to discover new and updated tables..
  - Mark the **Auto Scan** checkbox to enable automatic re-scans of your Oracle ERP Data system Instance.
  - Mark the **Track Schema Changes Only** checkbox to configure the Connector to only look for Schema changes. If a new Table gets added, it learns that Table, and any new columns added to existing tables. If new data is inserted into one or more of the existing tables, it isn't scanned.
  - Use the **Scan Interval** tools to configure how often Securiti does the re-scan.
2. Near the upper right corner of the page, click **Save** to save any scan policy changes.
3. Near the bottom of the Connector tab, click **Initiate Learning**.

Securiti scans your Oracle ERP Data system to learn its tables and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects.
4. Wait while the Connector transitions through the following states:

After the Connector finishes Learning the tables and schemas, it redirects you to the Table Training tab.
  - Scheduled for Learning
  - Learning Schemas
5. Do Table training on the Oracle ERP Data system Instance described in [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
