---
title: "Creating a Data Labeling policy for Microsoft Purview Information Protection"
slug: "creating-data-labeling-policy-for-microsoft-purview"
updated: 2026-10-01T05:54:44Z
published: 2026-10-01T05:54:44Z
canonical: "helpcenter.securiti.ai/creating-data-labeling-policy-for-microsoft-purview"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Creating a Data Labeling policy for Microsoft Purview Information Protection

> [!WARNING]
> Important
> 
> Securiti has deprecated data labeling V1 (rule based) policies. Existing V1 policies remain view-only, and you cannot create, edit, deactivate, or run V1 labeling policies.
> 
> All new data labeling policies must be created using V2 (graph query based) policies. If you need to update a labeling rule, recreate the policy as a new V2 labeling policy by referencing the configuration of the existing V1 policy.

**Scenario**

As a Data Security Officer, you need to ensure that sensitive files are correctly labeled across the organization. Manually reviewing documents is time-consuming and increases the risk of overlooking sensitive data. With content profile–based auto-labeling policies, sensitivity labels are applied automatically and accurately without constant manual oversight. This reduces compliance risks, minimizes operational effort, and ensures sensitive information is consistently protected at scale.

## Overview

Securiti Data Labeling policy integrates with [Microsoft Purview Information Protection (MIP)](/latest/docs/microsoft-purview-information-protection-connectors) to let organizations define data labeling policies based on data discovery and classification results. These policies let you scope files precisely and automatically apply sensitivity labels and metadata, helping identify sensitive information and strengthening Data Loss Prevention (DLP) efforts to ensure secure data handling across the organization.

The Microsoft Purview Information Protection (MIP) Data Labeling policy allows policy creation by defining data scope through queries executed in the Data Command Graph. During policy configuration, you can fully leverage the Data Command Graph’s capabilities to tailor the data scope to specific requirements. Additionally, a single policy can apply multiple sensitivity labels based on different scope conditions, enabling more granular, accurate, and flexible data protection.

> [!NOTE]
> Note
> 
> - Data Labeling policies do not run on a fixed schedule. After the initial execution, policies are triggered only when new data is discovered. The time required to complete labeling depends on several factors, including system load, data volume, and policy complexity. Under light system load with a small number of files, labeling may complete almost instantly. In contrast, under heavy load or when processing large datasets, labeling can take anywhere from several minutes to several hours.
> - Existing Data Labeling policies are automatically triggered after a discovery scan completes, provided the discovered data matches the content profile defined in the policy.
> - Data Labeling policies are available as part of the DSPM Enterprise + package and are only available to customers with this subscription.
> - Securiti does not support Microsoft Purview Information Protection (MIP) sensitivity labels that have access control enabled.

## Supported data system types

You can create a data labeling policy for the following data system types:

- [Amazon S3](/latest/docs/amazon-s3-connectors-1) (Self Hosted Pod Connector)
- [Azure Blob Storage](/latest/docs/azure-files-connectors) (Self Hosted Pod Connector)
- [Azure Files](/latest/docs/azure-files-connectors) (Self Hosted Pod Connector)
- [Box](/latest/docs/box-connectors) (Self Hosted Pod Connector)
- [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors) (Self Hosted Pod Connector)
- [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors) (Self Hosted Pod Connector)
- [NFS](/latest/docs/nfs-connectors) (Self Hosted Pod Connector)
- [Securiti for Box](/latest/docs/securiti-for-box-connector) (Self Hosted Pod Connector)
- [SMB](/latest/docs/smb-1) (Self Hosted Pod Connector)

