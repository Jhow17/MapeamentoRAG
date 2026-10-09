---
title: "Using the Cookie Consent Management Audit Log"
slug: "using-the-cookie-consent-management-audit-log"
updated: 2026-09-21T15:27:48Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/using-the-cookie-consent-management-audit-log"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Cookie Consent Management Audit Log

**Scenario**

As a Cookie Consent Management admin, you need to investigate recent changes made to cookie consent configurations across multiple domains. For instance, you might need to review who updated a cookie banner, when a domain scan detected cookie changes, or when a deployment was completed. With the Cookie Consent Management Audit Log, you can review module-specific audit activity from one centralized view. You can search audit records by message, filter them by domain, user, activity, object, or time, and export the filtered results for offline review or compliance reporting.

The Cookie Consent Management Audit Log gives you a module-level view of cookie consent-related activity across domains in your Securiti tenant. You can use it to review domain actions, scans, deployments, configuration changes, Cookie & Tracker Library activity, and other Cookie Consent Management events from one centralized view.

> [!NOTE]
> Note
> 
> The platform-level audit log remains available. However, we recommend using the module-level audit log because it provides more detailed information.

## Key capabilities

Use the following table to understand the key capabilities available in the Audit Log:

| Capability | Description |
| --- | --- |
| Message-based search | Lets you search audit records by message text to find relevant activity more quickly. |
| Filtered audit review | Lets you filter audit records by available audit properties, such as domain, user, activity, object, and time. |
| Domain-based filtering | Lets you filter audit records by domain when the audit record includes domain information. |
| Active and deleted domain coverage | Includes audit records for domains that currently exist in the tenant and domains that existed previously. |
| Cookie & Tracker Library audit consolidation | Merges Cookie & Tracker Library audit activity into the module-level audit log. When you access the audit log from Cookie & Tracker Library, Securiti opens the Cookie Consent Management Audit Log with the Cookie & Tracker Library filter pre-applied. |
| CSV export | Lets you export audit log data in `CSV` format. Exports honor the filters applied to the audit log view. |

> [!WARNING]
> Important
> 
> Domain URL filtering works for audit records created in the current Securiti release 1.151 (which started to go live the week of September 21, 2026) and later. Older audit records remain visible, but some historical records may not include the domain information required for domain-based filtering.

## Procedure

To access the Cookie Consent Management Audit Log:

1. In Securiti, open **Cookie Consent Management**, and choose **Explorers > Audit Log**.

The **Audit Log** page shows audit activity, including domain actions, scans, deployments, and configuration changes, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Audit-Log-page.png)

Use the following table to understand the audit log columns:

| Column | Description |
| --- | --- |
| Time | Shows when the audit activity occurred. > [!NOTE] > Note > > The audit log table shows the latest audit records at the top by default. > > To view the oldest records first, click the upward arrow next to the **Time** column to switch the sort order to ascending, as shown below. > > ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Time-Ascending-Order.png) |
| User | Shows the Securiti user that performed the activity. |
| Activity | Shows the activity type, such as create, update, export, or other recorded actions. |
| Object | Shows the object associated with the activity, such as a cookie domain, consent banner, deployment, bulk domain scan, tracker library, or audit log report. |
| Message | Shows a short description of the recorded activity. |
2. (Optional) Click the metadata icon next to a scan to view detailed scan information, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Metacard-Icon.png)

The metadata card shows more information about the selected audit record, including the recorded changes, where available.
3. To export the audit log data in `CSV` format, click **Export**, as shown below.

> [!WARNING]
> Important
> 
> - All Securiti user roles can view the comprehensive audit log, but export permissions are limited to the following roles:
>   - Super Admin
>   - Organization Admin
>   - Module Owner
> - When exporting a large number of audit records, keep the audit log page open while Securiti prepares the `CSV` file. Larger exports might take longer to generate.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Export-button(2).png)

The export includes the records that match the filters currently applied to the audit records.

## Filtering the audit records

The top-level filter lets you narrow audit records using one or more audit properties.

To filter audit records:

1. From the upper left corner of the **Audit Log** page, click **+**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Filters-button.png)
2. From the filters panel, select a property and define the filter condition.
3. Once you have selected the filters, click **Apply**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Apply-Filter.png)

Securiti builds a query based on your selected properties and displays the filtered audit records.

Use the following table to understand the available filter properties:

| Property | Description |
| --- | --- |
| Domain | Filters audit activity by one or more domains. Use this filter when you want to review activity associated with specific domains. |
| User | Filters audit activity by the Securiti user who performed the action. |
| Activity | Filters audit records by activity type, such as create, update, export, or other recorded actions. |
| Object | Filters audit records by the object associated with the activity, such as domain, deployment, consent banner, tracker library, or audit log report. |
| Time | Filters audit records by the date and time when the activity occurred. |

### Searching audit records by message

You can use message-based search to find audit records that contain specific message text.

To search audit records:

1. On the **Audit Log** page, click the **Search by message** text field, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Search-by-message.png)
2. Enter the message text you want to search for.
3. Press **Enter** or click the search icon. Securiti displays audit records that match the message text.

## Related

- [Viewing the Securiti audit log](/securiti-platform-viewing-the-securiti-audit-log.md)
