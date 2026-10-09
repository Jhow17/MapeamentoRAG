---
title: "Configuring Data Inventory Sync for SharePoint Online (Self-hosted)"
slug: "configuring-data-inventory-sync-for-sharepoint-online-self-hosted"
updated: 2026-09-14T08:12:56Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-sharepoint-online-self-hosted"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for SharePoint Online (Self-hosted)

Securiti supports Data Inventory Sync and entitlement scanning for SharePoint Online (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

For more information, see [Data Inventory Sync for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync and Entitlement scanning for your Data system Instance, after the Connector Activation. Prior to the Connector Activation process, fulfill any required prerequisites as highlighted in the [Prerequisites section for Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors), for successful scanning.

#### Prerequisites for configuring Data Inventory Sync for SharePoint Online

#### Permissions required for SharePoint Data Inventory Sync

> [!WARNING]
> **Important**
> 
> You must activate your connector with **Certificate Thumbprint** and **Private Key** for Data Inventory Sync results to show in [Data Command Graph](/v1/docs/using-data-command-graph). For more information, see [Connecting Microsoft 365 SharePoint Online (Self-hosted) with Securiti](/latest/docs/new-ui-connecting-microsoft-365-sharepoint-online-self-hosted-with-securiti).

- **Microsoft Graph API Permissions**
  - User.Read.All: This permission is required for discovering metadata for SharePoint users and their entitlements during the Data Inventory Sync and entitlement scans.
  - Directory.Read.All: This permission is required for discovering metadata for SharePoint directories during the Data Inventory Sync.
- **SharePoint API Permission**
  - Sites.FullControl.All: This permission provides access to SharePoint sites and their entitlements to be used in Gencore AI pipelines.
  - Sites.Read.All: This permission lets Securiti read the sharing settings for the Sharepoint sites. SharePoint sites and hubsites do not show in the Data Command Graph correctly if this permission is not configured.

> [!NOTE]
> **Note**
> 
> This permission is different from the **Sites.Read.All** Graph API permission.
- **Permissions required for MIP labels extraction**

For successful extraction of MIP labels, you must provide the following Permissions before the Connector Activation process.
  - **Files.Read.All**: This permission is required to fetch classification labels per file.
  - **InformationProtectionPolicy.Read.All**: This permission is required to fetch all classification labels

#### Allowlist APIs for SharePoint Online

You must allowlist the following APIs between your deployed Securiti Pod and the Microsoft Graph and Sharepoint APIs, to successfully run the Data Inventory Sync for SharePoint Online.

Default Graph URL is `https://graph.microsoft.com/`

Default SharePoint site URL is `https://{tenant}.sharepoint.com/`

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://graph.microsoft.com/v1.0/sites/$collection/sites | Get all sites for collection |
| 2 | GET | https://graph.microsoft.com/v1.0/sites/$site_id/drives | Get all site drives |
| 3 | GET | https://graph.microsoft.com/v1.0/sites | Get all sites |
| 4 | GET | https://graph.microsoft.com/v1.0/drives/$drive_id/root/delta | Get SharePoint drive delta |
| 5 | GET | https://graph.microsoft.com/v1.0/sites/$site_id | Get site meta |
| 6 | GET | https://graph.microsoft.com/v1.0/drives/$drive_id | Get drive meta |
| 7 | GET | https://graph.microsoft.com/v1.0/drives/$drive_id/root:/$folder_encoded_path:/children | Get configured folders data |
| 8 | GET | https://graph.microsoft.com/v1.0/drives/$drive_id/items/$item_id/children | Get folder content per drive |
| 9 | GET | https://{tenant}.sharepoint.com/_api/Web/SiteGroups | Get site groups |
| 10 | GET | https://{tenant}.sharepoint.com/_api/HubSites | List Hubsites |
| 11 | GET | https://{tenant}.sharepoint.com/_api/search/query | List Hub Linked Sites |
| 12 | GET | https://{tenant}.sharepoint.com/_api/SPO.Tenant/sites('$site_id') | Get Site Properties |

#### MIP labels extraction for Microsoft 365 SharePoint Online

Microsoft Information Protection (MIP) labels are extracted during the Data Inventory Sync which can be viewed in the [Data Command Graph](/latest/docs/using-graph-explorer) module. For more information, see [Microsoft Information Protection (MIP) label extraction for data systems](/latest/docs/microsoft-information-protection-mip-label-extraction-for-data-systems).

#### Configuring Data Inventory Sync

After activating the SharePoint Online (Self-hosted) Connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for SharePoint Online.

> [!WARNING]
> Important
> 
> Securiti does not support entitlement scans for OAuth (Client ID + Secret) based Authentication. Without providing a Certificate and Private key, metadata scan fails and an audit trail is generated if Entitlement Scan is enabled.

1. In the **Inventory** tab, under **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Mark the checkbox to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: SharePoint Sites and libraries. - Data inventory: All Files and Folders for all scoped document libraries and/or sites. > [!NOTE] > Note > > Data Inventory Sync doesn’t process SharePoint Online locked or blocked sites for any Securiti module. |
| Run Entitlement Scan | Mark the checkbox to sync the entitlement metadata for the discovered resources. | View Permissions on Microsoft 365 SharePoint Online files that are used to restrict prompt responses in our Gencore product. |
| Include System libraries | Mark the checkbox to Include System Libraries to sync the system-managed libraries in your SharePoint sites. | Include Style Library, Master Page Gallery, and Form Templates. |
2. (Optional) In the **Inventory Scope** section on the same **Inventory Sync** section, select the collections of data resources to be included in your inventory.

You can select the following scopes:
  - All
  - Group(s)
  - User(s)

> [!NOTE]
> **Note**
> 
> For new connectors, the scope is selected "None" by default with Inventory Sync Options disabled. For existing connectors, you must reconfigure the Connector to add scopes.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/SharePoint DS.png)
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

> [!WARNING]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.

> [!NOTE]
> **Note**
> 
> Securiti displays owners' field for SharePoint Online files displayed in **Data Command Graph** and **Unstructured Data Discovery** results by following a structured fallback logic, especially when email addresses or display names are missing or incomplete.
> 
> - If the user creates a file:
>   - Securiti first uses the user’s email address.
>   - If the email is not available, it falls back to the user’s display name.
> - If the system generates a file:
>   - Securiti displays the application’s display name, since application-created files typically don't have an associated email.
> - If neither user nor application-generated details are available:
>   - Securiti uses information from the drive owner:
>   - First, it uses the drive owner’s email address.
>   - If that is not available, it falls back to the drive owner’s display name.
