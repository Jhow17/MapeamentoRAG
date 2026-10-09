---
title: "Data Inventory Sync and Entitlement Scan for data systems"
slug: "data-inventory-sync-for-self-hosted-connectors"
updated: 2026-08-03T06:55:14Z
published: 2026-08-03T06:55:14Z
canonical: "helpcenter.securiti.ai/data-inventory-sync-for-self-hosted-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Data Inventory Sync and Entitlement Scan for data systems

Securiti performs Data Inventory Sync and Entitlement Scan on self-hosted connectors after the connector activation process to provide a view of the data contained within your data systems. The scanning lets you organize and categorize data effectively as metadata is collected from your Data system Instance. Data Inventory Sync lets you build an inventory of data resources in your system for use in [Gencore AI](/latest/docs/gencore-ai-onboarding) data pipelines without doing a full content classification scan on the data.

You can configure the following scans on your data systems to discover file metadata and entitlements:

| Scan | Description |
| --- | --- |
| **Data Inventory Sync** | Data Inventory Sync collects detailed metadata about the files within a Data system. This includes file names, types, sizes, creation and modification dates, and other relevant properties. The scan builds an inventory of all resources that are discovered during the scan. The sync collects and creates inventory for the following types of data. - Scoping inventory: The discovery metadata captured to limit the connector and discovery scan scope. The scoping inventory includes high-level metadata such as groups, sites, libraries, etc, depending on the type of data system. - Data inventory: The information and data present inside the scope, such as files and folders. Data inventory is represented by **Files** in Securiti's [Data Command Graph](/latest/docs/data-command-graph-use-cases) module. |
| **Entitlement Scan** | Entitlement scans collect information about user entitlements to the files for use by the [Gencore pipelines](/latest/docs/using-genai-pipelines). The Entitlement Scan collects the following types of data: - Identity principal information: Information about the users, groups, and organizations for a Connector Instance. Also known as instance-level entitlements. - File or document exposures: Details about which users or groups have access to specific files. |

> [!WARNING]
> **Important**
> 
> You must do the following for your data system before the connector configuration process.
> 
> - Configure any required inventory and entitlement scan permissions. Refer to your relevant Data system's topic for more information.
> - Allowlist endpoints required for successful metadata scanning.

## Supported data systems

Securiti supports Data Inventory Sync for the self-hosted connectors of the data systems listed in the table below. The table also highlights the data scanned in scoping and data inventories and the entitlements discovered for each data system.

