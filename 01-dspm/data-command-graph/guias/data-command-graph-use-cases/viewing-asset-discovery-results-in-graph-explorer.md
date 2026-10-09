---
title: "Viewing asset discovery results in Graph Explorer"
slug: "viewing-asset-discovery-results-in-graph-explorer"
updated: 2026-07-21T10:43:25Z
published: 2026-07-21T10:43:25Z
canonical: "helpcenter.securiti.ai/viewing-asset-discovery-results-in-graph-explorer"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Viewing asset discovery results in Graph Explorer

Asset discovery is a fundamental capability within Securiti that can be analyzed in the Data Command Graph. It enables you to identify and catalog assets within your IaaS environments, which include AWS, GCP, and Azure. This functionality provides you with deep visibility into your cloud infrastructure and resources. Asset discovery lets you manage your resources and handle security and compliance efforts for them. With asset discovery, you can visualise and gain contextual insights into asset relationships with various nodes in Graph Explorer and by exploring a resource using Instance Explorer.

Asset discovery utilizes data system connectors to interface with cloud services and discover various assets. Covered assets include infrastructure components like virtual machines, storage, networking resources, as well as AI services such as Amazon Bedrock and Sagemaker Notebooks.

### Prerequisites

Asset discovery is performed on IaaS cloud accounts or data systems that are configured with the required set of permissions. See [Configuring connectors for monitored data systems](/latest/docs/configuring-connectors-for-monitored-data-systems) for more information.

> [!NOTE]
> **Note**
> 
> During the IaaS connector configuration process, once you provide cloud account and discovery permissions, the system utilizes the same set of permissions for asset discovery at any time, eliminating the need for updates.

Moreover, you must enable your module for data and resources to show in the Data Command Graph. If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### Creating queries for asset discovery

You can create queries for your cloud accounts and fetch data for your assets in the Data Command Graph. See [List of supported cloud services](/latest/docs/supported-cloud-native-services-for-posture-policy-rules), for more information about the services and their representation in graph modules.

See the video below to learn about creating asset discovery queries for your cloud services in the Graph Explorer.

[Embedded content](https://player.vimeo.com/video/1030672070)

To create asset discovery query.

1. In the **New Navigation** left sidebar, choose **Graph Explorer**, as shown below.

![Securiti interface showing Graph Explorer with options for data filtering and querying.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Graph Explorer Navigation.png)
2. To open the filter menu, near the upper left corner of the page, click **+** or the **Begin Your Search** button at the center of the page.

![Graph Explorer interface showing options to add filters and begin a search.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add Query button_Graph Explorer.png)
3. Select **Account**, **IaaS** or **Data System** node from the entities menu to fetch your cloud accounts and resources.
4. Add relationship and properties as required to fetch filtered results for your assets. For more information, see [Managing queries in the Graph Explorer](/v1/docs/managing-queries-in-the-graph-explorer).
5. The grid displays all assets and their properties in columns. You can inspect a particular instance by clicking on your cloud resource and visualising the relationships in the Instance explorer. For more information, see [Inspecting instances in Graph Explorer](/v1/docs/inspecting-instances-in-graph-explorer).

The screenshots below shows a sample query where asset details are fetched for Bedrock Knowledge Base for Amazon Bedrock.

![Graph Explorer interface displaying AI Agent and Account entities with various asset names.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/AI Agent with account query_Graph Explorer.png)

![Diagram illustrating AI agent components, including data loader and security posture findings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/AI Agent query_Graph Explorer.png)

## Related

- [Managing queries in the Graph Explorer](/managing-queries-in-the-graph-explorer.md)
