---
title: "Viewing the Securiti audit log"
slug: "securiti-platform-viewing-the-securiti-audit-log"
updated: 2026-08-19T13:39:44Z
published: 2026-08-19T13:39:44Z
canonical: "helpcenter.securiti.ai/securiti-platform-viewing-the-securiti-audit-log"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Viewing the Securiti audit log

The audit log shows you an audit trail of activities taken by various users and by the Securiti platform.

- For users of type Super Admin, DPO, and Operator, the audit log shows all log entries.
- For users of type User or Module Owner, the audit log only shows log entries directly related to the user and their activities.

> [!NOTE]
> **Note**
> 
> The audit log only retains the records for 12 months. After this period, the records are deleted.

To open the audit logs:

- In Securiti, from the upper left corner of the left navigation bar, click the **Jewel** icon.
- From the Platform Services section, click **Settings**.
- From the **System Settings** left menu bar, select **Security** > **Audit Logs**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-WVIXS4V8.png)

For each log entry, the audit log page shows you:

| Column | Description |
| --- | --- |
| Time | The time the action was taken, relative to the local time zone for the location configured in your browser. |
| User | The user who took the action. For system-generated actions, the user is "System." |
| Activity Object | The type of activity and the object of the activity. |
| Message | A brief description of the activity taken. It contains both user credentials and API generating logs. The message description mentions it if the API generated the log item. |

For more information about a log entry, click the down arrow at the right end of the entry to expand it. The expanded view typically shows you some or all of the following information, where applicable:

- Object type
- Session ID (where the object type is "Session")
- Changed values
- Message description
- IP address
- User agent

You can filter the audit log according to the message contents by entering filter text in the text box at the top of the page. You can also use the filter panel to filter the audit log on more sophisticated criteria as described in [Filtering Securiti pages and dashboards](/latest/docs/filtering-securiti-pages-and-dashboards).

An Object or an Object Question is an entity that holds data and is part of the Assessment V2 Object and Field Framework. For example, a Data Mapping entity such as an Asset or a Process is an Object. This can also mean any entity in the source of truth module and not limited to Data Mapping is considered an Object that you can use to create object questions in the assessment.

## Related

- [Managing your Securiti user profile](/securiti-platform-managing-your-securiti-user-profile.md)
