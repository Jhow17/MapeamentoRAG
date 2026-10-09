---
title: "Using Gencore AI Analytics"
slug: "using-gencore-ai-analytics"
updated: 2026-07-20T21:00:00Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/using-gencore-ai-analytics"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Using Gencore AI Analytics

The Gencore AI **Analytics** dashboard gives you a clear view of how you are using your platform and how key services are performing over a certain time range. It brings usage and performance data into one place so you can understand activity trends and spot issues early. You can see how many unique users log in through the portal, how often pipelines are queried, and where those queries come from. It also shows average response times for both pipeline requests and standalone Firewall API calls, helping you track performance and plan improvements.

To open the Gencore AI **Analytics** dashboard, in Securiti, open **Gencore AI > Dashboard > Analytics**.

![Analytics dashboard displaying user logins, pipeline queries, and response times over time.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI Analytics dashboard(2).png)

Some of the key insights you can receive from the **Analytics** dashboard include:

| Item | Description |
| --- | --- |
| Number of Unique User Portal Logins | Shows how many distinct users accessed the user portal during the selected period. This helps you understand overall user adoption and engagement. |
| Pipeline Queries Performed | Displays the total number of queries run through your GenAI pipelines. Use this to track activity levels and workload over time. |
| Pipeline Queries by Source | Breaks down your GenAI pipeline queries by their source: - Test Prompt - Conversation API - Web Widget - Slack - Microsoft Teams - User Portal This helps identify where requests are coming from and which integrations or entry points are most active. |
| Average Response Time – Pipeline (seconds) | Shows the average time your GenAI pipelines take to respond to queries. This helps you monitor performance and spot potential slowdowns. |
| Standalone Firewall API Calls | Displays the total number of API calls made directly to the standalone firewalls, outside of pipelines. This gives visibility into direct usage patterns. |
| Average Response Time – Standalone Firewall (seconds) | Shows the average response time for standalone firewall API calls. Use this to track performance and ensure response times stay within expected limits. |

### Applying filters

You can choose to view insights based on the following:

| Menu | Description |
| --- | --- |
| Pipeline | Choose a specific pipeline or view insights across all pipelines. |
| Firewall | Choose a specific firewall or view insights across all firewalls. |
| Time range | Set the time period for analytics. Available options include: - Last 7 days - Last 30 days - Last 90 days |

To **apply filters** on Gencore AI Analytics dashboard:

1. Go to **Gencore AI > Analytics**.
2. Apply one or more filters as needed.

The dashboard displays insights based on the filters you selected.

To **reset filters** on the Analytics dashboard

1. Go to **Gencore AI > Analytics**.
2. Click **Clear Filters** in the dashboard toolbar.

![Analytics dashboard displaying user logins, pipeline queries, and response times over time.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GenAI Analytics - Clear Filters(1).png)

This resets the Gencore AI analytics dashboard.
