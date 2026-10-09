---
title: "Scoping Inventory Syncs for connectors"
slug: "scoping-metadata-syncs-for-connectors"
updated: 2026-09-01T05:19:23Z
published: 2026-09-01T05:19:23Z
canonical: "helpcenter.securiti.ai/scoping-metadata-syncs-for-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Scoping Inventory Syncs for connectors

Scoping Inventory Sync collects data from the connected data system to define scopes for Data Inventory Syncs and Discovery Scans. Examples include SharePoint Sites and Libraries, SMB Shares, and databases or tables from structured data systems. These syncs run automatically after a connector is activated, enabling scan scopes to appear for Data Inventory Syncs and in the Discovery scan page.

> [!NOTE]
> **Note**
> 
> - Securiti does not perform Scoping Inventory Syncs for connectors hosted on the Securiti-Cloud.
> - Securiti disables scoping inventory sync configuration options when the connector authentication fails.

The following options are available for managing these Scoping Inventory Syncs.

- **Starting syncs manually**: To manually start Scoping Inventory Sync, click **Start Sync**.

> [!NOTE]
> **Note**
> 
> The sync runs automatically upon activating the connector for the first time.

![Overview of integration settings with options for syncing and configuration details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scopingsync_start.png)
- **Scheduling automatic syncs**: To schedule the Scoping Inventory Sync, click **Scoping Schedule** and select the sync frequency to 3, 7, or 30 days. To disable automatic sync, select **Off** and manually start the sync when needed.

On **Overview** screen, click the down arrow next to **View Stats** and click **Scoping Schedule**, as shown below.

![Overview of integration settings with highlighted options for Scoping Inventory Sync.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scopingsync_schedule.png)

- **Cancelling a sync**: To cancel an ongoing sync, click **Cancel Sync** if the sync is not required.

![Overview of integration settings with highlighted options for syncing and configuration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scopingsync_cancel.png)

These options let you control Scoping Inventory Syncs as needed and prevent unnecessary syncs or manually trigger them to pick up newly added metadata.

### Monitoring Scoping Inventory Sync progress

You can monitor the progress of a Scoping Inventory Sync from the **Overview** page. The information displayed varies depending on whether the sync is running or has finished.

#### While the sync is running

While a Scoping Inventory Sync is running, the **Scoping Inventory Sync** section displays the **In Progress** status, elapsed time, and a running count of the entities discovered so far. The counts update automatically as discovery progresses.

The entity types displayed depend on the connector. For example for Microsoft 365 OneDrive, you can view the number of **Users** and **OneDrive Groups** discovered, as shown below

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-31 at 9.25.32 AM.png)

> [!NOTE]
> Note
> 
> A Scoping Inventory Sync remains **In Progress** while the sync is running or discovered entities are still being ingested and published. The status changes to **Completed** only after both the sync and entity processing are complete.

#### After the sync is finished

After discovery and entity processing are complete, the status changes to **Completed**. The final discovered entity counts remain visible in the **Scoping Inventory Sync** section, allowing you to view the entities discovered during the completed sync.

For example, the completed sync displays the final counts for **Sites** and **Libraries** for Microsoft 365 SharePoint Online, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-27 at 3.34.02 PM.png)

> [!NOTE]
> Note
> 
> To view discovered entity counts and the updated Scoping Inventory Sync status, upgrade to pod version 1.150.0 or later.

You can also check the status and timestamp of the last sync for your connector on the **Overview** page.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-31 at 9.35.51 AM.png)

## Related

- [Configuring connectors for monitored data systems](/configuring-connectors-for-monitored-data-systems.md)
- [Understanding connector status](/understanding-connector-status.md)
