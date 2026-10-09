---
title: "Configure Data Inventory Sync for SMB"
slug: "configure-data-inventory-sync-for-smb"
updated: 2026-08-31T08:36:52Z
published: 2026-08-31T08:36:52Z
canonical: "helpcenter.securiti.ai/configure-data-inventory-sync-for-smb"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure Data Inventory Sync for SMB

Securiti supports Data Inventory Sync for SMB (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

See [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors), for more information.

You can configure Data Inventory Sync for your Data system Instance from the **Connector** tab, after the Connector Activation.

#### Prerequisites for running Data Inventory Sync for SMB

Following prerequisites must be met to successfully run Data Inventory Sync for SMB Connector:

- Ensure the SMB host is reachable and properly configured for communication.
- Verify that the selected shares are discoverable on the SMB host.
- Ensure files within the shares are accessible using the provided Credentials.
- SMB owner information and file creation dates should be retrievable, if available.

In addition to the above prerequisites, you must provide necessary Permissions as described in the section below.

#### Permissions required for SMB Data Inventory Sync

You must configure the following required Permissions as described in [Acquire authentication credentials in SMB](/v1/docs/acquire-authentication-credentials-in-smb) for running Data Inventory Sync on SMB Data system Instance.

| Permission | Use case |
| --- | --- |
| List shares | The permission is required to discover network shares. It is necessary in case you are activating the Connector with “/” as a shared path. |
| Read | The permission is required to scan an SMB share. |
| Read and Write | The read and write Permissions are required on both the source share and the quarantine share if quarantine policy is being used. |

### Configuring Data Inventory Sync

After authenticating the SMB connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for Microsoft Teams.

1. In the **Inventory** tab, under **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | Data inventory: Files in SMB shares, SMB share names |
| Fetch Owner? | Enable the toggle if you want to scan and fetch the owner's information. | Owner information. |
| Fetch Timestamps? | Enable the toggle if you want to fetch the file's creation date and last access date. > [!NOTE] > Note > > To use this feature, you must upgrade your pod version to release 1.137 or higher. | File creation and last access date. |
| Exclude Snapshot Directories? | Enable the toggle if you want to exclude `.snapshot` or `~snapshot` directories from data inventory to reduce the scanning time. > [!NOTE] > Note > > To use this feature, you must upgrade your pod version to release 1.140 or higher. | Excludes files that reside in snapshot directories |
2. In the **Data Inventory and Entitlement Sync Scope** section on the same **Connector** tab, select the collections of data resources to be included in your inventory.
3. Click **Save**
4. Click **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
5. To view the Scan statistics for Inventory scans, proceed to the [Inventory Sync Statistics page](/latest/docs/viewing-data-inventory-sync-statistics).

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.
