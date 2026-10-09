---
title: "Webhooks"
slug: "webhooks"
updated: 2026-04-06T05:34:59Z
published: 2026-04-06T05:35:01Z
canonical: "helpcenter.securiti.ai/webhooks"
area: integrations
modulo: webhooks
tipo: guia
data_captura: 2026-10-08
---

# Webhooks

The Webhooks page in **Integrations** lets you create, view, and manage webhook endpoints used by Securiti workflows and integrations. Webhooks enable external systems to receive real-time event notifications from Securiti.

To access the **Webhooks** dashboard:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon, and choose **Integrations** from the left navigation bar.
2. From the left menu of the **Integrations** page, select **Webhooks**.

The dashboard displays a summary count and a table of all configured Webhooks in your tenant. The page provides the following capabilities:

- A table view for all configured Webhooks instances.
- Summary metric displayed at the top of the grid that shows count for total **Webhooks**.
- A search bar to search webhooks by name.
- A top-level filter that lets you search webhooks by the webhook name, description, source, authentication type, and URL.
- A **Column Selector** that lets you include or exclude specific columns, and rearrange their order for custom viewing. It also contains a **Restore Default** button that lets you reset the custom layout back to the original one.
- A **Generate Webhook URL** button that lets you generate webhook URLs and copy endpoints directly from the same interface.

![Webhook integration settings with options for filtering and generating URLs displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/webhookspage(1).png)

### **Understanding the table view**

Each row in the table represents a single webhook instance. Key columns include:

| Column | Description |
| --- | --- |
| Name | Displays the webhook instance name. |
| Source | Displays the source for webhook creation, such as **Workflow**. |
| Target Endpoint | Displays the destination data system, such as Box. |
| Authentication Type | Displays the authentication type for a webhooks instance, such as **Signature Based** or **Key Based**. |
| URL | Displays the generated webhook endpoint URL. |

> [!NOTE]
> **Note**
> 
> You can remove columns using the column selector. Securiti adds a horizontal scrollbar automatically as the number of columns increases.

For each webhook, you can select **Copy URL** to copy the endpoint and open the options (three dots) to edit or delete a webhook.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/webhookoptions.png)

### **Filtering and searching webhooks**

Use the search bar at the top of the grid to quickly locate webhooks by name. To narrow down the results, use the top-level filter to focus on specific webhook or filter them by a property.

![Webhook integration settings with options for filtering and generating URLs displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/webhookspage(1).png)

The top-level filter supports filtering by the following properties:

| **Property** | **Description** |
| --- | --- |
| Name | Lets you filter by a webhook name. |
| Description | Lets you filter by a webhook description. |
| Source | Lets you filter by the source application. |
| Authentication Type | Lets you filter a webhook authentication type. |
| URL | Lets you filter by a webhook URL. |
