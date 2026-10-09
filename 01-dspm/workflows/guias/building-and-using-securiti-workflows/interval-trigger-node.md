---
title: "Interval"
slug: "interval-trigger-node"
updated: 2025-10-30T19:12:32Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/interval-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Interval

An interval trigger node in a Workflow triggers a Workflow at the set interval, such as 20 hours, 5 minutes or 10 seconds etc. This node acts as a scheduler, triggering the execution of a Workflow at predetermined time intervals you configure. The interval can be set to various durations, ranging from seconds for highly time-sensitive tasks to hours, minutes or seconds.

Using this node automates repetitive workflows that need to run periodically without manual intervention. Interval trigger Nodes can manage workflows even for high-volume scenarios where tasks need to run frequently.

> [!NOTE]
> **Note**
> 
> **Cron** and **Interval** Nodes cannot run in parallel. Before starting a new execution, the system checks for any ongoing executions to maintain process consistency and prevent scheduling conflicts.

#### Example use case

As an example, a use case demonstrates how an interval trigger node can be used to automate a data pipeline that runs at regular intervals. The Workflow starts with an interval trigger node configured to run at a specific time interval (e.g., every hour, every day). An **execute Workflow node** then executes a Workflow with the given ID that needs to be executed at the specified interval.

The following Nodes are used in this Workflow:

1. Interval Trigger Node
2. [Execute Workflow Node](/v1/docs/execute-workflow)

#### Automating workflow execution with interval trigger

1. Add the interval trigger node and set the interval to your desired time. In this case the interval is set to 30 minutes.

![Screenshot_2024-03-05_at_7_50_27_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-54d5745d-c7a5-2120-78a9-5a4116926bc5.png)
2. Add the Execute Workflow node with the ID of the Workflow that needs to be executed on the set interval.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-03-05_at_7_51_21_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a489eb3c-541b-b76b-00ca-1f87b1c370b9.png)
4. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| Interval | Number of units in the interval |
| Unit | - Seconds - Minutes - Hours |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
