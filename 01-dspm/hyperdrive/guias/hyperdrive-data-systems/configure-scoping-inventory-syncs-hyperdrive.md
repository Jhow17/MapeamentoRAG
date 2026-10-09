---
title: "Configure scoping inventory syncs (Hyperdrive)"
slug: "configure-scoping-inventory-syncs-hyperdrive"
updated: 2026-03-10T08:18:22Z
published: 2026-03-10T08:18:22Z
canonical: "helpcenter.securiti.ai/configure-scoping-inventory-syncs-hyperdrive"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Configure scoping inventory syncs (Hyperdrive)

Scoping Inventory Sync collects data from the connected Microsoft 365 applications to define scopes for Data Inventory Syncs and Discovery Scans. These syncs run automatically after a Connector is activated, enabling scan scopes to appear for Data Inventory Syncs and in the Discovery scan page.

> [!NOTE]
> Note
> 
> Securiti disables scoping metadata sync Configuration options when Authentication fails.

Accessing the scoping inventory sync configuration

1. On the **Overview** page, scroll down to the **Scoping Inventory Sync** section.
2. On the right side of the selected Microsoft 365 app, click the Actions **(Down Arrow)** icon. The following options are available for managing these Scoping Metadata Syncs.
  - **Starting syncs manually:** To manually start Scoping Metadata Sync, click Start Scan.

> [!NOTE]
> Note
> 
> The sync runs automatically upon activating the Connector for the first time.
  - **Scheduling automatic syncs:** To schedule the Scoping Metadata Sync, click Automatically Sync and select the sync frequency to 3, 7, or 30 days. To disable automatic sync, select Off and manually start the sync when needed. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scoping sync.png)