> [!NOTE]
> Note
> 
> After Securiti applies or updates a Microsoft Purview Information Protection (MIP) label, the file's Last Modified timestamp behavior varies by data system.
> 
> 
> 
> **Preserved timestamp**
> 
> For the following data systems, Securiti preserves the file's Last Modified timestamp. After Securiti applies the label, the Last Modified timestamp reverts to the timestamp captured before labeling in near real-time.
> 
> - SMB
> - NFS
> - Microsoft 365 OneDrive
> - Microsoft 365 SharePoint Online
> 
> **Non-preserved timestamp**
> 
> For all other data systems, Securiti does not preserve the file's Last Modified timestamp. After Securiti applies the label, the Last Modified timestamp updates to reflect the time the label was applied. Securiti records and displays the updated timestamp after the next Discovery Scan.

## Prerequisites

- To collect the metadata in the graph for use in data labeling policies, you must create and run a Discovery Scan before configuring data labeling policies. For more information, see:
  - [Discovery scans](/latest/docs/discovery-scans).
- You must connect the Microsoft Purview Information Protection (MIP) data system connector with Securiti to import Microsoft Purview Information Protection (MIP) labels. For more information, see [Microsoft Purview Information Protection (MIP)](/latest/docs/microsoft-purview-information-protection-connectors).
- You must have an active pod version 1.136.0 and above if a data system is configured. For MIP policies, note that if the pod version is below 1.141.0, only successful labeling results are reported back to Securiti. In this case, the status updates from processing labeling to labeling completed only for successful files. In case of skipped and failed documents, only policy log is published and will continue to appear as processing labeling on the dashboard. For more information, see [Pods (cluster version v1.28 and later)](/latest/docs/pods-deployment).
- Ensure the required permissions are enabled for your role. For more information, see [Sensitive Data Intelligence Roles and Permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions).
- You must ensure outbound connectivity requirements are met for Microsoft Purview Information Protection (MIP) labeling by allowlisting required endpoints.

### Core MIP and Azure Rights Management System endpoints (Policy and Protection)

| Sr.No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | HTTPS | `*.protection.outlook.com` | This endpoint is used for downloading sensitivity labels, rules, and policy configurations via the Microsoft Information Protection (MIP) Policy SDK. |
| 2 | HTTPS | `*.protection.office365.com` | This endpoint is used for legacy policy synchronization. |
| 3 | HTTPS | `*.aadrm.com` | This endpoint is used for Azure RMS operations including licensing, encryption, and decryption. |
| 4 | HTTPS | `*.azurerms.com` | This endpoint is used for accessing regional Azure RMS services to support data residency and compliance requirements. |
| 5 | HTTPS | `*.informationprotection.azure.com` | This endpoint is used for accessing the Azure Information Protection unified labeling backend. |
| 6 | HTTPS | `informationprotection.hosting.portal.azure.net` | This endpoint is used for app portal access and management console integration. |
| 7 | HTTPS | `ecn.dev.virtualearth.net` | This endpoint is used for geolocation-based routing to the nearest Azure RMS cluster. |

### Identity, Telemetry, and Configuration endpoints

| Sr.No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | HTTPS (OAuth2) | `login.microsoftonline.com` | This endpoint is used for Azure AD authentication and token acquisition. |
| 2 | HTTPS | `login.windows.net` | This endpoint is used for legacy Azure AD authentication fallback. |
| 3 | HTTPS API | `graph.microsoft.com` | This endpoint is used for accessing Microsoft Graph APIs to retrieve user and compliance data. |
| 4 | HTTPS | `*.events.data.microsoft.com` | This endpoint is used for telemetry and diagnostic data collection. |
| 5 | HTTPS | `*.aria.microsoft.com` | This endpoint is used for compliance audit telemetry collection, including Microsoft Information Protection (MIP) Activity Explorer data. |
| 6 | HTTPS | `*.office.com` | This endpoint is used for accessing Microsoft 365 frontend services and handling authentication redirection. |

### Sovereign and Regional Cloud endpoints

