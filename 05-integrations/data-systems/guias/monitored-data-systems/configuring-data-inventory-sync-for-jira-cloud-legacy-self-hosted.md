---
title: "Configuring Data Inventory Sync for Jira Cloud Self-hosted"
slug: "configuring-data-inventory-sync-for-jira-cloud-legacy-self-hosted"
updated: 2026-08-31T09:13:41Z
published: 2026-08-31T09:13:41Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-jira-cloud-legacy-self-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Jira Cloud Self-hosted

Securiti supports Data Inventory Sync and entitlement scanning for Jira Cloud (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For Gencore AI use cases, the scan builds an index of Entitlements to files for populating Gencore AI Pipelines.

For more information, see [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync and entitlement scanning for your data system Instance after the connector activation. Prior to the connector activation process, fulfill any required prerequisites as highlighted in the [section below](/v1/docs/configuring-data-inventory-sync-for-zendesk-support-self-hosted), for successful scanning.

> [!NOTE]
> **Note**
> 
> No additional Permissions are required to run Data Inventory Sync and entitlement scans for Jira Cloud (Self-hosted) Connector.

### Prerequisites for running Data Inventory Sync for Jira Cloud

#### Allowlisting APIs for Data Inventory Sync

You must allowlist the following APIs between your deployed Securiti Pod and the Jira Cloud APIs to run the Data Inventory Sync successfully.

You can use the following URLs to allowlist APIs:

- **Default Base URL:** https://api.atlassian.com/ex/jira
- **Atlassian URL:** https://api.atlassian.com
- **Site URL:** https://{site_name}.atlassian.net

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://{site_name}.atlassian.net/_edge/tenant_info | Get Site ID |
| 2 | GET | https://api.atlassian.com/oauth/Token/accessible-resources | List accessible resources |
| 3 | GET | https://api.atlassian.com/ex/jira/$site_id/rest/api/2/project/search | Get paginated projects |
| 4 | GET | https://api.atlassian.com/ex/jira/$site_id/rest/api/2/search | Search for issues using JQL |
| 5 | GET | https://api.atlassian.com/ex/jira/$site_id/rest/api/2/issue/$issue_id | Get issue |
| 6 | GET | https://api.atlassian.com/ex/jira/$site_id/rest/api/2/issue/$issue_id/comment | Get comments |
| 7 | GET | https://api.atlassian.com/ex/jira/$site_id/rest/api/2/users/search | Find users |
| 8 | GET | https://api.atlassian.com/ex/jira/$site_id/rest/api/2/Permissions/check | Get bulk Permissions |

#### Configuring Data Inventory Sync

After authenticating the Jira Cloud (Self-hosted) Connector, wait until the scoping metadata is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan.

1. In the **Inventory** tab, under **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Jira Sites and Projects - Data inventory: All attachments as separate files and comments and description of an issue as a single file. |
| Run Gencore AI Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. This is used in Gencore AI pipelines | View Permissions on Jira Cloud files that are used to restrict prompt responses in our Gencore AI product. > [!NOTE] > **Note** > > Some users directly added to a Jira project may appear as entitled in the Entitlement Scan, even though they may not be able to view the project from the UI. This occurs because users can be added directly to projects without having visible access from the UI. |
2. (Optional) In the **Inventory Scope** section on the same **Inventory Sync** section, select the collections of data resources to be included in your inventory.

You can select the following scopes:
  - Jira
  - Sites

> [!NOTE]
> **Note**
> 
> For new connectors, the scope is selected "None" by default with Inventory Sync Options disabled. For existing connectors, you must reconfigure the Connector to add scopes.
3. Click **Save**
4. Click **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
5. To view the Scan statistics for Inventory and Entitlement scans, see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics)

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.

For more information on Jira Cloud metadata and properties, see [Viewing Jira Cloud metadata in Securiti](/v1/docs/viewing-jira-cloud-metadata-in-securiti).
