---
title: "Using the Mobile App Consent Usage Metrics"
slug: "using-the-mobile-consent-usage-metrics"
updated: 2026-09-03T09:13:11Z
published: 2026-09-03T09:13:11Z
canonical: "helpcenter.securiti.ai/using-the-mobile-consent-usage-metrics"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Mobile App Consent Usage Metrics

**Scenario**

As a Data Privacy Officer, you need to understand how mobile app users interact with consent experiences across your apps. For instance, if one mobile app shows significantly fewer consent interactions than others, it could indicate a misconfigured consent banner or low user engagement. With Securiti’s Consent Usage Metrics you can monitor consent activity across your apps, track consent reads and writes, and analyze trends in unique users over time. This visibility helps you identify engagement gaps, refine your consent strategy, and export reports to support audits and compliance reviews.

Securiti’s **Consent Usage Metrics** in the Mobile App Consent Management module helps you track how consent data flows across your tenant. It gives you visibility into mobile app-specific activity, so you can monitor metrics, understand how mobile app users interact with in-app consent banners and preference centers, and identify engagement trends across your mobile applications.

With the consent metric widgets, all mobile app consent data is brought into one place, giving you a unified view to see what’s working and where engagement drops off. You can use these insights to assess in-app banner effectiveness, evaluate consent collection performance, and fine-tune your mobile compliance strategy.

> [!NOTE]
> Note
> 
> - If this functionality is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
> - Only the **Super Admin** Securiti user role in your organization has permission to access this functionality.

This functionality lets you visualize consent usage across the following data points:

- Unique data subjects (collective)
- Unique data subjects by subscribed modules
- Mobile apps used
- Mobile apps available
- Mobile app consent overview (total, reads, and writes)
- Top mobile app consent sources (both reads and writes)

You can also monitor the usage metrics over selectable time periods such as **last week**, **last month**, **last three months**, **last six months**, or **last year** to gain insights over time, as shown below.

![Filter Consent Usage Metrics by Time](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Filter-By-Time.png)

## Key considerations

- The dashboard shows usage metrics only for the consent modules you are subscribed to. For instance, if you use both Mobile App Consent and Cookie Consent Management, it shows consent usage metrics for both; otherwise, it shows metrics only for the module you are subscribed to.
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
| Mobile Apps Used/Available | Displays the number of mobile apps in your Securiti tenant compared to the total included in your plan. |
| Mobile App Consent Reads | Displays how many times mobile app consent status was checked during the selected time period, including through reports and API calls. |
| Mobile App Consent Writes | Displays the total number of mobile app consent records created or updated (coincides with the consent collection date) in the Securiti consent database during the selected time period. |
| Mobile App Consent Top Read Sources | Tracks the top sources, along with their counts, from which mobile app consent data is fetched through in-app banners, preference centers, APIs, and reports during the selected time period. |
| Mobile App Consent Top Write Sources | Tracks the top sources of mobile app consents received through in-app banners, preference centers, and APIs, listed with their corresponding counts during the selected time period. |

## Generating report for Consent Usage Metrics

Securiti lets you export these widgets as `PDF` or `PPTX` reports, share them via email with recipients inside or outside Securiti, or do both actions at once.

To download and share the generated report:

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile App Consent > Consent Usage Metrics**.
2. From the upper right corner of the page, click **Report Generation**, and select **Generate report**, as shown below.

![Click Generate report](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Generate-Report.png)
3. On the **Generate Report** popup, mark the radio button to choose a file format for the report such as `PDF` or `PPTX`, as shown below.

![Generate Report Popup](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Generate-Report-Popup(2).png)
4. (Optional) To share the generated report with internal or external stakeholders, mark the **Share it with others** checkbox.
  1. From the **Add Recipients** menu, select the names of the recipients or type their email addresses, and press enter, as shown below.

> [!NOTE]
> Note
> 
> Securiti lets you share the generated report with anyone inside or outside Securiti via an email link which remains valid for **7 days**.

![Add Recipients on Generate Report Popup](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-Recipients(1).png)
  2. (Optional) To remove a recipient, click **Options** (three dots) next to their name, then select **Remove**.
5. Once done, near the bottom of the popup, click **Generate and share report** to send the generated report to yourself and the selected recipients via email, as shown below. ![Consent Usage Metrics Email](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Consent-Metrics-Email.png)

## Related

- [Configuring Mobile Apps dashboard](/configuring-mobile-apps-dashboard.md)
- [Using the Cookie Consent Usage Metrics](/using-the-cookie-consent-usage-metrics.md)
