---
title: "Configuring Data Inventory Sync for Zendesk Support (Self-hosted)"
slug: "configuring-data-inventory-sync-for-zendesk-support-self-hosted"
updated: 2026-08-31T09:56:58Z
published: 2026-08-31T09:56:58Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-zendesk-support-self-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Zendesk Support (Self-hosted)

Securiti supports Data Inventory Sync and entitlement scanning for Zendesk Support (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For Gencore AI use cases, the scan builds an index of Entitlements to files for populating Gencore AI Pipelines.

For more information, see [Data Inventory Sync for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync and entitlement scanning for your Data system Instance from the **Inventory** tab, after the Connector Activation. Prior to the Connector Activation process, fulfill any required prerequisites as highlighted below for successful scanning.

### Prerequisites for Data Inventory Sync in Zendesk Support

#### Allowlisting APIs

You must allowlist the following APIs between your deployed Securiti Pod and the Zendesk APIs to successfully run the Data Inventory Sync.

Default URL is https://{{tenant}}.zendesk.com

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://{{tenant}}.zendesk.com/api/v2/organizations.json | Get organizations |
| 2 | GET | https://{{tenant}}.zendesk.com/api/v2/tickets.json | Get tickets |
| 3 | GET | https://{{tenant}}.zendesk.com/api/v2/tickets/{{ticket_id}}/comments.json | Get ticket comments |
| 4 | GET | https://{{tenant}}.zendesk.com/api/v2/attachments | Get attachments |
| 5 | GET | https://{{tenant}}.zendesk.com/api/v2/organizations/{{organization_id}}.json | Get organization information |
| 6 | GET | https://{{tenant}}.zendesk.com/api/v2/search/export.json | Get updated tickets |
| 7 | GET | https://{{tenant}}.zendesk.com/api/v2/attachments/{{attachment_id}}.json | Get attachment url |
| 8 | GET | https://{{tenant}}.zendesk.com/api/v2/users.json | Get users |
| 9 | GET | https://{{tenant}}.zendesk.com/api/v2/users/{{user_id}}/group_memberships.json | Get user groups |
| 10 | GET | https://{{tenant}}.zendesk.com/api/v2/groups/{{group_id}}/users.json | Get group users |
| 11 | GET | https://{{tenant}}.zendesk.com/api/v2/groups.json | Get groups |

### Configuring Data Inventory Sync for Zendesk Support connector

After activating the Zendesk Support (Self-hosted) Connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for Zendesk Support.

1. > [!NOTE]
> **Note**
> 
> The Zendesk Support Connector’s entitlement resolution does not include external users at the Instance level, so external users are not saved in the data inventory.

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Zendesk organizations - Data inventory: All attachments, subject, description, and comments of a ticket. |
| Run Gencore AI Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. This is used in Gencore AI pipelines | View Permissions on Zendesk Support organizations that are used to restrict prompt responses in our Gencore AI product. |
  1. In the **Inventory** tab, under **Inventory Sync** section, configure the following settings:
2. In the **Data Inventory and Entitlement Sync Scope** section on the same **Connector** tab, select the collections of data resources to be included in your inventory.

![Data inventory screen showing selected organizations and options for syncing data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/zendeskscopes.png)
3. Click **Save**
4. Click **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
5. To view the Scan statistics for Inventory and Entitlement scans, see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.
