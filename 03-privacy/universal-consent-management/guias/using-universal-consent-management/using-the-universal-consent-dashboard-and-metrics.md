---
title: "Using the Universal Consent Dashboard and Metrics"
slug: "using-the-universal-consent-dashboard-and-metrics"
status: "new"
updated: 2026-09-01T10:38:38Z
published: 2026-09-01T10:38:38Z
canonical: "helpcenter.securiti.ai/using-the-universal-consent-dashboard-and-metrics"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Universal Consent Dashboard and Metrics

**Scenario**

As a **Data Privacy Officer**, you must monitor how data subjects give consent and ensure records are accurate across channels. Reviewing web forms, APIs, and bulk uploads separately is slow and increases the risk of missing inconsistent records. For example, you may struggle to confirm whether data subjects who withdrew consent are updated across all intake channels such as, preference center, web form, or API. Using the Universal Consent Dashboard & Metrics, you can view consent records in one place and analyze trends by purpose and channel. You can quickly identify gaps, confirm updates, and reduce compliance risk with clear, centralized insight.

> [!NOTE]
> Note
> 
> The [legacy dashboard](/latest/docs/using-the-universal-consent-management-dashboard) remains available and unchanged. If the **Universal Consent Dashboard and Metrics** experience is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm plan eligibility and activation requirements.

> [!WARNING]
> Important
> 
> - The new **Universal Consent Dashboard and Metrics** experience is now available in the module. For more information on how to migrate your existing consent data to the new dashboard, see [Migrating consent records from Legacy to New Consent Dashboard Experience](/latest/docs/using-the-universal-consent-management-dashboard#migrating-consent-records-from-legacy-to-new-universal-consent-dashboard-experience).
> - Securiti lets you filter and analyze consent records going back **18 months** from the current date, but within that timeframe the dashboard can display **only one year of consent data at a time**.
> 
> You can access consent records older than 18 months through the **Legacy Consent Data** view.
> - The **Legacy Consent Data** view supports only date-based filtering and does not support the advanced filters available in the new Universal Consent Domains dashboard.

The **Universal Consent Dashboard & Metrics** experience provides centralized visibility into universal consent activity, helping you understand how data subjects give consent, which processing and consent purposes they select, and how they interact with preference centers.

The experience includes two primary views:

- **Dashboard**, which displays individual consent records that Secuiti collects through preference centers and other consent routes, such as web consent form, bulk upload, consent API, or platform integration.
- **Metrics**, which presents aggregated consent trends and performance through visual widgets.

You can switch between these views using the Dashboard and Metrics tabs at the upper center of the page, as shown below.

![Universal Consent Dashboard displaying consent records and metrics for user management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_metrics_1.png)

## Universal Consent Dashboard

The **Dashboard** view focuses on individual consent records that Securiti collects through preference centers, bulk upload, consent APIs, platform integration, forms or workflows. It provides record-level visibility into how and when consent was captured.

The universal consents table shows records of every event in which a data subject grants, declines, or withdraws consent for the selected consent type. It includes the following consent statuses:

| Status | Description |
| --- | --- |
| Granted | The data subject actively gave consent for all applicable processing purposes. The action is completed and recorded in Securiti. |
| Declined | The data subject explicitly refused to grant consent for all processing activities. Securiti logs this refusal as a completed action. |
| No Consent | The data subject has not yet responded to a consent request. No consent was granted or withdrawn at the time of recording. It represents inactivity or inaction. |
| Withdrawn | The data subject had previously granted consent but later revoked it. Securiti records this as a completed event, updating the consent status accordingly. |
| Pending | The consent request has been issued but not yet acted upon. It remains in Securiti, awaiting the data subject’s response. |

### Viewing detailed consent record information

The **Universal Consents** table displays records of consent actions, such as granting, declining, and withdrawing consent. To view detailed information for an individual consent record from the **Dashboard**:

1. From the **Universal Consents** table, locate the consent record you want to review in detail.
2. Click the **metadata** icon next to the consent record, as shown below.

![Universal Consent Dashboard displaying consent records and their statuses for email marketing.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_metrics_2.png)
3. On the **Metadata Explorer** popup, expand the accordions to view the information, as shown below.

![Dashboard displaying universal consent records with consent statuses and processing purposes listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_dash_metrics_3.png)

## Universal Consent Metrics

The **Metrics** view provides an aggregated, visual overview of consent behavior across various touchpoints such as preference center, web forms, or consent APIs. It helps you evaluate engagement trends, consent outcomes, and regulatory signals at scale.

Use the following table to understand the definitions of widgets specific to the Universal Consent Metrics:

| Widget | Definition |
| --- | --- |
| Unique Users | Displays the total count of distinct users who have provided or updated consent through various sources such as, preference center, forms, platform integration, bulk upload, consent API within a selected timeframe. For instance, if the same data subject interacts multiple times, the widget counts them only once within the selected range. |
| Consent Status | Displays all consent records and their statuses, such as granted, declined, no action, withdrawn, and pending. These records are collected from all configured consent sources, including web-based forms, preference centers, bulk uploads, platform integrations, and APIs. For instance, if a data subject grants consent and later withdraws it, the latest status is reflected. |
| Consent by Route | Displays consent records based on the route through which consent was given such as preference center, form, platform integration, bulk upload, consent narrow path, consent API, workflows. Only routes with non-zero values are shown, and values are rounded to thousands or millions depending on volume. |
| Unique Subject Identifiers | Displays the total number of times each unique subject identifier, referred to as a UUID key, appears in consent records. If a UUID key such as an email appears in four different records, the count is four, even if the email value is the same. The widget shows the top nine UUID keys and groups the rest into an **Others** category, which can still be filtered. It reports on both tenant-configured UUID keys and the default Securiti-assigned UUID key, email. |
| Custom Parameters | Displays the total number of times each custom parameter appears in consent records. It shows the top nine custom parameters and groups the remaining ones into **Others** category, which is filterable. Securiti does not flag the use of the same UUID key as a custom parameter or vice versa as a duplicate. |
| Consent By Consent Purpose | Displays the total number of times each consent purpose appears in consent records over a selected period. By default, it shows the top six purposes, with others grouped into **Others** and allows filtering through an expression builder. |
| Consent By Processing Purpose | Displays the total number of times each processing purpose appears in consent records over a selected time period, with dynamic updates based on applied filters. |
| Consent By Processing Purposes Categories | Displays the total number of times each processing purpose category appears in consent records over a selected time period. If a category changes, previously recorded consents remain in their original category, and the change only applies to consents recorded after the update. |

To download and delete universal consent records from Dashboard & Metrics, see [Downloading the universal consent records from the Dashboard and Metrics](/latest/docs/downloading-universal-consent-records-from-dashboard-metrics) and [Deleting universal consent records from the Dashboard and Metrics](/latest/docs/deleting-universal-consent-records-from-the-dashboard-and-metrics).

## Related

- [Filtering universal consent records in the Dashboard and Metrics](/filtering-universal-consent-records-in-dashboard-and-metrics.md)
- [Downloading the universal consent records from the Dashboard and Metrics](/downloading-universal-consent-records-from-dashboard-metrics.md)
