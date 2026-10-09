---
title: "SMB - NetApp"
slug: "smb-netapp"
updated: 2026-09-23T05:29:38Z
published: 2026-09-23T05:29:38Z
canonical: "helpcenter.securiti.ai/smb-netapp"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# SMB - NetApp

This section describes the Data Access Governance features supported for SMB Shares hosted on NetApp ONTAP storage and outlines the steps to configure these capabilities.

## Supported Data Access Governance Feature Sets

The following features are supported for SMB NetApp:

### Access Intelligence

- Privilege Analysis - Privilege Analysis is supported for Self-Hosted SMB Connectors.

- File level Permissions granularity

- Activity Analysis - Supported

### Access Control

- Not supported

### Cross Border Transfer Policies

- Not supported

> [!NOTE]
> Note
> 
> If Data Access Governance features for SMB NetApp are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

## Example Supported Use Cases

The supported example use cases include:

Access Intelligence

- Identify and report on which NetApp Users have access to specific Files and what their permissions are on those Files.
- Identify and report on which NetApp Users have access to Files containing sensitive data elements.
- Identify and report Users assigned to a specific User Group that have access to Files.

## Configuring SMB NetApp Data Access Governance

To see the SMB NetApp intelligence data including both Privilege Analysis and Activity analysis, there are some prerequisite steps.

### **Configuring** **Access Intelligence (****Privilege Analysis)**

#### Prerequisites

> [!NOTE]
> Note
> 
> Steps 1-9 are same for both Activity analysis and Privilege analysis . A few exceptions are there, that are already mentioned in the steps.

1. Permissions

The user account you use for activating the SMB connector must have the following permissions:

| Permission Level | Permission |
| --- | --- |
| Share | Read |
| Advanced NTFS | Read |
| Basic NTFS | Read |

NetApp ONTAP REST API Access Required

The SVM admin account configured in the IAM Metadata Source must have read access to the following ONTAP REST API endpoints. Securiti uses these to retrieve local groups, membership, and share metadata during Access Scans.

