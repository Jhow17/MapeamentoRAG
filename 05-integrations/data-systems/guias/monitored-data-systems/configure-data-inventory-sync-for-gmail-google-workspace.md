---
title: "Configure Data Inventory Sync for Gmail (Google Workspace)"
slug: "configure-data-inventory-sync-for-gmail-google-workspace"
updated: 2026-08-31T08:59:40Z
published: 2026-08-31T08:59:40Z
canonical: "helpcenter.securiti.ai/configure-data-inventory-sync-for-gmail-google-workspace"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure Data Inventory Sync for Gmail (Google Workspace)

Securiti supports data inventory sync and entitlement scanning for Configure discovery scans in Gmail (Google Workspace) (self-hosted) data system connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For Gencore AI use cases, the scan builds an index of Entitlements to files for populating Gencore AI Pipelines.

For more information, see [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure data inventory sync and entitlement scanning for your data system instance, after the connector activation. Prior to the connector activation process, fulfill any required prerequisites as highlighted in the [section below](/v1/docs/configuring-data-inventory-sync-for-zendesk-support-self-hosted), for successful scanning.

### Prerequisites for running Data Inventory Sync for Gmail (Google Workspace)

#### Permissions required for Gmail (Google Workspace) Data Inventory Sync

You must configure the required OAuth scopes in [Prerequisites and obtaining authentication credentials for Gmail (Self-hosted)](/latest/docs/prerequisites-and-obtaining-authentication-credentials-in-google-apps) for running Data Inventory sync on Gmail (Google Workspace) data system instance

#### Allowlisting APIs for Data Inventory Sync

You must allowlist the following APIs between your deployed Securiti pod and the Gmail (Google Workspace) APIs to successfully run the Data Inventory Sync. For more information on complete list of APIs, see [Allowlisting URLs and APIs for scanning Gmail (Google Workspace)](/latest/docs/allowlisting-urls-and-apis-for-scanning-gmail-google-workspace).

### Configure Data Inventory Sync for Gmail (Google Workspace)

After activating the Gmail (Google Workspace) connector, wait until the discovery scan meta is synced.

Perform the following steps to run the Data Inventory Sync and entitlement scan for Gmail (Google Workspace).

1. In the **Inventory** tab, under the **Data Inventory Sync**, configure the following settings:
  1. On the **Data Inventory Sync** page, mark the **Enable Inventory Sync** checkbox to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources.
  2. Under the **Enable Inventory Sync**, click **Show More Options**, and mark the **Run Entitlement Scan** checkbox.

Enable the toggle to sync the entitlement metadata for the discovered resources. This is used in Gencore AI pipelines

| Scan setting | Type of data scanned |
| --- | --- |
| Enable Data Inventory Sync | - Scoping inventory: Domains and Groups - Data inventory: Message content and Attachments |
| Run Entitlement Scan | View Permissions on Gmail (Google Workspace) files that are used to restrict prompt responses in our Gencore AI product. |
2. (Optional) In the **Data Inventory Sync and Gencore Entitlements Scope** section on the same **Inventory** tab, select the collections of data resources to be included in your inventory.

You can select the following scopes:
  - Domains
  - Groups
3. Click **Save**
4. Click **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
5. To view the Scan statistics for Inventory and Entitlement scans:

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.

For more information on Scan statistics, see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).
