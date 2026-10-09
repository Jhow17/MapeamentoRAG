---
title: "Initiate Salesforce Marketing Cloud (SOAP + REST) learning"
slug: "initiate-salesforce-marketing-cloud-soap-rest-learning"
updated: 2025-10-31T07:08:43Z
published: 2025-11-03T07:32:35Z
canonical: "helpcenter.securiti.ai/initiate-salesforce-marketing-cloud-soap-rest-learning"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Initiate Salesforce Marketing Cloud (SOAP + REST) learning

After you configure the Salesforce Marketing Cloud (REST + SOAP) Cloud connectors, configure its scan policy, then initiate the Data scan:

1. On the **Connector** tab, configure the Connector Data scan policy as follows:

Since your Salesforce Marketing Cloud users are constantly adding, editing, and deleting files from their respective drives, the Securiti Connector must regularly rescan your Salesforce Marketing Cloud Data system to discover new and updated tables.

> [!NOTE]
> **Note**
> 
> You can change scan policy settings (if any) during a scan instead of waiting for the scan to complete. New changes take effect when the current scan finishes.
  - Mark the **Auto Scan** checkbox to enable automatic re-scans of your Salesforce Marketing Cloud (REST + SOAP) Data system Instance.
  - Use the **Scan Interval** tools to configure how often Securiti does the re-scan.
  - Mark the **Disable Scanning** checkbox to specify the **From** and **To** values for the interval in which you want to skip scanning.
2. Near the upper right corner of the page, click **Save** to save any scan policy changes.
3. Near the bottom of the **Permissions** tab, click **Initiate Data scan**.

Securiti scans your Salesforce Marketing Cloud (REST + SOAP) Data system to learn its tables and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects. For more information, see [Supported tables for Salesforce Marketing Cloud learning](/v1/docs/supported-tables-for-salesforce-marketing-cloud-learning).

> [!NOTE]
> **Note**
> 
> Securiti supports a specific set of tables for Salesforce Marketing Cloud (REST and SOAP) data systems while Learning. During the Learning phase, the following tables get skipped and return the error “*Internal server error*”:
> 
> - DataExtensionObject__MobileAddress
> - DataExtensionObject__MobileSubscription
> - DataExtensionObject__MobileLineProfileAttribute
4. Wait while the Connector transitions through the following states:

After the Connector finishes Learning the tables and schemas, it redirects you to the Table Training tab.
  - Scheduled for Learning
  - Learning Schemas
5. Do Table training on the Salesforce Marketing Cloud Data system Instance described in [Table training for structured and hybrid data systems](/v1/docs/table-training-for-structured-and-hybrid-data-systems).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
