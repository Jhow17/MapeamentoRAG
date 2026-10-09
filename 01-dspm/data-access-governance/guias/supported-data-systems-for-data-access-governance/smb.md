---
title: "Windows SMB"
slug: "smb"
updated: 2026-09-28T04:38:53Z
published: 2026-09-28T04:38:53Z
canonical: "helpcenter.securiti.ai/smb"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Windows SMB

This section describes the Data Access Governance features supported for Windows SMB and the steps to configure these functionalities.

## Supported Data Access Governance Feature Sets

The following features are supported for Windows SMB:

#### Access Intelligence

- Privilege Analysis - Privilege Analysis is supported for Self- Hosted Connectors.
  - File level permissions granularity
- Activity Analysis - Not Supported

#### Cross Border Transfer Policies

- Not supported

#### Example Supported Use Cases

The supported example use cases include:

#### Access Intelligence

- Identify and report on which Windows SMB users have access to Specific Files and what their permissions are on those Files
- Identify and report on which Windows SMB users have access to Files containing sensitive data elements
- Identify and report users assigned to a specific user group that have access to Files.
- Identify and report Windows SMB User and Groups and their associated relationships to user and group identities in Active Directory.

## Configuring Windows SMB Data Access Governance

To see the Windows SMB intelligence data there are some prerequisite steps.

### Configuring Access Intelligence Privilege Analysis

### Prerequisites

**1. Permissions**

The user account you would use to for activating the connector must have following permissions:

| Permission level | Permission |
| --- | --- |
| Share | Read |
| Advanced NTFS | Read permissions |
| Basic NTFS | Read |

> [!NOTE]
> Note
> 
> The account configured in the IAM Metadata Source requires Read access to the **Windows SMB** Share in order for Securiti to extract file metadata and ACL information during Access Scans.

Securiti requires read access to retrieve ACL information from folders and files in the Windows SMB Share. This ACL information is essential for performing privilege analysis on the share’s files, which enables us to provide customers with accurate access information.

> [!NOTE]
> **Note**
> 
> Windows SMB related communication occurs over TCP port 445. Ensure that this port is open to allow traffic for the Securiti appliance. If communication issues arise, verify that port 445 is not being blocked.

**Remote SAM access**

During an Access Scan, Securiti queries the Security Account Manager (SAM) on the Windows SMB file server. These queries retrieve the domain Security Identifier (SID) and enumerate local users and groups. Securiti uses this information to interpret ACL entries on files and link them to the correct principals in the Data Command Graph.

> [!NOTE]
> **Note**
> 
> Securiti sends these queries to the connected file server, not to the domain controller. Securiti does not independently discover or connect to domain controllers.

By default, newer versions of Windows Server restrict which accounts can make remote SAM calls. If the connector user account doesn't have this permission, the Access Scan may fail. To resolve this, configure the **Network access: Restrict clients allowed to make remote calls to SAM** policy on the Windows file server to include the connector user account in the list of accounts allowed to make SAM requests. See the steps below.

> [!NOTE]
> **Note**
> 
> From Securiti release 1.147.1 onward, the lookupdomain builtin call is skipped during Access Scans. If you're on release 1.147.1 or later, the Access Scan no longer fails on this specific call. Securiti uses SAM to resolve the user and user group information it encounters during metadata collection. You must configure your SMB metadata sources or data system connectors with permissions to access SAM remotely.

To allow the connector user to make remote SAM calls:

1. Press **Win + R** to open the Run dialog. Type gpedit.msc in the **Open** field and click **OK**.

![Run dialog box showing 'gpedit.msc' command for Windows settings access.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 9(10).png)
2. In the Local Group Policy Editor, navigate to **Computer Configuration > Windows Settings**. In the right pane, double-click **Security Settings**.

![Local Group Policy Editor displaying security settings and configuration options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 10(5).png)
3. In the left pane, expand **Security Settings** and click **Local Policies**.

