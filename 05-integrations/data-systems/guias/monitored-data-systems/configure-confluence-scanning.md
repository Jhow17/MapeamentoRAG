---
title: "Configure Confluence scanning"
slug: "configure-confluence-scanning"
updated: 2025-10-30T19:43:17Z
published: 2025-11-03T06:14:10Z
canonical: "helpcenter.securiti.ai/configure-confluence-scanning"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure Confluence scanning

After you configure the Confluence connector, Securiti scans your Confluence resources to discover your OUs, users, folder structures, and files. Securiti then scans the files to detect, classify, and link personal data to identities. Securiti uses this data to respond quickly to DSR requests submitted by data subjects whose personal data is in the files.

Since your Confluence users are constantly adding, editing, and deleting files, the Securiti connector must regularly rescan your Confluence data sources to discover new and updated files and update its internal inventory.

After configuring the connector, start an initial data scan:

- On the Permissions tab in the Data Scan Policies section, configure options to suit and click **Initiate Data Scan**.

![Confluence_initiate_data_scan.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-68739900-a7e8-2952-6eda-bb40ed02d127.png)

The connector discovers information about all contents within the Confluence data system(s), during which the state shows as “learning”. The connector re-learns this information after every scan interval before a rescan. Once it finishes the initial learning state, the status shows “learning complete”, and the connector waits for your input to scan all discovered drive contents using the default scan policy. By default, the Confluence connector scans once daily when prompted.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
