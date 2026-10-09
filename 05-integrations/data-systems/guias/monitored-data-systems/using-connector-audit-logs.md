---
title: "Using connector Activity logs"
slug: "using-connector-audit-logs"
status: "update"
updated: 2026-09-30T10:50:21Z
published: 2026-09-30T10:50:50Z
canonical: "helpcenter.securiti.ai/using-connector-audit-logs"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Using connector Activity logs

> [!NOTE]
> **Note**
> 
> For structured data systems, the activity log may interpret the renaming of a column as the removal of the column plus the addition of a new column under the new name.

Securiti lets you view and track activity records for your data system connectors on the **Activity Log** page. The **Activity Log** page shows activity logs by different users based on the Object Types. Each Activity Log entry provides information about the user, object, and error to track the actual phase in which the error occurs.

For each data system instance, you can use its **Activity Log** tab to view logs of activities for the data system, as shown below.

Refer to the following procedure to view activity logs for your data system instance:

1. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
2. From the Platform Services section in new navigation, select **Integrations >** **Monitored** **Data Systems**
3. On the **Monitored** **Data Systems** page, find the data system type and click on it to open details.
4. In the **Monitoring** section, click the **Activity** **Log** tab.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Activity Log(3).png)

### Using Activity Log filter

Click on the **Select Filter “+”** to open filters. Here you can use either search or use pre-defined filters to narrow down your search results.

- **Filter by Search**

Simply type the matching word from the activity log messages. It automatically shows the list of all activity logs containing that word
- **Pre-defined filters**

You can apply this filter to **User**, **Activity**, and **Object Type** parameters.

| Filter options | Description |
| --- | --- |
| Is one of | Select **Is one of** filters to get the audit trail results which contains at least one value from a specified list of values |
| Is not one of | Select **Is not one of** filters to get the audit trail results which field does not contain any of the specified values. |
| Equals | Select **Equals** if you want to return results where the field exactly matches the specified value. |
| Not equals | Select **Not equals** if you want to see all results except those where the field exactly matches the specified value. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Filters(2).png)

For each activity, the log shows the following summary information:

| Time | UTC time at which the activity was detected. |
| --- | --- |
| User | The Securiti user that initiated the activity. Users can be a system, a Pod, or a specific user. |
| Activity/Object | **Activity** refers to a specific action performed by the user. See the examples below for the actions: - **Create** - **Update** - **Log** The **Object** refers to the type of object on which the user performs the activity. See the examples of a few object types: - Data source - Connector Access Scan |
| Message | A short description of the activity. See the example below for a message. *A new connector was added to SharePoint Online Datasource.* |
| View log metadata | **View log metadata** shows further details of activity in the dialogue box. |

To view log metadata details, click the **View log metadata** icon on the right side of each activity log entry. The dialogue box provides the following information.

| Activity | Actual activity performed by the user |
| --- | --- |
| Detailed Message Description | Currently, the **View log metadata** dialogue box shows detailed error messages for Authentication failure and Diagnostic utility errors. The Audit Trail provides you with information about the following: - Actual error message from the server - Timestamp - IP address - Username - Phase in which error occurred. > [!NOTE] > **Note** > > Detailed error message displays the **user** and I**P address** information if it exists in the data system. Currently, this information is only available for authentication and diagnostic issues. |
| Changed Values | The values changed while performing the activity. If the activity does not affect the values, it shows a blank field. |
| IP Address | The IP address from which the user initiated the action, if applicable. |
| User Agent | The user that initiated the activity. Users can be a system, a Pod, or a specific user. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Log Metadata(1).png)

## Related

- [Configuring connectors for monitored data systems](/configuring-connectors-for-monitored-data-systems.md)