| Data system | Scoping Inventory | Data Inventory | Gencore AI Entitlement Support |
| --- | --- | --- | --- |
| [Amazon S3](/latest/docs/configuring-data-inventory-sync-for-amazon-s3-hyperdrive) | Not applicable | S3 Objects in buckets | Not supported |
| [Azure Blob Storage](/latest/docs/configuring-data-inventory-sync-for-azure-blob-storage-self-hosted) | Azure Containers | Blobs stored in containers | Not supported |
| [Azure Data Lake Storage](/latest/docs/configuring-data-inventory-sync-for-adls-connector-en) | Azure Data Lake File System(s) | Containers or Folder Path(s) | Not supported |
| [Confluence Cloud](/latest/docs/configure-data-inventory-sync-for-confluence-cloud) | All sites and their spaces | All Pages, Blog Posts, and Attachments modeled as **Files** in Graph | Entitlements for spaces, groups, and users to be used in Gencore pipelines |
| [Dropbox](/latest/docs/configuring-data-inventory-sync-for-dropbox) | Dropbox groups | - All files in Personal and Shared Folders - All files in Team Folders | Entitlements for groups and users to be used in Gencore pipelines |
| [G Suite Google Drive](/latest/docs/configuring-data-inventory-sync-for-g-suite-google-drive-self-hosted) | Google groups | All files in Personal and Shared Drives | Entitlements for organizations, groups, and users to be used in Gencore pipelines |
| [GitHub](/latest/docs/configure-data-inventory-sync-for-github) | Organizations, repositories and branches | - Description of all repositories - Files in all branches in a repository - All issues, commits, and pull requests as CSV files | Entitlements for spaces, groups, and users to be used in Gencore pipelines |
| [GitLab](/latest/docs/gitlab-connectors-configuring-data-inventory-sync-for-gitlab) | Groups, including projects and branches | All issues, commits, and pull requests modeled as CSV files | Entitlements for projects, groups, and users to be used in Gencore pipelines |
| [Google Cloud Storage](/latest/docs/configuring-data-inventory-sync-for-google-cloud-storage) | GCP buckets | Objects stored in GCP buckets | Not supported |
| [HDFS](/latest/docs/configuring-data-inventory-sync-for-hdfs) | HDFS repositories | Files stored in HDFS repositories | Not supported |
| [Jira Cloud](/latest/docs/configuring-data-inventory-sync-for-jira-cloud-self-hosted) | Sites and Projects | - Tickets and attachments are modeled as **Files** in Graph - Description of an issue as a single file | Entitlements for files, organizations, groups, and users to be used in Gencore pipelines |
| [Microsoft 365 OneDrive](/latest/docs/configuring-data-inventory-sync-for-onedrive-self-hosted) | Microsoft 365 Groups | Files for all personal (default) drives. | Entitlements for groups and users to be used in Gencore pipelines. |
| [Microsoft 365 Outlook](/latest/docs/configuring-data-inventory-sync-for-outlook) | Outlook groups or users. | Messages and attachments modeled as **Files** in Graph. | Entitlements for groups and users to be used in Gencore pipelines. |
| [Microsoft 365 SharePoint Online](/latest/docs/configuring-data-inventory-sync-for-sharepoint-online-self-hosted) | - Level 1: SharePoint Sites - Level 2: SharePoint Libraries | All Files for all scoped document libraries and/or sites, excluding locked or blocked sites. | Entitlements for sites, groups, and users to be used in Gencore pipelines. |
| [Microsoft 365 Teams](/latest/docs/configuring-data-inventory-sync-for-microsoft-teams) | Teams and Channels | - Chat Messages are modeled as **Files** representing each month. - Channel messages are modeled as **Files** in Graph. | Entitlements for channels, teams, and users to be used in Gencore pipelines. |
| [NFS](/latest/docs/configuring-data-inventory-sync-for-nfs) | Not applicable | Files in NFS shares | Not supported |
| [Securiti for Box](/latest/docs/configuring-data-inventory-sync-for-securiti-for-box) | Box groups in enterprise | Files for all users in the enterprise | Entitlements for Box file objects to be used in Gencore pipelines |
| [Slack Enterprise Grid](/latest/docs/configuring-data-inventory-sync-for-slack-enterprise-grid) | Slack Workspaces and channels | Channel conversations and attachments | Entitlements for Slack file objects to be used in Gencore pipelines |
| [SMB](/latest/docs/configure-data-inventory-sync-for-smb) | SMB shares | - Files in SMB shares - SMB share names | Not supported |
| [Zendesk Support](/latest/docs/configuring-data-inventory-sync-for-zendesk-support-self-hosted) | Organizations in Zendesk Support | Attachments and tickets for organization are modeled as **Files** in Graph. | Entitlements for Zendesk Support file objects to be used in Gencore pipelines |

## Configuring Data Inventory Sync and Entitlement scan for a connector

You can configure Data Inventory Sync and Entitlement Scan for your Self-hosted data system Instance during the connector activation process.

### Initiating the Data Inventory or Entitlement sync

To configure Data Inventory Sync or Entitlement Scan for your Data system:

1. In **Securiti**, go to **Integrations > Data Systems**
2. Type the data system name for the required connector and click on your Instance. Create a new Instance if not created already. For more information, see [Configuring connectors for monitored data systems](/latest/docs/configuring-connectors-for-monitored-data-systems).
3. Configure the connector to suit, and under **Configuration**, click the **Inventory** tab, configure the sync in **Data Inventory Sync**.
4. Enable the checkbox for **Enable Data Inventory Sync** or **Run Entitlement Scan** as required, to perform Data Inventory Sync and Entitlement Scan for your connector.
5. In the **Data Inventory Sync & Entitlements Scopes section**, specify the inventory and entitlement scopes such as Google Drive groups to include in the inventory.
6. To change the scope of the inventory sync, choose the desired scope and click **save** after the initial sync is completed.

> [!WARNING]
> Important
> 
> - Changing the inventory sync scope immediately purges previously synced inventory data and re-run the sync using the updated scope.
> - When you change the scope, Securiti purges the Data Inventory Sync job and its relationship to the **Files** entity in the Data Command Graph. However, **Files** themselves, and any results a Discovery scan populated on those files, are not purged.
> 
> This affects your data as follows:
>   - The Data Inventory Sync job and its relationship to previously scanned files are removed. Securiti rebuilds this relationship using only the new scope.
>   - Data Inventory Sync statistics reset to reflect only the new scope.
>   - Sensitivity labels, classified data elements, content profiles, and Discovery Scan Job IDs that a Discovery scan populated on a file remain on that file's **Files** entity.
> - To add new sites, folders, or groups to your scope without losing previous Data Inventory Sync results, you must set up a new connector instance scoped to the new items instead of changing the scope of the existing instance.
7. Click **Save**
8. Click **Initiate Data Inventory Sync**, as shown below.

