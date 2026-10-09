---
title: "ServiceNow"
slug: "servicenow-regular-node"
updated: 2025-10-31T14:22:43Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/servicenow-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# ServiceNow

ServiceNow is a cloud-based platform offering IT service management, business process automation, and other tools. It streamlines IT operations through modules like incident management, change management, and service catalog.

Securiti’s ServiceNow node lets you automate work in ServiceNow, and integrate ServiceNow with other applications. Securiti provides support for a wide range of ServiceNow features such as:

- Create or update a ticket in ServiceNow.
- Get a list of tickets or fetch details of a specific ticket based on the ID.
- Delete a ticket from ServiceNow.

Refer to the [Node configurations section](/v1/docs/synchronizing-assets-from-servicenow) to understand the node working and properties.

#### Example use case

In this example Workflow, the **Assessments Trigger node** serves as the catalyst, responding to the generation of a risk in an assessment. This leads to the integration of the **ServiceNow node**, which plays a central role in automating incident management. The ServiceNow node is configured to swiftly create a ticket in the ServiceNow platform, capturing crucial details about the identified risk. This seamless interaction with ServiceNow ensures that risk incidents are promptly logged and tracked within the robust IT service management system, fostering a proactive approach to risk mitigation.

Following the ServiceNow node's execution, the Workflow seamlessly extends its reach to notify the relevant team about the risk. The integration with Slack, facilitated by the Workflow, serves as an effective communication channel, alerting the designated team members to the incident logged in ServiceNow.

Following Nodes are used in this Workflow:

1. [Assessments Trigger Node](/v1/docs/assessments)
2. Service Now Node
3. [Slack Node](/v1/docs/slack)

#### Ticket creation in ServiceNow based on assessment risks

1. Start the Workflow by adding the Assessment trigger node and set the trigger type to **Risk**, so that the Workflow gets triggered whenever a new risk is flagged in the assessment.
2. Add the **ServiceNow node** to create a ticket for the risk and set the parameters of the node as shown below:

![Screenshot_2023-12-12_at_3_08_11_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b4247094-aa03-66f3-6166-0357e4eca805.png)
3. Add the **Slack Node** to notify the relevant channel about the ticket creation. Add a meaningful message in the Slack node to post in the channel with the relevant team.
4. Connect the Nodes and execute the Workflow

![Screenshot_2023-12-12_at_3_13_14_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-83f69805-d8de-8538-9943-46e2bb771b7c.png)
5. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Specify the datasource name for Box. To understand the data system configuration for Box, see the [connector documentation](/v1/docs/activate-the-servicenow-legacy-and-servicenow-connectors-in-securiti). |
| Operation | Create Ticket | Specify this option to create a ticket in ServiceNow. |
| Get Ticket Details | Specify this option to get details of a ServiceNow ticket. |
| Update Ticket | Specify this option to update a ticket in ServiceNow. |
| Delete Ticket | Specify this option to delete a ticket from ServiceNow. |
| List Tickets | Specify this option to list tickets in a specified table. |
| Ticket Type | The type of ticket to operate on: - Change request - Request Item - Problem - Incident - Ticket |
| Ticket Number | For Get Details and Delete operations, the **sys_id** of the ticket |
| Add Custom Payload | Toggle to create and add a custom payload in the message body |
| Create Payload | Add the customised payload in the message body. |
| Table Name | For Update and List operations, the table name to query on |
| Update Key | For Update operations, the key to update on |
| Update Key Value | For Update operations, the key to update on |
| Update Payload | For Update operations, the payload for the update request. Must be a valid JSON object |
| Delta sync | For List Ticket operations, enable to use the last saved time pointer to query the table |
| Perform Data Classification | Whether to perform data classification tagging from privaci classifications or perform other operations |
| ServiceNow Table | Name of the ServiceNow table |
| Field Classifications | Array of objects containing columns and detections from privaci system.Use the classifications field as raw data expression when using this node with the Field Classification Trigger node |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
