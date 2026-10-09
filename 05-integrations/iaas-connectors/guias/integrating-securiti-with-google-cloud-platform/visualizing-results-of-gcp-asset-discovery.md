---
title: "Visualizing Results of Asset Discovery"
slug: "visualizing-results-of-gcp-asset-discovery"
updated: 2026-05-21T07:14:26Z
published: 2026-05-21T07:14:26Z
canonical: "helpcenter.securiti.ai/visualizing-results-of-gcp-asset-discovery"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Visualizing Results of Asset Discovery

Create queries for your cloud accounts to retrieve asset discovery data and view all discovered assets across these modules:

- [Graph Explorer](/v1/docs/using-graph-explorer)
- [Data Command Graph](/v1/docs/using-data-command-graph)
- [Inventory](/latest/docs/using-inventory)
- [Reporting](/v1/docs/using-graph-reporting-dashboards)

The following use case demonstrates a query that retrieves asset details for Data Systems scoped by Discovery Scans using **Graph Explorer**.

1. Select the jewel icon from the left panel, and choose **Graph Explorer** from the left navigation bar.

![Dashboard displaying security posture findings and risk severity metrics for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-20 at 8.29.02 PM(1).png)
2. To open the filter menu, near the upper left corner of the page, click **+** or the **Begin Your Search** button at the center of the page.

![GCP-Results-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d0ed8d8d-53c8-3b77-c0f0-658b077e8260.png)
3. Select the **Data System** node from the entities menu to fetch your data systems.
4. Add a relationship, and choose **Discovery Scan** node from the entities menu.

![GCP-Results-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5d95b6dc-c08e-e189-2ae7-bdde2a16e180.png)
5. To view details of the data systems discovered by discovery scan, select a discovered data system and click **Explore**.

![GCP-Results-4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f03e4747-2cef-dfd3-b7d2-d2055b0f635a.png)

The graph below shows the relationships between a Google Cloud BigQuery asset and its associated components, such as accounts, regions, user groups, and data structure elements.

![GCP-Results-5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ebad662-f673-ec00-867c-4b433f985d2a.png)

## Related

- [Creating a GCP IaaS Instance (version 1.124 and later)](/creating-a-gcp-iaas-instance-version-1124-and-later.md)
- [Creating a GCP IaaS Instance (version 1.123 and earlier)](/creating-a-gcp-iaas-instance-version-1123-and-earlier.md)
