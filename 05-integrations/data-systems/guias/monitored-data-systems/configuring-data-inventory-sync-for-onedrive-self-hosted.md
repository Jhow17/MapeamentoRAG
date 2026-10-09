---
title: "Configuring Data Inventory Sync for OneDrive (self-hosted)"
slug: "configuring-data-inventory-sync-for-onedrive-self-hosted"
updated: 2026-08-31T09:20:23Z
published: 2026-08-31T09:20:23Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-onedrive-self-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for OneDrive (self-hosted)

Securiti supports Data Inventory Sync and entitlement scanning for Microsoft 365 OneDrive (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

For more information, see [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync and entitlement scanning for your Data system Instance, after the Connector Activation. Prior to the Connector Activation process, fulfill any required prerequisites as highlighted in the [section below](/v1/docs/configuring-data-inventory-sync-for-onedrive-self-hosted), for successful scanning.

#### Prerequisites for running Data Inventory Sync for OneDrive

#### Allowlisting APIs for Data Inventory Sync

You must allowlist the following APIs between your deployed Securiti Pod and the Microsoft APIs to successfully run the Data Inventory Sync.

Default URL is "https://graph.microsoft.com/"

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://graph.microsoft.com/v1.0/users/{{user_id}}/drive | Get drive |
| 2 | GET | https://graph.microsoft.com/v1.0/drives/{{drive_id}}/root/delta | Get drive delta |
| 3 | GET | https://graph.microsoft.com/v1.0/users | Get users |
| 4 | GET | https://graph.microsoft.com/v1.0/users/{{user_id}}/drive/items/{{file_id}}/content | Download file |
| 5 | GET | https://graph.microsoft.com/sites/{{site_id}}/drive | Get drive info by site ID |
| 6 | GET | https://graph.microsoft.com/users/{{user_id}}/drive/items/{{file_id}} | Get file |

#### MIP labels extraction for Microsoft 365 OneDrive

Microsoft Information Protection (MIP) labels are extracted during the Data Inventory Sync which can be viewed in the [Data Command Graph](/v1/docs/using-graph-explorer) module. See [Microsoft Information Protection (MIP) label extraction for data systems](/v1/docs/microsoft-information-protection-mip-label-extraction-for-data-systems), for more information.

For successful extraction of MIP labels, you must provide the following Permissions before Connector Activation process.

- **Files.Read.All**: To fetch classification labels per file.
- **InformationProtectionPolicy.Read.All**: To fetch all classification labels

#### Configuring Data Inventory Sync

After activating the OneDrive (Self-hosted) Connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for OneDrive.

1. In the **Inventory** tab, under the **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Microsoft 365 Groups - Data inventory: Files and folders for all personal (default) drives. |
| Run Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. | View Permissions on Microsoft 365 OneDrive files that are used to restrict prompt responses. |
2. (Optional) In the **Inventory Scope** section on the same **Inventory Sync** section, select the collections of data resources to be included in your inventory.

You can select the following scopes:

> [!WARNING]
> **Important**
> 
> Permissions granted through SiteGroups and members assigned via the old SharePoint personal site administration interface are not handled for OneDrive. This means that any Permissions set through these older methods may not be included in the Entitlement Scan results for OneDrive.
  - All
  - Group(s)
  - User(s)

> [!NOTE]
> **Note**
> 
> For new connectors, the scope is selected "None" by default with Inventory Sync Options disabled. For existing connectors, you must reconfigure the Connector to add scopes.

![OneDrive data inventory showing selected groups and execution options for syncing.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/onedrivescopes.png)
3. Click **Save**
4. Click **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)

To view the Scan statistics for Inventory and Entitlement scans, see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).

> [!WARNING]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.

## Fallback plan for owner’s field in Graph

Securiti manages displays owners' field for OneDrive files displayed in Data Command Graph and Unstructured Data Discovery results by following a structured fallback logic, especially when email addresses or display names are missing or incomplete.

- If the user creates a file:
  - Securiti first uses the user’s email address.
  - If the email is not available, it falls back to the user’s display name.
- If the system generates a file:
  - Securiti displays the application’s display name, since application-created files typically don't have an associated email.
  - If neither user nor application-generated details are available:
    - Securiti uses information from the drive owner:
      - First, it uses the drive owner’s email address.
      - If that is not available, it falls back to the drive owner’s display name.
