---
title: "Policy Alert"
slug: "policy-alert-trigger-node"
updated: 2025-11-04T10:49:15Z
published: 2025-11-04T10:49:15Z
canonical: "helpcenter.securiti.ai/policy-alert-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Policy Alert

In Securiti, you can create policies related to data security posture management, access control, and cross-border data transfer. Some of these policies generate alerts based on the violations of the defined rules. You can create posture policies for cloud systems as well as SaaS systems. Each policy has rules that, when matched by a file, document, or resource, trigger a response. With Securiti's data access control policies, you have a centralized framework to manage authorization policies for your data systems.

The **Policy Alert** trigger node gets triggered whenever a new policy alert is generated for the following policies:

- Cloud security posture policies
- SaaS security posture policies
- Cross border transfer policies
- File insights policies
- Structured insights policies

You can configure workflows for the policies and integrate the policy Alert node with other application Nodes to get alerts. Refer to the [Node configurations section](/v1/docs/policy-alert) to understand the node's working and properties.

### Example use case 1: Cross-border Policy

As an example, let’s create a Workflow that is triggered every time a cross-border policy alert is generated. The **Policy Alert** node is triggered and connected to the **Slack** node to alert the data owners about the cross-border data transfer violations on Slack.

In Securiti, Cross border transfer policies let you mitigate the risk associated with illegal data access across borders and assist with the remediation through governance workflows. See [cross border policy documentation](/v1/docs/cross-border-transfer-policies) to get more information about cross border transfer policies.

The following Nodes are used in this Workflow:

- Policy Alert trigger node
- [Slack node](/v1/docs/slack)

#### Getting notified via Slack on every cross border transfer alert

1. Add the Policy Alert node and provide the **Name**. Set the **Type** to **Cross Border Transfer**.

![CB_Policy_Alert_Trigger.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-03ceabcb-9877-180c-9666-3a034eb18700.png)
2. Add the **Slack node**. Select the activated instance for Slack in the **DataSource Name.** Select **Message** from the **Resource** menu. Set the **Operation** to **Post to Channel**. Select the **Channel** to which you want to post the alert. Add the message content to the **Text**.

![Slack_node.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7267d43b-92b7-06c4-799a-d36a2711edc9.png)
3. Connect the Nodes and execute the Workflow.

![Connect_nodes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d6d31702-37d0-36b1-e86c-d783bdb464b3.png)
4. Activate the Workflow.

![policy_alert_trigger_cb-execution.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-19ad91fb-a197-7030-7a59-3e3ba2cb7b33.png)
5. Once the Workflow is successfully executed, you can view both the table view and the JSON response.

#### Enabling Policy Trigger response in Cross Border Transfer Policy

You also need to enable the response in the policy section using the following steps:

1. In the **Responses** section of the cross border transfer policy that you have created, enable the **Trigger Workflow** toggle to add the Workflow. Click the **Add Workflows** button.
2. Select the workflows from the **Add Trigger Workflow**. Click **Add Workflows**.

### Example use case 2: Security Posture Policy

As another example, let’s create a Workflow that is triggered every time a cloud security posture policy alert is generated. The **Policy Alert** node is triggered and connected to the **Slack** node to alert the data owners about the cloud security posture policy rules violations on Slack.

In Securiti, Cloud Security Posture Policies let you prioritize the discovery of sensitive data to identify and mitigate security and compliance misconfiguration risks in your cloud environment.

For more information, see [Posture Policies](/modules/security-posture-management/en/index-en.html?contextId=/modules/security-posture-management/en/index-en.html?contextId=spmCreatePosturePolicy) and [Security posture findings](/v1/docs/configuring-security-posture-policies).

The following Nodes are used in this Workflow:

- Policy Alert trigger node
- [Slack node](/v1/docs/slack)

#### Getting notified via Slack on every cloud security posture alert

1. Add the Policy Alert node and provide the **Name**. Set the **Type** to **Cloud Data Security Posture**.

![Screenshot_2024-02-12_at_12_01_51_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-15e02134-c207-94a3-50ee-fcaf4c3be709.png)
2. Add the **Slack node**. Select the activated instance for Slack in the **DataSource Name.** Select **Message** from the **Resource** menu. Set the **Operation** to **Post to Channel**. Select the **Channel** to which you want to post the alert. Add the message content to the **Text**.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-02-12_at_12_00_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7f9ca6e1-d117-6f21-58d8-acff94d11398.png)
4. Activate the Workflow. Once the Workflow is successfully executed, you can view both the table view and the JSON response.

![Screenshot_2024-02-12_at_12_01_02_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1996ab20-fa59-8d03-2d16-679054355866.png)

