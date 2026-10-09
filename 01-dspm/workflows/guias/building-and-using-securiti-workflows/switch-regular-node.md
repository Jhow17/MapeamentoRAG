---
title: "Switch"
slug: "switch-regular-node"
updated: 2025-10-30T19:08:47Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/switch-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Switch

A Switch node in a Workflow is used to make decisions and route the Workflow based on specific conditions. It evaluates conditions, directs the Workflow down different branches based on the condition's outcome, and can handle multiple scenarios with fallback or default paths.

It can be commonly used for decision-making, error handling, process routing, scenario management, and data validation for automating complex workflows. This node is quite similar to the IF node except that the “Switch” node has up to 4 branches each with its own set of tasks. Switch node is designed for more complex decision-making workflows with multiple conditions and branches, while the "IF" node is better suited for simpler binary decisions.

Refer to the [Node configuration section](/v1/docs/switch) to understand the node parameters and descriptions.

#### Example use case

In this example, we are creating a Workflow designed to retrieve user data via an API and subsequently perform role-based filtration, followed by sending tailored emails. The process starts with the **HTTP request node**, which fetches user details. Subsequently, the data output is directed to the Wrap node, which transforms the object data into a more accessible list format for enhanced clarity and processing.

The **Switch node** then establishes distinct routes based on the users' roles. Leveraging the user details, the Workflow is directed to the **Send Email** node, sending customized emails to users with varying roles. For instance, if the user type is designated as "Superadmin," a specifically tailored email, designed exclusively for superadmins, is dispatched.

The following Nodes are used in this Workflow:

1. [Unwrap node](/v1/docs/unwrap)
2. [HTTP Request node](/v1/docs/http-request)
3. Switch Node
4. [Send Email Node](/v1/docs/send-email)

#### Sending Emails based on the user roles

1. Start the Workflow by adding an HTTP request node to fetch the details of the user using the Get users API.
2. Add the unwrap node to convert the data object into a list item.
3. Add the switch node to route the Workflow based on the user roles. Add the role names and set the output to the respective node as shown below:

![switch-params.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1f22b0b3-e4b7-c4a3-b8f7-6496ca3ff142.png)
4. Add the Send Email Nodes on the specific routes based on the roles.
5. Connect and execute the Workflow.

![switch-wf.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba62c4cf-0c5e-052c-29a1-f4431f12b292.png)
6. Upon successful execution, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| Mode | Expression | Route data based on an expression |
| Rules | Route data based on rules |
| Output | For Expression mode, the index of the output to which to send data |
| Value 1 | The value to compare with Value 2 |
| Data Type | - Boolean - Number - String |
| Routing Rules | Operation | Depending on Data Type: - Equal - Not Equal - Smaller - Smaller or equal - Larger - Larger or equal - Contains - Not Contains - Regex |
| Value 2 | The value to compare with Value 1 |
| Output | The index of the output to send data to when the rule matches |
| Fallback Output | The output to send data to when no rules are matched |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
