---
title: "Initiate Odoo ERP learning"
slug: "initiate-odoo-erp-learning"
updated: 2025-10-31T07:56:02Z
published: 2025-11-03T06:24:48Z
canonical: "helpcenter.securiti.ai/initiate-odoo-erp-learning"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Initiate Odoo ERP learning

After you configure the Odoo ERP Connector, configure its scan policy, then initiate Learning:

1. On the Connector tab, configure the Connector scan policy as follows:

Since your Odoo ERP users constantly add, edit, and delete files from their respective drives, the Securiti Connector must regularly rescan your Odoo ERP Data system to discover new and updated tables.

> [!NOTE]
> **Note**
> 
> You can change scan policy settings (if any) during a scan instead of waiting for the scan to complete. New changes take effect when the current scan finishes.
  - Mark the **Auto Scan** checkbox to enable automatic rescans of your Odoo ERP Data system Instance.
  - Mark the **Track Schema Changes Only** checkbox to configure the Connector to only look for Schema changes. If a new Table gets added, it learns that Table and any new columns added to existing tables. It isn't scanned if new data is inserted into one or more of the existing tables.
  - Use the **Scan Interval** tools to configure how often Securiti does the rescan.
2. Near the upper right corner of the page, click **Save** to save any scan policy changes.
3. Near the bottom of the Connector tab, click **Initiate Learning**.

Securiti scans your Odoo ERP Data system to learn its tables and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects.
4. Wait while the Connector transitions through the following states:

The Connector finishes Learning tables and schemas.
  - Scheduled for Learning
  - Learning Schemas

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