| API Endpoint | Purpose | Access Level |
| --- | --- | --- |
| /api/protocols/cifs/local-groups | Fetches local CIFS groups | Read-only |
| /api/protocols/cifs/local-groups/{svm_uuid}/{group_id}/members | Fetches members of a local CIFS group | Read-only |
| /api/protocols/cifs/services/{svm_uuid}?fields=name,ad_domain | Fetches the connected AD domain and NetBIOS name | Read-only |
| /api/protocols/cifs/shares?fields=svm.name,name,path | Fetches share metadata for shares and SVMs | Read-only |
| /api/svm/svms | Fetches the list of Storage Virtual Machines (SVMs). For more infromation, see [NetApp documentation](https://docs.netapp.com/us-en/ontap-automation/workflows/wf_svm_list_svms.html). | Read-only |

> [!NOTE]
> Note
> 
> The following ports are required based on the SMB system type:
> 
> **NetApp SMB**
> 
> - **443 (HTTPS)** – Required for ONTAP REST API communication (user, group, and share metadata)
> - **445 (SMB)** – Required for SMB file system access and permission evaluation
> 
> **Windows SMB**
> 
> - **445 (SMB)** – Required for SMB file system access and permission evaluation
> 
> If **any required port is not open**, the collector will **bail out and terminate the scan.** Ensure that this port is open to allow traffic for the Securiti appliance. No inventory, discovery, access, or activity scans will proceed until connectivity is restored.

1. Pod Configuration and Deployment

You must configure and deploy a Securiti pod in your environment to connect your NetApp server with a Self-Hosted Connector. Make sure the pod deployment has appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information, see [Pod Installation](/latest/docs/pod-installation-cluster-version-v128).

1. Configure Private Cloud Storage

Securiti lets you store Identity and Access Management (IAM) related metadata of your data systems, extracted using Access Scan Definitions (ASDs), in your Private Cloud Storage.

For more information, see [**Configuring Private Cloud Storage**](/latest/docs/system-settings-configuring-private-cloud-storage). If you have not configured Private Cloud Storage for your tenant, the IAM metadata will be stored in Securiti’s cloud storage.

1. Configure and Activate the NetApp Self-Hosted Connector Configure and Activate the SMB Connector. Note that Securiti uses the SMB Share information you specify during connector configuration to determine the scope of Access Scans. If you configure the NetApp connector without specifying any Share names, Securiti will scan **all the Shares hosted on the NetApp server**. If you specify one or more particular Shares, Securiti will only scan those specific Shares for Access Intelligence Scans.

When configuring the connector, ensure that:

- The Securiti pod has network reachability to the SMB interface and the management interface of your NetApp ONTAP system.
- The credentials used have read-level access to the Shares and NTFS permissions being scanned.

For more detailed setup steps and configuration parameters, refer to the [SMB Connector](/latest/docs/connecting-smb-with-securiti) documentation.

1. Perform Inventory Sync and Discovery Scan

For your SMB instance, perform:

- Data Inventory Sync Data Inventory Sync for SMB lets Securiti read Files metadata in SMB NetApp Shares and display it in the Data Command Graph.

OR

- Discovery Scan The Discovery scans lets Securiti detect sensitive and personal data in Files stored within your SMB NetApp Shares.

> [!NOTE]
> Note
> 
> **Data Inventory Sync:** Reads metadata from Files and unstructured data resources and makes them available in the graph. In conjunction with an access-scan on the data-system(s), it can show access permissions that principals have on those Files and data resources.
> 
> **Discovery Scan:** Detects sensitive or personal data associated with data resources. In conjunction with an access scan on the data-system(s), it shows which users can access specific sensitive data elements.

1. Configure an Active Directory Server (Optional)

Configure an Active Directory (AD) Server to synchronize users and groups into the Securiti Data Command Graph. **AD Sync** can run on demand or on a schedule and fetches authoritative identity information from the configured AD server for access analysis. Ensure that the **AD server configured in Securiti is the same AD server used by the NetApp Share**. Any mismatch between NetApp and AD configurations can result in incomplete or inaccurate user-to-file access mappings.

When you run a **NetApp or SMB Access Scan**, Securiti discovers users and groups referenced in access control entries.

- If **Active Directory is not configured or synced**, these users and groups are ingested as shell principals. Shell principals provide a minimal representation of identities and show access only from a direct-principal perspective. They do not include AD attributes or user-to-group membership relationships.
- If **Active Directory is configured and synced**, Securiti links users and groups to their corresponding AD identities by matching Security Identifiers (SIDs). These relationships reveal user access to NetApp files and folders and are represented in the Data Command Graph.

To view Active Directory **user-to-group memberships**, you **must configure and successfully sync an AD connector**. Access Scans do not create user-to-group membership edges for AD users. User-to-group relationships are created only through AD Sync.

> [!NOTE]
> Note
> 
> Nested group memberships are currently not supported. Only direct user-to-group memberships from Active Directory are ingested and represented in the Data Command Graph.
> 
> To accurately analyze group-based access paths, sync Active Directory and then re-run the Access Scan.

If an Access Scan is run before an AD Sync, access mappings may not reflect the current state if users or groups were added, deleted, or modified in Active Directory during that time.

When **Active Directory Sync** is enabled after an **Access Scan**, the sync process enriches existing principals with AD identity attributes and direct group membership information instead of creating duplicate identity nodes. This preserves existing access relationships while enhancing identity context.

Any subsequent **AD Sync or NetApp or SMB Access Scan triggers re-analysis** to keep the Data Command Graph up to date. Changes to data or access permissions are reflected only after the relevant scan or sync is executed.

1. Configure IAM Metadata Source

To configure an IAM Metadata Source:

- In Securiti, open Data Access Governance, from the left menu bar, click Settings.
- Click IAM Metadata Sources. This opens the IAM Metadata Sources page.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000142465.png) Near the upper right corner of the page, click +New IAM Metadata Source.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000142467.png)

