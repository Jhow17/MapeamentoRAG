---
title: "Configuring Data Inventory Sync for Outlook"
slug: "configuring-data-inventory-sync-for-outlook"
updated: 2026-08-31T09:27:45Z
published: 2026-08-31T09:27:45Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-outlook"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Outlook

Securiti supports Data Inventory Sync and entitlement scanning for Outlook (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For Gencore AI use cases, the scan builds an index of Entitlements to files for populating Gencore AI Pipelines.

For more information, see [Data Inventory Sync for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync and Entitlement scanning for your Data system Instance, after the Connector Activation. Prior to the Connector Activation process, fulfill any required prerequisites as highlighted below:

#### Prerequisites for configuring Data Inventory Sync for Outlook

#### Permissions required for Outlook Data Inventory Sync

> [!NOTE]
> **Important**
> 
> You must activate your connector for Data Inventory Sync results to show in [Data Command Graph](/latest/docs/using-data-command-graph).

- **Microsoft Graph API Permissions**
  - User.Read.All: This permission is required for discovering metadata for Outlook users and their entitlements during the Data Inventory Sync and entitlement scans.
  - Mail.Read: This permission is required for discovering metadata for Outlook folders during the Data Inventory Sync.
  - GroupMember.Read.All: This permission is required for discovering metadata for Outlook groups and organizations during the Data Inventory Sync.

#### Allowlist APIs for Data Inventory Sync for Outlook (Self-hosted)

You must allowlist the following APIs to successfully run the Data Inventory Sync for Microsoft 365 Outlook.

Default URL is *https://graph.microsoft.com/*

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | `https://graph.microsoft.com/v1.0/organization` | Get organization |
| 2 | GET | `https://graph.microsoft.com/v1.0/groups` | Get a list of groups |
| 3 | GET | `https://graph.microsoft.com/v1.0/groups/$group_id/members` | Get a list of group members |
| 4 | GET | `https://graph.microsoft.com/v1.0/users/$user_id` | Get user |
| 5 | GET | `https://graph.microsoft.com/v1.0/users` | Get a list of users |
| 6 | GET | `https://graph.microsoft.com/v1.0/users/$user_id/mailFolders` | Get a list of mailFolders |
| 7 | GET | `https://graph.microsoft.com/v1.0/users/$user_id/mailFolders/$mail_folder_id/messages/delta` | Get a list of messages |
| 8 | GET | `https://graph.microsoft.com/v1.0/users/$user_id/messages/$message_id/attachments` | Get a list of attachments |

#### Configuring Data Inventory Sync

After activating the Outlook (Self-hosted) Connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for Outlook.

1. In the **Inventory** tab, under **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Outlook groups or users. - Data inventory: Messages, attachments, folders and child folders. > [!NOTE] > **Note** > > Externally linked inline attachments are not scanned, i.e. images linked in the email’s HTML. |
| Run Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. | View Permissions on Microsoft 365 Outlook messages and attachments that are used to restrict prompt responses in our Gencore product. |
2. (Optional) In the **Inventory Scope** section on the same **Inventory Sync** section, select the collections of data resources to be included in your inventory.

You can select the following scopes:
  - All
  - Group(s)
  - User(s)

> [!NOTE]
> **Note**
> 
> - The Outlook data inventory sync now includes all emails within mailbox content for the scoped users or groups, regardless of whether the emails are from internal or external senders.
> - To include all mailboxes and nested folders in the scanning, you must upgrade the pod version to release 1.146 or higher.
> - For new connectors, the scope is selected "None" by default with Inventory Sync Options disabled. For existing connectors, you must reconfigure the Connector to add scopes.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Outlook DS.png)
3. Click **Save**, and **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
4. To view the Scan statistics for Inventory and Entitlement scans, see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.

#### Key considerations for scope configuration

- Externally linked inline attachments are not scanned, i.e. images linked in the email’s HTML.
- Discovery scan includes the following items multiple times:
  - Messages copied to other folders
  - A Message sent by external users to multiple internal users (can be via a group).
  - Emails “Sent As” another user, where copies are saved to multiple mailboxes.
- Messages not scanned:
  - Messages sent by users that are not scoped

#### Entitlement scan limitations

- Users are not entitled to previous emails in a thread after adding them to it.
- Cases related to shared mailbox are not handled at this time, only email senders and receivers is entitled to the message and its attachments.
- All members of DLs will be entitled to all emails sent to it, regardless of their membership at the time the email was sent. Cases where emails are deleted by one of the entitled users also cannot be handled, this also applies to emails sent by groups IF they are not copied to the group’s mailbox.
- In some cases, users receiving external emails as Bcc may not be considered entitled if not selected in the Connector scope.
