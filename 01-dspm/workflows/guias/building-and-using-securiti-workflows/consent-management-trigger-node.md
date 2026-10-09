---
title: "Consent Management"
slug: "consent-management-trigger-node"
updated: 2025-10-30T19:10:38Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/consent-management-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Consent Management

The Consent Management trigger node records consent based on specific events, ensuring it activates only when the selected event types occur. This method allows for precise tracking and management of each user's consent record.

#### Example use case

As an example, let’s create a Workflow that records a single consent. The process commences with a Consent node, triggered to downstream single consent record at a time. Subsequently, the fetched consent data record is populated into the database using the Oracle node.

The following Nodes are included in this Workflow:

- Consent node
- Oracle node

#### Recording single consent using Consent node

1. Add a Consent Management Trigger node and set the **Type** with a meaningful **Name** and provide the type, **Execution Mode** and **Source** as per your requirement.

![Screenshot_2024-11-04_at_12_45_57_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae9f3ee7-ee63-631d-1717-6ac5d0449161.png)
2. Add an Oracle node with the required datasource. Use the query, as shown below.

![Usecase-2-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-78e6de40-0703-38f2-1e24-4c560753a01a.png)
3. Connect the Nodes and at the bottom of the Workflow tab, click **Execute Workflow** to execute the Workflow, as shown below.

![consent-trigger.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a067729f-14f1-7c6c-957a-18ea58c0ae9d.png)

#### Node configurations

| Parameters |
| --- |
| Name | (Optional) The name of the trigger |
| Execution Mode | Event Mode | Choose this option to set the execution to event based execution. In this mode, the selected events trigger the node. |
| Cron Mode | Choose this option to trigger the node based on the interval set. |
| Type | Any | Any consent management event |
| Form | Form consent management events |
| Preference Center | Cookie preferences center events |
| API | Consent management API events |
| Expiry | Consent expiration events |
| Narrow Path | Narrow path consent upload events |
| Source | Source of consent. Leave null for all sources. |
| Operation | List | Choose this operation to list the available consents. |
| Page Size | Specify the number of objects to fetch per page. |
| Polling Interval | Specify the minutes/hours for the trigger to work |
| Unit | Specify the unit of the polling interval i.e. hours or minutes |
| From Date | Specify the date to fetch the records from the selected date to current time, in initial sync. By default, data will be fetched from the very beginning if no starting date is mentioned. |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
