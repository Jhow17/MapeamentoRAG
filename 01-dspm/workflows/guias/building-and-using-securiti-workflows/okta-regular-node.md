---
title: "Okta"
slug: "okta-regular-node"
updated: 2025-10-30T19:06:34Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/okta-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Okta

Okta is a cloud-based identity management service that provides identity and access management (IAM) solutions. It is widely used by organizations to manage and secure user authentication into applications and to manage users and groups. Okta serves as a single platform to securely connect the right people to the right technologies at the right time.

Using the Okta node in Workflows module, you can:

- Create a new user in Okta.
- Deactivate a specified user in Okta.
- List all the users or fetch details of a specific user.

Refer to the [node configuration section](/v1/docs/synchronizing-assets-from-okta) to understand the node working and properties.

#### Example use case

As an example, let’s create a use case that automates routine data operations involving user or application data from Okta, processes it into a usable format, and stores it securely in Dropbox. The automation saves time and reduces errors associated with manual data handling. It can be particularly useful for regular reporting, compliance audits, or ensuring that backups of critical data are consistently maintained.

The following Nodes are used in this use case:

1. [Cron Trigger Node](/v1/docs/cron)
2. Okta Node
3. [Process CSV Node](/v1/docs/process)
4. [Dropbox Node](/v1/docs/dropbox)

#### Automated data management workflow with Integrating Okta

1. Start the Workflow with a Cron trigger node that executes at the end of each day.
2. Add an Okta node that fetches the list of users from Okta datasource.

![Screenshot_2024-05-07_at_1_08_16_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-58ee5d4e-80c8-dc3d-26b2-71cd307eb462.png)
3. Add Process CSV node to process the data into a CSV file and upload it on Dropbox using the Dropbox node.
4. Connect the Nodes and execute the Workflow.

![Screenshot_2024-05-07_at_1_08_32_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c387f321-d7cf-10a7-d3c4-2844a03b75c4.png)
5. Once the Workflow is executed, you can view the response in both JSON and table view.

![Screenshot_2024-05-07_at_1_04_57_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e93e3d69-9151-6851-c3bb-a1c37c9f445a.png)

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Data system instance name in Securiti |
| Operation | Get Profile | Fetch details for a specified user |
| List Users | Find users |
| Deactivate User | Deactivate a specified user |
| Create User | Create a new user |
| Username/Email | For Get Profile and Deactivate User operations, the Okta username to operate on |
| First Name | For Create User operations, the new user first name |
| Last Name | For Create User operations, the new user last name |
| Email | For Create User operations, the new user email address |
| Login | For Create User operations, the new user login name |
| Mobile Phone | For Create User operations, the new user mobile phone number |
| User Attributes | For Create User operations, additional user properties |
| Secondary Email | Secondary Email |
| Recovery Question | Recovery question for the new user account |
| Recovery Answer | Recovery answer for the new user account |
| Password | Password for the new user account |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
