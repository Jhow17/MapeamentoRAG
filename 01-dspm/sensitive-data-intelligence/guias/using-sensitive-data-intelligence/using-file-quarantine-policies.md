---
title: "Using File Quarantine Policies"
slug: "using-file-quarantine-policies"
updated: 2026-09-22T12:04:27Z
published: 2026-09-22T12:04:27Z
canonical: "helpcenter.securiti.ai/using-file-quarantine-policies"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using File Quarantine Policies

**Scenario**

As a Data Security Officer, you are responsible for protecting your organization against data risks and ensuring compliance across connected systems. Manually identifying and isolating suspicious or non-compliant files across multiple data systems is time-consuming and increases the risk of exposure the longer action is delayed. With File Quarantine policies, you can isolate files that match your defined risk or compliance criteria, so you can respond faster, limit potential impact, and maintain a secure and compliant data environment.

## Overview

File Quarantine policies help you contain and mitigate risk by isolating files that violate your security or compliance requirements across connected data systems. You can use these policies to automatically identify and quarantine risky or non-compliant files based on defined conditions. This reduces manual effort, limits potential exposure, and helps you maintain a secure and compliant data environment.

You can also use File Quarantine policies to quarantine duplicate files across your data environment. Securiti runs a weekly scan that detects duplicate files across organizations and data systems within your tenant. Once the scan completes, you can use the `Is Duplicate=True` condition in a File Quarantine policy scope to locate the detected duplicates and quarantine them. Securiti detects duplicate files only within the selected organization and does not identify matching duplicate files in other organizations under the same tenant. The duplicate files you see in the results depend on your Graph Explorer organization settings. If your access is limited, you might not see all detected duplicates.

> [!NOTE]
> **Note**
> 
> - This policy does not work with the Securiti Sovereign, as it requires integration with the Data Command Graph.
> - File Quarantine policies support the multi-org feature. For more information, see [Changing your Organization.](/latest/docs/system-settings-managing-organizations)
> - The Data Inventory Sync for data system connectors must be enabled for your tenant to perform any action on File Quarantine policies.
> - Ensure the required permissions are enabled for your role. For more information, see [Sensitive Data Intelligence Roles and Permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions).
> - Before configuring a policy, run the required scans to gather metadata for identifying files that match your policy conditions. These may include Data Inventory Syncs, Discovery Scans, and Access Intelligence Scans.

## Key features of the File Quarantine policies

Securiti provides the following File Quarantine capabilities:

- **Auto-quarantine files**: Automatically isolates files that meet defined risk or compliance criteria, reducing the need for manual intervention.
- **Quarantine files on demand**: Allows you to manually quarantine files by enabling or disabling a File Quarantine policy.

This streamlined approach helps you quickly identify and secure sensitive data, such as first names, last names, SSNs, API secrets, and passwords within specific file types. It leverages previously scanned data, eliminating the need for redundant scans.

## Prerequisites for quarantining files

Before configuring a File Quarantine policy, ensure the following prerequisites are met:

- Enable the **Apply Quarantine Policy** option for the relevant data system.
- Configure the following settings for your data system connector during the connector configuration process.

| Data System | Settings |
| --- | --- |
| [Amazon S3](/latest/docs/amazon-s3-connectors-1) | - Enable the **Allow Quarantine actions on this Data System** setting on both the source and destination connectors. |
| [Azure Blob Storage](/latest/docs/azure-blob-storage-connectors) | - Enable the **Allow Quarantine actions on this Data System** setting on both the source and destination connectors. |
| [Azure Data Lake Storage (ADLS) Gen2](/latest/docs/azure-data-lake-storage-adls-gen2-connectors) | - Enable the **Allow Quarantine actions on this Data System** setting on both the source and destination connectors. |
| [Azure Files](/latest/docs/azure-files-connectors) | - Enable the **Allow Quarantine actions on this Data System** setting on both the source and destination connectors. |
| [Microsoft 365 OneDrive (self-hosted)](/latest/docs/microsoft-365-onedrive-connectors) | - Enable the **Allow Quarantine actions on this Data System** setting on both the source and destination connectors. |
| [Microsoft 365 SharePoint Online (self-hosted)](/latest/docs/microsoft-365-sharepoint-online-connectors) | - Enforce Selective site(s) access - Root domain for different regions - Enable the **Allow Quarantine actions on this Data System** setting on both the source and destination connectors. |
| [NFS (self-hosted)](/latest/docs/nfs-connectors) | - Evaluate data system size - Enable the **Allow Quarantine actions on this Data System** setting on both the source and destination connectors. |
| [SMB (self-hosted)](/latest/docs/smb-connectors) | - Evaluate data system size - Enable the **Allow Quarantine actions on this Data System** setting on both the source and destination connectors. |
- Configure a separate folder for quarantined files. The quarantine folder must not be a child directory of the source (main) share.
- Enable Read, Write, and Delete (RWD) permissions on both the source and destination data systems. Permission requirements may vary by connector. For example, Microsoft SharePoint Online includes delete capabilities as part of Microsoft WRITE permissions rather than as a separate delete permission.
- To view the files within the source and destination folders for SharePoint, OneDrive, NFS, and SMB, use the folder path and the destination folder path.

