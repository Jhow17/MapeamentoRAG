---
title: "Deactivate and purge data in data system connector"
slug: "deactivate-and-purge-data-in-data-system-connector"
updated: 2026-10-01T04:56:42Z
published: 2026-10-01T04:56:42Z
canonical: "helpcenter.securiti.ai/deactivate-and-purge-data-in-data-system-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Deactivate and purge data in data system connector

When you have activated a data system connector, Securiti lets you deactivate the connector and remove its data for troubleshooting and upgrading. There are two options:

| Deactivation type | Explanation |
| --- | --- |
| Deactivate and purge data | Use this option to deactivate the Data system Connector and permanently remove all associated data from logs, databases, and storage. In this case, Securiti removes the connector but retains the data source. |
| Purge data | Use this option to permanently delete data from logs, databases, and storage while keeping the Connector active. In this case, Securiti removes the data but retains both the Connector and its data source. |

To deactivate the connector and purge data:

1. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
2. From the Platform Services section in new navigation, select **Settings**.
3. From the **System Settings** menu, choose **Integrations > Data Systems > Monitored**.
4. Open your relevant Data system Instance, go to **Overview**, and click **Authentication** section dropdown .
5. Choose **Deactivate & purge data** or **Purge data** as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Deactivating Button(1).png)

> [!NOTE]
> Note
> 
> The time to complete the Deactivation or purge data is different.
> 
> - In the case of Deactivate & purge data, the process is fast, as you see an empty Connector immediately. It follows the fire-and-forget model, where it sends deletion tasks and doesn't wait for the acknowledgment.
> - In the case of Purge data, it takes a little longer to complete the purge as it waits for all purge tasks to complete.
> - Before deactivating a connector, ensure that all active scans, such as Discovery, Inventory Sync, Scoping Inventory, or any other ongoing scans, are either completed or cancelled. The connector can be deactivated only after there are no active scans in progress.

## Related

- [Configuring connectors for monitored data systems](/configuring-connectors-for-monitored-data-systems.md)
