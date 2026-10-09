---
title: "Configuring Data Inventory Sync for Google Drive (Google Workspace) (Self-hosted)"
slug: "configuring-data-inventory-sync-for-g-suite-google-drive-self-hosted"
updated: 2026-08-31T09:02:47Z
published: 2026-08-31T09:02:47Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-g-suite-google-drive-self-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Google Drive (Google Workspace) (Self-hosted)

Securiti supports Data Inventory Sync and entitlement scanning for Google Drive (Google Workspace) (Self-hosted) data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For Gencore AI use cases, the scan builds an index of Entitlements to files for populating Gencore AI Pipelines.

For more information, see [Data Inventory Sync for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync and entitlement scanning for your Data system Instance from the **Inventory** tab, after the connector activation. Prior to the connector activation process, fulfill any required prerequisites as highlighted in the section below, for successful scanning.

### Prerequisites for configuring Data Inventory Sync for Google Drive (Google Workspace)

#### Permissions and enabling APIs

To run the Data Inventory Sync scan, add the following scope in the **OAuth scopes** section of your Google Workspace domain:

```plaintext
https://www.googleapis.com/auth/admin.directory.orgunit.readonly 
```

To enable Google Drive labels ingestion during the Data Inventory Sync, ensure the following prerequisites are fulfilled as described in [Prerequisites for Google Drive (Google Workspace) (Self-Hosted)](/latest/docs/prerequisites-for-g-suite-google-drive).

- You must use a Pod version of 1.120.0 or greater.
- In Google Cloud console, enable the **Drive Labels API**.
- Enable **Domain wide delegation** for your project.
- Provide the following scopes for your Google project:

```plaintext
https://www.googleapis.com/auth/drive.labels.readonly
https://www.googleapis.com/auth/drive.admin.labels.readonly
```

#### Enabling Drive & Docs service

You must enable the Drive & Docs service for the user who is used in the connector activation, as shown below.

![Admin settings for Google Drive and Docs, showing service status options for users.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/docs-n-drive-api.png)

#### Allowlisting APIs

Allowlist the following APIs between your deployed Securiti Pod and the Google Workspace APIs to run Data Inventory Sync successfully.

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://www.googleapis.com/drive/v3/files | Get drive items |
| 2 | GET | https://www.googleapis.com/drive/v3/files/{{folder_id}} | Get folder name |
| 3 | GET | https://www.googleapis.com/admin/directory/v1/groups/{{group_id}}/members | Get group members |
| 4 | GET | https://www.googleapis.com/admin/directory/v1/groups/{{group_id}} | Get group aliases |
| 5 | GET | https://www.googleapis.com/admin/directory/v1/customer/my_customer/orgunits | Get organization |
| 6 | GET | https://www.googleapis.com/admin/directory/v1/groups/ | Get Google Workspace domain groups |
| 7 | GET | https://www.googleapis.com/drive/v3/files/{{drive_id}}/Permissions | Get shared drive permission |
| 8 | GET | https://www.googleapis.com/admin/directory/v1/users | Get users within org |
| 9 | GET | https://www.googleapis.com/admin/directory/v1/users | Fetch Google Workspace domain user |
| 10 | GET | https://www.googleapis.com/admin/directory/v1/users | Get users |
| 11 | GET | https://www.googleapis.com/admin/directory/v1/groups/ | Get groups |
| 12 | GET | https://www.googleapis.com/admin/directory/v1/groups/{{group_id}}/members | Get group members |
| 13 | GET | https://www.googleapis.comdrive/v3/files/{{id}}/Permissions | Get Permissions |

### Configuring Data Inventory Sync

After activating the Google Drive (Google Workspace) (Self-hosted) Connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for Google Drive (Google Workspace).

1. On the **Inventory** tab, under the **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Google groups - Data inventory: Files and folders in My Drive and Shared Drives. Additionally, the Google Drive labels applied on files are also ingested as data inventory. |
| Run Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. This is used in Gencore AI pipelines | View Permissions on Google Drive files that are used to restrict prompt responses in our Gencore AI product. |
2. (Optional) In the **Inventory Scope** section on the same **Inventory Sync** section, select the collections of data resources to be included in your inventory.
  1. You can select either **Group(s)** or set the scope to **My Drive(s) and Shared Drive(s).**

> [!WARNING]
> **Important**
> 
> - When you scope a scan to specific groups, Securiti only scans shared drives that those users have access to. Scans configured for "All Groups" continue to process all shared drives in your organization. This ensures more efficient and relevant scan results.
> 
> Securiti does not scan any personal or shared drive if "None" is selected.
> - Securiti does not include suspended or archived Google Workspace user accounts in the scan scope, and files belonging to these accounts are not scanned. If such inaccessible files are encountered during processing and return Access Denied errors, Securiti skips them and continues processing the remaining accessible files without interruption.
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

To view scanned results, see [Visualizing Google Drive metadata in Data Command Graph](/latest/docs/visualizing-google-drive-metadata-in-data-command-graph).
