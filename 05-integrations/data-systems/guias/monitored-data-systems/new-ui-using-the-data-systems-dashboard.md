---
title: "Using Monitored Data Systems page"
slug: "new-ui-using-the-data-systems-dashboard"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/new-ui-using-the-data-systems-dashboard"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Using Monitored Data Systems page

The **Monitored** **Data Systems** page lets you discover, configure, and manage data system connectors from a single, centralized view. It brings together search, filters, status indicators, and quick actions to easily track the state of connector activation and scan readiness.

From this page, you can add new integrations, review configured and active connectors, and identify unmonitored or partially configured systems.

The **Monitored Data Systems** page provides the following capabilities:

- A table view for all configured data system connectors.
- Summary metrics displayed at the top of the grid that show counts for **Configured**, **Active**, Securiti**-Cloud Hosted Connectors**, and **Self-Hosted Connectors** data systems.
- A search bar to search connectors by instance name or data system type.
- A top-level filter that lets you search connectors by their status, data system, or appliance name, type, or owner.
- A **Save View** button that lets you save the current filter and search combination as a named view.
- A **Saved Views** button that lets you apply a view you saved earlier.
- A **Column Selector** that lets you include or exclude specific columns, and rearrange their order for custom viewing. It also contains a **Restore Default** button that lets you reset the custom layout back to the original one.

> [!NOTE]
> Note
> 
> You can add more columns using the column selector.
- A Group by menu that lets you group connectors by data system type, and see the number of connector instances in each group.
- An **Add Integrations** button at the upper right corner of the page to add new connectors. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 11.46.18 AM.png)

## Grouping connectors by data system type

By default, the table view lists every connector instance as its own row. Grouping collects the instances for each data system type into a single row, and shows how many connectors that data system type has.

To group connectors by data system type, on the **Monitored Data Systems** page, to the right of the search bar, from the Group by menu, choose Data System Type. Securiti groups the rows by data system type, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KGNL0BTL.png)

> [!NOTE]
> Note
> 
> Securiti retains your selected Group by option across page refreshes and user sessions.

## Understanding the table view

Each row in the table represents a single connector instance. Key columns include:

| Column name | Description |
| --- | --- |
| Instance name | The name assigned to the connector |
| Status | Indicates whether the connector is active or inactive |
| Data system type | Indicates whether the connector is active or inactive |
| Data system hosting | Shows whether the data system is hosted on SaaS, IaaS, or private cloud |
| Connector type | Indicates whether the connector runs on Securiti Cloud or is self-hosted |
| Authenticated | Shows whether authentication is configured successfully |
| Data Inventory Sync | Indicates whether the Data Inventory Sync is enabled for the connector |
| Scoping Inventory Sync | Indicates whether Scoping Inventory Sync for a connector is successful or not. |
| Discovery scan | Indicates whether the discovery scan is enabled for the connector |
| Owner | Shows the username for the data system instance |

> [!NOTE]
> **Note**
> 
> For some connectors, the Discovery Scan, Data Inventory Sync, or Scoping Inventory Sync columns may show a different icon indicating that the capability isn't supported for that data system.
> 
> Hover over the icon to see a tooltip explaining why, for example, "Discovery Scan isn't supported for this data system." For structured connectors specifically, Data Inventory Sync always shows this state, since Data Inventory Sync isn't supported for structured connectors.

## Filtering and searching connectors

Use the search bar at the top of the grid to quickly locate connectors by instance name or data system type, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-10 at 2.52.51 PM.png)

To narrow down the results, use the top-level filter to focus on specific systems or states, as shown below. You can select a single or multiple properties to filter the results.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-10 at 2.57.45 PM.png)

The top-level filter supports filtering by the following properties:

