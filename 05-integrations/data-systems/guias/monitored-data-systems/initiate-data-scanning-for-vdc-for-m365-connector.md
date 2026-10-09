---
title: "Initiate data scanning for VDC for M365 connector"
slug: "initiate-data-scanning-for-vdc-for-m365-connector"
updated: 2026-06-22T09:52:57Z
published: 2026-06-22T09:52:57Z
canonical: "helpcenter.securiti.ai/initiate-data-scanning-for-vdc-for-m365-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Initiate data scanning for VDC for M365 connector

Once you successfully authenticate and activate the Veeam Data Cloud connector, it syncs a list of tenants available in your VDC organization.

To initate the data scanning, perform the following steps:

1. On the **VDC Tenant Mapping** page, in the **Tenant** menu, select the VDC tenant you want to onboard for scanning.
2. Click **Save**.
3. Open the Integration page, and under the “Initiate Data Scan” section, click **Initiate Sync** It takes time to complete the data scanning.
  - Once data scanning is complete, it fetches all restore points and data backup objects avaialble in your VDC tenant.
4. The inventory of all of the restore points and backup objects can be viewed in data command graph. Once data scanning is complete, you can explore the backup objects and restore points in the Data Command Graph. For more information, see [Viewing VDC data in Data Command Graph](/latest/docs/viewing-vdc-data-in-data-command-graph).
