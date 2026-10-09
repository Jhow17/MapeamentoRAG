---
title: "Using File ROT Policies"
slug: "using-file-rot-policies"
updated: 2026-09-22T12:05:17Z
published: 2026-09-22T12:05:17Z
canonical: "helpcenter.securiti.ai/using-file-rot-policies"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using File ROT Policies

**Scenario**

As a Data Security Officer, you are responsible for managing data lifecycle and ensuring your organization retains only what is necessary. Over time, redundant, obsolete, and trivial (ROT) files accumulate across multiple data systems, driving up storage costs and increasing the risk of retaining sensitive data beyond its required lifecycle. With File ROT policies, Securiti lets you detect and act on ROT data based on defined retention and lifecycle criteria, so you can minimize risk, reduce storage overhead, and stay compliant with data retention regulations.

## Overview

File ROT policies help you identify and manage redundant, obsolete, or trivial (ROT) files across connected data systems by applying retention and lifecycle rules. You can use these policies to automatically detect files that no longer need to be retained based on insights derived from scans and Data Command Graph queries. This helps you reduce storage costs, minimize risk from over-retained data, and simplify data lifecycle management across your organization.

You can also use File ROT policies to remediate duplicate files across your data environment. Securiti runs a weekly scan that detects duplicate files across organizations and data systems within your tenant. Once the scan completes, you can use the `Is Duplicate=True` condition in a File ROT policy scope to locate the detected duplicates and remediate them based on your policy configuration. Securiti detects duplicate files only within the selected organization and does not identify matching duplicate files in other organizations under the same tenant. The duplicate files you see in the results depend on your Graph Explorer organization settings. If your access is limited, you might not see all detected duplicates.

## Prerequisites

- This policy does not work with the Securiti Sovereign, as it requires integration with the Data Command Graph.
- The Data Inventory Sync for data system connectors must be enabled for your tenant to perform any action on File ROT policies.
- Ensure the required permissions are enabled for your role. For more information, see [Sensitive Data Intelligence Roles and Permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions).
- Before configuring a policy, run the required scans to gather metadata for identifying files that match your policy conditions. These may include Data Inventory Syncs, Discovery Scans, and Access Intelligence Scans.

## Supported data system types

You can create a File ROT policy for the following data system types:

- [Amazon S3](/latest/docs/amazon-s3-connectors-1) (self-hosted)
- [Azure Data Lake Storage (ADLS) Gen2](/latest/docs/activate-the-azure-data-lake-storage-adls-gen2-connector-in-securiti)
- [Azure Blob Storage](/latest/docs/azure-blob-storage-connectors) (self-hosted)
- [Azure Files](/latest/docs/azure-files-connectors) (self-hosted)
- [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors) (self-hosted)
- [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors) (self-hosted)
- [NFS](/latest/docs/nfs) (self-hosted)
- [SMB](/latest/docs/smb-connectors) (self-hosted)

If you enable Hyperdrive mode, you can create a File ROT policy only for the following data systems:

- [Amazon S3](/latest/docs/amazon-s3-connectors-1) (self-hosted)
- [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors) (self-hosted)
- [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors) (self-hosted)
- [SMB](/latest/docs/smb-connectors) (self-hosted)

For more information, see [Using File ROT policies with Hyperdrive mode](/latest/docs/using-file-rot-policies-with-hyperdrive-mode).

## Key capabilities

File ROT policies support robust data lifecycle and retention strategies using relative date operators in **Data Command Graph** queries. You can define policies based on attributes such as, file creation date, last modified date, last accessed date. For example, you can identify files that are older than a specific number of months or years and no longer required for business, legal, or regulatory purposes.

By default, retention policies of 1,3,5 and 7 years are provided out of the box, as shown below. These retention policies align with common data retention and disposal regulations such as SOX and FLSA, which require data to be preserved for a prescribed time period before being deleted. These policies help automate the identification and disposal of obsolete data without manually creating new rules. You can use the default policies as they are or clone them to create customized versions.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image4.png)

## Interactive demos

These click-through demos show how to perform actions step by step. Click the **Start Demo** button to begin. Then, click the **Next** button or use the **right arrow** key on your keyboard to proceed, and the **left arrow** key to go back. These demos may include screens from multiple features to illustrate the complete procedure.

### File ROT policy for SharePoint Online files

See how Securiti lets you create a File ROT policy to identify and manage redundant, obsolete, and trivial files in Microsoft 365 SharePoint Online, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/klud2lmitehh?embed=popup)

> [!NOTE]
> Note
> 
> To see more demos related to policies, refer to the following help center articles:
> 
> - [Interactive Demos: Discover and Classify Sensitive Data for AWS](/latest/docs/sensitive-data-intelligence-interactive-demos)
> - [Interactive Demos: Discover and Classify Sensitive Data for GCP](/latest/docs/interactive-demos-discover-and-classify-sensitive-data-for-gcp)
> - [Interactive Demos: Discover and Classify Sensitive Data for SharePoint Online](/latest/docs/policies-2)

## Using the File ROT policies page

The File ROT **Policies** page lets you manage and analyze your policies effectively.

- Use the top filters to view policies by **Date Created**, **Data Modified**, **Policy ID**, **Policy Name**, **File Owner** and **Status**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SXVGJKQQ.png)
- You can view the total number of File ROT policies and the active policies, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VAHGXENZ.png)
- Use the **Column Selector** to include or exclude columns such as **Policy ID**, **Policy Name**, **Files**, **Total Volume**, and so on, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-81VZ9TFR.png)
- Use the **Status** toggle to activate or deactivate a policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VC8ROBW5.png)

> [!NOTE]
> Note
> 
> You can now enable or disable system-defined ROT policies regardless of their current response or status.
- Click **Files** under the **Data Scope** column to view scoped files in **Graph Explorer**, as shown below. For more information, see [Using Data Command Graph](/latest/docs/using-data-command-graph). ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8QWE13RR.png)
- Click **Show Policy Metadata** and select **Explore** to view file relationships in **Graph Explorer**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-9UPRA4QR.png)
- From the options menu (the three dots) on the right side of a policy entry, you can view, edit, clone, or delete the policy, view it in the dashboard, or check its activity, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VM5ULP9R.png)

> [!NOTE]
> Note
> 
> You can cancel File ROT policies only when they are in the **Running** state, as shown below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XO02YULG.png)
- Drag the column resize handle to view complete information in any column, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-13 at 7.01.39 PM.png)