## Supported data system types

You can create a File Quarantine policy for the following data system types:

- [Amazon S3](/latest/docs/amazon-s3-connectors-1) (self-hosted)
- [Azure Data Lake Storage (ADLS) Gen2](/latest/docs/activate-the-azure-data-lake-storage-adls-gen2-connector-in-securiti)
- [Azure Blob Storage](/latest/docs/azure-blob-storage-connectors) (self-hosted)
- [Azure Files](/latest/docs/azure-files-connectors) (self-hosted)
- [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors) (self-hosted)
- [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors) (self-hosted)
- [NFS](/latest/docs/nfs-connectors) (self-hosted)
- [SMB](/latest/docs/smb-connectors) (self-hosted)

If you enable Hyperdrive mode, you can create a File Quarantine policy only for the following data systems:

- [Amazon S3](/latest/docs/amazon-s3-connectors-1) (self-hosted)
- [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors) (self-hosted)
- [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors) (self-hosted)
- [NFS](/latest/docs/nfs) (self-hosted)
- [SMB](/latest/docs/smb-connectors) (self-hosted)

For more information, see [Using File Quarantine policies with Hyperdrive mode](/latest/docs/using-quarantine-policies-with-hyperdrive-mode).

## Interactive demos

This click-through demo show how to perform actions step by step. Click the **Start Demo** button to begin. Then, click the **Next** button or use the **right arrow** key on your keyboard to proceed, and the **left arrow** key to go back. This demo may include screens from multiple features to illustrate the complete procedure.

### File Quarantine policy for SharePoint Online files

See how Securiti lets you create a File Quarantine policy to quarantine sensitive files in Microsoft 365 SharePoint Online, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/o0l24shauq2b?embed=popup)

### 

1. 

> [!NOTE]
> Note
> 
> To see more demos related to policies, refer to the following help center articles:
> 
> - [Interactive Demos: Discover and Classify Sensitive Data for AWS](/latest/docs/sensitive-data-intelligence-interactive-demos)
> - [Interactive Demos: Discover and Classify Sensitive Data for GCP](/latest/docs/interactive-demos-discover-and-classify-sensitive-data-for-gcp)
> - [Interactive Demos: Discover and Classify Sensitive Data for SharePoint Online](/latest/docs/policies-2)

## Using the File Quarantine policies page

The File Quarantine **Policies** page lets you manage and analyze your policies effectively.

- Use the top filters to view policies by **Date Created**, **Data Modified**, **Policy ID**, **Policy Name** and **File Owner**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BZVV7EL9.png)
- You can view the total number of File Quarantine policies and the active policies, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Y0N6PJ02.png)
- Use the **Column Selector** to include or exclude columns such as **Policy ID**, **Policy Name**, **Files**, **Total Volume**, and so on, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6YO85KJF.png)
- Use the **Status** toggle to activate or deactivate a policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-QY5P7GTE.png)
- Click **Files** under the **Data Scope** column to view scoped files in **Graph Explorer**, as shown below. For more information, see [Using Data Command Graph](https://helpcenter.securiti.ai/docs/using-data-command-graph). ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FZP1DFBI.png)
- Click **Show Policy Metadata** and select **Explore** to view file relationships in **Graph Explorer**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-9ZCBKD7F.png)
- From the options menu (the three dots) on the right side of a policy entry, you can view, edit, clone, or delete the policy, view it in the dashboard, or check its activity, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-M7YE4XHM.png)

> [!NOTE]
> Note
> 
> You can cancel File Quarantine policies only when they are in the **Running** state, as shown below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TH82VSRK.png)
- Drag the column resize handle to view complete information in any column, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-13 at 5.26.21 PM.png)
