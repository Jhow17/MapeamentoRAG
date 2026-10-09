---
title: "Configuring Data Inventory Sync for Securiti for Box"
slug: "configuring-data-inventory-sync-for-securiti-for-box"
updated: 2026-08-31T09:54:37Z
published: 2026-08-31T09:54:37Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-securiti-for-box"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Securiti for Box

Securiti supports Data Inventory Sync and entitlement scanning for Securiti for Box (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For Gencore AI use cases, the scan builds an index of Entitlements to files for populating Gencore AI Pipelines.

For more information, see [Data Inventory Sync for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync and entitlement scanning for your Data system Instance from the **Connector** tab, after the Connector Activation. Prior to the Connector Activation process, fulfill any required prerequisites as highlighted in the [section below](/v1/docs/configuring-data-inventory-sync-for-zendesk-support-self-hosted), for successful scanning.

#### Prerequisites for configuring Data Inventory Sync for Securiti for Box

#### Accepting Custom Terms of Service (ToS) for Box

You must have a Box administrator account and accept Custom Terms of Service (ToS) to let Securiti perform scans successfully.

Securiti skips scanning the user's directly-owned data if the ToS is not accepted and continues to process other users. This prevents the scan from failing and ensures that data from compliant users is still processed.

> [!NOTE]
> **Note**
> 
> Files owned by a skipped user may still be included in the scan if they are accessed via a collaborator who is within the scan's scope and has accepted the ToS.

#### Allowlisting APIs

You must allowlist the following APIs to successfully run the Data Inventory Sync for Securiti for Box.

Following are the Base URLs:

- **Default URL:** "https://api.box.com"
- **App URL:** "https://app.box.com"

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://api.box.com/2.0/users/me | Get current user |
| 2 | GET | https://api.box.com/2.0/users | Get users |
| 3 | GET | https://api.box.com/2.0/folders/{{folder_id}}/items | Get box folders |
| 4 | GET | https://api.box.com/2.0/groups/{{group_id}}/memberships | Get members of a group |
| 5 | GET | https://api.box.com/2.0/files/{{id}}/collaborations | Get collaborators |
| 6 | GET | https://api.box.com/2.0/folders/%s | Get folder details |
| 7 | GET | https://api.box.com/2.0/files/%s | Get file details |
| 8 | GET | https://api.box.com/2.0/groups | Get Groups |

#### Configuring Data Inventory Sync for Securiti for Box

After activating the Securiti for Box (Self-hosted) Connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for Securiti for Box

1. In the **Inventory** tab, in the **Inventory Sync** section, enable the following settings to suit.

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Box groups in enterprise - Data inventory: All Files and Folders in Personal, Shared, and Team folders |
| Run Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. | View Permissions on Box files used to restrict prompt responses. |
2. (Optional) In the **Inventory Scope** section on the same **Inventory Sync** tab, select the collections of data resources to be included in your inventory.

![Data inventory settings showing selected groups and sync options for Dropbox integration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dropboxscopes.png)
3. Click **Save.**
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
