---
title: "Hyperdrive release notes"
slug: "hyperdrive-release-notes"
updated: 2026-09-22T19:20:30Z
published: 2026-09-22T19:20:30Z
canonical: "helpcenter.securiti.ai/hyperdrive-release-notes"
area: dspm
modulo: hyperdrive
tipo: release
data_captura: 2026-10-06
---

# Hyperdrive release notes

## 1.151

### Release updates - September 2026

#### Introducing egress paths for Outpost data scanning nodes

Securiti now lets you select how data scanning nodes in a Hybrid deployment with Outpost send outbound traffic. This helps security teams maintain allow lists more predictably, align Outpost deployments with their network access requirements, and manage costs.

Use the following table to understand the details of the available egress paths.

| Option | Description |
| --- | --- |
| Single Static Elastic IP (EIP) | Your firewall or target data systems require fixed source IP addresses. |
| Dynamic IP Range | The data system does not require source IP restrictions. |

You can select the egress path under **Advanced Settings > Privilege Analysis Configuration** while creating a new Outpost, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EAX40LVZ.png)

For more information, see [Hybrid deployment with Outpost.](/latest/docs/hybrid-deployment-with-outpost)

#### Provisioning your own IAM roles for Hybrid deployment with Outpost

Securiti has added support for bringing your own IAM roles when deploying with Outpost. This supports enterprise IAM governance by letting your security team pre-approve and provision roles, and by preventing automated IAM role creation where required.

You can select one of three IAM provisioning strategies based on how your organization manages IAM role creation and approval. Use the following table to understand the details of each strategy.

| Deployment strategy | Description |
| --- | --- |
| Fully automated (default) | The CloudFormation template creates all required IAM roles during deployment. |
| Modular | You create and provide Amazon Resource Names (ARNs) for the two cross-account bridge roles: - Metadata Access Role - Monitoring Access Role The CloudFormation template creates the remaining roles for Outpost. |
| Fully Manual (Bring your own IAM) | You provide ARNs for the two cross-account bridge roles and deploy the separate IAM roles template to create the remaining roles. The main CloudFormation template does not create any IAM role in your AWS account. |

You can select the IAM provisioning strategy under **Advanced Settings > IAM Provisioning Strategy** while creating a new Outpost, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PSIQEOOT.png)

For more information, see [Hybrid deployment with Outpost.](/latest/docs/hybrid-deployment-with-outpost)

### Adding Certificate credentials for Microsoft 365 connectors

Securiti has extended Certificate support to Microsoft 365 OneDrive, Microsoft 365 Outlook, and Microsoft Teams connectors. This provides an alternative to creating, storing, and rotating client secrets in Microsoft Entra ID while reducing configuration errors and failed connection tests for Microsoft 365 applications. Certificate-based authentication was previously available only for Microsoft 365 SharePoint Online.

When configuring connector credentials, use the **Authentication Type** menu to select **Client Secret** and provide the **Client ID** and **Client Secret**, or select **Certificate** to provide the **Client ID** and **Certificate** credentials, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-18 at 11.55.54 AM.png)

> [!NOTE]
> Note
> 
> - To use this feature, you must upgrade to pod version 1.151.0 or later.
> - Microsoft recommends using certificates instead of client secrets for application authentication when possible.

For more information, see [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-1), [Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors), [Microsoft 365 Outlook](/latest/docs/microsoft-365-outlook-connectors), and [Microsoft Teams](/latest/docs/microsoft-teams-connectors).

#### Configuring Microsoft 365 SharePoint Online system libraries

Securiti has introduced the **Include System Libraries** option in **Advanced Settings** for Microsoft 365 SharePoint Online Discovery Scans and Data Inventory Syncs. Previously, SharePoint system-managed libraries, such as Master Page Gallery and Form Templates, were always scanned with no option to exclude them.

For existing Discovery Scans and Data Inventory Syncs, Include System Libraries remains enabled, so existing scan behavior is unchanged. For new configurations, the option is disabled by default, helping reduce scan volume and processing time when system-managed content is not required.

To scan these libraries, mark the **Include System Libraries** checkbox when configuring a Discovery Scan or Data Inventory Sync, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-09 at 11.43.51 AM.png)

> [!NOTE]
> Note
> 
> To use this feature, you must upgrade to outpost version 1.151.0 or later.

