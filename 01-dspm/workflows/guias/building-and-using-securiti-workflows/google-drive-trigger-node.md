---
title: "Google Drive"
slug: "google-drive-trigger-node"
updated: 2025-10-30T19:12:11Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/google-drive-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Google Drive

Google Drive is a cloud-based file storage and synchronization service provided by Google. It offers a central location to store, access, and collaborate on your files from anywhere with an internet connection. A Google Drive trigger node acts like a lookout, regularly checking your Google Drive for changes at an interval you set. During each check, the node looks for new files, modifications to existing files, or any other changes. Based on those results the rest of the Workflow gets triggered.

You define the following items to configure the node:

- Google Drive data system and the user.
- The resource ID of the resource that needs to be monitored.
- The polling interval i.e. how frequently to check the Google Drive (e.g., every 5 minutes).

Refer to the [Node configurations section](/v1/docs/prerequisites-for-g-suite-google-drive) to understand the node working and properties.

#### Example use case

As an example, let’s create a Workflow that triggers every few hours to check if a new file is uploaded to a folder. The folder contains users data files that need to be updated on the database.

To automate the process of getting alerted on the addition of new files add a Google Drive trigger node and set the polling interval to 5 hours so that every 5 hours, the drive is checked for the addition of any new file. Add a **Send Email** node after the Google Drive node to send an email to the relevant people who are responsible for updating the database with the updated files.

The following Nodes are used in this use case:

1. Google Drive Trigger Node
2. [Send Email Node](/v1/docs/send-email)

#### Polling-Based File Monitoring on Google Drive

1. Add Google Drive trigger node and set the necessary details such as polling interval, page size etc. Add the folder ID that needs to be monitored for updates.

![Screenshot_2024-03-05_at_7_16_00_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a8deff59-4055-8d04-d639-8abcc8ed2222.png)
2. Add Send Email node that sends an email to the relevant user to notify about the updates.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-03-05_at_7_15_49_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-55d1307a-6eb4-5a51-a456-b6ed31ebb03e.png)
4. Execute the Workflow and on any event trigger, the Workflow node provides a successful response. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| Data Source Name | Specify the Data system instance name in Securiti. |
| User | Specify the user to perform operation as. |
| Folder Id | Specify the ID of the folder to scan, for example, 172832934726. |
| Polling Interval | Specify the number of units. |
| Unit | Specify the type of unit, for example, hours or minutes. |
| Page Size | Specify the number of objects to fetch per page. |
| From Date | Specify the date to fetch the records from the selected date to current time, in initial sync. By default, data will be fetched from the very beginning if no starting date is mentioned. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
