---
title: "Dropbox"
slug: "dropbox-connectors"
status: "update"
updated: 2026-03-10T04:32:46Z
published: 2026-03-10T04:32:46Z
canonical: "helpcenter.securiti.ai/dropbox-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Dropbox

Dropbox is a file hosting service that offers cloud storage, file synchronization, personal cloud and client software. Dropbox offers its suite of service across multiple platforms including personal computers and smartphones and syncs saved content across cloud stores and these linked devices. Dropbox falls under the category of [Monitored, Unstructured data systems](/latest/docs/managing-data-system-connectors).

### Supported Connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Dropbox (Self-hosted) | - DSR Automation using Full scan - Workflow - Discovery Scan - Breach Analysis - Data Inventory Sync - Entitlements scan |
| Dropbox (Securiti Cloud) | - Security Posture Scan - Breach Analysis |

### Supported Pod types for Dropbox (Self-hosted)

- Standard Securiti pod (for self-hosted connector only)

### Supported authentication methods

- For Self-hosted connector:
  - OAuth based authentication
- For Securiti Cloud connector:
  - OAuth based authentication

#### Keyring support for Dropbox (Self-hosted)

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings) for more information.

- **HashiCorp**. For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault)

HashiCorp is OAuth supported.

> [!NOTE]
> Note
> 
> To configure the Hashicorp OAuth token, see [(Optional) Configure the Hashicorp OAuth token for Dropbox](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-dropbox).

### Supported items for Inventory and Classification scans

For more information on inventory and entitlement scans, see [Data Inventory Sync for self-hosted connectors](/v1/docs/data-inventory-sync-for-self-hosted-connectors). For more information about classification in discovery scans, see [Understanding Discovery Scans](/v1/docs/discovery-scans).

- Groups
- Members
- Folders
- Attachments/Files

### Prerequisites for configuring Dropbox

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your data system using a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate endpoints.

For more information on configuring pods, see [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).

#### 2. Register an application in Dropbox

To create an application, see [Register an application in Dropbox](/latest/docs/register-an-application-in-dropbox)

You must be an administrator to grant permissions to the applications created in Dropbox.

#### 3. Allowlist APIs for Data Inventory Sync

You must allowlist the following APIs between your deployed Securiti Pod and Dropbox APIs to successfully run the Data Inventory Sync.

Following are the base URLs:

- **Default URL**: `https://api.dropboxapi.com`
- **Content URL:** `https://content.dropboxapi.com`
- **Preview URL:** `https://www.dropbox.com/home`
- **Paper URL**: `https://paper.dropbox.com/doc/`

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

#### 4. Grant Permission to APIs in Dropbox app

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Inventory Metadata Sync - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector. | Set the following scopes for API level permission: - `Account_info.read` - `Files.metadata.read` - `Files.content.read` - `Sharing.read` - `Team_info.read` - `Team_data.member` - `Team_data.team_space` - `Members.read` - `Events.read` - `Groups.read` | These permissions let Securiti read the files and file metadata in Dropbox for inventory and classification purposes. These permissions also build the Personal Data Index for DSR Automation. |
| Data Inventory Sync and Entitlement scanning | - Available for self-hosted connector only. - Requires allowlisting APIs between your deployed Securiti pod and the Dropbox. | These permissions let Securiti read the files and file metadata in Dropbox for inventory. The permission also let Securiti discover entitlements and read sharing settings. |
| Security Posture Management Rule Evaluation | This capability lets Securiti to evaluate posuture findings in Dropbox. | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |

### Connect Dropbox with Securiti

**New UI**

#### Steps to connect the Dropbox (self-hosted) connector with Securiti

To configure the Dropbox (self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in Securiti [pods](/v1/docs/pods-cluster-version-v128-and-later).
3. [Register an application in Dropbox](/v1/docs/register-an-application-in-dropbox)
4. [(Optional) Configure the Hashicorp OAuth token for Dropbox](/v1/docs/optional-configure-the-hashicorp-oauth-token-for-dropbox)
5. [(New UI) Connecting Dropbox (self-hosted) with Securiti](/latest/docs/new-ui-connecting-dropbox-with-securiti)
6. [(New UI) Configuring General permissions for Dropbox (self-hosted)](/latest/docs/new-ui-configuring-general-permissions-for-dropbox-self-hosted)
7. [Configuring Data Inventory Sync for Dropbox](/v1/docs/configuring-data-inventory-sync-for-dropbox)
8. [Configuring discovery scan in Dropbox](/v1/docs/configuring-discovery-scan-in-dropbox)

#### Steps to connect the Dropbox Securiti Cloud connector with Securiti

To configure the Dropbox Securiti Cloud connector, perform the procedures in the following topics:

1. [Grant permissions and obtain credentials in OneDrive Cloud](/v1/docs/grant-permissions-and-obtain-credentials-in-onedrive-cloud)
2. [(New UI) Connecting the OneDrive (Securiti Cloud) data system](/latest/docs/new-ui-connecting-microsoft-365-onedrive-cloud-with-securiti)
3. [(New UI) Configuring General permissions for OneDrive (Securiti Cloud)](/latest/docs/configure-general-permissions-for-microsoft-365-onedrive-self-hosted)

**Classic UI**

To configure the Dropbox connectors, perform the procedures in the following topics:

1. [Register an application in Dropbox](/v1/docs/register-an-application-in-dropbox)
2. [(Optional) Configure the Hashicorp OAuth token for Dropbox](/v1/docs/optional-configure-the-hashicorp-oauth-token-for-dropbox)
3. [Activate the Dropbox connector in Securiti](/v1/docs/activate-the-dropbox-connector-in-securiti)
4. [Configuring Data Inventory Sync for Dropbox](/v1/docs/configuring-data-inventory-sync-for-dropbox)
5. [Configuring discovery scan in Dropbox](/v1/docs/configuring-discovery-scan-in-dropbox)

See [Fulfilling DSR requests for Dropbox](/v1/docs/fulfilling-dsr-requests-for-dropbox) for more information about how Securiti uses the Dropbox data to respond to DSR requests.
