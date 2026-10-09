---
title: "EmailReadImap"
slug: "emailreadimap-trigger-node"
updated: 2025-10-30T19:11:45Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/emailreadimap-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# EmailReadImap

An Email Trigger (IMAP) node in a Workflow Automation platform is designed to monitor an email account for new messages and trigger actions within a Workflow based on the emails it receives. This node utilizes the Internet Message Access Protocol (IMAP), which is a standard email protocol that allows email clients to access and manipulate messages stored on a mail server.

You can configure your IMAP credentials and the node gets triggered whenever a new email is received. You can then perform functions such as marking the email as read or you can choose to do nothing.

Refer to the [node configuration section](/v1/docs/emailreadimap) to understand the node working and properties.

#### Prerequisites

You must configure the node with the necessary IMAP credentials to trigger the node. Please refer to the [setting up credentials section](/v1/docs/emailreadimap).

#### Example use case

As an example, let’s create a Workflow for a company that receives regular emails containing important documents as attachments from clients, partners, or internal departments. These documents need to be systematically stored in Google Drive for record-keeping, collaboration, and compliance purposes. Automating this process reduces manual work, minimizes the risk of human error, and ensures that all documents are consistently and securely stored.

The **EmailReadIMAP trigger node** starts the Workflow and gets triggered whenever a new email is received. A **function node** executes to fetch the attachments from the received emails and a **Google Drive node** uploads these attachments to Google Drive.

The following Nodes are used in this use case:

1. EmailReadIMAP Trigger Node
2. [Function Node](/v1/docs/function)
3. [Google Drive Node](/v1/docs/google-drive)

#### EmailReadIMAP Trigger Node

1. Start the Workflow by adding EmailReadIMAP Trigger node. Also enable the toggle that downloads the attachments.

![Screenshot_2024-05-07_at_5_51_54_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d3445f23-ea60-3449-5253-e3585a0adc28.png)
2. Add a function node with a Javascript code that fetches the attachments from the received emails and upload those using the Google Drive node.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-05-07_at_5_51_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bbb9fabd-b2e3-bc8d-b4e2-a7c3d18d44fc.png)
4. Upon successful execution, the Workflow Node will provide a successful response. After the Workflow runs successfully, you can access the results in two formats i.e. table view and JSON response

#### Node configurations

| Parameters |
| --- |
| IMAP credentials | Choose or create credentials to access the IMAP instance. Refer to the [setting up credentials section](/v1/docs/emailreadimap). |
| Mailbox Name | The name of the mailbox to read |
| Action | What to do after the email has been received. If you choose "Nothing" the email is processed multiple times. - Mark as read - Nothing |
| Download attachments | Enable the slider if you must download email attachments. Leave disabled unless you really need it; it increases processing overhead. |
| Options | Ignore SSL Issues | Enable to connect even if SSL certificate validation isn't possible |

#### Setting up credentials

Use the following credentials to set up credentials for the EmailReadIMAP trigger node

| Parameters |
| --- |
| User | Specify the email address of data subject's account |
| Password | Specify the password for the user account |
| Host | Specify the host name for example “smtp.office365.com” |
| Port | Specify the active port number |
| SSL/TLS | Turn the toggle on if SSL/TLS is enabled on the account |
| Nodes with access | Add the Nodes who can access using the credentials and mark the checkbox to select them |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
