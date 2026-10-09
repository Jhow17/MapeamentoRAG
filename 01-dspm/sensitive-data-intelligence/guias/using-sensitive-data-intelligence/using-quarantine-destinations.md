---
title: "Using Central Quarantine Destination"
slug: "using-quarantine-destinations"
updated: 2026-08-06T10:10:14Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/using-quarantine-destinations"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using Central Quarantine Destination

## 

**Scenario**

Your data governance team requires a centralized place for temporary storage of files that have been quarantined, regardless of the source data systems.

By enabling the Central Quarantine, all quarantined files can be moved to a central destination. Teams can review, audit, and manage quarantined files without navigating individual data systems.

## Overview

Securiti lets you remediate files identified by File Quarantine policies by quarantining those files at a destination defined in a data system. Securiti supports the following methods for quarantining files. These methods determine where and how quarantined files are moved once a policy is executed.

- Quarantine Files within the Same Data System
- Quarantine Files to a Central Quarantine Location

Central Quarantine is designed for files from one or more data systems that are moved to a single, centralized quarantine location for easier management and control.

Central Quarantine lets you quarantine files from multiple data systems into a single, centralized destination. Securiti quarantines files from one or multiple sources, such as OneDrive, SharePoint, and NFS, into a central location, for example, in SharePoint. This approach removes the need to manage separate quarantine destinations for each data source and simplifies quarantine operations.

Use the diagram below to understand the central quarantine process flow:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Centralquarantine-flow.drawio.svg)

## Supported data system types

Currently, Securiti supports the following data systems types as Central Quarantine destinations:

- [Amazon S3](/latest/docs/amazon-s3-connectors-1) (self-hosted)
- [Azure Data Lake Storage (ADLS) Gen2](/latest/docs/activate-the-azure-data-lake-storage-adls-gen2-connector-in-securiti) (self-hosted)
- [Azure Blob Storage](/latest/docs/activate-the-azure-blob-storage-connector-in-securiti) (self-hosted)
- [Azure Files](/latest/docs/azure-files-connectors) (self-hosted)
- [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors) (self-hosted)
- [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors) (self-hosted)
- [NFS](/latest/docs/nfs) (self-hosted)
- [SMB](/latest/docs/smb-connectors) (self-hosted)

## 

## Understanding the process

Quarantining files to a central destination follows the process flow described below.

1. Configure and activate source and destination data system connectors.
2. Enable quarantine settings on both the source and destination connectors.
3. Enable Read, Write, and Delete (RWD) permissions on both the source and destination data systems. Permission requirements may vary by connector. For example, Microsoft SharePoint Online includes delete capabilities as part of Microsoft WRITE permissions rather than as a separate delete permission.
4. Run data inventory sync or discovery scans on source connectors.
5. Configure a File Quarantine policy for the source data system, and select **Quarantine Files to a Central Destination** as policy action.
6. Securiti evaluates discovered files against configured policies.
7. Securiti quarantines matching files to the central quarantine destination.

For more information, see the following topics:

- [Amazon S3 connector documentation](/latest/docs/amazon-s3-connectors-1)
- [Azure Data Lake Storage (ADLS) connector documentation](/latest/docs/activate-the-azure-data-lake-storage-adls-gen2-connector-in-securiti)
- [Azure Blob Storage connector documentation](/latest/docs/activate-the-azure-blob-storage-connector-in-securiti)
- [Azure Files connector documentation](/latest/docs/azure-files-connectors)
- [Microsoft 365 OneDrive connector documentation](/latest/docs/microsoft-365-onedrive-connectors)
- [Microsoft 365 SharePoint Online connector documentation](/latest/docs/microsoft-365-sharepoint-online-connectors)
- [NFS connector documentation](/latest/docs/nfs-connectors)
- [SMB connector documentation](/latest/docs/smb-connectors)
- [Using File Quarantine policies](/latest/docs/using-file-quarantine-policies)

> [!CAUTION]
> Warning
> 
> When using Central Quarantine, Securiti does not prevent the intra-system quarantine method from running in parallel. If both methods apply to the same files, rescans can cause already quarantined files to be evaluated again and quarantined a second time by another policy.
> 
> We strongly recommend that you do not use the legacy quarantine method when Central Quarantine is enabled. You must also exclude quarantine destinations from discovery scans to prevent duplicate quarantine actions.

## Understanding central quarantine execution across pods

Central Quarantine supports connection across multiple pods. A destination connector can authenticate on one pod, while source connectors run on other pods. Source pods communicate directly with the destination connector to quarantine files.

This design ensures flexibility in distributed environments without requiring all connectors to run on the same appliance.

