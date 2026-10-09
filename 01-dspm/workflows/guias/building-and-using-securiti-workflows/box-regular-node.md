---
title: "Box"
slug: "box-regular-node"
updated: 2026-01-09T08:45:55Z
published: 2026-01-09T08:45:55Z
canonical: "helpcenter.securiti.ai/box-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Box

Box is a cloud-based content management platform that enables users to securely store, share, and collaborate on files. It offers features such as file synchronization, access control, and workflow automation, making it a valuable tool for businesses to manage their digital content effectively. Use the Box node to automate work in Box, and integrate Box with other applications.

In Securiti, the Box node lets you perform the following actions on the Box data system:

- Create or delete a new folder
- List items specified in a folder
- Upload or download the specified file
- Delete the specified file

Refer to the [Node Configurations section](/v1/docs/grant-permissions-and-obtain-credentials-in-box) to understand the node working and properties.

#### Example use case

As an example, let’s create a workflow that gets triggered every time a new assessment is published. It then writes the data of the assessment into a CSV file using the **Process CSV** node.

Subsequently, the workflow ensures the secure transfer and storage of this valuable data by uploading the csv file onto the Box data system. This orchestrated sequence not only automates the data handling process but also ensures that the latest assessment information is accurately and promptly integrated into the designated storage infrastructure, enhancing organizational efficiency and data management practices.

The following nodes are used in this workflow:

1. [Assessments Trigger Node](/v1/docs/assessments)
2. [Process CSV Node](/v1/docs/process-csv)
3. Box Node

#### Automated Workflow for Assessment Publication and Data Integration

1. Start the workflow by incorporating an Assessment trigger node set to respond to the event of a new assessment being published.
2. Integrate the Process CSV node into the workflow responsible for extracting and processing assessment data.
3. Add the Box node to upload the processed file into Box data system. Here is how the configurations look like:

![Screenshot_2023-12-12_at_12_59_37_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-370c26b1-cab0-949e-2674-7b31eeab8a04.png)
4. Connect the nodes and execute the workflow.

![Screenshot_2023-12-12_at_12_59_12_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-24e2ce35-c774-e5a7-82b9-992a03f083e2.png)
5. Once the workflow is successfully executed, you can view both table view and JSON response.

![Screenshot_2023-12-12_at_12_59_02_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7d5376fa-dfdf-cab1-4d48-46c77c4ae686.png)

#### Node configurations

| Parameters |
| --- |
| Data Source Name | Specify the datasource name for Box. To understand the data system configuration for Box, see the [Box connector documentation](/v1/docs/activate-the-box-securiti-cloud-connector-in-securiti). |
| As User | Specify the username that is performing the action using the node. The users typically appear in the form of a drop down after selecting the active datasource. |
| Resource | Folder | Select this option to perform an action on the specified folder. |
|  | File | Select this option to perform an action on the specified file. |
| Operation | The operation to perform on the resource |
| List items | Select this option to list all the items in a folder. |
| Create | Select this option to create a new folder. |
| Upload | Select this option to upload a file on the box datasystem. The maximum file size allowed for both uploading and downloading via the node is 100 MB. |
| Download | Select this option to download an uploaded file on the data system. The maximum file size allowed for both uploading and downloading via the node is 100 MB. |
| Delete | Select this option to delete a file or a folder. |
| File ID | Specify the file ID of the file on which the operation is performed. |
| Folder ID | Specify the folder ID to perform the operation on. |
| Folder Name | Specify the folder name for the new folder that is being created. |
| Parent ID | Specify the ID of the parent folder if any. It is an optional field. |
| Property Name | Specify the name of the binary property to which to write the data of the read file for upload and download operations |
