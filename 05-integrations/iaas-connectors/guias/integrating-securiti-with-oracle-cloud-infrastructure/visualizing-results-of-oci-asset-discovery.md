---
title: "Visualizing Results of Asset Discovery"
slug: "visualizing-results-of-oci-asset-discovery"
updated: 2026-07-21T15:08:35Z
published: 2026-07-21T15:08:35Z
canonical: "helpcenter.securiti.ai/visualizing-results-of-oci-asset-discovery"
stale: true
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Visualizing Results of Asset Discovery

Create queries for your cloud accounts to retrieve asset discovery data and view all discovered assets across these modules:

- [Graph Explorer](/latest/docs/using-graph-explorer)
- [Universal Data Explorer](/latest/docs/using-the-universal-data-explorer)
- [Inventory](/latest/docs/using-inventory)
- [Reporting](/latest/docs/using-graph-reporting-dashboards)

The following use case demonstrates a query that retrieves asset details for Compute Instances using Graph Explorer.

1. Select the **jewel icon** from the left panel, and choose **Graph Explorer** from the left navigation bar.

![Dashboard displaying security posture findings and risk severity metrics for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/1(3).png)
2. To open the filter menu, near the upper left corner of the page, click **+** or the **Begin Your Search** button at the center of the page.

![Graph Explorer interface showing options to add filters and begin a search.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/2(2).png)
3. Select the **Compute Instance** node from the entities menu to fetch your compute assets.

![Graph Explorer interface showing options for Compute Instance and related services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/3(2).png)
4. Add a relationship, and choose the **Network** node to bring in the networks each instance connects to.

![Graph Explorer interface showing network options and related entities for selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/4(1).png)
5. Add a relationship to the **Network** node, and choose the **Subnetwork** to further scope results down to the subnetworks each network belongs to.

![Graph Explorer interface showing Subnetwork details within the Network section.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/5.png)
6. Add a property to the Compute Instance node: select **Add Property > Hosting > is one of > Oracle Cloud Infrastructure** and click **Apply**.

![User selects Oracle Cloud Infrastructure and applies filters in Graph Explorer interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/6.png)
7. Click **Run Query**.
8. To view details of a compute instance discovered through this query, select a discovered compute instance and click **Explore**.

![Graph Explorer interface displaying OCI Compute Instances and their properties in a table format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/7(1).png)

The graph below shows the relationships between an OCI Compute Instance and its associated components, such as IaaS Cloud, Region, Account, Network, Subnetwork, Block Storage, and Security Posture findings. The Properties panel below the graph displays instance details such as Asset Name, Asset Type, Hosting, Region, Web Link, Cloud Resource ID, OS Platform, and Account.

![Overview of a compute instance with security posture and storage details displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-20 at 3.29.16 PM.png)

## Related

- [Creating an OCI Instance](/creating-an-oci-instance.md)
