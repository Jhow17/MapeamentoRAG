---
title: "Outlook"
slug: "outlook-regular-node"
updated: 2025-10-31T14:22:22Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/outlook-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Outlook

An Outlook node in Securiti Workflows module is a specific component designed to fetch email summaries for a given email ID. It serves as a connector or interface between the workflows system and Microsoft Outlook or similar email services. Its primary function is to retrieve essential information about an email, such as its subject, sender, date, and other metadata, without necessarily fetching the entire email content. This capability is useful for automating various Workflow processes that require email data without the need to open and read the full email message.

The Outlook node's ability to retrieve email summaries can be a valuable feature in Workflow automation. By extracting and summarizing email data, this component streamlines Workflow processes, reduces manual intervention, and ensures that critical information from emails is efficiently integrated into the larger workflows system.

See the [Node configurations section](/v1/docs/outlook) to understand the node configuration and properties.

#### Example use case

As an example, a Workflow is designed to fulfill a specific use case where a Data Subject Request (DSR) access request requires a summary of emails from Microsoft Outlook. To accomplish this, the Workflow leverages Outlook's querying function, which allows it to retrieve a message digest of all emails where a particular email address is either the sender or recipient. The returned data is presented in a tabular format, including fields such as **From**, **ToRecipients**, **Subject**, and **BodyPreview**. This redaction helps maintain data privacy and security, ensuring that the identities of individuals involved in the email communication other than the data subject remain confidential.

In this Workflow, the primary goal is to respond to DSR access requests efficiently by extracting relevant email data from Outlook. This is achieved by querying O365 for emails associated with the specified email address, collecting relevant information such as sender, recipient, subject, and a brief email preview. The automatic redaction of email addresses that are not part of the query helps maintain data privacy and compliance with regulations. Overall, this streamlined process enables organizations to provide data subjects with a summarized view of their email communications, while safeguarding the privacy of others involved in those communications.

This Workflow uses the following Nodes:

1. [DSR Trigger Node](/v1/docs/dsr)
2. [DSR Task Node](/v1/docs/dsr-task)
3. [DSR Subtask Node](/v1/docs/dsr-sub-task)
4. Outlook Node
5. [Process CSV Node](/v1/docs/process-csv)
6. [DSR Sub-task Attachment Node](/v1/docs/dsr-sub-task-attachment)

#### Streamlining Data Subject Request (DSR) Response by Extracting Email Data from Outlook

1. Add DSR Trigger node and set the type to **Access**, source to Internal and status to InProgress. Add the DSR Task and DSR Subtask node with the data source selected for which the task should be created.
2. Add the Outlook node and select the Data Source for the O365 Outlook connection that will be used to enumerate emails for.

![Screenshot_2023-11-07_at_4_54_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f6b73414-dc55-5a02-1075-6cc9ade4ae58.png)
3. Add the Process CSV file and set the operation to **Produce** to generate a CSV output. The File Name here will be the name of the attachment in the sub-task. Make sure to enable the **Aggregate** option
4. Add the DSR sub-task Attachment node to attach the email file in the DSR Subtask.
5. Connect the Nodes and execute the Workflow.

![Screenshot_2023-11-07_at_4_56_30_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1cf0199b-07d1-abfb-345d-77e7d104fc2e.png)
6. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configuration

| Parameters |
| --- |
| DataSource Name | Specify the name of the datasource configured for Outlook data system. See the [connectors documentation](/v1/docs/activate-the-microsoft-dataverse-connector-in-securiti) to understand how to configure a data system. |
| Email | Specify the email ID of the email to operate on. The node fetches the email summary of all the emails that are received or sent from the provided email ID. |
| Operation | Email summary | Choosing this option fetches email summary of the provided data system and email ID. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
