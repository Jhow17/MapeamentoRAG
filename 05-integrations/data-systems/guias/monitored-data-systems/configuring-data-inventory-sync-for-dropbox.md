---
title: "Configuring Data Inventory Sync for Dropbox"
slug: "configuring-data-inventory-sync-for-dropbox"
updated: 2026-08-31T08:51:42Z
published: 2026-08-31T08:51:42Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-dropbox"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Dropbox

Securiti supports Data Inventory Sync and entitlement scanning for Dropbox (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

For more information, see [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync and entitlement scanning for your Data system Instance, after the Connector Activation. Prior to the Connector Activation process, fulfill any required prerequisites as highlighted in the [section below](/v1/docs/configuring-data-inventory-sync-for-zendesk-support-self-hosted), for successful scanning.

### Prerequisites for running Data Inventory Sync for Dropbox

#### Allowlisting APIs for Data Inventory Sync

You must allowlist the following APIs between your deployed Securiti Pod and Dropbox APIs to successfully run the Data Inventory Sync.

Following are the base URLs:

- **Default URL**: "https://api.dropboxapi.com"
- **Content URL:** "https://content.dropboxapi.com"
- **Preview URL:** "https://www.dropbox.com/home"
- **Paper URL**: "https://paper.dropbox.com/doc/"

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://api.dropboxapi.com/2/team/Token/get_authenticated_admin | Get Dropbox admin |
| 2 | GET | https://api.dropboxapi.com/2/team/members/list | Get team members list |
| 3 | GET | https://api.dropboxapi.com/2/team/members/list/continue | Get team members list continue |
| 4 | GET | https://api.dropboxapi.com/2/team/groups/list | Get groups |
| 5 | GET | https://api.dropboxapi.com/2/team/get_info | Get team info |
| 6 | GET | https://api.dropboxapi.com/2/team/groups/list/continue | Get groups continue |
| 7 | GET | https://api.dropboxapi.com/2/files/list_folder | Get folders |
| 8 | GET | https://api.dropboxapi.com/2/files/list_folder/continue | Get folders continue |
| 9 | GET | https://api.dropboxapi.com/2/team/team_folder/list | Get team folders |
| 10 | GET | https://api.dropboxapi.com/2/team/team_folder/list/continue | Get team folders continue |
| 11 | GET | https://api.dropboxapi.com/2/sharing/list_mountable_folders | Get shared folders |
| 12 | GET | https://api.dropboxapi.com/2/sharing/list_mountable_folders/continue | Get shared folders continue |
| 13 | GET | https://api.dropboxapi.com/2/files/get_metadata | Get file metadata |
| 14 | GET | https://api.dropboxapi.com/2/sharing/get_folder_metadata | Check if folder is team folder |
| 15 | GET | https://api.dropboxapi.com/2/team/Token/get_authenticated_admin | Get admin id |
| 16 | GET | https://api.dropboxapi.com/2/files/download | Download a file |
| 17 | GET | https://api.dropboxapi.com/2/files/export | Export a file |
| 18 | GET | https://api.dropboxapi.com/2/sharing/list_shared_links | Get shared links |
| 19 | GET | https://api.dropboxapi.com/2/sharing/list_file_members | List file members |
| 20 | GET | https://api.dropboxapi.com/2/sharing/list_file_members/continue | List file members continue |
| 21 | GET | https://api.dropboxapi.com/2/sharing/list_folder_members | List folder members |
| 22 | GET | https://api.dropboxapi.com/2/sharing/list_folder_members/continue | List folder members continue |

### Configuring Data Inventory Sync

After activating the Dropbox (Self-hosted) Connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for Dropbox.

1. In the **Inventory** tab, in the **Inventory Sync** section, enable the following settings to suit.

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Dropbox groups - Data inventory: All Files and Folders in Personal, Shared, and Team folders |
| Run Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. | View Permissions on Dropbox files used to restrict prompt responses. |
2. (Optional) In the **Inventory Scope** section on the same **Inventory Sync** tab, select the collections of data resources to be included in your inventory.

![Data inventory settings showing selected groups and sync options for Dropbox integration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dropboxscopes.png)
3. Click **Save.**
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
