---
title: "Cron"
slug: "cron-trigger-node"
updated: 2026-06-04T11:49:43Z
published: 2026-06-04T11:49:43Z
canonical: "helpcenter.securiti.ai/cron-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Cron

The CRON trigger node in Workflows module initiates workflows (a series of automated actions) based on a specific schedule you define. This is incredibly useful when you need tasks or processes to run at recurring times or intervals.

The Workflow automation platform continuously monitors the current time. When the time matches your defined CRON expression, the node triggers the associated Workflow. Using the CRON node, removes the need for manual intervention in recurring processes and tasks run consistently on-time as long as your Workflow automation platform is operational.

> [!NOTE]
> **Note**
> 
> - **Cron** and **Interval** Nodes cannot run in parallel. Before starting a new execution, the system checks for any ongoing executions to maintain process consistency and prevent scheduling conflicts.
> - Workflows that execute in under 5 minutes are not recommended for use with a **Cron** or **Interval** node.
> - If more than two scheduled executions are missed, only the most recent one will run automatically. Earlier missed executions will not be processed.

Refer to the [Node configurations section](/v1/docs/cron) to understand the node working and properties.

#### Example use case

As an example, let’s create a Workflow that executes at the end of each day and fetches the data of leads collected using the **Salesforce** node. The CRON node is set such that it executes the Workflow every day. The retrieved data is then stored into a CSV file that gets uploaded on Dropbox to keep track of all the generated leads.

The **Process CSV** node transforms this structured lead data into a CSV file format. The **Dropbox** node then securely uploads the newly generated CSV file to a designated Dropbox location. By automating the process, the Workflow is executed automatically without manually executing the Workflow every day.

The following Nodes are used in this Workflow:

- CRON Trigger Node
- [Salesforce Node](/v1/docs/salesforce)
- [Process CSV Node](/v1/docs/process-csv)
- [Dropbox Node](/v1/docs/dropbox)

#### Automated Daily Lead Data Extraction

1. Add the Cron trigger node to set the time such that the Workflow is executed everyday. Set the Mode to everyday and set the time at which the Workflow is set to execute every day.

![Screenshot_2024-02-20_at_7_55_22_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-14a43964-95e7-c9d4-c711-4cfa1d73b85f.png)
2. Add the Salesforce node to fetch the data of leads followed by the Process CSV node to process the data into a CSV file.
3. Finally, add the Dropbox node to upload the fetched results into Dropbox.
4. Connect the Nodes and execute the Workflow.

![Screenshot_2024-02-20_at_7_07_57_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86cd5f9d-44af-2308-ff31-084623c62e85.png)
5. Upon successful execution, the Workflow Node will provide a successful response. After the Workflow runs successfully, you can access the results in two formats i.e. table view and JSON response

#### Node configurations

| Parameters |
| --- |
| Mode | Every: - Minute - Hour - Day - Week - Month - X units - Custom |
| Hour | The hour of the day at which the Workflow triggers |
| Weekday | For mode "Every week," the day of the week at which the Workflow triggers |
| Minute | The minute of the hour at which the Workflow triggers |
| Day of month | For mode "Every Month," the day of the month. Use dates 29 through 31 with caution. |
| Value | For mode "Every X," the number of units in the interval |
| Unit | For mode "Every X," the type of unit in the interval |
| Cron Expression | For mode "Custom" the Cron expression that determines the interval |
