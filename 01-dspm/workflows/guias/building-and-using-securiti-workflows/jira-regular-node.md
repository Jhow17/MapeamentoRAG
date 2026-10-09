---
title: "Jira"
slug: "jira-regular-node"
updated: 2026-01-16T06:17:59Z
published: 2026-01-16T06:17:59Z
canonical: "helpcenter.securiti.ai/jira-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Jira

The Jira node within Securiti's Workflow automation module acts as a bridge between your data security platform and your issue tracking system. It empowers you to automate key tasks, enhance security visibility, and simplify collaboration within your workflows.

The node offers the following functionalities:

- Automatically generate Jira issues based on specific triggers or data events or modify details or add comments to existing Jira issues based on data insights or actions taken. You can also fetch details of a specific issue or get details of all the existing issues.
- Retrieve historical data and audit trails related to specific Jira issues for in-depth analysis or reporting within Securiti. You can also obtain a list of available transitions for a specific Jira issue, enabling dynamic decision-making within your workflows.
- Send email alerts to assigned users or teams within Jira, ensuring timely communication and collaboration.

Refer to the [Node configurations section](/v1/docs/jira#node-configurations) to understand the node working and properties.

#### Example use case

As an example use case, let’s create a Workflow where if the Workflow encounters an error (e.g., data format mismatch, server timeout), the error trigger fires. It then connects to the Jira node to automatically create a ticket in your project, capturing details like error message, timestamp, and affected Workflow. Finally, the Slack node comes in, notifying the relevant assignee (e.g. developer) about the reported bug.

This automates tedious manual bug reporting, saving time and ensuring consistent capture of errors. Assignees receive prompt notifications, facilitating faster bug resolution and improved Workflow stability.

The following nodes are used in this Workflow:

1. [Error Trigger Node](/v1/docs/error)
2. Jira Node
3. [Slack Node](/v1/docs/slack)

#### Automated Bug Reporting and Notification Workflow

1. Place the Error Trigger Node. Position it towards the end of your main Workflow, capturing potential errors during execution.
2. Add Jira node and populate the corresponding fields in the Jira node. Choose the issue type, priority, and other relevant settings for your Jira tickets.

![Screenshot_2024-02-20_at_2_21_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-03f0ed1f-f4eb-4537-8f08-321ca7c9bd96.png)
3. Add the Slack node to notify the relevant assignee about the Jira ticket being created.
4. Connect the nodes and execute the Workflow.

![Screenshot_2024-02-20_at_2_22_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aa432101-a105-9fce-42b8-8889301a133e.png)
5. Upon successful execution, the Workflow Node will provide a successful response. After the Workflow runs successfully, you can access the results in two formats i.e. table view and JSON response

![Screenshot_2024-02-20_at_2_23_01_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0f695c58-d2f5-96d4-29bd-eae3273f3b75.png)

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Specify the name of the Jira data system instance on which to operate. |
| Cloud ID | Select your JIRA domain from the menu. |
| Resource | - Issue |
| Operation | The operation to perform on the resource |
| Create | Choose this option to create a new issue. |
| Get All | Choose this option to get all issues. |
| Get | Choose this option to get a specific issue. |
| Update | Choose this option to update an issue. |
| Changelog | Choose this option to get issue change logs |
| Project | Select the project in which to create the issue. |
| Issue Type | Specify the issue type from the menu as per the selected project. |
| Summary | Specify the issue summary in textual format. |
| Return All | For operations that return multiple issues, toggle to either return all or return only up to the selected limit |
| Limit |
| Options (Get All) | Expand | Include additional information about issues in the response |
| Fields | A list of fields to return for each issue; use to retrieve a subset of fields. Options include: - **all**--Returns all fields - **navigable**--Returns navigable fields - Any issue field to include, or prefixed with a minus to exclude |
| Fields by key | Toggles whether fields in fields are referenced by keys rather than IDs. Use where fields have been added by a connect app and a field's key may differ from its ID |
| JQL | A JQL expression |
| Additional Fields | Click **Add Field** to add: - Issue type - Summary - Parent issue key - Labels - Priority - Assignee - Description - Status - Fields - Fields by key - Expand - Properties |
| Issue key | Specify the issue key of the issue to get, update, or get change log, for example, 12345. |
| Required Fields For IssueType | Click **Add Property** to add: - Field - Value |
| Options | Click **Add Option** to add: - Expand - Fields - Fields by key - JQL |
