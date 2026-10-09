---
title: "Google drive"
slug: "google-drive-regular-node"
updated: 2026-01-12T08:30:36Z
published: 2026-01-12T08:30:36Z
canonical: "helpcenter.securiti.ai/google-drive-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Google drive

A Google Drive node in a workflow is a component used to interact with Google Drive, a cloud-based file storage service. It facilitates various file and folder operations, such as uploading, downloading, moving, and deleting files, as well as managing folder structures. Additionally, Google Drive Nodes allow users to handle sharing and permissions, search for specific files, trigger notifications and alerts, and integrate Google Drive with other applications and services.

Google Drive Nodes play a key role in workflow automation, helping organizations and individuals streamline document management processes and achieve greater efficiency. They can automate tasks like file backups, data synchronisation, and version control, making it easier to manage and access files stored in Google Drive as part of a broader, automated workflow.

Refer to the [Node configurations section](/v1/docs/prerequisites-for-g-suite-google-drive) to understand the node configuration and parameters.

#### Example use case

As an example use case, we are creating a workflow with the primary objective to automate a workflow triggered by the publication of an assessment using the **Assessment Trigger node**. Whenever a new assessment is published, a series of actions are initiated. The workflow then fetches the list of all the assessments published.

Once the data is fetched using the **Assessments node**, the workflow proceeds to write the fetched data into a file with the content of the newly created assessment, ensuring that the latest information is integrated. Finally, the updated file is uploaded to Google Drive, effectively adding the information of all the published assessments. This workflow streamlines the process of keeping assessment-related documents up-to-date, reducing the manual effort required for this task and ensuring that stakeholders always have access to the latest assessment data.

The following nodes are used in this workflow:

1. [Assessments Trigger Node](/v1/docs/assessments)
2. [Assessments Node](/v1/docs/assessment)
3. [Spreadsheet File](/v1/docs/spreadsheet-file)
4. Google Drive

#### Uploading a spreadsheet file to Google Drive with the latest assessments list

1. Add an Assessment Trigger node and set the type to **Publish**. So anytime a new assessment is published the workflow gets triggered.
2. Add the Assessments node to fetch the list of all the assessments so that the newly published assessment is also a part of the assessments list.
3. Add the spreadsheet file node to write the data into a file. Choose the format to **CSV** to create a CSV file with assessments list.
4. Add the Google Drive node and provide the required credentials. Set the resource to **File** and the operation type to **Upload** to upload the assessment list to Google Drive.

![Screenshot_2023-11-07_at_3_35_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dec26935-9cd8-9f73-5e75-c67352a37b03.png)
5. Connect the nodes and execute the workflow.

![Screenshot_2023-11-07_at_3_33_22_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-127a6edf-6117-d77d-16d7-2cbf40a9bcc1.png)
6. Once the workflow is successfully executed, you can view the success response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| Data Source Name | Specify the datasource name for Google Drive. To understand the data system configuration for Google Drive, refer to the Google Drive connector documentation. |
| User | On providing a valid datasource, a drop down appears in this section to choose a user from. |
| Resource | File | Choose this option if the operation is performed on a file. |
| Folder | Choose this option if the operation is performed on a folder. |
| Operation | The operation to perform on the resource |
| List | Choose this operation to fetch a list of files or folders |
| Create | Choose this option to create a folder on Google Drive. |
| Upload | Choose this operation to upload a file to Google Drive. The maximum file size allowed for uploading via the node is 100 MB. |
| Download | Choose this option to download a file from Google Drive. The maximum file size allowed for downloading via the node is 100 MB. |
| Delete | Choose this option to delete an existing file or folder from Google Drive. |
| Copy | Choose this option to create a copy of an existing file on Google Drive. |
| Shared Drive | Specify this option if you want to include items from a shared drive in fetching a list of files or folders. This option automatically enables if your Google Drive has shared folders or files. |
| Name | Specify the name of the files or folders for the selected operation. This is an optional field and can be left empty if all the files or folders need to be fetched. For example, *ListOfUsers.txt*. |
| Parent | Specify the parent folder ID that will contain the file or folder as selected. This ID can be fetched from the URL, for example, *1Trgc6ngFyKGSkgCRzXHG2KJfykx7EeR7LQQc* is an ID of a file. |
| File/Folder Id | Specify the ID of the file or folder as selected as per the operation performed. This ID can be fetched from the URL, for example, *1Trgc6ngFyKGSkgCRzXHG2KJfykx7EeR7LQQc* is an ID of a file. |
| Property Name | Specify the name of the property to which the data is written for the selected file. |