![Local Group Policy Editor displaying account and local policies for configuration settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 11(3).png)
4. In the right pane, double-click **Security Options**.

![Local Group Policy Editor showing security options and user rights assignment settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 12(5).png)
5. In the right pane, locate and double-click **Network access: Restrict clients allowed to make remote calls to SAM**.

![Local Group Policy Editor displaying network access settings and security options for configuration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 13(5).png)
6. In the policy properties dialog, click **Edit Security**.

![Network access settings for restricting remote calls to SAM with security descriptor options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 14(3).png)
7. In the **Security Settings for Remote Access to SAM** dialog, click **Add**. Enter the connector user account name and click **OK**. Under **Permissions**, mark **Allow** for **Remote Access** and click **OK**.

![Security settings for remote access to SAM with user permissions and options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 15(3).png)

> [!NOTE]
> **Note** For more information about this policy setting, see [Network access: Restrict clients allowed to make remote calls to SAM](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-10/security/threat-protection/security-policy-settings/network-access-restrict-clients-allowed-to-make-remote-sam-calls) on Microsoft Learn.

**2. Pod Configuration and deployment**

You must configure and deploy a Securiti pod in your environment to connect your Windows SMB with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information, see [Pod Installation](/latest/docs/securiti-pods-and-elastic-pods).

**3. Configure Private Cloud Storage**

Securiti lets you store Identity and Access Management (IAM) related metadata of your data systems, extracted using Access Scan Definitions (ASDs), in your Private Cloud Storage.

For more information, see [Configuring Private Cloud Storage](https://helpcenter.securiti.ai/docs/system-settings-configuring-private-cloud-storage).

If you have not configured Private Cloud Storage for your tenant, the IAM metadata will be stored in Securiti’s cloud storage.

**4. Configure and Activate the Windows SMB Self-Hosted Connector**

[Configure and activate the SMB Connector](/latest/docs/smb-connectors#steps-to-connect-smb-with).

**5. Perform Inventory Sync and Discovery Scan**

For your SMB instance, perform:

- [Data Inventory Sync](/latest/docs/configure-data-inventory-sync-for-smb) : Data Inventory Sync for SMB lets Securiti read Files metadata in SMB Shares and display it in Data Command Graph.
- [Discovery Scan](/latest/docs/configuring-discovery-scans-in-smb) : The Discovery Scans lets Securiti detect sensitive and personal data in Files stored within your SMB Shares.

> [!NOTE]
> **Note**
> 
> **Data Inventory Sync:** Reads metadata from Files and unstructured data resources and makes them available in the Data Command Graph. In conjunction with an access-scan on the data-system(s), it can show access permissions that principals have on those files and data resources.
> 
> **Discovery Scan:** Detects sensitive or personal data associated with data resources. In conjunction with an access scan on the data-system(s), it shows which users can access specific sensitive data elements.

**6. Configure an Active Directory Server (Optional)**

AD Synchronization, either on-demand or periodic, fetches users and groups from the [configured AD server](/latest/docs/identity-providers-idp-providers-for-identity-sync) and makes them available in the Securiti Data Command Graph. You must configure Active Directory (AD) server controlling SMB as an Identity Provider in the Access Scan Definition. When you execute an SMB Access Scan, users and groups discovered on the SMB server are linked to their corresponding AD users and groups in the graph by the Identity Analyzer. These relationships reveal user access to SMB files. Any subsequent AD Synchronization or SMB Access Scan triggers a re-analysis to ensure the graph remains up to date with current identity relationships and access details.

**7. Configure IAM Metadata Source**

To configure an IAM Metadata Source:

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ETTGGYIS.png)
2. Click **IAM Metadata Sources**. This opens the IAM Metadata Sources page.
3. Near the upper right corner of the page, click **+New IAM Metadata Source**.
4. On the **New IAM Metadata Source** popup:
  1. Enter the **Connection Name**. For example, SMB Metadata Source.
  2. Select the **SMB** in **Source Type** if you want to create a metadata source for SMB.
  3. In the Connection Information area, select the pod in **Pod Name**.
  4. Enter the **Host**, e,g, 111.111.111.111
  5. In the **Authentication Type,** select **Basic**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-MCH63NTI.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-X9PJFAHM.png)
  6. Enter the SMB **Username** and **Password**, e.g, Administrator. Note that if an Active Directory user account is being used to configure an IAM Metadata Source for SMB, you must specify the Active Directory domain with SMB username in **Username** field. For example, you must enter Administrator@securiti.local, **Administrator** is the SMB username, and **securiti.local** is the Active Directory domain.
  7. Click Create **New IAM Metadata source**.

