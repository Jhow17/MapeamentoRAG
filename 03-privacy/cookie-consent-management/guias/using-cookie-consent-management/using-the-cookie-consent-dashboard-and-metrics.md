---
title: "Using the Cookie Consent Dashboard and Metrics"
slug: "using-the-cookie-consent-dashboard-and-metrics"
status: "new"
updated: 2026-09-17T17:18:38Z
published: 2026-09-17T17:19:48Z
canonical: "helpcenter.securiti.ai/using-the-cookie-consent-dashboard-and-metrics"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Cookie Consent Dashboard and Metrics

**Scenario**

As a Data Protection Officer (DPO), you must manage multiple websites across departments. But without a central system to track ownership and privacy responsibilities, things become chaotic. With Securiti’s Cookie Consent Management module, you can add domains and assign owners directly. You ensure each website meets regulatory requirements from the start by establishing clear ownership.

> [!WARNING]
> Important
> 
> - The new Cookie Consent Dashboard and Metrics experience is now available in the module. For more information on how to migrate your existing consent data to the new dashboard, see [Migrating consent records from Legacy to New Consent Dashboard Experience](/latest/docs/using-the-cookie-consent-management-dashboard#migrating-consent-records-from-legacy-to-new-consent-dashboard-experience).
> - Securiti lets you filter and analyze consent records going back **18 months** from the current date, but within that timeframe the dashboard can display **only one year of consent data at a time**.
> 
> You can access consent records older than 18 months through the **Legacy Consent Data** view.
> - The Legacy Consent Data view supports only date-based filtering and does not support the advanced filters available in the new Cookie Consent Domains dashboard.

The **Cookie Consent Dashboard & Metrics** experience provides centralized visibility into cookie consent activity, helping you understand how data subjects interact with cookie banners and preference centers across your domains.

The experience includes two primary views:

- **Dashboard**, which displays individual consent records collected through cookie banners and preference centers.
- **Metrics**, which presents aggregated consent trends and performance through visual widgets.

You can move between these views using the **Dashboard** and **Metrics** tabs at the top of the page.

## Cookie Consent Dashboard

The Dashboard view focuses on individual consent records collected through cookie banners and preference centers across published domains. It provides record-level visibility into how and when consent was captured.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Dashboard-View.png)

The **Cookie Consents** table shows records of every event in which a data subject grants, declines, or withdraws consent for the selected consent type. It includes the following consent statuses:

| Status | Description |
| --- | --- |
| Granted | The data subject consented to cookies. |
| Declined | The data subject did not consent for the first time. |
| Withdrawn | The data subject withdrew their consent after previously granting it. This includes removing consent after an . |
| No Action | The data subject did not take any action to accept or decline cookies within the same day. Securiti automatically omits No Action consents that are clearly caused by a bot, spider, or crawler visiting the page. > [!NOTE] > **Note** > > If this feature is not available in your tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. |

### Viewing detailed consent record information

To view detailed information for an individual consent record from the Dashboard:

1. From the **Cookie Consents** table, locate the consent record you want to review in detail.
2. Click the **metadata** icon next to the consent record, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Metadata-Icon.png)
3. In the **Metadata Explorer** popup, expand the accordions to review the following information, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Metadata-Explorer.png)

## Cookie Consent Metrics

The **Metrics** view provides an aggregated, visual overview of consent behavior across your domains. It helps you evaluate engagement trends, consent outcomes, and regulatory signals at scale.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Metrics-View.png)

Use the following table to understand the definitions of widgets specific to the Cookie Consent Metrics:

| Widget | Definition |
| --- | --- |
| Unique Users | Displays the total number of distinct data subjects who interacted with a cookie banner or preference center during the selected time period. The widget also shows a cumulative total for comparison. For instance, if the same data subject interacts multiple times, the widget counts them only once within the selected range. > [!NOTE] > Note > > Super Admins can view the complete cumulative total in the **Total Unique Users** widget on the Consent Usage Metrics dashboard. |
| Consent Status | Shows the distribution of consent outcomes such as **Granted**, **Declined**, and **Withdrawn** for the selected time period. To avoid double counting, the widget reflects each data subject’s first consent interaction and their most recent change. For instance, if a data subject grants consent and later withdraws it, the latest status is reflected. |
| GPC Users | Reports how many data subjects’ browsers sent a Global Privacy Control (GPC) signal during consent collection during the selected time period. |
| Managed Preferences | Displays how often data subjects updated and saved their cookie preferences for non-essential categories during the selected time period. Only true state changes are counted; saving without making changes does not increase the count. For instance, actions such as switching from Opt-in to Opt-out for Analytics or Advertising cookies. |
| Banner Dismissed | Tracks how many times data subjects actively dismissed the cookie banner by clicking the close or dismiss option during the selected time period. |
| Consent Status by Non-Essential Category | Visualizes trends showing how data subjects grant or decline consent across non-essential cookie categories during the selected time period. Granted and declined actions are shown separately in two graphs, grouped into buckets (1, 2, 3, 4, or 5+ cookie categories) based on the number of cookie categories affected by each data subject’s consent preference decision. |
| Granted vs. Declined by Category | Shows the percentage breakdown of granted versus declined consent for each cookie category, such as Analytics or Advertising, during the selected time period. Withdrawn consent is included with declined. De-duplication is applied so that only the initial interaction and the latest state changes for each cookie category are counted, avoiding double counting. |

> [!NOTE]
> Note
> 
> Earlier consent records did not capture the detail required for consent metrics. As a result, the following widgets do not include historical consent data and only show consent data collected after **Securiti release 1.142** (week of February 9):
> 
> - Managed Preferences
> - Banner Dismissed
> - Consent Status by Non-Essential Category

A key role within your organization responsible for overseeing and ensuring compliance with data protection laws and regulations, such as the General Data Protection Regulation (GDPR) in the European Union. The primary responsibility of the DPO is to monitor the organization's data processing activities, assess potential risks to data subjects' privacy rights, and implement measures to mitigate those risks.

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences
