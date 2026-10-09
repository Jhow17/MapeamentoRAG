---
title: "Visualizing Results of Asset Discovery in Graph Explorer"
slug: "visualising-results-of-aws-asset-discovery-in-graph-explorer"
updated: 2026-05-20T15:36:15Z
published: 2026-05-20T15:36:15Z
canonical: "helpcenter.securiti.ai/visualising-results-of-aws-asset-discovery-in-graph-explorer"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Visualizing Results of Asset Discovery in Graph Explorer

Create queries for your cloud accounts to retrieve asset discovery data and view all discovered assets across these modules:

- [Graph Explorer](/v1/docs/using-graph-explorer)
- [Data Command Graph](/v1/docs/using-data-command-graph)
- [Inventory](/latest/docs/using-inventory)
- [Reporting](/v1/docs/using-graph-reporting-dashboards)

1. Select the jewel icon from the left panel, and choose **Graph Explorer** from the left navigation bar.

![Dashboard displaying security posture findings and risk severity metrics for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-20 at 8.29.02 PM.png)
2. To open the filter menu, near the upper left corner of the page, click **+** or the **Begin Your Search** button at the center of the page.

![de_beginsearch.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff36ade5-fcfe-8e12-25a3-d337cb24fabf.png)
3. Select **Account**, **IaaS** or **Data System** node from the entities menu to fetch your cloud accounts and resources.
4. Add relationship and properties as required to fetch filtered results for your assets. See [Using the Graph Explorer Dashboard](/v1/docs/using-graph-explorer) for more details.
5. The grid will display all assets and their properties in columns. You can inspect a particular instance by clicking on your cloud resource and visualizing the relationships in the Instance explorer. See [Using instance explorer in Graph Explorer](/v1/docs/inspecting-instances-in-graph-explorer) for more details.

The screenshots below show a sample query where asset details are fetched for the Amazon Bedrock Knowledge Base for Amazon Bedrock.

![Bedrock_query.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-35de3543-6708-55ca-badd-5f664228e144.png)

![Bedrock_instanceexplorer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f960d0d0-2e0b-d39e-17b0-c0692206e093.png)

> [!NOTE]
> Note
> 
> To see the above process in action, see the [interactive demo](/latest/docs/interactive-demos-enabling-dspm-for-aws#demo-2-visualize-asset-discovery-results-for-aws) on how to visualize asset discovery results for AWS.

## Related

- [Creating an AWS IaaS instance (version 1.111 and later)](/creating-an-aws-iaas-instance-version-1111-and-later.md)
- [Creating an AWS IaaS instance (version 1.110 and earlier)](/creating-an-aws-iaas-instance-version-1110-and-earlier.md)