1. The destination connector authenticates on its assigned pod.
2. Source connectors running on other pods initiate quarantine actions.
3. Source pods communicate directly with the destination connector.
4. Files move securely to the central quarantine destination.

This behavior enables centralized quarantine even in multi-pod deployments. Use the diagram below to understand the execution across pods:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Centralquarantine-crossappliance.drawio.svg)

## Prerequisites

You must fulfill the following prerequisites to successfully use the central quarantine destination feature:

- You must verify that destination data systems support read, write, and delete operations.
- You must activate the source and destination data system connectors.

> [!NOTE]
> Note
> 
> When you activate a connector, Securiti creates an empty folder at the destination data system. This folder is used to validate permissions and connectivity for quarantine operations.
> 
> The temporary file is deleted after verification, which is why the folder may appear empty. Securiti retains the folder to prevent accidental data loss during parallel write operations.

- You must enable the **Allow Quarantine actions on this Data System** setting on both the source and destination connectors.
- You must exclude quarantine destinations from discovery scans.
- If you use Azure Data Lake Storage Gen2 as a quarantine destination with **Azure Service Principal** authentication, you must assign the **Storage Blob Data Contributor** role to the associated app registration.

## Interactive Demos

This click-through demo show how to perform actions step by step. Click the **Start Demo** button to begin. Then, click the **Next** button or use the **right arrow** key on your keyboard to proceed, and the **left arrow** key to go back. This demo may include screens from multiple features to illustrate the complete procedure.

### Central Quarantine Destination for SharePoint Online files

See how Securiti lets you create a Central Quarantine destination to move and manage quarantined files from a data system in a centralized location, as shown in the demo below.

## 

[Embedded content](https://app.storylane.io/demo/ovmb9qxtnfer?embed=popup)

> [!NOTE]
> Note
> 
> To see more demos related to policies, refer to the following help center articles:
> 
> - [Interactive Demos: Discover and Classify Sensitive Data for AWS](/latest/docs/sensitive-data-intelligence-interactive-demos)
> - [Interactive Demos: Discover and Classify Sensitive Data for GCP](/latest/docs/interactive-demos-discover-and-classify-sensitive-data-for-gcp)
> - [Interactive Demos: Discover and Classify Sensitive Data for SharePoint Online](/latest/docs/policies-2)

## Creating a central quarantine destination

To create a quarantine destination:

1. In Securiti, open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
2. From the Platform Services section in the new navigation, select **Settings**.
3. From the **System Settings** menu, choose **Policy Center** **> Quarantine Destinations**, as shown below.

![System settings display showing quarantine destinations and associated data system instances.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image10(1).png)
4. Use the top-level filter to search for a specific destination, as shown below. The filter displays the following properties: • Data System Instance • Name • Organization • Data System Type

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-K76DNUHY.png)
5. To create a new destination, from the upper-right corner of the page, click **New Destination**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RFRMHD2A.png)
6. On the **New Destination** modal, in the **Destination Information** section, specify the following settings:

| Setting | Description |
| --- | --- |
| Name | Enter a unique name of your destination, such as “smb-pod1”. |
| Description (Optional) | Enter the description for your quarantine destination, such as “This destination quarantines all files in SMB file system. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-central-quarantine-destination-image-zhzqyrvw.png)
7. In the **Destination Selection** section, click the **+** icon to choose the data system instance to use as quarantine destination, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-R6ZF58PF.png)
8. Specify the required quarantine parameters for the selected data system as described in the table below:

| **Data System** | **Quarantine parameter** | **Parameter description** |
| --- | --- | --- |
| Amazon S3 | Quarantine Bucket | Specify the name of the S3 bucket where files identified for quarantine will be moved. |
| (Optional) Quarantine Path | Specify the path for the directory inside the Quarantine Container where files identified for quarantine are to be placed. The quarantine path can include only alphanumeric characters, `/`, `_`, and `-`, with no other special characters. For example, `/folder` |
| Azure Data Lake Storage | Quarantine Container | Specify the container where files identified for quarantine are to be placed. The container name must be 3–63 characters long. For example, `quarantine-container` |
| (Optional) Quarantine Path | Specify the path for the directory inside the Quarantine Container where files identified for quarantine are to be placed. The quarantine path can include only alphanumeric characters, `/`, `_`, and `-`, with no other special characters. For example, `/folder` |
| Azure Blob Storage | Quarantine Container | Specify the container where files identified for quarantine are to be placed. The container name must be 3–63 characters long. For example, `quarantine-container` |
| (Optional) Quarantine Path | Specify the path for the directory inside the Quarantine Container where files identified for quarantine are to be placed. The quarantine path can include only alphanumeric characters, `/`, `_`, and `-`, with no other special characters. For example, `/folder` |
| Azure Files | (Optional) Quarantine Share | Enter the name of the Azure Files share where you want Securiti to move the files identified for quarantine. |
| (Optional) Quarantine Path | Specify the path for the directory inside the Quarantine Share where files identified for quarantine are to be placed. The quarantine path can include only alphanumeric characters, `/`, `_`, and `-`, with no other special characters. For example, `/folder`. |
| Microsoft 365 SharePoint Online | Quarantine Site URL | Specify the site URL for quarantine destination. You must ensure that the quarantine site is within the default root domain. For example, `https://acme.sharepoint.com/sites/regressiontest` For more information on acquiring Site URL, see [SharePoint documentation](/latest/docs/microsoft-365-sharepoint-online-connectors). |
| Quarantine Site Library Name | Specify the library name for the quarantine site, such as `/central/Documents`. |
| (Optional) Quarantine Path | Specify the path for the directory inside the Quarantine Library where files identified for quarantine are to be placed. The path must start with `/`, must not end with `/`, and can include only alphanumeric characters, hyphens (`-`), and underscores (`_`), with a maximum length of 255 characters. For example, `/documents/folder` |
| Microsoft 365 OneDrive | Quarantine Site URL | Specify the site URL for quarantine destination. You must ensure that the quarantine site is within the default root domain. For example, “[https://acme-my.onedrive.com/personal/testuser1_acme_onmicrosoft_com](https://dsrtestautomation-my.sharepoint.com/personal/testuser1_dsrtestautomation_onmicrosoft_com)” For more information on acquiring Site URL, see [OneDrive documentation.](/latest/docs/microsoft-365-onedrive-connectors) |
| (Optional) Quarantine Path | Specify the path for the directory inside the Quarantine Site where files identified for quarantine are to be placed. The path must start with `/`, must not end with `/`, and can include only alphanumeric characters, hyphens (`-`), and underscores (`_`), with a maximum length of 255 characters. For example, `/documents/folder` |
| - NFS - SMB | Mount Path | Specify the share name or export path as the base location for all quarantine operations. Securiti validates the mount path for the following rules: - For NFS, the mount path must start with `/`, must not end with `/`, and must not exceed 255 characters. - For SMB, the mount path must start with `/`, must not contain additional `/`, and must not exceed 80 characters. For example, `/quarantine-nfs` > [!NOTE] > Note > > For SMB, the mount path represents the share name. This share can differ from the share configured on the connector. Securiti uses the credentials defined on the connector to mount this share and perform quarantine operations. |
| (Optional) Quarantine Path | Specify the path for the subdirectory within the mount path where Securiti places quarantined files. The quarantine path must start with `/`, must not end with `/`, and can include only alphanumeric characters, hyphens (`-`), and underscores (`_`), up to 255 characters. For example, `/folder` |

> [!NOTE]
> Note
> 
> After you create a quarantine destination, the selected data system and quarantine path become read-only. You cannot modify these fields later.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-06 at 11.24.11 AM.png)
9. In the **Test Connection & Permission** section, you can test the connectivity between the destination and selected source pods. This ensures that data can be successfully quarantined from these sources.

> [!NOTE]
> Note
> 
> - Test connectivity verifies that the destination pod can reach the destination data system and that the selected source pods can read, write, and delete data at the destination. This step is optional.
> - For Hyperdrive data systems, Securiti tests connectivity between source and destination outpost deployments. For more information, see [Hyperdrive documentation](/latest/docs/policies-1).

Expand the **Sources (Optional)** menu to select the source data systems.
10. Click **Add scope rule**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-U5JTXXTO.png)

The **Graph Explorer** page opens with a default query for source data systems, as shown below. You can edit this query for the source data.
11. Click **Use Query**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-central-quarantine-destination-image-psn9axmg.png)
12. Click **Save Destination and Test Connection**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7WP9ZNSO.png)

Use the table below to understand the possible connection statuses.

> [!NOTE]
> Note
> 
> Securiti updates the test connectivity status every 5 minutes.

| Connection Status | Description |
| --- | --- |
| Connection test completed, some items require attention | Indicates available destination but shows that some configuration settings are incomplete or missing, such as a missing **Mount Path**. |
| Connection test completed | Indicates available destination and successful connection with sources. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-central-quarantine-destination-image-k8nkhcmn.png)

## Creating a file quarantine policy using central destination

After you create a central quarantine destination and confirm a successful connectivity test, create a file quarantine policy as described in [Using File Quarantine Policies](/latest/docs/using-file-quarantine-policies).

> [!WARNING]
> Important
> 
> - With Central Quarantine, you can select only one quarantine action per policy.
> - Policy logs are generated only for failures.

To configure a policy to use a central quarantine destination:

1. In the **Actions** section of the policy, select **Quarantine Files to a Central Destination**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-central-quarantine-destination-image-obg4lkgo.png)
2. In the **Quarantine Files to a Central Destination** modal, from the **Quarantine destinations** menu, select a destination, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-central-quarantine-destination-image-n86l5koy.png)

> [!NOTE]
> Note
> 
> - You cannot change the destination after you select a quarantine destination for a policy.
> - Securiti creates quarantine paths using the following structure: `securiti_policy_&lt;policyID&gt;/&lt;DataSystemID&gt;/&lt;replicated_folder_structure&gt;/&lt;file&gt;`
> - Quarantine and revert actions continue to work correctly with hashed paths across all supported data systems.
> - When you quarantine files from Azure Blob Storage to Microsoft 365 SharePoint Online or Microsoft OneDrive, the source file or folder path must not contain special characters, such as `*`, `@`, `#`, `$`, `(`, or `)`because these characters cause the quarantine operation to fail. This is a Microsoft limitation for SharePoint and OneDrive paths.
3. Mark the **Auto Quarantine** checkbox to quarantine files automatically when the policy is activated.
4. Under the **Advanced Settings** menu for the **Auto Quarantine** option, select one or both of the following options to control how the policy handles files affected by other policies:
  - **Ignore files reverted by other policies**
  - **Ignore files failed by other policies**
5. Mark the **Drop placeholder file** checkbox to place a marker at the original file location after quarantine. The placeholder file indicates that a policy quarantined the file and helps preserve context at the source location.

> [!NOTE]
> Note
> 
> The placeholder is deleted if a file is reverted.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-central-quarantine-destination-image-i6mrckqa.png)
6. Click **Save Action**.
7. Click **Create Policy** with the central quarantine destination settings, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-central-quarantine-destination-image-6425rppy.png)

## Quarantining files in a centralized destination

Once the quarantine policy is marked as **Completed** in the **Policies** page, you can manually quarantine or revert the files from the **Data Remediation** dashboard. For more information, see [Using Data Remediation Dashboards](/latest/docs/using-data-remediation-dashboards).

> [!NOTE]
> Note
> 
> - Central Quarantine policies support cancellation and revert actions.
> - If a policy scopes multiple data systems, Securiti quarantines files from all supported systems to the selected destination.
> - During periods of high activity, Microsoft 365 OneDrive and SharePoint may return rate limit errors when you run quarantine or revert operations. Securiti retries these requests automatically, but they may still fail if the load continues. If rate limit errors persist, you must complete the Quarantine or Revert action manually.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-central-quarantine-destination-image-el542a4e.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-central-quarantine-destination-image-pqblst3m.png)

## Key considerations

- Files already present in a quarantine destination are not quarantined again.
- If a file with the same name already exists at the destination, quarantine fails.
- If a file already exists at the quarantine destination but not at the source, Securiti marks the quarantine action as successful. This can occur if the file was previously quarantined or manually moved to the destination.

> [!NOTE]
> Note
> 
> We recommend that you do not manually move files into quarantine destinations. Manual file movement can cause inaccurate quarantine status and affect remediation.

- When Securiti moves a file from SharePoint Online or OneDrive to a quarantine destination, it checks whether the file already exists at the destination before attempting the move. If the file already exists, the operation fails immediately with the following error: `file move failed: file already exists at destination`.
- When Securiti quarantines a file, metadata such as creation date, last modified date, and file owner metadata are not preserved. The metadata differs when files move between different data systems. For example, SharePoint files include site and folder metadata that NFS files do not contain. These differences affect how inventory metadata appears after quarantine and revert.
- If a data system does not support quarantine and is included in scope, Securiti skips its files.
- If a site is configured as a quarantine destination, Securiti excludes that site from discovery scans to prevent repeated processing of the quarantined data.
- Central Quarantine supports moving files within the same data system. Use only Central Quarantine-based policies for these workflows to ensure consistent behavior.
- Files must be quarantined and reverted using the same policy type. Files quarantined through a File Quarantine policy can be reverted only through a File Quarantine policy. Similarly, files quarantined through a Central Quarantine policy can be reverted only through a Central Quarantine policy.
- If a quarantine upload succeeds but deletion from the source fails, Securiti attempts a rollback by deleting the destination file. If rollback also fails, the quarantine operation fails and leaves the file in both locations.

> [!WARNING]
> Important
> 
> You must manually delete the destination file before retrying quarantine in this scenario.
- If a quarantine destination is inadvertently included in a scan or policy scope, Securiti applies policy-side filtering that identifies files already residing in a quarantine destination and excludes them from being scoped and quarantined again to a different destination. This prevents already quarantined files from being re-processed and moved a second time.