For more information, see [Discovery Scan](https://helpcenter.securiti.ai/docs/configure-discovery-scans-in-microsoft-365-sharepoint-online) and [Data Inventory sync](https://helpcenter.securiti.ai/docs/configuring-data-inventory-sync-for-sharepoint-online-self-hosted) for Microsoft 365 SharePoint Online.

#### Introducing tag-based grouping in Automation policies

Securiti now supports **Securiti Tag Category** as a grouping attribute in Automation policies in Hyperdrive tenants. With this update, you can group File Insights, File Quarantine, and File ROT entities by tag values and route remediation tasks to stakeholders associated with those values.

Securiti creates a separate work item for each unique tag value. If a file has multiple values for the selected tag category, Securiti includes the file in the corresponding work item for each value.

> [!WARNING]
> Important
> 
> The tag value used in the **Assignee** and **Recipient** fields must be a valid email address. If the value is missing or invalid, Securiti assigns the task to the Automation policy owner.

The **Securiti Tag Category** grouping attribute appears as shown below.

![Selecting 'Securiti Tag Category' in the automation policy entity options menu.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image8(4).png)

For more information, see [Using Automation policies in Hyperdrive mode](/latest/docs/using-automation-policies-in-hyperdrive-mode).

#### Introducing smart labeling for Data Labeling policies

Securiti now supports smart labeling for Data Labeling policies in Hyperdrive tenants. With this update, after the initial policy run, Securiti processes only new or rescanned files in subsequent runs and skips unchanged files. If you update the policy configuration, Securiti reevaluates the affected files and applies the updated labels. This reduces redundant processing while keeping file labels up to date.

For more information, see [Using Data Labeling policies in Hyperdrive mode](/latest/docs/using-data-labeling-policies-in-hyperdrive-mode).

#### Removing labels from files in the Data Remediation dashboard

Securiti now lets you remove specific labels or all labels from selected files in the Data Remediation dashboard in Hyperdrive tenants.

> [!NOTE]
> Note
> 
> Label removal behavior varies by data system type. Google Drive supports multiple labels per file, so you can remove one or more labels in a single operation. Microsoft Purview Information Protection (MIP) supports a single label per file, so removing the label leaves the file unlabeled.

The **Remove Labels** option appears as shown below.

![Data labeling interface showing file statistics and options for managing labels.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image1(14).png)

For more information, see [Using Data Remediation dashboards in Hyperdrive mode](/latest/docs/using-data-remediation-dashboards-in-hyperdrive-mode).

#### Reverting quarantined files across policies

Securiti now lets you revert quarantined files across policies in Hyperdrive tenants. With this update, you can restore quarantined files without depending on the policy that originally quarantined them, even if that policy has been modified, disabled, or deleted.

When you revert files quarantined by different policies, Securiti uses the quarantine information associated with each file to restore it to its original location.

The **Revert files quarantined by other policies as well** option appears as shown below.

![Dialog box for reverting quarantined files with options for auditing and policy selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image5(10).png)

For more information, see [Using Data Remediation dashboards in Hyperdrive mode](/latest/docs/using-data-remediation-dashboards-in-hyperdrive-mode).

#### Introducing Data Remediation system dashboards

Securiti now supports Data Remediation system dashboards in Hyperdrive tenants. The **Data Remediation** category includes the following dashboards:

- File Insights
- File Quarantine
- File ROT
- File Labeling

The **Data Remediation** system dashboards appear as shown below.

![Dashboard displaying file insights, total volume, and processed data trends.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image3(14).png)

For more information, see [Using Data Remediation system dashboards in Hyperdrive mode](/latest/docs/using-data-remediation-system-dashboards-in-hyperdrive-mode).

---

## 1.150

### Release updates - August 2026

#### Introducing support for existing networking in Hybrid Outpost

Securiti has introduced support for deploying the hybrid Outpost model into your existing Virtual Private Cloud (VPC) networks and subnets. Instead of deploying a new network infrastructure specifically for the hybrid Outpost, Securiti now lets you use your custom VPC infrastructure across your existing resources. This enhancement supports organizations where network infrastructure is managed centrally, and helps align hybrid Outpost deployment with existing cloud network governance and security controls.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-L9AOUK11.png)