- On the New IAM Metadata Source popup:
  - Enter the Connection Name. For example, *NetApp Metadata Source*. Select **NetApp** in **Source Type** if you want to create a metadata source for NetApp.
  - Enter a name for the metadata source. Example: NetApp Metadata Source

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000142468.png)

- Select **NetApp** in the Source Type
- Select the pod from the dropdown (e.g., the pod where NetApp is deployed)
- Enter the SMB server hostname or IP. Example: netapp-smb.qa.corp.local
- Select **Basic** in the **Authentication Type** menu
- **Enter SMB Username & Password.** These fields display once you select **Basic Authentication Type**. Example:
  - SMB Username: devuser@iam-starburst.qa
  - SMB Password: ••••••••

Note: If using an Active Directory user, include the AD domain like: [Administrator@securiti.local](mailto:Administrator@securiti.local)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(9).png)

- In the REST API Configuration area, configure the following parameters

- SVM Management Address: Enter the management IP/FQDN of the NetApp ONTAP SVM. Example: 10.40.11.15
- Authentication Type: Select Basic and it expands to show:
- SVM User Name: Enter the admin-level SVM management username. Example: ontap_admin
- SVM User Password: Enter the SVM management password. Example: password123
- Disable TLS Verification (Optional): Enable only if required for non-trusted certs.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(2).png)

- (Optional) In the **Audit Log Configuration** area, configure the following parameters (Required only for enabling Activity Analysis for NetApp):
  - Audit Share Name : *(Optional)* Enter the Audit Share Name. This is the share name where audit logs reside. Note that Audit Log Folder and Audit Share Name fields are only required if you plan to enable Activity Analysis for NetApp. Example: NetApp_Audit_Share
  - Audit Log Folder : (*Optional)* Enter the Audit Log Folder. This is the path where audit logs are stored for your NetApp ONTAP system. Example: /vol/audit_logs/netapp_logs/ . If left blank, Securiti defaults to /.

Once you have configured all the fields, click ​**Create New IAM Metadata Sourc**e​​. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000142469.png)

> [!NOTE]
> Note
> 
> If an Active Directory user account is being used to configure an IAM Metadata Source for NetApp, you must specify the Active Directory domain (used to authenticate user access to the NetApp server) along with the username in the **Username** field. **For example**, you must enter Administrator@securiti.local, where Administrator is the username, and securiti.local is the Active Directory domain attached to the NetApp server.
> 
> If Active Directory users or groups don't yet have access to your NetApp ONTAP system, you'll need to grant that access first:
> 
> - **To Configure Active Directory for AWS FSx for NetApp ONTAP**: see AWS's [guide on setting up Active Directory authentication](https://docs.aws.amazon.com/fsx/latest/ONTAPGuide/set-up-ad-auth.html).
> - **To Configure Active Directory for on-premises NetApp ONTAP**: see NetApp's [guide on granting AD user/group access](https://docs.netapp.com/us-en/ontap/authentication/grant-access-active-directory-users-groups-task.html).

1. Configure an Access Scan Definition

To configure an Access Scan Definition:

- In Securiti, open **Data Access Governance**, then from the left menu bar choose Settings > Access Scan Definitions. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000146235.png)
- Near the upper right corner of the page, click + New Access Scan Definition.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000146462.png)

