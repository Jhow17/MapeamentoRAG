---
title: "Using the Workflows execution log"
slug: "viewing-the-workflow-execution-log"
updated: 2026-03-09T07:23:05Z
published: 2026-03-09T07:23:05Z
canonical: "helpcenter.securiti.ai/viewing-the-workflow-execution-log"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Using the Workflows execution log

Securiti maintains a workflow execution log that shows all workflow executions for the prior 30 days.

To open the log:

- On the Workflow Editor page, select **Executions** from the options in panel.

![Workflow editor displaying execution details and filters for Marketo Consent Workflow.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/wf-ex-1.png)

For each workflow execution, the log shows:

| Started At / ID | The UTC time at which the workflow triggered, and a unique ID number for the execution |
| --- | --- |
| Name | The name of the workflow |
| Correlation Id | The correlation Id of the workflow |
| Status | The status with which the workflow ended: - Success - Running - Error |
| Mode | How workflow execution started |
| Running time | How long the workflow took to execute |

> [!NOTE]
> **Note**
> 
> - You can configure how long workflow execution logs are retained. This lets you define a custom retention period for each workflow to support extended troubleshooting and audit needs. You can choose from 30 days (default), 90, 180 , or 365 days.
> - If no retention period is specified, logs automatically follow the default 30-day policy.
> - All active workflows now automatically timeout after 6 hours of execution. Please ensure your workflows are designed to complete within this timeframe to avoid interruptions.
> - When a Workflow is deleted, all associated executions are also deleted. However, if there are any running executions for a Workflow, it cannot be deleted until those executions have completed.

### Storing execution logs in customer private cloud storage

Securiti lets you view the execution logs in detail for workflows in customer private cloud storage. You can get a detailed execution log in the form of JSON file.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

Securiti stores workflow execution data in **Privacy Cloud Storage (PCS)** to support visibility and troubleshooting of workflow executions.

To store workflow execution data, the workflow log retention feature must be enabled. If log retention is not enabled, Securiti does not store workflow execution data.

When both PCS and log retention are enabled, Securiti stores workflow execution data in PCS for all workflow executions, including both successful and failed ones. The stored execution data includes information processed by the workflow nodes during the execution. For failed executions, you can review node-level processed data from the execution logs to identify where the run failed.

Execution data is displayed only for failed workflow executions. When you open a failed execution, Securiti displays the data stored in PCS. A 14.01 MB size limit applies to the data displayed.

> [!NOTE]
> Note
> 
> If a workflow includes a loopback node, Securiti stores only the last iteration of the workflow execution data in PCS.

To review a failed execution:

1. From the **Execution logs**, click on the folder icon to open the past executions.

![Workflow executions display errors for various tasks with running times and correlation IDs.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/wf-ex-2.png)
2. The visual workflow page displays the data processed by each node. Click any node to see the data processed during that execution.

![Screenshot_2024-06-25_at_1_47_41_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be08a2d6-1ecf-d4cd-5932-05446fd447ed.png)
