---
title: "Auditing EPod V2 logs"
slug: "auditing-epod-v2-logs"
updated: 2026-08-24T09:43:22Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/auditing-epod-v2-logs"
stale: true
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Auditing EPod V2 logs

In EPod V2, the **Audit Trail** tab for each pod shows you a chronological record of activities related to that pod, including resource utilization warnings, configuration changes (creations, updates, and deletions), database state changes, and certificate status changes. Each entry captures who or what triggered the activity, when it happened, and additional session details such as the IP address and user agent involved. Logging each event, it assists you investigating and debugging the pods’ current status and recent activities performed. It also lets you identify the problems or unexpected behaviors from the pods. It can assist you in several scenarios including:

- Monitoring pods health over time
- Troubleshoot incidents
- Track configuration and lifecycle changes
- Manage certificate lifecycle
- Support security review
- Maintain a change record for compliance

## Accessing audit trail

To access the audit trail, proceed with the following steps:

1. In Securiti, from the top left corner of the Dashboard, click the **Jewel** icon.
2. From the Platform Services section, click **Settings > Deployment > Elastic Pods V2**.
3. Select the pod you want to open the **Audit Trail** tab for. On the right side of the selected pod, click **Options** (three dots), then click **View**.
4. On the pods dashboard page, click the **Audit Trail** tab to open the pod’s status page.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-MBXZU78M.png)

It displays all the logs in this tab.

## Viewing the Audit Trail tab

The **Audit Trail** tab contains the table with all the logs in it. It has several fields displaying relevant data of the pods. It does not display all the logs at once, so you must scroll down on this page to load more logs to display on this page.

### Search bar

This tab contains a search bar for you to look for specific logs using keywords. It lets you search the logs using Message column of logs.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-AVL34RPD.png)

### Logs filter

This tab also provides the filter for the logs. You can apply different filters to display specific logs meeting your applied condition. It applies filter to different fields to narrow the results.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XJH2FJ5D.png)

It provides the following filters that you can apply:

| Filter | Description |
| --- | --- |
| Time | It contains the following filters to apply: - Before - After - Between You can set the time selector and apply the above filters on them. It displays the logs of a specific time period. |
| User | It contains the following filters to apply: - Is one of - Is not one of - Equals - Not equals You can select users and apply the above filter on them. It displays the logs that involves the selecting users. |
| Activity | It contains the following filters to apply: - Is one of - Is not one of - Equals - Not equals You can select the listed activities and apply the above filter on them. It displays the logs that contain the selecting activities. |
| Object Type | It contains the following filters to apply: - Is one of - Equals You can select the listed objects and apply the above filter on them. It displays the logs accordingly, as for Pods v1.28+ or Elastic Pods V2. |

### Logs table

It displays the logs in the form of a table that consists of the following columns:

| Column | Description |
| --- | --- |
| Time | Displays the date and time when Securiti records the log entry in your local time zone. |
| User | Identifies the source that triggers the log entry, such as the pod or a specific user account. |
| Activity | Identifies the type of event recorded in the log, such as a resource utilization warning. |
| Message | Provides additional details about the event, such as the resource usage percentage that triggers the warning. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FO3C1L5W.png)

It also lets you get more information about a specific logs. To access this information:

1. Select a log you wish to get additional information.
2. On the right side of the log, click on additional message icon.

It opens a small popup to display the additional information.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-B5D32TCI.png)
