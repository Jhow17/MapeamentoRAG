---
title: "Using Data Labeling Policies"
slug: "using-data-labeling-policies"
updated: 2026-09-24T02:56:25Z
published: 2026-09-24T02:56:25Z
canonical: "helpcenter.securiti.ai/using-data-labeling-policies"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using Data Labeling Policies

**Scenario**

As a Data Governance Officer, you're responsible for making sure sensitive files carry the right classification label across your Microsoft 365 environment. Applying labels manually, file by file, doesn't scale once your data spans thousands of files, and any gap in labeling leaves sensitive data unprotected and out of compliance. With a Data Labeling policy, you define the scope once, and the policy automatically applies the matching Microsoft Purview label to new files as they're discovered. For example, the policy periodically labels every file containing financial records as Confidential. This keeps your labeling consistent without manual review.

> [!WARNING]
> Important
> 
> Securiti has deprecated data labeling V1 (rule based) policies. Existing V1 policies remain view-only, and you cannot create, edit, deactivate, or run V1 labeling policies.
> 
> All new data labeling policies must be created using V2 (graph query based) policies. If you need to update a labeling rule, recreate the policy as a new V2 labeling policy by referencing the configuration of the existing V1 policy.

After classification detection is complete, you can use the identified information to apply sensitivity labels to files and documents using tools such as [Microsoft Purview Information Protection (MIP)](/latest/docs/microsoft-purview-information-protection-connectors) and [Google Drive](https://developers.google.com/drive/api/guides/about-labels). This helps enforce data protection policies and maintain compliance based on the classification results.

Data Labeling policies leverage data discovery and classification insights, along with integrations with Microsoft Purview Information Protection (MIP) or Google Drive to automate the application of sensitivity labels and metadata across your unstructured data systems. These labels act as informative tags that provide additional context about the type of sensitive data within your files. For example, indicating whether a document belongs to a financial category.

To improve efficiency in subsequent policy runs, only files that have been modified are re-labeled. This targeted approach reduces processing time, eliminates redundant operations, and ensures labeling remains accurate and up to date.

Overall, this process helps train models to recognize and manage sensitive information, supports compliance with data protection regulations, and enhances overall data security.

> [!CAUTION]
> Warning
> 
> The Data Inventory Sync for data system connectors must be enabled for your tenant to perform any action on Data Labeling policies.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Data Labeling-Design.drawio(1).svg)

## Interactive demos

These click-through demos show how to perform actions step by step. Click the **Start Demo** button to begin. Then, click the **Next** button or use the **right arrow** key on your keyboard to proceed, and the **left arrow** key to go back. These demos may include screens from multiple features to illustrate the complete procedure.

### Data Labeling policy for AWS files

See how Securiti lets you create a Data Labeling policy to apply sensitivity labels to discovered AWS files, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/vdtfcx7fsp4j?embed=inline)

### Data Labeling policy for SharePoint Online files

See how Securiti lets you create a Data Labeling policy to apply sensitivity labels to discovered Microsoft 365 SharePoint Online files, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/ehv5k8og4ump?embed=inline)

### Data Labeling policy for Google Drive files

See how Securiti lets you create a Data Labeling policy to apply sensitivity labels to discovered Google Drive presentation files, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/rj5canqrw5f2?embed=inline)

> [!NOTE]
> Note
> 
> To see more demos related to policies, refer to the following help center articles:
> 
> - [Interactive Demos: Discover and Classify Sensitive Data for AWS](/latest/docs/sensitive-data-intelligence-interactive-demos)
> - [Interactive Demos: Discover and Classify Sensitive Data for GCP](/latest/docs/interactive-demos-discover-and-classify-sensitive-data-for-gcp)
> - [Interactive Demos: Discover and Classify Sensitive Data for SharePoint Online](/latest/docs/policies-2)

## Supported data system types

You can create a Data Labeling policy for the following data system types:

- **Google Drive**
  - [G Suite Google Drive](/latest/docs/g-suite-google-drive-connectors) (self-hosted)

- **Microsoft Purview Information Protection (MIP)**
  - [Amazon S3](/latest/docs/amazon-s3-connectors-1) (self-hosted)
  - [Azure Blob Storage](/latest/docs/azure-blob-storage-connectors) (self-hosted)
  - [Azure Files](/latest/docs/azure-files-connectors) (self-hosted)
  - [Box](/latest/docs/box-connectors) (self-hosted)
  - [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors) (self-hosted)
  - [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors) (self-hosted)
  - [NFS](/latest/docs/nfs-connectors) (self-hosted)
  - [Securiti for Box](/latest/docs/securiti-for-box-connector) (self-hosted)
  - [SMB](/latest/docs/smb-connectors) (self-hosted)

If you enable Hyperdrive mode, you can create a Data Labeling policy only for the following data systems:

- [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors) (self-hosted)
- [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors) (self-hosted)
- [NFS](/latest/docs/nfs-connectors) (self-hosted)
- [SMB](/latest/docs/smb-connectors) (self-hosted)

For more information, see [Using Data Labeling policies with Hyperdrive mode](/latest/docs/using-data-labeling-policies-with-hyperdrive-mode-1).

