---
title: "Initiate Salesforce data scanning"
slug: "initiate-salesforce-data-scanning"
updated: 2026-03-10T05:54:07Z
published: 2026-03-10T05:54:07Z
canonical: "helpcenter.securiti.ai/initiate-salesforce-data-scanning"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Initiate Salesforce data scanning

> [!NOTE]
> Note
> 
> For Securiti-Cloud connectors, the first scheduled scan after activation must be initiated manually by clicking the Initiate Data Scan. This requirement does not apply to connector reconfigurations. After the initial scan, all subsequent scheduled scans run automatically according to the configured schedule.

After you configure the Salesforce Cloud Connector, configure its scan policy, then initiate Data scan:

1. On the **Permissions** tab, configure the Connector scan policy as follows:

Since your Salesforce users are constantly adding, editing, and deleting files from their respective drives, the Securiti Connector must regularly rescan your Salesforce Data system to discover new and updated tables.

> [!NOTE]
> **Note**
> 
> You can change scan policy settings (if any) during a scan instead of waiting for the scan to complete. New changes take effect when the current scan finishes.
  - Mark the **Auto Scan** checkbox to enable automatic re-scans of your Salesforce Data system Instance.

> [!WARNING]
> **Important**
> 
> **Auto Scan** begins automatically after completing the initial manual scan triggered by clicking **Initiate Data scan**. Ensure the first scan is fully completed to verify if the Auto Scan feature is functioning as expected.
  - Use the **Scan Interval** tools to configure how often Securiti does the re-scan.
  - Mark the **Disable Scanning** checkbox to specify the **From** and **To** values for the interval in which you want to skip scanning.
2. Near the upper right corner of the page, click **Save** to save any scan policy changes.
3. Near the bottom of the **Connector** tab, click **Initiate Data scan**.

Securiti scans your Salesforce Data system to learn its tables and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects.
4. Wait while the Connector transitions through the following states:

After the Connector finishes Learning the tables and schemas, it redirects you to the **Table Training** tab.
  - Scheduled for Learning
  - Learning Schemas
5. Do Table training on the Salesforce Data system Instance as described in [Table training for structured and hybrid data systems](/v1/docs/table-training-for-structured-and-hybrid-data-systems).
