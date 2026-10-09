---
title: "Configuring Data Inventory Sync for Slack Enterprise Grid"
slug: "configuring-data-inventory-sync-for-slack-enterprise-grid"
updated: 2026-08-31T09:55:54Z
published: 2026-08-31T09:55:54Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-slack-enterprise-grid"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Slack Enterprise Grid

Securiti supports Data Inventory Sync and entitlement scanning for Slack Enterprise Grid (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For Gencore AI use cases, the scan builds an index of Entitlements to files for populating Gencore AI Pipelines.

For more information, see [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors).

> [!NOTE]
> **Note**
> 
> Securiti uses the same scopes for Data Inventory Sync and Entitlement Scanning in Slack Enterprise Grid as those required for Discovery Scans.

#### Configuring Data Inventory Sync

After activating the Slack Enterprise Grid (Self-hosted) Connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan.

1. On the **Connector** tab, in the **Inventory Sync Options** section, enable the following settings to suit.

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Slack Workspaces and channels - Data inventory: Channel conversations and attachments |
| Run Gencore AI Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. This is used in Gencore AI pipelines | View Permissions on Slack files used to restrict prompt responses in our Gencore AI product. |
2. (Optional) In the **Data Inventory and Entitlement Sync Scope** section on the same **Connector** tab, select the collections of data resources to be included in your inventory.

![Data inventory setup for Slack workspace and channel selection process displayed on screen.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/slackscopes.png)
3. Click **Save**
4. Click **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
5. To view the Scan statistics for Inventory and Entitlement scans, see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.