![Settings page for SharePoint Online with options for data inventory sync and configuration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Data-Inventory-Sync-Start.png)

![Settings for SharePoint data systems, including libraries and site collections management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sharepointscopes(1).png)

### Pausing and resuming a sync

Once a sync is in running state, you use the pause option when you need to temporarily stop an in-progress inventory sync. Securiti lets you resume the sync later from the same point.

The pause and resume support is available for the following data systems only:

- Google Drive (Google Workspace)
- Microsoft 365 OneDrive
- Microsoft 365 Outlook
- Microsoft 365 SharePoint Online
- Microsoft Teams
- Securiti for Box

To pause and resume an inventory sync:

1. In the **Overview** tab of the connector, scroll to **Data Inventory Sync** section.
2. Expand the accordion next to **View Stats** and click **Pause Scan**, as shown below.

![Overview of OneDrive integration settings with sync and scan options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dis_pause.png)
3. In the **Pause the Data Inventory Sync** popup, click **Okay**, as shown below.

![Prompt to pause data inventory sync with options to cancel or confirm action.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dis_pause_popup.png)
4. To resume a scan, expand the accordion next to **View Stats** and click **Resume Scan**, as shown below.

![Overview of OneDrive settings with options to resume scan and view statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dis_resumescan.png)

### Viewing scan statistics

To view the scan statistics for Inventory and Entitlement scans:

> [!NOTE]
> **Note**
> 
> Scan statistics are available only after the scan is successfully completed.

1. For more information, see [Viewing Data Inventory Sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).
2. Once the scan is successful, under the **Data Inventory Sync**, click **View Stats**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 10.33.26 AM.png)
3. You will be redirected to the **Statistics** page. For more information, see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).

### Viewing sync status

Use the **Status** indicator to track the scan's progress and to monitor the data ingestion, as shown below.

![Data Inventory Sync status shows completed with last sync date and time details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sync-status.png)

The **Status** indicator displays the following states:

- **Inactive**: Indicates that the scan hasnot started yet and needs to be initiated.
- **Schedule**: Indicates that your scan is in queue.
- **Post processing in progress**: Data ingestion is in progress.
- **Scan successful**: Indicates successful execution of the scan.

### Cancelling a sync

To cancel to the **Data Inventory Sync**, perform the following steps:

1. Under the **Data Inventory Sync**, click **Cancel Scan.**

![Confirmation prompt to cancel the Data Inventory sync in SharePoint settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dis_cancelsync_popupnewUI.png)

![Cancel_Sync.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e254ee0c-4297-35cc-8747-be8de31347e8(13).png)
2. On **Cancel the Data Inventory Sync** popup, click **Okay**.

It takes time to complete the Scan cancellation process.

![Confirmation dialog asking to cancel the Data Inventory sync process in SharePoint.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dis_cancelsync_popupnewUI(1).png)

The **Status** indicator displays the following message once the scan is successfully cancelled:

"Inventory Data scan was cancelled by the user."

## Viewing Data Inventory Sync results in graph

You can view the discovered metadata in the **Files** entity in Data Command Graph's **Graph Explorer** and explore relationships with other entities as well. For more information, see [Viewing scan results for data system connectors](/latest/docs/viewing-scan-results-for-data-system-connectors).

The screenshot below shows a query to view Microsoft 365 SharePoint Online sites in the Graph Explorer.

![sitequery.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a26d2ae-1e22-7ebe-65ca-ee7dfd177ced.png)

![site_instexp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eb4fcfa7-f527-1e7a-591b-4d8ee147ee40.png)

## Related

- [Supported data system connectors in Securiti](/supported-data-system-connectors-in-securiti.md)
- [Microsoft Information Protection (MIP) label extraction for data systems](/microsoft-information-protection-mip-label-extraction-for-data-systems.md)
- [Scoping Inventory Syncs for connectors](/scoping-metadata-syncs-for-connectors.md)
- [Viewing scan results in Data Command Graph](/viewing-scan-results-for-data-system-connectors.md)
