---
title: "Using the Assessment Stage Change trigger node"
slug: "using-the-assessment-stage-change-trigger-node"
updated: 2025-12-08T07:00:08Z
published: 2025-12-08T07:00:08Z
canonical: "helpcenter.securiti.ai/using-the-assessment-stage-change-trigger-node"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Using the Assessment Stage Change trigger node

This topic describes the use case for the State Change trigger node in the Assessment Workflow Stages. For information on *assessments with workflows*, see the [Workflow Orchestration documentation](/v1/docs/assessments).

> [!NOTE]
> **Important**
> 
> You must have Assessment V2 enabled on your tenant to use the Stage Change trigger node.

#### Adding an assessment event for Stage Change

As a workflow admin, you may want to trigger a workflow whenever an assessment changes state. This helps you automate assessments that meet the workflow's criteria.

> [!NOTE]
> **Note**
> 
> You can configure the event however you want. In this example, we have used the State Change trigger to email us about the assessment status.
> 
> For example, you can configure it to start an assessment instead.

1. Create a workflow trigger node with a meaningful name, such as Assessment Trigger, and set the trigger type to **State Change.**

![Screenshot_2024-10-30_at_7_43_25_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-129ed9a9-2880-663e-9f25-d81139e2554e.png)
2. Specify filename and additional actions before the file is emailed, such as converting data from JSON to binary.
3. Assign action "Send Email."

![Screenshot_2024-10-31_at_3_29_21_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-55443345-4324-db2a-2a18-594e7ef4bc17.png)
4. Execute the workflow to trigger the event.

#### Node configurations

Below are the keys to get the relevant data:

| Parameters | Description |
| --- | --- |
| Event date | ```bash {{$node["Assessments Trigger"].json["stage_change_trigger"]["event_date"]}} ``` Epoch time stamp in *int* |
| Assessment ID | ```bash {{$node["Assessments Trigger"].json["stage_change_trigger"]["assessment_id"]}} ``` |
| Template ID | ```bash {{$node["Assessments Trigger"].json["assessment"]["template_id"]}} ``` The same applies to other fields like *template_type* and *template_version* |
| Previous Stage | ```bash {{$node["Assessments Trigger"].json["stage_change_trigger"]["previous_stage"]}} ``` |
| Current Stage | ```bash {{$node["Assessments Trigger"].json["stage_change_trigger"]["current_stage"]}} ``` |

Workflow Stages relate to the assessment lifecycle in V2. A typical Securiti assessment has four stages: Not Started, In Progress, In Review, and Complete. The Not Started stage is when you haven't begun answering. As soon as you interact with at least one question, the stage changes to In Progress. After the assessment is submitted, the reviewer is called In Review. Once the concerned parties approve, the assessment transitions to the Complete stage.

## Related

- [Understanding Workflow Stages and assessment use cases](/understanding-workflow-stages-and-assessment-use-cases.md)
