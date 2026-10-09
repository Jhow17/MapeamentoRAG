---
title: "Dropbox"
slug: "dropbox-regular-node"
updated: 2026-01-12T06:52:16Z
published: 2026-01-12T06:52:16Z
canonical: "helpcenter.securiti.ai/dropbox-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Dropbox

Dropbox is a cloud-based file hosting service that allows users to store, sync, and share files across multiple devices. Users can access their files from anywhere with an internet connection, collaborate on documents in real-time, and benefit from features like version history and file recovery. Securiti provides

Dropbox node in workflow automation and supports various operations both on file and folder level such as:

- Creating a new folder or deleting an existing folder.
- Moving a folder from one location to another or creating a copy of an existing folder.
- Uploading a new file or downloading an uploaded file.
- Moving a file from one folder to another or creating a copy of an existing file.

Refer to the [Node configurations section](/v1/docs/register-an-application-in-dropbox) to understand the node working and properties.

#### Example use case

As an example use case, let's create a workflow that compresses the binary files into zip format and uploads them on Dropbox. The process initiates with an HTTP request node, tasked with retrieving a comprehensive list of users. Following this initial data gathering, the workflow progresses to a Spreadsheet file node, where the acquired user information is systematically compiled into a binary file. The output of this node is then passed on to the Zip node that compresses the data into a zip file and subsequently uploads it to dropbox.

The following nodes are covered in this workflow:

1. [HTTP Request Node](/v1/docs/http-request)
2. [Spreadsheet File Node](/v1/docs/spreadsheet-file)
3. [Zip Node](/v1/docs/zip)
4. Dropbox Node

#### Uploading the compressed binary file on Dropbox

1. Start creating the workflow by adding an HTTP Request Node. This node fetches the list of all the users via a Rest API call.
2. Add the Spreadsheet File node to write the data into a binary file.
3. The workflow then goes to the Zip node to compress the Binary file into a zip file.
4. Add the Dropbox node to upload the file on Dropbox. Refer to the image below to understand how to fill out the node parameters.

![Screenshot_2024-01-16_at_8_00_35_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-37e78005-8ade-070f-9aa6-552061265332.png)
5. Connect the nodes and execute the workflow.

![Screenshot_2023-12-11_at_11_44_19_PM_3_31_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4f30d35a-d47f-22ef-3bea-bea8cb5f9a9e.png)
6. Once the workflow is successfully executed, you can view both table view and JSON response.

![Screenshot_2024-01-16_at_8_01_10_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-00c64f32-a2f7-ceb3-9c40-bfc67e4d7ff0.png)

#### Node configurations

| Parameters |
| --- |
| Data Source Name | Specify the data source name. See [Dropbox connector documentation](/v1/docs/activate-the-dropbox-connector-in-securiti) to understand how to configure a data system. |
| User | Select the user from the dropdown against the selected data source. |
| Resource | Select the resource to operate on. |
| File | Select this option if the operation is being performed on a file. |
| Folder | Select this option if the operation is being performed on a folder. |
| Operation | The operation to perform on the resource |
| Create | Select this option to create a folder on the specified path. |
| Upload | Select this option to upload a file to Dropbox by specifying the path. The maximum file size allowed for uploading via the node is 100 MB. |
| Download | Select this option to download a file from the specified path. The maximum file size allowed for downloading via the node is 100 MB. |
| Delete | Select this option to delete a file or folder from the specified path. |
| Move | Select this option to move a file from the source path to the destination path. |
| Copy | Select this option to copy a file or folder from the source path to the destination path. |
| Path | Mention the path of the file/folder, for example, */root/my_folder/* |
| Source path | Specify the source path of the file/folder where the file or folder exists, e.g, */root/source_path*. |
| Destination Path | Specify the source path of the file/folder where the file/folder is moved or copied to. |
| Property Name | Specify the property name of the file that needs to be uploaded on Dropbox, for example, *data*. |
