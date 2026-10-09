---
title: "No Operation, do nothing"
slug: "no-operation-do-nothing-regular-node"
updated: 2025-10-30T19:06:30Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/no-operation-do-nothing-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# No Operation, do nothing

A No Op Do Nothing node in a Workflow typically serves as a placeholder or a control element that doesn't perform any meaningful action or computation. Its purpose is to maintain the structure or flow of the Workflow without actually executing any significant task.

In many workflows, such as those used in business process management or automation systems, you might encounter Nodes or elements that represent different activities or tasks. The No Operation node is used when you want to indicate a point in the Workflow where nothing specific needs to be done, but you still want to maintain the sequential or conditional flow.

#### Example use case

Let’s take an example of a Workflow that gets triggered based on a new assessment being published. The Workflow then branches to the **Assessment node** to get the details of the assessment that is published using the assessment ID. Assuming that the user needs to be notified only if the assessment template type is CCPA, the Workflow further leads into an **IF node** to check the template type. If the template type is CCPA, the Workflow branches to a Send Email node to notify the user. And the No Op do nothing node is attached to the IF branch to perform no further action in the Workflow.

The following Nodes are used in this Workflow:

1. [Assessment Trigger Node](/v1/docs/assessments)
2. [Assessment Node](/v1/docs/assessment)
3. [IF Node](/v1/docs/if)
4. No Op Do Nothing Node

#### Assessment notification workflow for CCPA assessments

1. Add the Assessment Trigger node that gets triggered on any assessment being published, followed by an Assessment node to fetch the details of the assessment that triggered the Workflow.
2. Add the IF node to create branches based assessment details. Add the condition where the template type is equal to CCPA.
3. Add the Send Email node against the branch that is true and No Op Do Nothing against the false branch of the IF node.
4. Connect the Nodes and execute the Workflow.

![Screenshot_2023-12-11_at_11_18_50_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d8ec0595-0c8a-0290-3028-91aa0c6f1279.png)

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