- On the New Access Scan Definition popup:
  - Enter the Name for the Access Scan Definition. For example, *SMB-netapp*.
  - Select NetApp in the Data System.
  - Enter the Host. For example, 11.1.111.111 This is the IP address or FQDN of your NetApp system. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000146708.png)
  - In the **Source of Credentials and Connectivity for Access Intelligence Scans** area, you can select whether you will use an **IAM Metadata Source** or the Data System Connector as the source of credentials and connectivity for Access Intelligence Scans.
  - In the Metadata Sources field, select the configured metadata source. For example, smb-qa-netapp-mds.
  - In the **Associated Connectors** area, select the associated systems for which access metadata is being scanned. For example, in Data Systems, select the NetApp instance. Example: na-iam-smb
  - *(Optional)* In the **Identity Providers** area, select the **Active Directory Server Instance** if you want to include identity mapping between AD users/groups and NetApp users/groups.
  - *(Optional)* In the **Scan Configuration** area, enable **automatic access scans** and define the exclusion time window for running the scans. Use the info icons (info_outline) beside each field to view detailed tooltips or configuration help. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000146996.png)
- Click Add Definition to create the Access Scan Definition.

1. Perform an Access Scan

On the Access Scan Definition page:

- Activate the Access Scan Definition that you created by enabling the toggle.
- Click the three dots option, and select Scan Now.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 23.png)

### **Configuring SMB NetApp Connector as Metadata Source**

You can use SMB connectors as the source of credentials and connections to data systems for Access Scan Definitions (ASDs). This allows you to configure ASDs without setting up a separate IAM Metadata Source, and is particularly useful when access to the ONTAP APIs is unavailable or restricted.

> [!NOTE]
> **Note**
> 
> **Limitations** Be aware of the following restrictions when using this configuration:
> 
> - **Local domain user and group details are unavailable.** Because the ONTAP REST APIs are not used, the access scan cannot retrieve attributes, memberships, or other details about local domain users and groups.
> - **Activity Analysis is not supported** in this configuration mode.
> - **An IdP Connector (Active Directory Sync Server) is required.** This connector is mandatory and is used to derive information about Active Directory domain users and groups when executing Privilege Analysis.
> - When using SMB Connectors as **Data System Connectors in Access Scan Definitions**, please **be aware that connectors configured with Keyring for credentials are not supported**. Access Scan Definitions **only support basic NTLM Authentication for Access Scans**. Therefore the Data System Connectors ("Connectors as Metadata Source") should be configured with NTLM username and password. As a workaround, **you may configure either a new SMB Connector (that does not use Keyring) or configure an IAM Metadata Source (with NTLM username and password),** and then use it in the Access Scan Definition.
> 
> This limitation does not apply to SMB Connectors that are only configured as Associated Connectors.

To configure Access Intelligence scans using connector as Metadata Source, you must follow the same configuration steps (1-7) mentioned in [pre-requisites](/latest/docs/smb-netapp#prerequisites). Once configured:

- In Securiti, open **Data Access Governance**, then from the left menu bar choose Settings > Access Scan Definitions. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000146235.png)
- Near the upper right corner of the page, click + New Access Scan Definition.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000146462.png)

- On **New Access Scan Definition** page, Enter the Name for the Access Scan Definition. For example, *SMB-netapp*.
- Select NetApp in the Data System.
- Enter the **Host**. For example, 11.1.111.111 This is the IP address or FQDN of your NetApp system.![System settings interface showing data access governance and connector options for scans.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/SMB_Netpp.png)
- In the **Source of Credentials and Connectivity for Access Intelligence Scans** area, select **Data System Connector** tile.
- In **Data System Connector,** select the data system instance that you must scan to gather IAM related metadata.
- In **Associated Connectors>Data Systems,** the relevant data system instance will be automatically selected.
- Select the Active Directory Server that you configured in the **Identity Providers** area to include identity mapping between AD users/groups and NetApp users/groups.
- *(Optional)* In the **Scan Configuration** area, enable **automatic access scans** and define the exclusion time window for running the scans. Use the info icons (info_outline) beside each field to view detailed tooltips or configuration help.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GFHIO9FK.png)
- Click Add Definition to create the Access Scan Definition.