| Region | Sr.No | Method | URL | Purpose |
| --- | --- | --- | --- | --- |
| China Cloud (21Vianet) | 1 | HTTPS | `*.protection.partner.outlook.cn` | This endpoint is used for downloading policy and label configurations. |
| 2 | HTTPS | `*.aadrm.cn` | This endpoint is used for Azure RMS protection services, including data protection and rights management. |
| US Gov GCC High | 3 | HTTPS | `*.aadrm.us` | This endpoint is used for Azure RMS protection and licensing operations. |
| 4 | HTTPS | `*.informationprotection.azure.us` | This endpoint is used for accessing the unified labeling backend. |
| US Gov Department of Defense | 5 | HTTPS | `*.protection.apps.mil` | This endpoint is used for dedicated labeling and protection operations. |
| 6 | HTTPS | `*.protection.office365.us` | This endpoint is used for accessing policy data services. |

## Creating a Data Labeling policy for Microsoft Purview Information Protection

To create a data labeling policy for Microsoft Purview Information Protection (MIP):

1. From the main menu, choose **Policies**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-URFR8B76.png)
2. On the **Policies** page, choose **Data Labeling**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-18UBBBVR.png)
3. Near the upper right corner of the page, click **+ Create**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XRGEDWIA.png)
4. In the **Create a New Policy** popup, select the **Policy Type** and **Data System** **Type**, as shown below, and click **Get Started**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8YAJFO8C.png)
5. Enter a **Name** and **Description** for the policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-M6MHJL04.png)
6. Set the policy **Owner**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XCCWB0QD.png)
7. (Optional) Set the policy **co-owners**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-9T5BOI6D.png)
8. To activate the Data Labeling policy, turn on the **Activate Policy** toggle, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8T1K1XU0.png)
9. Securiti automatically chooses the **Integration type** based on the data system selected in the **Create a New Policy** popup.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-80AMNLHC.png)
10. In the **Scope** section, click **Edit Query** to add files to your scope, as shown below. This opens the **Graph Explorer**, where you can select the file scope and relevant data elements (such as first name, last name, SSN, and so on). Review the query results carefully to ensure the scoped files match your expectations. Then click **Use Query** to apply the selection. The scope is now defined, and you are returned to the data labeling policy configuration page. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-WJZ81AMN.png)

To learn more about **Graph Explorer**, see the [Graph Explorer](/latest/docs/using-graph-explorer) documentation. Securiti can automatically carry over queries created in Graph Explorer to the policy creation page. For more information, see [Create policies using Graph Explorer](/latest/docs/create-policies-using-graph).
  - You can add the **Files** node as a secondary node when configuring the scope query, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-JN6ASQGD.png)

> [!NOTE]
> Note
> 
> By default, Securiti applies a `Skipped = False` filter to the scope query in Data Labeling policies. This filter excludes files marked as **Skipped** from the policy scope and prevents them from being labeled.
11. To view the number of files included in the scope, click **Show Impact** in the **Scope** section, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-T0P1MW6F.png)
12. In the Actions section, click **+ Add Actions**, as shown below. You can add one or both of the following actions to the policy:

### Applying a classification label

### Sending an email notification

