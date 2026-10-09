---
title: "Mautic"
slug: "mautic-regular-node"
updated: 2025-10-30T19:06:07Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/mautic-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Mautic

Mautic is an open-source marketing automation platform that provides tools for managing and automating marketing campaigns. Securiti provides a Mautic node to interact with and consume Mautic’s API for manipulating and obtaining details on Mautic’s contacts. In Mautic, a contact refers to individuals or entities that you engage with through your marketing efforts. These contacts can be leads, prospects, customers, or any individuals.

You can perform the following operations on Mautic contacts using the node:

- Create or update a contact
- Get data of one or all contacts
- Delete contacts

Refer to the [Node configurations section](/v1/docs/mautic) to understand the Node Configurations and properties.

#### Prerequisites

You must have Mautic credentials set up to use the Mautic node. Refer to the [setting up credentials section](/v1/docs/mautic) for more information.

#### Example use case

As an example let’s create a Workflow where a list of contacts is fetched from Mautic using the Mautic node and the data is processed in a CSV file. This CSV file is then uploaded to Dropbox using the Dropbox node.

This Workflow automates the retrieval and processing of contact data from the Mautic marketing automation platform. The end-to-end process, from data retrieval to cloud storage, is efficiently managed, providing a streamlined solution for handling contact information within the specified marketing and storage ecosystems. Following Nodes are used in this Workflow:

1. Mautic Node
2. [Process CSV Node](/v1/docs/process-csv)
3. [Dropbox Node](/v1/docs/dropbox)

#### Fetching Mautic contact data and uploading to Dropbox

1. Add the Mautic node and set the configurations such that the node fetches the details of all the contacts on Mautic.

![Screenshot_2024-01-30_at_6_11_26_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-710ac2d3-7967-44fa-0a7f-1696b4bc2be3.png)
2. Add the Process CSV node to produce a CSV file from the contact list fetched using the Mautic node.
3. Add Dropbox node and set it up such that the CSV is uploaded to the Dropbox account of the user.
4. Connect the Nodes and execute the Workflow.

![Screenshot_2024-01-30_at_6_11_15_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-509c9dd8-b49e-672b-6b38-1dd8043269c4.png)
5. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| Credentials | Choose or create credentials to access the Mautic instance |
| Resource | Contact | Use this endpoint to manipulate and obtain details on Mautic contacts. |
| Operation | Create | Choose this option to create a new contact. |
| Update | Choose this option to update an existing contact. |
| Get | Choose this option to get data for a contact. |
| Get All | Choose this option to get data for all Mautic contacts. |
| Delete | Choose this option to delete a contact. |
| JSON Parameters | Enable this toggle to deliver the parameters as a JSON object. |
| Email | Specify the contact's email address, for example john@gmail.com. |
| First Name | Specify the contact's first name, for example, John. |
| Last Name | Specify the contact's last name, for example, Smith. |
| Primary Company | Specify the contact's primary company, for example, Microsoft |
| Position | Specify the contact's position, for example, Manager. |
| Title | Specify the contact title. |
| Contact ID | Specify the ID of the contact to get, update, or delete contact's data. |
| Return All | Enable to return all contacts. Disable to return only up to the limit. |
| Limit | Sets the number of contacts to return when Return All is disabled. |
| Additional Fields | IP Address | Specify the IP address to associate with the contact. |
| Last Active | Specify the last active date/time of the contact in UTC. |
| Owner ID | Specify the ID of the Mautic user to assign the contact to |
| Options | RAW Data | Enable this option to return the RAW response with all data. When disabled, returns only the data in the fields. |

#### Setting up credentials

Use the following parameters to set up credentials for Mautic:

| Parameters | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself. |
| URL | Specify the Mautic URL to access the Mautic API. |
| Username | Specify the username of the data subject's account, for example, john. |
| Password | Specify the password for the user account |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

Node configurations are the essential settings and characteristics that define how each node works in the Workflows module. These details cover everything from basic operations to specific features needed for the functioning of each node. Since nodes have different purposes and functions, their configurations vary from node to node to ensure they work smoothly together in a workflow.

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
