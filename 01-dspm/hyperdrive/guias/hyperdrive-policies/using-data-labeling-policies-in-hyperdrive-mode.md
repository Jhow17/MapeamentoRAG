---
title: "Using Data Labeling policies in Hyperdrive mode"
slug: "using-data-labeling-policies-in-hyperdrive-mode"
updated: 2026-09-22T03:51:29Z
published: 2026-09-22T03:51:29Z
canonical: "helpcenter.securiti.ai/using-data-labeling-policies-in-hyperdrive-mode"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Using Data Labeling policies in Hyperdrive mode

Overview

Data Labeling policies with Hyperdrive mode let you apply sensitivity labels to files across data systems that hold millions of files. Hyperdrive mode for Data Labeling policies currently supports the following self-hosted data system connectors:

- [Amazon S3](/latest/docs/amazon-s3-connectors-1)
- [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors)
- [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors)
- [NFS](/latest/docs/nfs-connectors)
- [SMB](/latest/docs/smb-connectors)

> [!NOTE]
> **Note**
> 
> When a Data Labeling policy with Hyperdrive mode processes a file, Securiti temporarily stores sensitive customer data in a specially guarded S3 bucket that is not accessible by Securiti's SaaS cloud. Securiti removes the file from this bucket once the labeling action completes.

> [!WARNING]
> Important
> 
> - If the Hyperdrive mode is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to determine if this feature is included in your subscription plan and if your tenant meets the eligibility requirements for its activation.
> - Data Labeling policies with Hyperdrive mode cannot be used with previously configured Microsoft 365 data system connectors. You must migrate to a tenant with Hyperdrive mode enabled and start a fresh scan for your data systems.

## Prerequisites

Before you create a Data Labeling policy with Hyperdrive mode, you must meet the following prerequisites:

- You must have a G Suite Google Drive (Self Hosted Pod Connector) instance configured. For more information, see [Google Drive (Google Workspace)](/latest/docs/g-suite-google-drive-connectors).
- You must connect the Microsoft Information Protection (MIP) data system connector with Securiti to import Microsoft Information Protection (MIP) labels. For more information, see [Microsoft Purview Information Protection](/latest/docs/microsoft-purview-information-protection-connectors).
- To collect metadata such as file owner, you must create and run a Discovery Scan or Data Inventory Sync. If you prefer not to run a Discovery Scan, you can instead perform a Data Inventory Sync to retrieve basic file information. However, a Data Inventory Sync does not collect content profiles. As a result, Securiti does not run labeling policies that depend on content profiles when you use only a Data Inventory Sync. For more information, see:
  - [Discovery scans](/latest/docs/discovery-scans).
  - [Data Inventory Sync and Entitlement Scan for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

## Creating a Data Labeling policy with Hyperdrive mode

To create a Data Labeling policy with Hyperdrive mode:

1. In Securiti, on the **Policies** page, choose **Data Labeling**, and create a Data Labeling policy as described in the following articles:
  - [Creating a Data Labeling Policy for Google Drive](/latest/docs/creating-data-labeling-policy-for-google-drive-files)
  - [Creating a Data Labeling Policy for Microsoft Information Protection (MIP)](/latest/docs/creating-data-labeling-policy-for-microsoft-purview)
2. In the **Scope** section of the policy, mark the **Hyperdrive Mode Enabled Data Systems** only checkbox. Marking this checkbox sets the scope query's **Is Hyperscale** property to true, so the policy applies only to the data systems running in Hyperdrive mode, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8K4TSYOZ.png)

> [!WARNING]
> Important
> 
> If the **Files** node does not include a supported data system type, Securiti displays a validation warning and prevents policy creation.
3. Click **Edit Query** to define the file scope in the Graph Explorer, as follows:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-DSJ7ZC5T.png)
  1. In the Graph Explorer, the **Files** entity is selected by default. Click options (three dots), then click **Add Property**.
  2. Choose **Data System Type** from the menu, then select your Hyperdrive-enabled data system.
  3. From the upper right corner of the page, click **Use Query** to apply the selection, as shown below.
4. In the **Actions** section, click **Edit** and configure the **Apply a Classification Label** action as described in the following articles
  - [Creating a Data Labeling Policy for Google Drive](/latest/docs/creating-data-labeling-policy-for-google-drive-files)
  - [Creating a Data Labeling Policy for Microsoft Information Protection (MIP)](/latest/docs/creating-data-labeling-policy-for-microsoft-purview)
5. Click **Create Policy**. Once created, the policy appears on the Data Labeling Policies page.

## Viewing data labeling policy execution

After you create a Data Labeling policy, Securiti lists it on the **Policies** page with the **State** column showing **Created**. For policies that use Hyperdrive mode, a lightning icon appears next to the policy, as shown below.

Data Labeling policies in Hyperdrive mode support smart labeling, which optimizes file processing across policy runs. When you run the policy for the first time, Securiti processes all files that match the policy scope and applies the configured labels. In subsequent policy runs, Securiti processes only new or rescanned files and skips unchanged files. If you update the policy configuration, Securiti reevaluates the affected files and applies the updated labels. This reduces redundant processing while keeping file labels up to date.

For more information on applying filters and actions to policies, see [Using Data Labeling Policies](/latest/docs/using-data-labeling-policies).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-N20NUV62.png)

## Next steps

To learn more about configuring, monitoring, and troubleshooting Data Labeling policies, see the following articles in Sensitive Data Intelligence:

- [Using Data Labeling Policies](/latest/docs/using-data-labeling-policies)
- [Creating a Data Labeling Policy for Google Drive](/latest/docs/creating-data-labeling-policy-for-google-drive-files)
- [Creating a Data Labeling Policy for Microsoft Information Protection (MIP)](/latest/docs/creating-data-labeling-policy-for-microsoft-purview)
- [Viewing and exporting policy logs](/latest/docs/viewing-and-exporting-policy-logs)
- [Troubleshooting data labeling policies](/latest/docs/troubleshooting-data-labeling-policies)
