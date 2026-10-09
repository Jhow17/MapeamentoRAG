---
title: "Using File Quarantine policies in Hyperdrive mode"
slug: "using-quarantine-policies-in-hyperdrive-mode"
updated: 2026-09-17T04:29:26Z
published: 2026-09-17T04:29:26Z
canonical: "helpcenter.securiti.ai/using-quarantine-policies-in-hyperdrive-mode"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Using File Quarantine policies in Hyperdrive mode

Overview

File Quarantine policies with Hyperdrive mode let you isolate at-risk files across data systems that hold millions of files. Hyperdrive mode for File Quarantine policies currently supports the following self-hosted data system connectors:

- [Amazon S3](/latest/docs/amazon-s3-connectors-1)
- [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors)
- [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors)
- [SMB](/latest/docs/smb-connectors)

> [!NOTE]
> **Note**
> 
> When a File Quarantine policy with Hyperdrive mode moves a file, Securiti temporarily stores sensitive customer data in a specially guarded S3 bucket that is not accessible by Securiti's SaaS cloud. Securiti removes the file from this bucket once the quarantine action completes.

> [!WARNING]
> Important
> 
> - If the Hyperdrive mode is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to determine if this feature is included in your subscription plan and if your tenant meets the eligibility requirements for its activation.
> - File Quarantine policies with Hyperdrive mode cannot be used with previously configured Microsoft 365 data system connectors. You must migrate to a tenant with Hyperdrive mode enabled and start a fresh scan for your data systems.
> - Hyperdrive mode works only with the Central Quarantine destination.

## Prerequisites

Before you create a File Quarantine policy with Hyperdrive mode, you must meet the following prerequisites:

- This policy does not work with the Securiti Sovereign, as it requires integration with the Data Command Graph**.**
- The Data Inventory Sync for your data system connectors must be enabled for your tenant.
- Before configuring a policy, run the required scans to gather metadata for identifying files that match your policy conditions. These may include Data Inventory Syncs, Discovery Scans, and Access Intelligence Scans.
- Ensure the required permissions are enabled for your role. For more information, see [Sensitive Data Intelligence Roles and Permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions).
- Configure and activate your connector instance. For more information, see Hyperdrive connectors documentation.
- Configure a Central Quarantine destination in Securiti. For more information, see [Using Central Quarantine Destination](/latest/docs/using-quarantine-destinations).
- File Quarantine policies support the multi-org feature. For more information, see [Managing organizations](/latest/docs/system-settings-managing-organizations).

## Creating a File Quarantine policy with Hyperdrive mode

To create a File Quarantine policy with Hyperdrive mode:

1. In Securiti, on the **Policies** page, choose **File Quarantine**, and create a File Quarantine policy as described in [Creating a File Quarantine policy](/latest/docs/creating-a-file-quarantine-policy).
2. In the **Scope** section of the policy, mark the **Hyperdrive Mode Enabled Data Systems only** checkbox. Marking this checkbox sets the scope query's **Is Hyperscale** property to true, so the policy applies only to the data systems running in Hyperdrive mode, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-N6Q7N5HI.png)

> [!WARNING]
> Important
> 
> If the **Files** node does not include a supported data system type, Securiti displays a validation warning and prevents policy creation.
3. Click **Edit Query** to define the file scope in the Graph Explorer, as follows:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-C2N7L6NN.png)
  1. In the Graph Explorer, the **Files** entity is selected by default. Click options (three dots), then click **Add Property**.
  2. Choose **Data System Type** from the menu, then select your Hyperdrive-enabled data system.
  3. From the upper right corner of the page, click **Use Query** to apply the selection, as shown below.
4. In the **Actions** section, click **Add Actions** and configure **Quarantine Files To A Central Quarantine Location** action as described in [Creating a File Quarantine policy](/latest/docs/creating-a-file-quarantine-policy).

> [!NOTE]
> Note
> 
> When Hyperdrive mode is enabled, you can configure only the **Quarantine Files To A Central Quarantine Location** action.
5. Click **Create Policy**. Once created, the policy appears on the File Quarantine Policies page.

## Viewing File Quarantine policy execution

Once created, the policy is listed in the Policies page with the **State** column showing **Created**. A lightning icon appears next to a policy when Hyperdrive mode is enabled, as shown below. For more information on applying filters and actions to policies, see [Using File Quarantine Policies](/latest/docs/using-file-quarantine-policies).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OFYFCGNN.png)

## Next steps

To learn more about configuring, monitoring, and troubleshooting File Quarantine policies, see the following articles in Sensitive Data Intelligence:

- [Using File Quarantine Policies](/latest/docs/using-file-quarantine-policies)
- [Creating a File Quarantine policy](/latest/docs/creating-a-file-quarantine-policy)
- [Viewing File Quarantine in the Data Remediation dashboard](/latest/docs/viewing-file-quarantine-in-data-remediation-dashboard)
- [Viewing and exporting policy logs](/latest/docs/viewing-and-exporting-policy-logs)
- [Troubleshooting File Quarantine policies](/latest/docs/troubleshooting-file-quarantine-policies)
