---
title: "Using the Universal Consent Usage Metrics"
slug: "using-the-universal-consent-usage-metrics"
updated: 2026-03-31T11:39:35Z
published: 2026-03-31T11:39:35Z
canonical: "helpcenter.securiti.ai/using-the-universal-consent-usage-metrics"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Universal Consent Usage Metrics

**Scenario**

As a Data Privacy Officer, you must understand how data subjects interact with your consent experiences. However, when consent activity is spread across multiple channels such as websites, mobile apps, and preference centers, it becomes difficult to see where consents are being collected, how users are engaging, or where engagement drops. For instance, you may notice that website visitors frequently open the consent banner but rarely complete their preference selections, making it difficult to evaluate whether the consent experience is effective. Consent Usage Metrics in Universal Consent Management provides centralized widgets that show how consent data flows across your Securiti tenant. This unified visibility helps you monitor consent activity, identify engagement patterns, and refine your consent experiences to improve participation and strengthen governance.

Securiti’s **Consent Usage Metrics** in the Universal Consent Management module helps you track how consent data flows across your tenant. It gives you visibility into key activity and integration data, so you can monitor metrics, understand how data subjects interact with consent experiences, and identify usage patterns across different consent channels.

With the consent metric widgets, all universal consent data is brought into one place, giving you a unified view to see what’s working and where engagement drops off. You can use these insights to assess consent experience effectiveness, evaluate consent collection performance, and fine-tune your consent management strategy.

> [!NOTE]
> Note
> 
> - If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
> - Only the **Super Admin** Securiti user role in your organization has permission to access this functionality.

This functionality lets you visualize consent usage across the following data points:

- Unique data subjects (collective)
- Unique data subjects by subscribed modules
- Privacy Platform Integrations used
- Privacy Platform Integrations available
- Universal consent overview (total, reads, and writes)
- Top universal consent sources (both reads and writes)

You can also monitor the usage metrics over selectable time periods such as **last week, last month**, **last** **three months**, **last six months**, or **last year** to gain insights over time, as shown below.

![Consent usage metrics display total users, mobile apps, and privacy platform integrations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_usage_metrics_1.png)

### Key considerations

- The dashboard shows usage metrics only for the consent modules you are subscribed to. For instance if you use both Universal and Cookie Consent Management, it shows consent usage metrics for both; otherwise, it shows metrics only for the module you are subscribed to.
- Securiti has backfilled data for the **Total Unique Users** widget starting from the beginning of your contract with Securiti.
- All other widgets display and reflect data that has been collected, and accumulated since Securiti **release 1.133**, which went live **the week of June 16, 2025**.

### Definitions of Widgets

Use the following table to understand the definitions of widgets specific to the Universal Consent Management module:

> [!TIP]
> Important
> 
> The Consent Usage Metrics calculations include deleted consent records. Once a consent record is created, it counts toward your usage, even if you delete it later. Deleting a consent record does not undo or reduce usage. This ensures Consent Usage Metrics reflect all consent records written to the database.

| **Widget** | **Definition** |
| --- | --- |
| Total Unique Users | Displays the cumulative total number of end-users who interacted with any consent product, such as a cookie banner, universal preference center, or consent form, aggregated across the consent modules included in your plan. > [!NOTE] > Note > > Securiti has backfilled data for the Total Unique Users widget starting from the beginning of your contract with Securiti. |
| Unique Users by Module | Displays the cumulative total number of data subjects who interacted with any consent product, such as a cookie banner, universal preference center, or consent form, broken down by each consent module included in your plan during the selected time period. This lets you compare usage across consent modules. If the selected time period shows no bar or trajectory for a module, it means there were no consent records for that module during that time |
| Privacy Platform Integrations Used/Available | Displays the number of privacy integrations in your Securiti tenant compared to the total included in your plan. |
| Universal Consent Reads | Displays how many times universal consent status was checked during the selected time period, including through reports and API calls. |
| Universal Consent Writes | Displays the total number of universal consent records created or updated (coincides with the consent collection date) in the Securiti consent database during the selected time period. |
| Universal Consent Top Read Sources | Tracks the top sources, along with their counts, from which universal consent data is fetched through universal preference centers, workflows, APIs, or reports during the selected time period. |
| Universal Consent Top Write Sources | Tracks the top sources of universal consents received through preference centers, consent forms, and APIs, listed with their corresponding counts during the selected time period. |

### Generating report for Consent Usage Metrics

Securiti lets you export these widgets as PDF or PPTX reports, share them via email with recipients inside or outside Securiti, or do both actions at once.

To download and share the generated report:

1. In Securiti, open Universal Consent Management, and choose **Universal Consent > Consent Usage Metrics**.
2. From the upper right corner of the page, click **Report Generation**, and select **Generate report**, as shown below.

![Report generation option highlighted in the consent usage metrics dashboard interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_usage_metrics_2.png)
3. On the **Generate Report** popup, mark the radio button to choose a file format for the report such as **PDF** or **PPTX**, as shown below.

![Report generation options for PDF and PPTX formats in the consent metrics dashboard.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_usage_metrics_3.png)
4. (Optional) To share the generated report with internal or external stakeholders, mark the **Share it with others** checkbox.
  1. From the **Add Recipients** menu, select the names of the recipients or type their email addresses, and press enter, as shown below.

![Report generation interface showing options to add recipients and select formats.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_usage_metrics_4.png)

> [!NOTE]
> Note
> 
> Securiti lets you share the generated report with anyone inside or outside Securiti via an email link which remains valid for 7 days.
  2. (Optional) To remove a recipient, click **Options** (three dots) next to their name, then select **Remove**.
5. Once done, near the bottom of the popup, click **Generate Report** to send the generated report to yourself and the selected recipients via email, as shown below.

![Consent Usage Metrics report generated with download link and expiration notice included.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_usage_metrics_5.png)

## Related

- [Using the Cookie Consent Usage Metrics](/using-the-cookie-consent-usage-metrics.md)
- [Using the Mobile App Consent Usage Metrics](/using-the-mobile-consent-usage-metrics.md)
