---
title: "Breach Management"
slug: "breach-management-trigger-node"
updated: 2026-02-12T15:21:23Z
published: 2026-02-12T15:21:23Z
canonical: "helpcenter.securiti.ai/breach-management-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Breach Management

In Securiti, Data Breach Management serves as an automated system for incident response, aiding in compliance with relevant breach notification regulations while minimizing the time and costs associated with remediation. This solution is designed to prevent expensive regulatory penalties and alleviate potential damage to reputation resulting from a data breach.

The breach Management trigger node lets you trigger a Workflow once an incident is created, approved, or any stage is updated in the Data Breach workbench. For instance, if the breach management trigger node is set to trigger on the type “incident” and the status is set to “created”, the Workflow automatically triggers when a new incident is created in the Data Breach module.

> [!NOTE]
> **Note**
> 
> You must set your Workflow to run in the [automated mode](/v1/docs/workflow-node-execution-modes) for the Breach management trigger node to work automatically. To learn how to run the Workflow in the automated mode, see the Workflow in the automated mode section.

#### Example Use Case

As an example use case, let’s create a Workflow where every time a new incident is reported, the relevant authorities are notified regarding the breach status on the Slack channel. This use case requires the following three Nodes:

- Breach Management Trigger
- Slack

#### Prerequisites

The trigger type must be “incident” and the Action must be “Created.

#### Notifying authorities in Slack channel on reporting an incident

1. In the Breach Management Trigger node, fill in the fields as per your requirements as shown below:

![breach-trigger.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-df745068-4c5d-238f-250d-6d9a210cef32.png)
2. Further add details in the Slack node to notify the relevant people, as per your requirements. Refer to the [Slack node](/v1/docs/slack) for details.
3. Connect the Nodes to execute the Workflow.

![Screenshot_2024-01-08_at_8_34_20_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b75cd069-d8fa-16f4-4dda-47d30c90d209.png)
4. Execute the Workflow, and upon reporting a new incident from the Data Breach Management module, the Workflow node should generate a successful response. After successful execution, you can examine the results in both table view and JSON format. This is how the success response looks:

![Screenshot_2023-12-02_at_11_26_16_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b1b309d4-50fb-c5f1-9b04-5ac3a2edec8d.png)

#### Node Configurations

| **Parameters** |
| --- |
| Name | (Optional) Specify the name of the trigger. |
| Execution Mode | Event Mode | Choose this option to set the execution to event based execution. In this mode, the selected events trigger the node. |
| Cron Mode | Choose this option to trigger the node based on the interval set. |
| Type | Specify the type of the breach action that triggers the Workflow. |
| Incident | Choose this option to trigger Workflow on creating a new incident or any incident. |
| Incident Task | Choose this option to trigger Workflow once the incident is reported and landed in the Data Breach Workbench containing different stages. |
| Action | Any | Choose this option to trigger Workflow on any incident |
| Created | Choose this option to trigger Workflow on a newly created incident. |
| Status | Any | Choose this option to trigger Workflow when the incident is at any stage in the Data Breach Workbench. |
| To do | Choose this option to trigger Workflow when the incident is at the “To Do” stage in the Data Breach Workbench. |
| Approved | Choose this option to trigger Workflow when the incident is approved in the Data Breach Workbench. |
| Declined | Choose this option to trigger Workflow when the incident is declined in the Data Breach Workbench. |
| Operation | List | Choose this operation to list the available breach incidents. |
| Page Size | Specify the number of objects to fetch per page. |
| Polling interval | Specify the minutes/hours for the trigger to work |
| Unit | Specify the unit of the polling interval i.e. hours or minutes |
| From Date | Specify the date to fetch the records from the selected date to current time, in initial sync. By default, data will be fetched from the very beginning if no starting date is mentioned. |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
