---
title: "Configuring Data Inventory Sync for Microsoft Team"
slug: "configuring-data-inventory-sync-for-microsoft-teams"
updated: 2026-08-31T09:30:37Z
published: 2026-08-31T09:30:37Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-microsoft-teams"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Microsoft Team

Securiti supports Data Inventory Sync and Entitlement scanning for Microsoft Teams (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

For more information, see [Data Inventory Sync for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync and entitlement scanning for your Data system Instance, after the connector activation. Prior to the aonnector activation process, fulfill the required prerequisites as highlighted below

#### Prerequisites for running Data Inventory Sync for Microsoft Teams

#### Permissions required

You must assign the required Permissions to Azure application to run the Data Inventory Sync successfully. For more information on required Permissions, see [permissions section in Microsoft Team connectors.](/latest/docs/microsoft-teams-connectors)

#### Allowlisting APIs

You must allowlist the following APIs between your deployed Securiti Pod and the Microsoft Teams APIs to successfully run the Data Inventory Sync.

Default URL is *https://graph.microsoft.com/*

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://graph.microsoft.com/v1.0/users | Get users |
| 2 | GET | https://graph.microsoft.com/v1.0/teams | Get all teams |
| 3 | GET | https://graph.microsoft.com/v1.0/users/{{user_id}}/chats | Get user chat |
| 4 | GET | https://graph.microsoft.com/v1.0/teams/{{{team_id}}/channels | Get team channels |
| 5 | GET | https://graph.microsoft.com/v1.0/teams/{{{team_id}}/channels/{{channel_id}}/messages/delta | Get channel messages |
| 6 | GET | https://graph.microsoft.com/v1.0/teams/{{team_id}}/members | Get team members |
| 7 | GET | https://graph.microsoft.com/v1.0/teams/{{team_id}} | Get team information |
| 8 | GET | https://graph.microsoft.com/v1.0/teams/{{team_id}}/channels/{{channel_id}} | Get channel information |
| 9 | GET | https://graph.microsoft.com/v1.0/teams/{{team_id}}/channels/{{channel_id}}/sharedWithTeams | Get channel shared with teams |
| 10 | GET | https://graph.microsoft.com/v1.0/teams/%s/channels/%s/members | Get channel members |
| 11 | GET | https://graph.microsoft.com/v1.0/chats/%s/messages | Get channel messages |
| 12 | GET | https://graph.microsoft.com/v1.0/teams/%s/channels | Get team channels |
| 13 | GET | https://graph.microsoft.com/v1.0/teams/{{{team_id}}/channels/{{channel_id}}/messages/{{message_id}}/replies | Get channel message replies |
| 14 | GET | https://graph.microsoft.com/v1.0/teams/{{{team_id}}/channels/{{channel_id}}/messages/{{message_id} | Get channel message |
| 15 | GET | https://graph.microsoft.com/v1.0/chats/{{chat_id}}/messages | Get chat messages |

#### Configuring Data Inventory Sync

After activating the Microsoft Teams Connector, wait until the Discovery scan metadata is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for Microsoft Teams.

1. In the **Inventory** tab, under **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Teams and Channels - Data inventory: Chat and Channel messages |
| Run Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. | View Permissions on Microsoft 365 Teams channels, used to restrict prompt responses. |
2. (Optional) In the **Inventory Scope** section on the same **Inventory Sync** section, select the collections of data resources to be included in your inventory.

You can select the following scopes:
  - All
  - Group(s)
  - User(s)

> [!NOTE]
> **Note**
> 
> For new connectors, the scope is selected "None" by default with Inventory Sync Options disabled. For existing connectors, you must reconfigure the Connector to add scopes.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Teams DS.png)
3. Click **Save**, and **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
4. To view the Scan statistics for Inventory and Entitlement scans, , see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.