The **Send an Email Notification** action lets you notify the data system owner, selected users, or both, with a summary of how many files were skipped, failed, or successfully labeled by the Data Labeling policy.
  - **Apply a Classification Label**: Applies a sensitivity label and metadata to the files in scope, based on their classification results.
  - **Send an Email Notification**: Notifies the policy owner or specific users by email about policy events, changes, or activities.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-YS5OF5EF.png)
  1. To apply a classification label, click **Edit,** as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IEB9FJPQ.png)
  2. (Optional) Mark the **Apply a specific label directly to all files** option to assign a single label to all scoped files, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Q2ZW6ODE.png)
  3. (Optional) Click **+ Add** to configure **Content Profile Mapping** or **Data Element Mapping**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-UQ8WJYH3.png)
    1. Choose one or more **Content Profile(s)** and assign **Sensitivity Label(s)**, as shown below. The **Content Profiles** with higher sensitivity labels are given preference, so the sequence of content profiles selected does not matter. When selecting **Content Profile(s)** you can also choose **Any** or **None**:
      - **Any:** Applies the **Sensitivity Label** if any content profile matches the document. When **Any** is selected, only one mapping is allowed in the policy.
      - **None:** Applies the **Sensitivity Label** if no content profile is matched on the document.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-M8ENL84F.png)
    2. Choose one or more **Data Elements(s)** and assign **Sensitivity Label(s)**, as shown below. The **Data Element(s)** with higher sensitivity labels are given preference, so the sequence of data elements selected does not matter. When selecting **Data Elements(s)** you can also choose **Any** or **None**:
      - **Any:** Applies the **Sensitivity Label** if any data element matches the document. When **Any** is selected, only one mapping is allowed in the policy.
      - **None:** Applies the **Sensitivity Label** if no data element is matched on the document.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Y2TW06WW.png)

> [!NOTE]
> Note
> 
> There is no limit to the number of content profiles and data elements you can add.
  4. There are two **Labeling Options** available:

| Labeling Options | Description |
| --- | --- |
| **Auto Labeling** | Automatically applies sensitivity labels to files when the policy runs. - **Set Scheduler Time:** Specifies the time of day for scheduled auto-labeling in UTC using a 24-hour format (for example, 10:00 or 22:00). If left empty, the policy runs daily at the time the schedule is saved. |
| **Override already applied labels** | Replaces existing sensitivity labels on files with the new labels the policy applies. When the policy runs, Securiti reads each file's current label at run time and uses it as the existing label. This check happens independently of whether Securiti ingests existing sensitivity labels during a discovery scan or data inventory sync, so the policy always has the latest label information when deciding whether to label the file. Securiti uses this label for the following controls: - **Skip if the new label lowers sensitivity:** Prevents the policy from replacing an existing label if the new label represents a lower sensitivity level. - **Skip manually labeled files:** Prevents the policy from overriding labels that were applied manually by a user. When **Skip manually labeled files** is enabled, Securiti skips all labels that have the assignment method `Privileged` . |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-LS830COU.png)
  5. You can also apply additional **File Metadata** such as, **Data Element Categories**, **Data Element Types**, **Document Categories**, **Document Types**, and so on, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SP2ZGGU5.png)
  6. You can also apply **Custom** **File Metadata** by entering a **Custom Key** and its **Value**, as shown below.

> [!WARNING]
> Important
> 
> For the following file formats, Securiti sanitizes **Custom File Metadata** values before applying them. It truncates values to 255 characters and replaces spaces with underscores.
> 
> - `.png`
> - `.jpg`
> - `.jpeg`
> - `.jpe`
> - `.jif `
> - `.jfif`
> - `.jfi`
> - `.tif`
> - `.tiff`
> - `.txt`
> - `.csv`
> - `.tsv`
> - `.json`
> - `.xml`
> - `.yaml`
> - `.yml`
> - `.md`
> - `.log`
> - `.doc`
> - `.dot`
> - `.ppt`
> - `.pps`
> - `.xls`
> - `.xlt`

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OVJDLX31.png)
  1. To send an email notification, click **+ Add Actions** and choose **Send an Email Notification**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-A5OCI64O.png)
  2. (Optional) In the **Send an Email Notification** popup, mark the **Notify store owner** checkbox to send an email notification to the policy owner, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VZRQRCKB.png)
  3. (Optional) To notify additional users, enter their username or email address in the search field and select them from the list. Each added user appears as a tag below the field, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PBTCXBXG.png)
  4. Click **Save Action**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CM4A2JJ7.png)
13. Click **Create Policy.** Once created, the policy appears on the data labeling **Policies** page, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-54GUXL78.png)

## Related

- [Viewing and syncing Microsoft Purview Information Protection sensitivity labels](/viewing-and-syncing-classification-labels.md)
