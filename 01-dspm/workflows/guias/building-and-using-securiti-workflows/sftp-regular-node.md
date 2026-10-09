---
title: "SFTP"
slug: "sftp-regular-node"
updated: 2025-10-30T19:08:10Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/sftp-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# SFTP

An SFTP node in a Workflow Automation platform enables secure file transfer operations using the SFTP (Secure File Transfer Protocol). Using the SFTP node, you can perform the following set of actions:

- Retrieves files from a remote SFTP server and brings them into your Workflow for further processing or storage.
- Transfers files from your local system or Workflow environment to a remote server that supports SFTP connections.
- Obtains a listing of files and directories within a specified path on the remote SFTP server.

Using the SFTP node provides a secure way to transfer files compared to unencrypted protocols like FTP and eliminates the need for manual file transfers using SFTP clients, saving time and reducing errors. Refer to the [Node configurations section](/v1/docs/acquire-authentication-credentials-in-sftp) to understand the node working and properties.

#### Prerequisites

You must have valid SFTP credentials to use the node. See the [setting up credentials section](/v1/docs/acquire-authentication-credentials-in-sftp) to understand how that can be done.

#### Example use case

As an example, let’s create a Workflow that fetches the consent records from SFTP server and uploads the records on Securiti. This automates the process of updating the consent records on the Securiti platform. The Workflow starts on a daily schedule at 6 AM, set using the Cron node. The SFTP node then connects to the SFTP server to retrieve a file containing consent data in CSV format. The CSV file is parsed, and the data within is split into smaller batches for processing using the Split in Batches node.

The consent records are then routed based on their statuses using the **Switch node**. The possible statuses in this case are authorised, awaiting and rejected. Based on the status, the Nodes are then connected to the **HTTP request node** to use a POST API call that uploads the consent statuses onSecuriti platform.

The following Nodes are used in this Workflow:

1. [Cron Node](/v1/docs/cron)
2. SFTP Node
3. [Process CSV Node](/v1/docs/process-csv)
4. [Split in Batches Node](/v1/docs/split-in-batches)
5. [Switch Node](/v1/docs/switch)
6. [HTTP Request Node](/v1/docs/http-request)

#### Consent data flow from SFTP to Securiti

1. Add the Cron node to set a time for the Workflow.
2. Add SFTP node and specify the parameters such as the operation is set as List and the path where the file resides.

![Screenshot_2024-03-19_at_4_31_53_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2db6098e-b3a4-0fae-faf8-f40a447dc763.png)
3. Add the Process CSV node to consume the data followed by the Split in Batches node to break down the data into streams.
4. Use the Switch node to set the condition and finally set the consent records in Securiti by adding the HTTP Request node.
5. Connect the Nodes and execute the Workflow.

![Screenshot_2024-03-18_at_11_42_21_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d8b0be6-e65d-a4fc-6ca6-d6c461b64af8.png)
6. Once the Workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| SFTP Credentials | Select the credentials from the menu. If there are no existing credentials, create new credentials by referring to the setting up credentials section. |
| Authentication Type | SFTP authentication type: - Basic Auth - Key Based Auth - Key + Password Based Auth |
| Operation | Specify the operation to perform: - Download the files from the SFTP server. - Upload files to the SFTP server. - List the existing files on the SFTP server. > [!NOTE] > **Note** > > The maximum file size allowed for both uploading and downloading via the node is 100 MB. |
| File Name | Specify the path of the file you want to upload or download |
| Property Name | Specify the name of the binary property in which you want to write the data of the read file |
| Key | Specify the key for SFTP authentication. |
| **Additional Fields** |
| Negotiation Algorithms | Specify algorithms to use during the SSL negotiation |
| Type | Specify the algorithm family: - HMAC - Cipher - KEX |
| Algorithm | Algorithm to use. Provide comma separated values for multiple algorithms. For instance, for the **Cipher** algorithm, the value could be "3des-cbc,aes128-ctr,aes256-ct”. |

#### Setting up credentials

Use the following parameters to set up credentials for the SFTP node. Retrieve the login credentials from your SFTP account such as host and port parameters.

| Parameters | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself. |
| Host | Specify the hostname or IP of SFTP server, for example, *129.146.211.82* |
| Port | Specify the port on which the SFTP server is running, for example, *9082*. |
| User | Specify the username of the SFTP account, for example, *johndoe*. |
| Password | Specify the password for the SFTP user. It is applicable for both password based or 2FA based authentication. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