## Prerequisites

- To collect the metadata in the graph for use in data labeling policies, you must create and run a Discovery Scan before configuring data labeling policies. For more information, see:
  - [Discovery scans](/latest/docs/discovery-scans).
- Review the prerequisites for Microsoft and Google labeling policies on their respective documentation pages. For more information, see:
  - [Creating a Data Labeling Policy for Google Drive](/latest/docs/creating-data-labeling-policy-for-google-drive-files)
  - [Creating a Data Labeling Policy for Microsoft Purview Information Protection](/latest/docs/creating-data-labeling-policy-for-microsoft-purview)
- The connector used as the data source must have the permissions required for data labeling. These permissions vary by connector

| Data system type | Permissions |
| --- | --- |
| G Suite Google Drive | You must enable the **Turn Labels On** option from the Google admin console to apply labels to Google Drive files. Assign the following OAuth scopes: To read labels: - `https://www.googleapis.com/auth/drive.labels.readonly` - `https://www.googleapis.com/auth/drive.admin.labels.readonly` To create labels: - `https://www.googleapis.com/auth/drive.labels` - `https://www.googleapis.com/auth/drive.admin.labels` To apply labels: - `https://www.googleapis.com/auth/drive.metadata` For more information, see [Google Drive](/latest/docs/google-drive-google-workspace). |
| Amazon S3 | Assign the following permissions to Amazon S3 objects: - `s3:GetObject` (to download files) - `s3:PutObject` (to upload files) - `s3:PutObjectTagging` (to label files) For more information, see [Amazon S3](/latest/docs/amazon-s3-connectors-1). |
| Azure Blob Storage | Assign the following roles for Service Principal authentication (with or without certificate): - Storage Blob Data Contributor (to read and write blob data) - Storage Blob Data Reader (to read blob data) For more information, see [Azure Blob Storage](/latest/docs/azure-blob-storage-connectors). |
| Azure Files | Assign the following roles for Service Principal authentication: - Storage File Data Privileged Reader (to read file data) - Storage File Data Privileged Contributor (to read and write file data) For more information, see [Azure Files](/latest/docs/azure-files-connectors). |
| Box | Assign the following permissions in the application scope: - Read all files and folders stored in Box - Write all files and folders stored in Box For more information, see [Box](/latest/docs/box-connectors) |
| Microsoft 365 OneDrive | Assign the following Microsoft Graph API application permissions: - `Files.ReadWrite.All` (to read and write files) - `Sites.ReadWrite.All` (to read and write site content) For more information, see [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors). |
| Microsoft 365 SharePoint Online | Assign the following Microsoft Graph API application permissions: - `Files.ReadWrite.All` (to read and write files) - `Sites.ReadWrite.All` (to read and write site content) For more information, see [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors). |
| NFS | You must have read/write permissions on the relevant container from the admin. For more information, see [NFS](/latest/docs/nfs-connectors). |
| Securiti for Box | You must have a Box administrator account and accept Custom Terms of Service (ToS). For more information, see [Securiti for Box](/latest/docs/securiti-for-box-connector). |
| SMB | Assign the following permissions: - Share permission: Change - NTFS/File-level permission: Read and Write These permissions let Securiti view, manage, and apply labels to files on SMB shares. With these permissions, you can apply the Data Labeling Policy to your files. For more information, see [SMB](/latest/docs/smb-connectors). |

## Using the Data Labeling policies page

The data labeling **Policies** page lets you manage and analyze your policies effectively.

- Use the top filters to view policies by the following properties:
  - Date Scope
  - Date Created
  - Date Modified
  - File Owner
  - Policy ID
  - Policy Name
  - Status ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1X3S1CDE.png)
- You can view the total number of data labeling policies, the active policies, and the files labeled as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-85A01544.png)
- Use the **Column Selector** to include or exclude columns such as **Policy ID**, **Policy Name**, **Data Scope**, **Status**, and so on, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-D300PHHD.png)
- Use the **Status** toggle to activate or deactivate a policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-98X6OENA.png)

> [!NOTE]
> Note
> 
> You can not perform any action on a data labeling policy while it is in the running or scheduled state. If you try to disable an active policy, Securiti displays the message **Cannot disable policy while it is running**, as shown below. This restriction applies only to the policy currently in progress.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GB8YSZJ7.png)
- Click **Files** under the **Data Scope** column to view scoped files in **Graph Explorer**, as shown below. For more information, see [Using Data Command Graph](/latest/docs/using-data-command-graph). ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OROPCTXJ.png)
- Click **Show Policy Metadata** and select **Explore** to view file relationships in **Graph Explorer**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OFKZ1EN0.png)
- From the options menu (three dots) on the right side of a policy entry, you can **View**, **Edit**, **Clone**, **Cancel**, or **Delete** the policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZMCLODLY.png)

> [!NOTE]
> Note
> 
> You can cancel Data Labeling policies only when they are in one of the following states:
> 
> • Running
> 
> • Scheduled
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image2(5).png)
- Drag the column resize handle to view complete information in any column, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-29 at 7.04.58 PM.png)