**8. Configure an Access Scan Definition**

To configure an Access Scan Definition

1. In Securiti, open Data Access Governance, then from the left menu bar choose **Settings>Access Scan Definitions**.
2. Near the upper right corner of the page, click **+ New Access Scan Definition**.
3. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition. For example, SMB Access Scan Definition
  2. Select **SMB** in the **Data System**.

> [!NOTE]
> Note
> 
> When using SMB Connectors as **Data System Connectors in Access Scan Definitions**, please **be aware that connectors configured with Keyring for credentials are not supported**. Access Scan Definitions **only support basic NTLM Authentication for Access Scans**. Therefore the Data System Connectors ("Connectors as Metadata Source") should be configured with NTLM username and password. As a workaround, **you may configure either a new SMB Connector (that does not use Keyring) or configure an IAM Metadata Source (with NTLM username and password),** and then use it in the Access Scan Definition.
> 
> This limitation does not apply to SMB Connectors that are only configured as Associated Connectors.
  3. In the **IAM Metadata Sources**, select the metadata sources that you have created for SMB. If you have not configured a metadata source, then you must click **+ Add New** to add a metadata source.
  4. In the **Associated Connectors** area, select the associated **Data System** Instances in the Data Systems for which access metadata is being scanned.

> [!NOTE]
> **Note**
> 
> The Access Scan Definition (ASD) and its Metadata Source must use a fully qualified domain name (FQDN) or an IP address for the host, matching the corresponding data source (for example, an SMB server or database server). When you select an Associated Connector, Securiti checks whether the connector's host is configured as an FQDN, IP address, or hostname:
> 
> - If the connector uses an FQDN or IP address, Securiti matches it against the FQDN or IP address configured in the ASD.
> - If the connector uses only a hostname, Securiti matches it against the first label of the FQDN configured in the ASD.
> 
> For example, if the ASD host is configured as ip-192-168-46-30.us-west-2.compute.internal, a connector configured with only ip-192-168-46-30 as its host still links and scans successfully.
> 
> ![Audit log displaying access scan definitions and their corresponding activities and timestamps.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-30 at 10.04.13 AM.png)
  5. (Optional) In the **Identity Providers**, select the Active Direcotry Server Instance.
  6. (Optional) In the Scan Configuration area, mark the Auto Scan checkbox if you want to automatically scan or re-scan the access information weekly.

> [!NOTE]
> Note
> 
> When you update credentials for an IAM Metadata Source, the changes apply only to newly initiated access scans. If an access scan continues to use old credentials, ensure the Metadata Source is updated, the ASD references the edited source, and the scan is re-initiated.

**9. Perform an Access Scan**

On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.

Click the three dots option, and select the **Scan Now** option.

## Using Access Intelligence with SMB

Below are example use cases to familiarize you with how to leverage our Data Command Graph to identify access and risk in your SMB tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

### Identifying Users with Access to a specific Files using the Access Graph Explorer

To identify users that have access to specific Files and their permissions:

1. In Securiti, open **Data Access Governance** and choose **Data Governance Command Graph** to access the Command Graph.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer** .
3. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **User Principal** Entity. Click three dots with the **User Principal** Entity, and select **Add Relationship**. Choose **Resource Access**.