For more information, see [Hybrid deployment with Outpost - AWS](/latest/docs/hybrid-deployment-with-outpost).

#### Deprecating support for new SMB version 1 connectors

Securiti has deprecated new SMB version 1 connector activations due to its known security limitations. You can no longer select SMB version 1 when creating a new connector. Existing SMB version 1 connectors continue to operate without interruption, and you can still view, edit, or reconfigure them.

> [!NOTE]
> **Note**
> 
> To avoid connector disruptions once SMB version 1 support is fully deprecated, migrate to SMB version 2 or 3. Securiti recommends using SMB version 3 if your file server supports it.

For more information, see [Upgrading from SMB version 1 to SMB version 2 or 3](/latest/docs/migrating-from-smbv1-to-smbv2-3).

#### Viewing agent activity on a dedicated Timeline page

Securiti now provides a dedicated **Agent Activity Timeline** page, letting you analyze how AI agents act on your data without first opening the Agent Activity Overview dashboard, as shown below. The page displays activity events in chronological order across agents, data systems, and files. From the timeline, you can undo an individual AI action on a file, or revert all changes made after a selected restore point.

![Agent activity timeline displaying various actions over specific dates and restore points.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/timeline_page.png)

For more information, see [Using Agent Activity Timeline](/latest/docs/using-agent-activity-timeline).

---

## 1.149

### Release updates - August 2026

No updates

---

## 1.148

### Patch 2 updates - July 2026

#### Upgrading hybrid Outpost to latest infrastructure

Securiti now lets you upgrade your hybrid Outpost deployment infrastructure using the latest cloud template. It helps you keep your hybrid Outpost infrastructure aligned with the newest changes Securiti supports. Upgrade can bring you:

- New cloud services or configurations
- Deprecate cloud services or configurations