Follow Step 9 mentioned above to perform the Access Scan.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 23(1).png)

## Using Access Intelligence with SMB NetApp

Below are example use cases to familiarize you with how to leverage the Data Command Graph to identify access and risk in your SMB NetApp tenant using Securiti’s Privilege Analysis and Activity Analysis feature sets. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

### Identifying NetApp Users that have access to specific Files using the Access Graph Explorer

1. In Securiti, open Data Access Governance and choose Data Governance Command Graph to access the Command Graph.
2. From the left navigation menu, click Data Command Graph, and choose Access Graph Explorer.
3. Near the upper left corner of the page, click + to open the filter menu. On the filter menu, select the Identity Provider (IAM Identity Provider) entity.
4. Click the three dots with the Identity Provider Entity, and select + Add Property → Provider Type. Select NetApp as the Provider Type.
5. Next, click the three dots with the Identity Provider Entity, and select Add Relationship → User Principal.
6. Click the three dots with the User Principal Entity, and select Add Relationship → Resource Access Entity. This step links each NetApp user to the resources they have access to.
7. Click the three dots with the Resource Access Entity, and select Add Relationship → File Entity. Add a property filter for Resource ID to specify the file of interest. For example, enter /IAMTestFsx1/ALLUSAPDs.csv in the Resource ID field to locate all users with access to that specific file.
8. Click Run Query.

### ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000149897.png)

> [!NOTE]
> Note
> 
> In the Access Graph Explorer, the SYNCHRONIZE permission is treated as an implicit supporting privilege. As a result, SYNCHRONIZE is normalized and displayed as part of the Privilege Bundle rather than being shown independently for every permission combination. The SYNCHRONIZE privilege is displayed explicitly in the Privilege Bundle only when Write-level access is present. For Read, Execute, Modify, or other permissions, SYNCHRONIZE is implicitly applied and therefore not displayed separately in the graph.

### Identifying Users Assigned to a Specific User Group that have Access to Files using the Access Graph Explorer

> [!NOTE]
> Note
> 
> This use case requires Active Directory integration. If the Access Scan is executed without AD integration, NetApp users and groups are created as shell principals and user-to-group membership edges are not created, so the results may be incomplete.

1. In Securiti, open Data Access Governance and choose Data Governance Command Graph to access the Command Graph.
2. From the left navigation menu, click Data Command Graph, and choose Access Graph Explorer.
3. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **User Group Principal Entity**. Click three dots with the User Group Principal Entity, and select Add Relationship **→ User Principal.** Click the three dots with the ​**User Principal Entity​​,** and select ​**Add Property → Provider Type​ = NetApp​​.**
4. Click the three dots with the ​**User Principal Entity​,** and select ​**Add Relationship → Resource Access​​.** ﻿
5. Then click three dots with the Resource Access Entity, and select Add Relationship **→ Files.**
6. Click three dots with the Files Entity, and select **+Add Property** **→ Data System Type = SMB.**
7. Click **Run Query.**
8. Click on the User Group Principal node to see the User Groups in the data grid. Click on the **Files node** to see the Files.

![Access Graph Explorer displaying user group principals and resource access details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/NetApp usergroup assignement.png)

### Identifying NetApp Users using the Access Graph Explorer

1. In Securiti, open Data Access Governance and choose Data Governance Command Graph to access the Command Graph.
2. From the left navigation menu, click Data Command Graph, and choose Access Graph Explorer.
3. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **User Principal Entity**. Click three dots with the User Principal Entity, and select **+Add Property** *→* **Provider Type = NetApp.**
4. Near the upper right corner, click **Run Query**. The results will display all user principals that belong to your NetApp system.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000150374.png)

## Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [Reporting Dashboard Documentation](/latest/docs/getting-started-with-graph-reporting-dashboards).

## Activity Analysis for SMB NetApp

This section describes the process for SMB NetApp Activity Analysis