![SMB_Files_Specific.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d133f657-65c2-225b-aa0a-556c94379e1f.png)
4. Click three dots with the **Resource Access** Entity, and select **Add Relationship**. Select **Files**. Add **File Name** Property for Files Entity.
5. Select the **Files** for which you want to identify the users that have access to. You can also write the File Name in the search box.
6. Click **Apply**.
7. Click on the **User Principal** node to see the users in the data grid.
8. Click on the **Resource Access** node to see the **Privilege** and **Privilege Category**.

> [!NOTE]
> **Note**
> 
> The data grid also shows the origin of a file or folder's permissions as a path:
> 
> - If permissions are inherited, this path points to the share or folder where the permission was actually defined, which may be several levels up the hierarchy and not the immediate parent.
> - If inheritance is broken at a file or folder, this path points to the file or folder itself for all of its permissions, since it no longer receives updates from its parent.
> 
> If this information isn't available for files and folders that were already scanned, run a new Access Scan to see it for existing data.

### Identifying Users with Access to a Files containing sensitive data using the Access Graph Explorer

To identify users that have access to Files containing sensitive data elements:

1. In Securiti, open **Data Access Governance** and choose **Data Governance Command Graph** to access the Command Graph.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer** .
3. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **Data Element** Entity. Click three dots with the **Data Element** Entity, and select **+ Add Property**. Choose **Non Personal Sensitive Data** property. Select **Equals** operator. Select **True**
4. Click three dots with the **Data Element** Entity, and select **Add Relationship**. Select **Files**. Click three dots with the **Files** Entity, and select **+Add Property**. Select **Data System Type**. Choose **SMB - Self - Hosted**.
5. Click three dots with the **Files** Entity, and select **Add Relationship**. Select **Resource Access** Entity.

![SMB_PII_Data_Files.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3d57a5ae-7621-51d0-f09b-ebe461fe4f2a.png)
6. Click three dots with the **Resource Access** Entity. Select **Add Relationship**. Choose **User Principal**.
7. Click on the **User Principal** node to see the users in the data grid.
8. Click on the **Data Element** node to see the sensitive data elements that users have access to.

### Identifying Users assigned to a specific user group that have access to Files using the Access Graph Explorer

1. In Securiti, open **Data Access Governance** and choose **Data Governance Command Graph** to access the Command Graph.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer** .
3. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **User Group Principal** Entity. Click three dots with the **User Group Principal** Entity, and select **Add Relationship**. Select **User Principal**.
4. Click three dots with the **User Principal** Entity, and select **Add Relationship**. Choose **Resource Access** Entity. Click three dots with the **Resource Access** Entity, and select **Add Relationship**. Select **Files**.

![SMB_Usergroup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1bd51f39-729a-5ac0-3691-b1cfba750370.png)
5. Click three dots with the **Files** Entity, and select **+Add Property**. Select **Data System Type**. Choose **SMB - Self - Hosted**.
6. Click on the **User Group Principal** node to see the User Groups in the data grid.
7. Click on the **Files** node to see the Files.

### Identifying SMB User and Groups and their associated relationships to user and group identities in Active Directory.

1. In Securiti, open **Data Access Governance** and choose **Data Governance Command Graph** to access the Command Graph.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer** .
3. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **User Principal** Entity. Click three dots with the **User Principal** Entity, and select **+ Add Property**. Select **Provider Type**. Choose **SMB**.
4. Click three dots with the **User Principal** Entity, and select **Add Relationship**. Choose **User (Active Directory)** Entity. Click three dots with the **User (Active Directory)** Entity, and select **+Add Property**. Choose **Provider Type**. Select **Active Directory**.

![DAG_SMB.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c5021150-9f51-d755-2e5e-08ef9879865e.png)

To identify the relationship between SMB User Groups and group identities in Active Directory:

1. In Securiti, open **Data Access Governance** and choose **Data Governance Command Graph** to access the Command Graph.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer** .
3. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **User Principal** Entity. Click three dots with the **User Group Principal** Entity, and select **+ Add Property**. Select **Provider Type**. Choose **SMB**.
4. Click three dots with the **User Group Principal** Entity, and select **Add Relationship**. Choose **User Group (Active Directory)** Entity. Click three dots with the **User Group (Active Directory)** Entity, and select **+Add Property**. Choose **Provider Type**. Select **Active Directory**.

## Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards).

## Troubleshooting for SMB connector

### Access Scan issues

#### Access Scan fails with "failed to fetch global domain SID"

If your Access Scan fails with the following error in the appliance logs, the connector user account doesn't have permission to make remote SAM calls on the Windows file server:

failed to create SMB collector: failed to fetch global domain SID: failed to run lsaquery: error running rpcclient command 'lookupdomain builtin': exit status 1

Securiti queries the SAM on the file server during an Access Scan to enumerate domain groups and look up user and group names. This is required to map ACL entries to principals in the Data Command Graph. Windows restricts access to the SAMR pipe by default, which causes the scan to fail when the connector account isn't permitted.

> [!NOTE]
> **Note**
> 
> This error applies to releases before Securiti release 1.147.1. From release 1.147.1 onward, the lookupdomain builtin call is skipped and this specific error no longer appears. If you're on release 1.147.1 or later and your Access Scan is still failing, see the resolution steps below or contact Securiti Support.

> [!NOTE]
> **Note**
> 
> This is a policy restriction on the Windows file server, not a network connectivity issue. A successful Inventory Sync or Discovery Scan doesn't confirm that remote SAM access is working, as those scans use a different code path.

To resolve this issue:

- If you're on a release before 1.147.1, upgrade to release 1.147.1 or later. The lookupdomain builtin call is skipped from this release onward.
- If you're already on release 1.147.1 or later and the scan is still failing, grant the connector user account permission to make remote SAM calls on the file server. For the configuration steps, see the Remote SAM access section in the Windows SMB prerequisites.

After applying either resolution, re-run the Access Scan.

#### Access Scan node is running an outdated image after upgrade

If you've upgraded to release 1.147.1 but the Access Scan continues to fail with the same error, the scan node may still be using a cached version of the previous image rather than the updated one.

To force the node to pull the correct image:

1. On the appliance, run the following command to remove the cached image: crictl rmi app.eu.securiti.ai/securiti/access-mgmt-job:1.147.1-01p
2. Re-run the Access Scan. The node pulls the correct updated image automatically.

> [!NOTE]
> **Note**
> 
> This step is only required if the scan node cached the image before the corrected build was available. If your deployment pulled the image after the fix was confirmed, this step isn't needed.

### Inventory Sync issues

#### File owners display as "Unknown" in Inventory Scan

After running a Data Inventory Sync, files in the SMB share display **Unknown** in the owner field in the Data Command Graph.

This occurs when Securiti connects directly to a backend Windows file server. The file server can only resolve identities for its own local accounts. Files owned by users from an external Active Directory domain display as Unknown because the file server can't translate those Security Identifiers (SIDs) to usernames without direct domain trust access.

> [!NOTE]
> **Note**
> 
> The SIDs on the files are intact. This is a name-resolution limitation of direct file server connections, not a scanning error. The Access Scan still runs, and ACL-based access analysis still works when an Active Directory server is configured as an Identity Provider in the Access Scan Definition.

This behavior is most common when the SMB connector was previously accessed through a DFS path and has been reconfigured to connect directly to the backend file server. DFS paths route through domain-connected servers that can resolve cross-domain identities. Direct connections don't.

To ensure AD users are correctly linked to ACL entries in the Data Command Graph, configure an Active Directory server as the Identity Provider in the Access Scan Definition.

This ensures consistent, least-privilege access management across your **Windows** and **Linux SMB environments**, directly from the **Securiti Data Command Center**.
