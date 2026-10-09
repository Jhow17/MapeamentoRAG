---
title: "Using File ROT policies in Hyperdrive mode"
slug: "using-file-rot-policies-in-hyperdrive-mode"
updated: 2026-09-17T04:29:33Z
published: 2026-09-17T04:29:33Z
canonical: "helpcenter.securiti.ai/using-file-rot-policies-in-hyperdrive-mode"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Using File ROT policies in Hyperdrive mode

## Overview

File ROT policies with Hyperdrive mode let you clean up redundant, obsolete, and trivial files across data systems that hold millions of files. Hyperdrive mode for File ROT policies currently supports the following self-hosted data system connectors:

- [Amazon S3](/latest/docs/amazon-s3-connectors-1)
- [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors)
- [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors)
- [SMB](/latest/docs/smb-connectors)

> [!WARNING]
> Important
> 
> - If the Hyperdrive mode is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to determine if this feature is included in your subscription plan and if your tenant meets the eligibility requirements for its activation.
> - File ROT policies with Hyperdrive mode cannot be used with previously configured Microsoft 365 data system connectors. You must migrate to a tenant with Hyperdrive mode enabled and start a fresh scan for your data systems.

## Prerequisites

Before you create a File ROT policy with Hyperdrive mode, you must meet the following prerequisites:

- This policy does not work with the Securiti Sovereign, as it requires integration with the Data Command Graph**.**
- The Data Inventory Sync for your data system connectors must be enabled for your tenant.
- Before configuring a policy, run the required scans to gather metadata for identifying files that match your policy conditions. These may include Data Inventory Syncs, Discovery Scans, and Access Intelligence Scans.
- Ensure the required permissions are enabled for your role. For more information, see [Sensitive Data Intelligence Roles and Permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions).

## Creating a File ROT policy with Hyperdrive mode

To create a File ROT policy with Hyperdrive mode:

1. In Securiti, on the **Policies** page, choose **File ROT**, and create a File ROT policy as described in [Creating a File ROT policy](/latest/docs/creating-a-file-rot-policy).
2. In the **Scope** section of the policy, mark the **Hyperdrive Mode Enabled Data Systems only** checkbox. Marking this checkbox sets the scope query's **Is Hyperscale** property to true, so the policy applies only to the data systems running in Hyperdrive mode, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-2DARES4J.png)

> [!WARNING]
> Important
> 
> If the **Files** node does not include a supported data system type, Securiti displays a validation warning and prevents policy creation.
3. Click **Edit Query** to define the file scope in the Graph Explorer, as follows:
  1. In the Graph Explorer, the **Files** entity is selected by default. Click options (three dots), then click **Add Property**.
  2. Choose **Data System Type** from the menu, then select your Hyperdrive-enabled data system.
  3. From the upper right corner of the page, click **Use Query** to apply the selection, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SJHB5XZ6.png)
4. In the **Actions** section, click **Add Actions** and configure **Quarantine Files To A Central Quarantine Location** action as described in [Creating a File ROT policy](/latest/docs/creating-a-file-rot-policy).

> [!NOTE]
> Note
> 
> When Hyperdrive mode is enabled, you can configure only the **Quarantine Files To A Central Quarantine Location** action.
5. Click **Create Policy**. Once created, the policy appears on the File ROT Policies page.

## Viewing File ROT policy execution

Once created, the policy is listed in the Policies page with the **State** column showing **Created**. A lightning icon appears next to a policy when Hyperdrive mode is enabled, as shown below. For more information on applying filters and actions to policies, see [Using File ROT Policies](/latest/docs/using-file-rot-policies).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RX4SH2PY.png)

## Next steps

To learn more about configuring, monitoring, and troubleshooting File ROT policies, see the following articles in Sensitive Data Intelligence:

- [Using File ROT Policies](/latest/docs/using-file-rot-policies)
- [Creating a File ROT policy](/latest/docs/creating-a-file-rot-policy)
- [Viewing File ROT in the Data Remediation dashboard](/latest/docs/viewing-file-rot-in-the-data-remediation-dashboard)
- [Viewing and exporting policy logs](/latest/docs/viewing-and-exporting-policy-logs)
- [Troubleshooting File ROT policies](/latest/docs/troubleshooting-file-rot-policies)