### Prerequisites:

Complete the setup [steps (1-9)](/v1/docs/smb-2#prerequisites) in **Configuring SMB NetApp Data Access Governance** (connector, metadata source, access scan definition, access scan). In addition, Activity Analysis requires NetApp audit logging to be enabled. Below is the given set of steps to configure NetApp audit logging.

1. #### Configure Audit Logs (Must be configured before creating MDS and Access Scan Definition)

To enable activity analysis for NetApp, you must configure audit logging on your NetApp instance.

> [!NOTE]
> **Note:**
> 
> - `vserver` commands must be run from the **NetApp ONTAP CLI**
> - `mkdir` and `ls` commands must be run on a **Unix/Linux system where the audit volume is mounted**

NetApp Audit Log Setup (CLI):

All logs from enabled shares on a single SVM are consolidated into a single audit log file within the designated audit log volume.

1. **Create the audit log destination folder in the SVM namespace** Ensure the path you will use for audit logs exists (example: /audit_logs) and does **not** contain symlinks.

```bash
mkdir /vol/audit_logs/netapp_logs
```

1. **Create the SVM audit configuration**

```bash
vserver audit create
  -vserver <svm_name> \
  -destination /vol/audit_logs/netapp_logs \
  -events file-ops,cifs-logon-logoff,cap-staging,file-share,user-account,security-group,authorization-policy-change,audit-policy-change,async-delete \
  -format xml
```

You must enable NetApp Audit logging to output in XML format. Securiti currently supports activity logs in XML format for Activity Analysis.

> [!NOTE]
> Note
> 
> IAM Intel’s NetApp integration uses ONTAP REST APIs in addition to SMB to retrieve local groups and group memberships. These APIs are only available starting with ONTAP 9.9. Earlier ONTAP versions (9.6 – 9.8) support share discovery and activity analysis but do not support group and membership retrieval. Full IAM Intel functionality requires ONTAP 9.9 or later.

1. **Enable auditing on the SVM**

```bash
vserver audit enable -vserver <svm_name>
```

1. **Configure an audit policy on the SMB path you want to monitor**

```bash
vserver security file-directory audit-policy create \
  -vserver <svm_name> \
  -path /share \
  -access-control success,failure
```

1. **Create an SMB share for the audit log destination (so Securiti can read logs).** Note : This is an optional step.

```bash
vserver cifs share create -vserver <svm_name> \
  -share-name NetApp_Audit_Share \
  -path /vol/audit_logs/netapp_logs \
  -share-properties admin-only
```

1. **Verify auditing + logs are being generated**

```bash
vserver audit show -vserver <svm_name>

ls -la /vol/audit_logs/netapp_logs/*.xml
```

> [!NOTE]
> Note (It’s optional)
> 
> Below is a sample command to verify on a system where the volume is mounted. In this case, we have a volume mounted to Windows.
> 
> ```bash
> ls Y:/audit_logs/*.xml
> ```

## Using Activity Analysis for SMB NetApp

Below are example use cases to familiarize you with how to leverage our Activity Explorer to identify activity of your users.

### Identify and report on users that have accessed Files within the specified Time

To filter the users that have accessed Files:

1. In Securiti , open Data Access Governance. From the left menu bar, under Activity Analysis click Activity Explorer. This will open the Activity Explorer page.
2. The Activity Explorer page presents you the data related to the activities that your users performed on the data system resources.
3. From the filter panel available on the top of the page, click Data System. Select the is one of operators. Select the Data System Connector instance that you configured for SMB NetApp . Click on the Apply button.
4. From the filter panel available on the top of the page, click Activity Action. Select the is one of operators. Select the File Accessed action.
5. Click on the Time filter, and specify the Before filter, and select Date and Time, For example, you want to identify the users that have accessed Files before 3rd March, 2025, 4:00 am.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000150830.png)

### Identify and report on users that have accessed Directory within the specified Time

