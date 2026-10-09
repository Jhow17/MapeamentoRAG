---
title: "Auditing Breach Incidents"
slug: "auditing-breach-incidents"
updated: 2025-11-02T05:59:24Z
published: 2025-11-02T05:59:24Z
canonical: "helpcenter.securiti.ai/auditing-breach-incidents"
area: privacy
modulo: data-breach-management
tipo: guia
data_captura: 2026-10-08
---

# Auditing Breach Incidents

The Audit log for each incident shows you details of every action taken by the Securiti system or by incident owners while processing the incident in the Data Breach Workbench.

To view the audit log for a breach incident:

1. Open the incident in the Data Breach Workbench as described in [Processing a data breach report.](/v1/docs/processing-a-data-breach-report)
2. Click the **Audit Log** tab

Securiti opens the Audit log to show you a list of activities for the reported incident.
  - Click **View log metadata** near the right end of the card for any activity to view more information.

![Screenshot_2024-08-30_at_12_34_31_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-19b9e55b-a079-7a14-a70f-74e7b4cc57c7.png)
  - Near the right end of the card, click **Refresh** to refresh log details.

![Screenshot_2024-08-30_at_12_40_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c1a5d333-4dff-b398-68e1-43724e3032b3.png)
  - Use the full-text search box at the top of the tab to filter activities on text strings within the Message field.

![Screenshot_2024-08-30_at_12_42_01_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7d3c9349-0b3d-a86c-d7b8-ca579490f6b8.png)

You can also filter audit logs details based on User, Activity and Object type.

| Filter | Description |
| --- | --- |
| User | The "User" filter in the breach audit log includes the "System” option for actions performed automatically by Securiti, and user email, to view actions by specific logged-in users. Choose either option and click **Apply** to view the filtered actions. |
| Activity | The activity menu in the audit log filter has three options: - Create - Update - Delete Use these options to filter actions performed on incidents, such as adding a new owner, updating the stage, or deleting a jurisdiction from the stage. |
| Object Type | Use this filter to view the list of actions taken on a specific breach incident. |

The log that Securiti maintains of all actions taken by various users, and by the Securiti system. Different users have different levels of access to the audit log. For users of type Super Admin, DPO, and Operator, the audit log shows all log entries. For users of type User or Module Owner, the audit log only shows log entries directly related to the user and their activities.