#### Enabling Policy Trigger Response in Cloud Security Posture Policy

You also need to enable the response in the policy section using the following steps:

1. In the **Responses** section of the cloud security posture policy that you have created, enable the **Trigger Workflow** toggle to add the Workflow. Click the **Add Workflows** button.
2. Select the workflows from the **Add Trigger Workflow**. Click **Add Workflows**.

![Screenshot_2024-02-12_at_1_05_59_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f7239404-01df-870c-c771-b44f95c5bc7a.png)

### Example use case 3: File Insights Policy

As an example, let’s create a Workflow that is triggered whenever the File insights policy is triggered

The Policy Alert node is triggered and connected to the Slack node to alert the data owners about the file insights policy applied to files on Slack.

In Securiti, file insights policies are supported for unstructured data systems having different purposes. File insights policies let you identify files that have sensitive data in them as well as other metadata information. For more information, see [File insights policies](/v1/docs/configuring-file-insights-policies).

The following Nodes are used in this Workflow:

- Policy Alert trigger node
- [Slack node](/v1/docs/slack)

#### Getting notified via Slack retention, and file insights policy alert

1. Add the Policy Alert node and provide the **Name**. Set the **Type** to the Retention policy.
2. Add the Slack node. Select the activated instance for Slack in the DataSource Name. Select Message from the Resource menu. Set the **Operation** to Post to Channel. Select the **Channel** to which you want to post the alert. Add the message content to the Text.
3. Connect the Nodes and execute the Workflow.
4. Activate the Workflow.
5. Once the Workflow is successfully executed, you can view both the table view and the JSON response.

#### Enabling Policy Trigger response in file retention, and file insights

You also need to enable the response in the policy section using the following steps:

1. In the **Responses** section of a policy, enable the **Trigger Workflow** toggle to add the Workflow. Click the **Add Workflows** button.
2. Select the workflows from the **Add Trigger Workflow**. Click **Add Workflows**.

#### Example use case 4: Structure data insights policy

Structured data insights policies let you identify tables and columns that have sensitive data in them, as well as other metadata information. For more information, see the [Structured Data Insights policies](/v1/docs/policies-configuring-structured-data-insights-policies).

As an example, let’s create a Workflow that is triggered whenever the Structured Data Insights policy is triggered.

The Policy Alert Trigger node is triggered and connected to the Slack node to alert the data owners about the structured data insights policy applied to the database tables and columns on Slack.

In Securiti, Structured Data Insights policies are supported for structured data systems having different purposes. The following Nodes are used in this Workflow:

- Policy Alert Trigger node
- [Slack node](/v1/docs/slack)

#### Getting notified via Slack

1. Add the **Policy Alert** node and provide the **Name**. Set the **Type** to the Structured insights policy.
2. Add the **Slack** node. Select the activated instance for Slack in the DataSource Name. Select Message from the Resource menu. Set the **Operation** to **Post to Channel**. Select the **Channel** to which you want to post the alert. Add the message content to the **Text**.
3. Connect the Nodes and execute the Workflow.
4. Activate the Workflow.
5. Once the Workflow is successfully executed, you can view both the table view and the JSON response.

#### Enabling Policy Trigger response in Structured Data Insights policy

You must enable the response in the policy section using the following steps:

1. In the **Responses** section of a policy, enable the **Trigger Workflow** toggle to add the Workflow. Click the **Add Workflows** button.
2. Select the workflows from the Add Trigger Workflow. Click **Add Workflows**.

### Node configurations

| Parameters |
| --- |
| Name | (Optional) Name of the policy alert trigger. |
| Execution Mode | Event Mode | Choose this option to set the execution to event-based execution. In this mode, the selected events trigger the node. |
| Cron Mode | Choose this option to trigger the node periodically based on the interval set. |  |
| Type | Any | Triggers on any policy type. |
| Cloud Data Security Posture | Triggers for cloud data security posture policy. |
| SaaS Data Security Posture | Triggers for data security posture policy. |
| Cross Border Transfer | Triggers for cross-border transfer policy. |
| File Insights | Triggers for file insights policy. |
| Structured insights | Triggers for Structured Data Insights policy. |
| Operation | List | Choose this operation to list the available policies. |
| Page Size | Specify the number of objects to fetch per page. |
| Polling Interval | Specify the minutes/hours for the trigger to work |
| Unit | Specify the unit of the polling interval i.e. hours or minutes |
| From Date | Specify the date to fetch the records from the selected date to the current time, in the initial sync. By default, data will be fetched from the very beginning if no starting date is mentioned. |

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