| Property | Description | Supported operators | Values |
| --- | --- | --- | --- |
| Status | Filters monitored data systems by one or more operational statuses. | is one of | - Active - Inactive - In Progress - Auth Failed |
| Data System Type | Filters monitored data systems by data system type, such as Dropbox (Self-hosted) and OneDrive (Securiti-Cloud). | - is one of - is equal to - is not equal to | List of all supported self-hosted and Securiti cloud hosted data systems. |
| Data Inventory Sync | Lets you filter data systems by their current status of Data Inventory Sync synchronization. | - is one of - is equal to | - Inactive - In Progress - Complete - Cancelled - Cancel Scheduled - Error - Timed Out - Scheduled - Paused - Pause Scheduled - Purge Progress |
| Scoping Inventory Sync | Lets you filter data systems by their current status of Scoping Inventory Sync synchronization. | - is one of - is equal to | - Inactive - In Progress - Complete - Cancelled - Cancel Scheduled - Error - Timed Out - Scheduled - Paused - Pause Scheduled - Purge Progress |
| Pod | Filters by the specific pod configuration used by a connector. | - is one of - is equal to - is not equal to | List of all configured pod instances. |
| Connector Type | Filters by the hosting architecture of a connector. | is one of | - Self-hosted - Securiti Cloud |
| Owner | Filters by the specific user who created the connector. | - is one of - is equal to - is not equal to | List of all user accounts who have created data system instances. |
| DSR Automation | Filters connectors by their DSR Automation support. | is equal to | - True - False |
| Data System Hosting | Filters data systems by their hosting location. | is one of | - SaaS - IaaS - Private Cloud |
| PCS Instance | Filters data systems by PCS instances. | - is one of - is equal to - is not equal to | List of all PCS instances created. |
| Keyring | Filters data systems by Keyrings created. | - is one of - is equal to - is not equal to | List of all Keyrings created. |
| Data System Country | Filters data systems based on the countries. | - is one of - is equal to - is not equal to | List of all the supported countries to create data systems. |

### Saving and reusing filter views

A saved view stores the filters and the search term you apply to the grid, under a name that you choose. Saving a view lets you return to a filter combination you use often, without building it again.

> [!NOTE]
> Note
> 
> The Save View option is disabled until you apply at least one filter or a search term.

**Saving a View**

1. To save a view, on the **Monitored Data Systems** page, apply the filters you want to reuse.
2. At the right end of the filter row, click **Save View**.
3. On the **Save View** popup, enter a **Group**, **Name**, and **Description** for the view and click Save, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-10 at 3.23.42 PM.png)

Securiti adds the view to the **Saved Views** list for the Monitored Data Systems page.

**Using a Saved View**

1. To apply a saved view, on the right end of the filter row for **Monitored Data Systems** page, click **Saved Views**.
2. On the **Saved Views**, click the view you want to apply.

Securiti loads the saved filters into the filter row, and the grid shows the matching connectors.
3. To view or delete a saved view, from the Saved Views list, click More Actions (three dots) for that view, then click Edit or Delete, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 10.01.00 AM.png)

## Filtering the integrations catalog

When adding a new connector, you can use the top-level filter on the **Add Integration** page to narrow down the catalog based on connector capabilities. This lets you quickly identify which connectors meet your requirements without browsing the full list. To filter connectors:

1. From the upper right corner of the **Add Integration** page, click **+** next to the top-level filter to open the filter panel.
2. Select the required properties to filter connectors by, and click **Apply**.
3. To remove all active filters and restore the full connector list, click **Clear All**.

![Interface for adding integrations with filter options and module selections displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datasystems_filtering(2).png)

> [!NOTE]
> **Tip**
> 
> To select or clear multiple filter values faster, click one value to set it as the starting point, then hold **Shift** and click another value. Every value between the two takes the state of the one you just clicked. **Shift-click** again to extend or shrink the range from the same starting point.

You can filter data systems by the following properties:

| Property | Description | Supported operators | Values |
| --- | --- | --- | --- |
| Connector Data Type | Filters connectors by the type of data they handle. | - Is equal to - Is not equal to | - Structured - Unstructured - Hybrid - Scanless |
| Deployment Model | Filters connectors by deployment type. | - Is equal to - Is not equal to - Is one of - Contains at least | - ePod - Hyperdrive |
| Module | Filters connectors by the Securiti modules they support, such as connectors that support Data Inventory Sync. | - Discovery Scan - Pause (Discovery Scan) - IAM Scan - DSR Automation - Smart Search DSR - Posture Scan - Data Inventory Sync - Gencore Entitlements - Scoping Inventory Sync - File Quarantine Policy - Data Labeling Policy - Custom Document Type - Access Verification |
| Credential Vault | Filters connectors by the credential vaults they support. > [!NOTE] > Note > > The **Credential Vaults** filter is only available on the **Self-Hosted** tab. Credential Vaults are not supported on the **Securiti Cloud** tab, so no values are displayed there. | - None - AWS Secret Manager - Azure Key Vault - CredStash - CyberArk - CyberArk Conjur - Delinea Secret Server - GCP Secret Manager - HashiCorp |
