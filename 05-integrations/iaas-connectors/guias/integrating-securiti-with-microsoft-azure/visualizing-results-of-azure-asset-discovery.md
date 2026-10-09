---
title: "Visualizing Results of Asset Discovery"
slug: "visualizing-results-of-azure-asset-discovery"
updated: 2026-05-22T07:25:11Z
published: 2026-05-22T07:25:11Z
canonical: "helpcenter.securiti.ai/visualizing-results-of-azure-asset-discovery"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Visualizing Results of Asset Discovery

You can create queries for your cloud accounts and fetch data for your assets in the Data Command Graph. To fetch discovered assets.

- [Graph Explorer](/v1/docs/using-graph-explorer)
- [Data Command Graph](/v1/docs/using-data-command-graph)
- [Inventory](/latest/docs/using-inventory)
- [Reporting](/v1/docs/using-graph-reporting-dashboards)

The following use case demonstrates a query that retrieves asset details for Azure cloud using Graph Explorer.

1. Select the jewel icon from the left panel, and choose **Graph Explorer** from the left navigation bar.

![Dashboard displaying security posture findings and risk severity metrics for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-20 at 8.29.02 PM(3).png)
2. To open the filter menu, near the upper left corner of the page, click + or the **Begin Your Search** button at the center of the page.

![Graph Explorer interface showing options to add filters and begin a search.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-22 at 12.18.27 PM.png)
3. Select the **Cloud** > **IaaS Cloud** node from the entities menu.

To view details such as discovered data systems, associated accounts, generated posture findings, suggested remediation actions, and more, select the metadata icon and click **Explore**.

![Overview of Azure Cloud services including data systems, storage, and network components.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-22 at 12.24.04 PM.png)
  1. Add a property to this node from the menu, select **Add Property** > **Hosting** > **Equals** > **Azure Cloud** and **click Apply**.

![Graph Explorer interface showing cloud hosting filter options for data queries.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-22 at 12.02.30 PM.png)

## Related

- [Creating a Microsoft Azure Instance](/creating-a-microsoft-azure-instance.md)
