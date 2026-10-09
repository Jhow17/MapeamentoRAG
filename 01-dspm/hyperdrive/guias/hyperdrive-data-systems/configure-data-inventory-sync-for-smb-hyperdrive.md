---
title: "Configure Data Inventory Sync for SMB (Hyperdrive)"
slug: "configure-data-inventory-sync-for-smb-hyperdrive"
updated: 2026-07-20T11:40:24Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/configure-data-inventory-sync-for-smb-hyperdrive"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Configure Data Inventory Sync for SMB (Hyperdrive)

Securiti supports Data Inventory Sync for SMB (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

See [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors), for more information.

You can configure Data Inventory Sync for your Data system Instance from the **Inventory** tab, after the connector activation.

#### Prerequisites for running Data Inventory Sync for SMB

Following prerequisites must be met to successfully run Data Inventory Sync for SMB Connector:

- Ensure the SMB host is reachable and properly configured for communication.
- Verify that the selected shares are discoverable on the SMB host.
- Ensure files within the shares are accessible using the provided Credentials.
- SMB owner information and file creation dates should be retrievable, if available.

In addition to the above prerequisites, you must provide necessary Permissions as described in the section below.

#### Permissions required for SMB Data Inventory Sync

You must configure the following required Permissions as described in [Permissions section in SMB](/latest/docs/smb-1#permissions-and-uses-cases) for running Data Inventory Sync on SMB Data system Instance.

| Permission | Use case |
| --- | --- |
| List shares | The permission is required to discover network shares. It is necessary in case you are activating the Connector with “/” as a shared path. |
| Read | The permission is required to scan an SMB share. |
| Read and Write | The read and write Permissions are required on both the source share and the quarantine share if the quarantine policy is being used. |

#### Configure Data Inventory Sync for SMB

After authenticating the SMB connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for Microsoft Teams.

1. In the **Inventory** tab, under the **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | Data inventory: Files in SMB shares, SMB share names |
| Run Entitlement Scan | Enable the toggle to assess how access and ownership of data are structured within your SMB environment. | **SMB resources:** - Users - Groups - Application - Computers **Relationship mapping:** - Mapping of which users, groups, application, or Computers have access to specific SMB Files and Folders. |
| Fetch Owner? | Enable the toggle if you want to scan and fetch the owner's information. | Owner information. |
| Fetch Timestamps? | Enable the toggle if you want to fetch the file's creation date and last access date. | File creation and last access date. |
| Exclude Snapshot Directories? | Enable the toggle if you want to exclude `.snapshot` or `~snapshot` directories from the data inventory to reduce the scanning time. | Excludes files that reside in snapshot directories |
2. In the **Data Inventory and Entitlement Sync Scope** section on the same **Inventory** tab, select the collections of data resources to be included in your inventory.
3. Click **Save**
4. Click **Execute** after the update is saved successfully.
  - It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** message in the **Inventory Sync Options** section.
  - If you want to cancel the **Data Inventory Sync**, perform the following steps:
    1. Under the **Inventory Sync Options** beside **Status**, click on the **Cancel Scan** link.

![iaasDIS_cancelscan_option.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-92b09589-1ad3-031b-faaf-1f9fd73abfea(3).png)
    2. On **Cancel the Data Inventory Sync** popup, click **Okay**.

It takes time to complete the scan cancellation process.

![iaasDIS_cancelscan_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a90a67b6-aae0-eb99-2176-239fdcbe3293(3).png)
5. To view the Scan statistics for Inventory scans, proceed to the [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive).

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.
