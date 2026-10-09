---
title: "Using the Cookie Consent Usage Metrics"
slug: "using-the-cookie-consent-usage-metrics"
updated: 2026-09-07T09:14:07Z
published: 2026-09-07T09:14:07Z
canonical: "helpcenter.securiti.ai/using-the-cookie-consent-usage-metrics"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Cookie Consent Usage Metrics

**Scenario**

As a Data Privacy Officer, you need to understand how cookie consent behaves across your organization’s domains. For instance, if one domain shows significantly fewer consent interactions than others, it may indicate a misconfigured cookie banner or low data subject engagement. With Securiti’s Consent Usage Metrics you can monitor consent activity across domains, track consent reads and writes, and view trends in unique data subjects over time. This visibility helps you identify issues early, refine your consent strategy, and generate exportable reports to support audits and compliance reviews.

Securiti’s **Consent Usage Metrics** in the Cookie Consent Management module helps you track how consent data flows across your tenant. It gives you visibility into cookie-related activity at the tenant level, so you can monitor key metrics, understand how data subjects engage with cookie banners, and spot usage patterns across different consent channels.

With the consent metric widgets, all cookie consent data is brought into one place, giving you a unified view to see what’s working and where engagement drops off. You can use these insights to assess cookie banner effectiveness, evaluate consent collection performance, and fine-tune your cookie compliance strategy.

> [!NOTE]
> **Note**
> 
> - If this functionality is not available in your Securiti tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether it is included in your plan.
> - Only the **Super Admin** Securiti user role in your organization has permission to access this functionality.

This functionality lets you visualize consent usage across the following data points:

- Unique data subjects (collective)
- Unique data subjects by subscribed modules
- Domains used
- Cookie consent overview (total, reads, and writes)
- Top cookie consent sources (both reads and writes)

You can also monitor the usage metrics over selectable time periods such as **last week**, **last month**, **last three months**, **last six months**, or **last year** to gain insights over time, as shown below.

![Using Time Filters in Usage Consent Metrics](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Consent-Mertics-Time-Filters.png)

## Key considerations

- The dashboard shows usage metrics only for the consent modules you are subscribed to. For instance, if you use both Cookie and Universal Consent Management, it shows consent usage metrics for both; otherwise, it shows metrics only for the module you are subscribed to.
- Securiti has backfilled data for the **Total Unique Users** widget starting from the beginning of your contract with Securiti.
- All other widgets display and reflect data that has been collected, and accumulated since **Securiti** **release 1.133**, which went live the **week of June 16, 2025**.

## Definitions of widgets

Use the following table to understand the definitions of widgets specific to the Cookie Consent Management module:

> [!WARNING]
> Important
> 
> The Consent Usage Metrics calculations include deleted consent records. Once a consent record is created, it counts toward your usage, even if you delete it later. Deleting a consent record does not undo or reduce usage. This ensures Consent Usage Metrics reflect all consent records written to the database.

| Widget | Definition |
| --- | --- |
| Total Unique Users | Displays the cumulative total number of end-users who interacted with any consent product, such as a cookie banner, universal preference center, or consent form, aggregated across the consent modules included in your plan. > [!NOTE] > Note > > Securiti has backfilled data for the **Total Unique Users** widget starting from the beginning of your contract with Securiti. |
| Unique Users by Module | Displays the cumulative total number of data subjects who interacted with any consent product, such as a cookie banner, universal preference center, or consent form, broken down by each consent module included in your plan during the selected time period. This lets you compare usage across consent modules. If the selected time period shows no bar or trajectory for a module, it means there were no consent records for that module during that time. |
| Domains Used/Available | Displays the number of domains in your Securiti tenant compared to the total included in your plan. |
| Cookie Consent Reads | Displays how many times cookie consent status was checked during the selected time period, broken down by cookie category. This includes checks through reports and API calls. |
| Cookie Consent Writes | Displays the total number of cookie consent records created or updated (coincides with the consent collection date) in the Securiti consent database, broken down by cookie category during the selected time period. |
| Cookie Consent Top Read Sources | Tracks the top sources, along with their counts, from which cookie consent data is fetched through cookie banners, preference centers, APIs, and reports during the selected time period. |
| Cookie Consent Top Write Sources | Tracks the top sources of cookie consents received through cookie banners, preference centers, and APIs, listed with their corresponding counts during the selected time period. |

## Generating report for Consent Usage Metrics

Securiti lets you export these widgets as `PDF` or `PPTX` reports, share them via email with recipients inside or outside Securiti, or do both actions at once.

To download and share the generated report:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Consent Usage Metrics**.
2. From the upper right corner of the page, click **Report Generation**, and select **Generate report**, as shown below.

![Click Generate Report](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Report-Generation.png)
3. On the **Generate Report** popup, mark the radio button to choose a file format for the report such as `PDF` or `PPTX`, as shown below.

![Generate Report Popup](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Generate-Report-Popup(1).png)
4. (Optional) To share the generated report with internal or external stakeholders, mark the **Share it with others** checkbox.
  1. From the **Add Recipients** menu, select the names of the recipients or type their email addresses, and press enter, as shown below.

> [!NOTE]
> Note
> 
> Securiti lets you share the generated report with anyone inside or outside Securiti via an email link which remains valid for **7 days**.

![Add Recipients from Generate Report Popup](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-Recipients.png)
  2. (Optional) To remove a recipient, click **Options** (three dots) next to their name, then select **Remove**.
5. Once done, near the bottom of the popup, click **Generate and share report** to send the generated report to yourself and the selected recipients via email, as shown below. ![Consent Usage Metrics Email](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Consent-Metrics-Email.png)

## Related

- [Using the Mobile App Consent Usage Metrics](/using-the-mobile-consent-usage-metrics.md)