1. In Securiti , open Data Access Governance. From the left menu bar, under Activity Analysis click Activity Explorer. This will open the Activity Explorer page.
2. The Activity Explorer page presents you the data related to the activities that your users performed on the data system resources.
3. From the filter panel available on the top of the page, click Data System. Select the is one of operators. Select the Data System Connector instance that you configured for SMB NetApp . Click on the Apply button.
4. From the filter panel available on the top of the page, click Activity Action. Select the is one of operators. Select the Directory Accessed action.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000151109.png)

### Viewing Most Active Users and Over-Privileged Users

For SMB NetApp:

- Most Active users are those user accounts that have accessed the SMB Shares most frequently in a selected period of time.
- Over-privileged users are the user accounts that have permissions (e.g., Read, Write, Full Control) on files and folders in the SMB Shares but have not accessed or interacted with that specific Share over a defined, substantial period (e.g.,30 days, 90 days, 180 days, etc.).

To view the Most Active users data:

1. In Securiti, open Data Access Governance. From the left navigation menu bar, click the Activity Analysis icon. Choose Most Active Users.
2. On the Most Active Users page, click the Data System filter available at the top. Select the Data System Connector instance that you configured for SMB NetApp . Click on the Apply button.
3. Open the Date Range filter at the top. Select the timeframe for which you want to identify which users have performed the most actions (e.g., Last 7 days), and click Apply. This will show you the list of most active users in the specified timeframe. This will show you the list of most active users in the specified timeframe. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled.png)
4. For any user displayed on the grid, click **Metadata Explorer** to see the Shares on which the selected user has performed the Actions.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1786000153056.png)

To view the Over-Privileged users data:

1. In Securiti, open Data Access Governance. From the left navigation menu bar, click Activity Analysis icon.
2. Choose Over-Privileged Users. This opens up the Over-Privileged Users page. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(2).png)
3. On the Over-Privileged Users page, click the Data System filter available at the top. Select the Data System Connector instance that you configured for SMB NetApp . Click on the Apply button. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(1).png)
4. You can see the count of shares to which users had access but did not make use of during the specified time period.
5. You can also see the list of users in the grid.

### **Identify users with direct and group-based access to Shares**

This query helps you identify users who have access to file Shares, including access granted directly and access inherited through group membership.

This ensures accurate visibility into indirect and direct user access to Shares.

### **To identify users with group-based access to Shares:**

1. In **Securiti**, open **Data Access Governance**
2. From the left navigation menu, choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Identity Provider** entity.
5. Click the three dots next to the **Identity Provider** entity, select **Add Property**, choose **Provider Type**, and select the required provider. Example: `NetApp`.
6. Click the three dots next to the **Identity Provider** entity, select **Add Relationship**, and choose **User Principal**.
7. Select the **Has** relationship.
8. Click the three dots next to **User Principal**, select **Add Relationship**, and choose **User Group Principal**.
9. Select the **Is Member Of** relationship.
10. Click the three dots next to **User Group Principal**, select **Add Relationship**, and choose **Resource Access**.
11. Select the **Has** relationship.
12. Click the three dots next to **Resource Access**, select **Add Relationship**, and choose **Files**.
13. Select the **Has Object** relationship.
14. Click **Apply**, and then click **Run Query**.
15. Click on the **User Principal** node to view users with direct and group-based access to Shares.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(7).png)

### **Default columns displayed in the data grid**

By default, the data grid displays identity and provider context for each user:

- Provider Name
- Provider Type
- Provider Account ID

### **Additional columns available in the data grid**

You can customize the data grid to include the following additional attributes for enhanced access analysis:

#### **User identity details**

- Display Name
- Organization

> [!NOTE]
> Note
> 
> Users returned as a part of above query should be present in Most Active or Over-privileged Users depending on the user actions on the scanned share.

### **Identify users who have access to a specific file**

This query helps you identify which users have access to a specific file and review detailed file metadata, access context, and governance attributes.

1. In **Securiti**, open **Data Access Governance** and choose **Data Command Graph**.
2. From the left navigation menu, click **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Files** entity.
5. Click the three dots next to the **Files** entity, select **Add Property**, choose **File Name**, and select **is one of**.
6. Enter the file name. Example: #Wire Tranfser_0.pdf
7. Click the three dots next to the **Files** entity, select **Add Relationship**, and choose **Resource Access**.
8. Click the three dots next to **Resource Access**, select **Add Relationship**, and choose **User Principal**.
9. Select the **Has Subject** relationship.
10. Click **Apply**, and then click **Run Query**.
11. Click on the **User Principal** node to view users who have access to the selected file.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(7).png)

**Default columns displayed in the data grid**

By default, the data grid displays high-level file and content metadata:

- File Name
- Cluster Name
- File Format
- Resource Path
- Data System Type
- Data Element
- Data Element Counts
- Content Profiles
- Exact Data Profile
- Resource URL

**Additional columns available in the data grid**

You can customize the data grid to include the following additional attributes for deeper access, classification, and governance analysis.

- Account Name
- Action
- Groups
- File Owner
- Sensitivity Label Name
- Version Of
- Resource Path
- Data Source Execution IDs
- Quarantine Processing Status

### **Identify all principals with access to a specific file and their privileges**

This query helps you identify all principals that have access to a specific file and review detailed metadata, access context, and governance attributes for the file.

**To identify principals with access to a specific file:**

1. In **Securiti**, open **Data Access Governance** and choose **Data Command Graph**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Files** entity.
5. Click the three dots next to the **Files** entity, select **Add Property**, choose **File Name**, and select **is one of**.
6. Enter the file name. Example: Item_CommonItem_Body.js.
7. Click the three dots next to the **Files** entity, select **Add Relationship**, and choose **Resource Access**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Resource Access** node to view access-related details for the selected file.

> [!NOTE]
> **Note**
> 
> The data grid also shows the origin of a file or folder's permissions as a path:
> 
> - If permissions are inherited, this path points to the share or folder where the permission was actually defined, which may be several levels up the hierarchy and not the immediate parent.
> - If inheritance is broken at a file or folder, this path points to the file or folder itself for all of its permissions, since it no longer receives updates from its parent.
> 
> If this information isn't available for files and folders that were already scanned, run a new Access Scan to see it for existing data.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 6(3).png)

**Default columns displayed in the data grid**

By default, the data grid displays high-level file and content metadata:

- File Name
- Cluster Name
- File Format
- Resource Path
- Data System Type
- Data Element
- Data Element Counts
- Content Profiles
- Exact Data Profile
- Resource URL

**Additional columns available in the data grid**

You can customize the grid to include the following additional attributes for deeper access and governance analysis:

- Account Name
- Action
- Groups
- O365 ID
- Checksum
- Evidence File Path
- Data System URN
- File Size
- Quarantine Processing Status

Access Intelligence is the insight into the users’ access to applications and data. This includes permissions and activity perfromed on data sources.

Privilege Analysis is a feature set of DAG Access Intelligence which ingests the Identity and Access Management (IAM) and Role Based Access Control (RBAC) metadata within your data systems and presents the data through a normalized knowledge graph allowing you to quickly identify who can access sensitive data, how that access is created, and who can administer that access within a data system.

Permissions refer to the minimum set of access details required to connect a data system with Securiti and allow scanning of data. Permissions could be of an administrative role where the user has all privileges to scan, share and access data, or it can be READ/WRITE only. Without the required permissions, data cannot be discovered or scanned for sensitive information.

You use discovery scan jobs to look for specific data elements distributed across different locations, and different data systems, on specific schedules and owners, etc. These discovery scans can be based on structured, streaming, or unstructured data systems.
