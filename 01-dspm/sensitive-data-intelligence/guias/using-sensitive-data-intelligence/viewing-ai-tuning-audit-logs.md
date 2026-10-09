---
title: "Viewing AI Tuning audit logs"
slug: "viewing-ai-tuning-audit-logs"
updated: 2026-09-21T16:06:04Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/viewing-ai-tuning-audit-logs"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Viewing AI Tuning audit logs

Every action performed through AI Tuning is recorded on the **Tuning Audit Logs** page. This page tracks the user or system process that performed each activity, when it occurred, and the object it affected, giving you a complete trail of AI Tuning changes over time.

To access the Tuning Audit Logs:

1. From the left navigation bar, click the **Jewel** icon to open the main menu and select **Settings > AI Tuning**, as shown below.

![Securiti dashboard displaying sensitive data intelligence and AI tuning options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aituningnavigation_sidebar.png)
2. Click **Tuning Audit Logs** under the **AI Tuning** category, as shown below.

![Overview of Tuning Audit Logs with user activities and timestamps displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tuningauditlogs_navigation.png)
3. Select the **Structured Data** tab to view logs for column-level AI Tuning, or the **Document Type** tab to view logs for file-level AI Tuning, as shown below.

![Tuning audit logs displaying user activities and system messages for AI tuning configurations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/structureddataanddocumenttype_tabselection.png)
4. Click **Add Filter** (plus) icon to filter the audit log entries.

The available filters for **Structured Data** include:

Similarly, the available filters for **Document Type** include:
  1. Object Type
  2. Database
  3. Schema
  4. Table
  5. Data System
  6. Date
  7. Activity
  1. Object Type
  2. Data System
  3. Document Type
  4. Date
  5. Activity
5. Click **Refresh** to load the latest log entries, as shown below.

![Tuning audit logs showing user activities and system updates in a structured format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/refreshbutton_tuningauditlogs(1).png)
6. Go through the logs to track the history. It includes the following columns:

![Tuning audit logs showing user activities and system updates for AI tuning configurations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/structureddata_tuningauditlogs.png)

Use the following table to understand the columns:

| Column | Description |
| --- | --- |
| Time | Displays the date and time the activity was recorded |
| User | Displays the user or system process that performed the activity |
| Activity | Displays the type of action performed, for example, Create, Update, or Sync |
| Object | Displays the object type that was acted on |
| Message | Displays a summary of the activity |
7. Click **View log metadata** (metadata) icon to open the session log details, as shown below.

![Tuning audit logs showing user activities and system updates for AI tuning configurations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewmetadataicon_tuningauditlogs.png)

To understand how the feedback scope works, see [AI Tuning feedback scenarios](/latest/docs/ai-tuning-use-cases).