For more information, see [Upgrading hybrid deployment with Outpost](/latest/docs/upgrading-hybrid-deployment-with-outpost#upgrading-hybrid-outpost-deployment).

### Release updates - July 2026

#### SMB enhancements for Hyperdrive mode

Securiti has enhanced SMB data system connectors in Hyperdrive mode with improved scan performance, enhanced file owner resolution, and Kerberos authentication support.

| Enhancement | Description |
| --- | --- |
| Improved scan performance | Added enhanced file enumeration and processing to improve Discovery Scan performance across large SMB environments while maintaining consistent scan results. |
| Optional Domain Controller configuration | Added an optional Domain Controller setting during connector activation to improve file owner resolution. This helps retrieve file owner names more reliably when the scanned file server cannot resolve domain accounts directly. |
| Kerberos authentication | Added support for Kerberos authentication using both Keytab and Password authentication methods. This extends the existing Kerberos authentication support previously available for non-Hyperdrive SMB connectors, enabling secure credential-based authentication and mutual authentication between the client and the server. |

> [!NOTE]
> Note
> 
> - To use this feature, you must upgrade your Outpost version to release 1.148 or higher.
> - If Hyperdrive is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

For more information, see [SMB (Hyperdrive)](/latest/docs/smb-1).

#### Extending native inventory support for GCS Discovery Scans in Hyperdrive

Securiti has extended native inventory support to Google Cloud Storage (GCS) Discovery Scans running in Hyperdrive mode. Previously available for non-Hyperdrive deployments, this capability lets the connector retrieve object metadata from Google Cloud Storage Inventory Reports instead of querying each object individually. Enable the **Use Native Inventory** option during connector activation and configure GCS Inventory Reports in your Google Cloud project. This improves scan performance and scalability, particularly for storage environments containing a large number of objects.

> [!NOTE]
> Note
> 
> - To use this feature, you must upgrade your Outpost version to release 1.148 or higher.
> - If Hyperdrive is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

For more information, see [Google Cloud Storage (Hyperdrive)](/latest/docs/google-cloud-storage-hyperdrive).

#### IAM Role Authentication for Amazon S3 using Full SaaS deployments

Securiti now supports cross-account **IAM Role** authentication for Amazon S3 connectors in Full SaaS Hyperdrive deployments, eliminating the need to use AWS access keys. With this update you can use Securiti provided AWS Account ID and your External ID to create Master Member CloudFormation template.

Unlike other deployment models, the Full SaaS deployment model does not require you to create an instance profile or modify the IMDSv2 hop count. Instead, Securiti accesses your S3 buckets by assuming your IAM roles through cross-account `sts:AssumeRole`.

> [!NOTE]
> Note
> 
> Ensure that the External ID entered on the connector activation page exactly matches the External ID configured in the Master role trust policy. Any mismatch prevents Securiti from establishing the connection.

For more information, see [Amazon S3 (Hyperdrive)](/latest/docs/connect-amazon-s3-using-hyperdrive-mode).

#### Additional discovery scan controls for Microsoft 365 Outlook using Hyperdrive

Securiti now provides separate **Scan Attachments** and **Scan Mail Content** options in the **Advanced Settings** for Microsoft Outlook (self-hosted) Discovery Scans using Hyperdrive mode. These options let you independently control whether email attachments and email body content are included in the scan, giving you greater flexibility to tailor scan scope based on your requirements. Both options are enabled by default to preserve the existing scan behavior.

![Checkboxes for scanning email attachments and content are displayed for user selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-15 at 6.24.31 PM.png)

> [!NOTE]
> Note
> 
> - These options are enabled by default and don’t impact the existing in-progress scans.
> - To use this feature, upgrade your Outpost to release 1.148 or later.

For more information, see [Configuring Discovery scans in Outlook (Hyperdrive)](/latest/docs/configuring-discovery-scans-in-sharepoint-hyperdrive-1).

#### Incremental Inventory scans for Hyperdrive SharePoint and OneDrive connectors

Securiti has introduced Incremental Inventory scans for the Hyperdrive SharePoint and OneDrive connectors, reducing the time and resources needed to keep inventory up to date. Previously, every sync scanned the entire data system from scratch. Inventory syncs now use activity logs to detect and process only the changes made since the last run. Securiti skips the scan entirely if no activity has occurred since then. Incremental inventory scans require you to enable Activity Analysis for the connector and complete at least one Activity Analysis run after the last inventory sync.

For more information, see [Configuring Data Inventory Sync for SharePoint (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-sharepoint-hyperdrive).

#### Introducing Amazon S3 support for Hyperdrive policies

We now support Amazon S3 data system for Hyperdrive Quarantine and ROT policies, as shown below. With this update, you can quarantine sensitive files stored in Amazon S3 buckets onboarded through hyperdrive mode.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-DOUSKW8P.png)

For more information, see [Using File Quarantine policies with Hyperdrive mode](https://helpcenter.securiti.ai/docs/using-quarantine-policies-with-hyperdrive-mode).

---

## 1.147

### Release updates - June 2026

#### Support for Hyperdrive in Confluence Cloud (Self-hosted)

Securiti now supports **Hyperdrive mode** for **Confluence Cloud** using self-hosted data system connector. You can enable Hyperdrive mode when creating a Confluence Cloud data system instance to leverage additional compute capacity for supported scans.

With this enhancement, you can run **Discovery Scans**, **Inventory Sync**, and **Entitlement Scans** on Confluence Cloud to discover, classify, and build an inventory of your Confluence resources and access permissions.

| **Feature** | **Scanning entities** |
| --- | --- |
| Discovery Scan | - **Scan scopes:** Sites and Spaces - **Discovered resources:** Pages, Blog posts, Attachments, and comments in scoped Sites and Spaces |
| Inventory Sync | - **Scoping inventory:** Sites and Spaces - **Data Inventory:** Pages, Blog posts, Attachments, and comments in scoped Sites and Spaces |
| Entitlement Scan | - **Entitlement resources:** - **Instance level:** Users, Groups, Confluence Spaces, AI Agents, and Applications. - **File level:** Pages and Blog posts - **Relationship mapping:** Identifies which Users, Groups, Applications, and AI Agents have access to specific Confluence Pages and Blog posts |

> [!NOTE]
> Note
> 
> - Currently, Activity Analysis support is not available for Confluence Cloud using Hyperdrive mode.
> - If Hyperdrive is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

#### Support for Hyperdrive in Google Drive (Google Workspace)

Securiti now supports **Hyperdrive mode** for **Google Drive (Google Workspace)** using self-hosted data system connector. You can enable Hyperdrive mode when creating a Google Drive data system instance to leverage additional compute capacity for supported scans.

With this enhancement, you can run **Discovery Scans**, **Data Inventory Sync**, and **Entitlement Scans** on Google Drive to discover, classify, and inventory files, folders, labels, and access permissions across My Drive and Shared Drives.

| Feature | Scanning entities |
| --- | --- |
| Discovery Scan | **Scan scopes:** My Drive and Shared Drives **Discovered resources:** Files and folders in My Drive and Shared Drives, including Google Drive labels applied to files |
| Data Inventory Sync | **Scoping inventory:** Google Groups and Drives **Data inventory:** Files and folders in My Drive and Shared Drives, including Google Drive labels applied to files |
| Entitlement Scan | **Entitlement resources:** Users, Groups, Applications, and AI Agents **Relationship mapping:** Identifies which users, groups, applications, and AI agents have access to specific Google Drive files |

This update also introduces **Activity Analysis** for Google Drive. You can monitor how users, groups, applications, and AI agents interact with files and folders across My Drive and Shared Drives. In Graph Explorer, the Activity Log node displays activity events mapped to actions such as access, create, modify, delete, move, share, and search.

> [!NOTE]
> Note
> 
> - In release 1.147, Hyperdrive mode for Google Drive supports authentication only through a Global Administrator email. Custom role for non-admin users is not currently supported.
> - If Hyperdrive is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

#### Support for Hyperdrive in Gmail (Google Workspace)

Securiti now supports **Hyperdrive mode** for **Gmail (Google Workspace)** using self-hosted data system connector. You can enable Hyperdrive mode when creating a Gmail data system instance to leverage additional compute capacity for supported scans.

With this enhancement, you can run **Discovery Scans**, **Data Inventory Sync**, **Entitlement Scans**, and **Activity Analysis** on Gmail (Google Workspace) to discover, classify, and inventory email data, understand access permissions, and monitor how users, applications, and AI agents interact with Gmail resources.

| Feature | Resources |
| --- | --- |
| Discovery Scan | - **Scan scope:** Domains and Groups - **Discovered resources:** Email message content and attachments |
| Data Inventory Sync | - **Scoping inventory:** Domains and Groups - **Data inventory:** Email message content and attachments |
| Entitlement Scan | - **Entitlement resources:** Users, Groups, Applications, and AI Agents - **Relationship mapping:** Identifies which users, groups, applications, and AI agents have access to specific Gmail mailboxes and files |

With this update, Security and Governance teams can use Activity Analysis to gain visibility into how Gmail data is accessed and used across the organization. You can monitor how emails are sent, forwarded, and accessed, helping identify risky behavior and maintain oversight of AI agent activity.

> [!NOTE]
> Note
> 
> If Hyperdrive is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

#### Adding SMB Provider support for Hyperdrive Entitlement Scans

Securiti has enhanced the SMB connector by introducing an **SMB Provider** configuration option to support Entitlement Scans across different SMB storage platforms using Hyperdrive mode.

This update lets you select the appropriate SMB provider during connector configuration, including **Dell Isilon**, and **NetApp ONTAP**. By supporting provider-specific entitlement collection methods, Securiti can more accurately retrieve and analyze access permissions across SMB environments.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-04 at 11.36.43 AM.png)

> [!NOTE]
> Note
> 
> - These configurations currently apply only to support Entitlement scans using Hyperdrive mode.
> - To use the SMB Provider configuration, you must upgrade to Outpost version 1.147.0 or higher.

For more information, see [SMB](/latest/docs/smb-1).

#### Restricting restore point actions to a single agent

We have updated the **Agent Activity Overview** dashboard to remove restore point actions, such as revert and undo if multiple agents are selected in the view. Restore point actions, including the ability to revert AI-driven changes, are now only available when viewing activity for a single AI agent, as shown below.

![Overview of agent activities with data systems and restore points displayed over time.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/restoreactions_multipleagents.png)

![Overview of agent activity with options to undo file deletion and view logs.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/restoreactions_singleagent.png)

This update ensures that Undo AI actions are only accessible where they are relevant, reducing the risk of unintended reverts and keeping the multi-agent view focused on monitoring and investigation.

For more information, see [Using Agent Activity Overview dashboard](https://helpcenter.securiti.ai/docs/agent-activity-overview-dashboard).
