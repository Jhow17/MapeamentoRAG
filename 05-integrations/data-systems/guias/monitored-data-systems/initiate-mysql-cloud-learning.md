---
title: "Initiate MySQL Cloud learning"
slug: "initiate-mysql-cloud-learning"
updated: 2026-03-25T09:18:16Z
published: 2026-03-25T09:18:16Z
canonical: "helpcenter.securiti.ai/initiate-mysql-cloud-learning"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Initiate MySQL Cloud learning

> [!NOTE]
> Note
> 
> For Securiti-Cloud connectors, the first scheduled scan after activation must be initiated manually by clicking the Initiate Data Scan. This requirement does not apply to connector reconfigurations. After the initial scan, all subsequent scheduled scans run automatically according to the configured schedule.

After you configure the MySQL Connector, configure its scan policy, then initiate Learning:

1. On the **Permissions** tab, configure the Connector scan policy as follows:

Since your MySQL users are constantly adding, editing, and deleting files from their respective drives, the Securiti Connector must regularly rescan your MySQL Data system to discover new and updated tables.

> [!NOTE]
> **Note**
> 
> You can change scan policy settings (if any) during a scan instead of waiting for the scan to complete. New changes take effect when the current scan finishes.
  - Mark the **Auto Scan** checkbox to enable automatic re-scans of your MySQL Data system Instance.
  - Mark the **Track Schema Changes Only** checkbox to configure the Connector to only look for Schema changes. If a new Table gets added, it will learn that Table, and it will learn any new columns added to existing tables. But, if new data is inserted into one or more of the existing tables, that data won't be scanned.
  - Use the **Scan Interval** tools to configure how often Securiti does the re-scan.
2. Near the upper right corner of the page, click **Save** to save any scan policy changes.
3. Near the bottom of the Connector tab, click **Initiate Learning**.

Securiti scans your MySQL Data system to learn its tables and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects.
4. Wait while the Connector transitions through the following states:

After the Connector finishes Learning the tables and schemas, it redirects you to the Table Training tab.

In cases where the Connector or Pod encounters an error during the Learning process, you can click the **Retry Learning** link, as shown below.

![SQL-Retry-Learning.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aff069cd-9577-e329-a9a3-adc080692511(2).png)

Use the subsequent popup to configure whether or not to discard the current Table training data.
  - Scheduled for Learning
  - Learning Schemas
5. Do Table training on the MySQL Data system Instance as described in [Table training for structured and hybrid data systems](/v1/docs/table-training-for-structured-and-hybrid-data-systems).
