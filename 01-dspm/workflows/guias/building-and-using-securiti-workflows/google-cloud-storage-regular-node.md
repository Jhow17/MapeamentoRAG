---
title: "Google Cloud Storage"
slug: "google-cloud-storage-regular-node"
updated: 2026-01-12T08:28:33Z
published: 2026-01-12T08:28:33Z
canonical: "helpcenter.securiti.ai/google-cloud-storage-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Google Cloud Storage

A Google Cloud Storage (GCS) node in a Workflow Automation platform allows you to interact with your GCS buckets and the files within them. The following actions can be performed using the Google Cloud Storage node:

- Download objects from a Google cloud storage bucket for further processing within the workflow.
- Upload objects to a designated bucket in your Google Cloud Storage project.
- Fetch a list of objects (files and folders) within a specified bucket or prefix.

Refer to the [Node configurations section](/v1/docs/gencoreai-configuring-private-cloud-storage-on-google-cloud-storage) to understand the node working and properties.

#### Prerequisites

You must configure the Google cloud storage node with the necessary credentials to access your GCS buckets. See the [setting up credentials section](/v1/docs/gencoreai-configuring-private-cloud-storage-on-google-cloud-storage).

#### Example use case

As an example, let’s create a workflow that automates the process of listing consent data from a specific date, converting it to JSON format, and uploading it to a designated Google Cloud Storage (GCS) bucket.

The workflow starts with a **Consent Management node** that lists all the consents from the specified date. This data is then moved to the **Move Binary Data** node to convert the data into the JSON format as Google cloud storage can only have a file uploaded to it. And finally, use the Google Cloud Storage node to upload the generated JSON data to your designated bucket. The connector allows you to specify the bucket name, object name (filename), and the property. This eliminates the need for manual data extraction and upload, saving time and reducing errors.

The following nodes are used in this workflow:

- [Consent Management Node](/v1/docs/consent)
- [Move Binary Data Node](/v1/docs/move-binary-data)
- Google Cloud Storage Node

#### Centralizing consent data in Google Cloud Storage

1. Add the Consent management node to start the workflow. Set the operation type to List to fetch the data of the consent records.
2. Add Move Binary Data node to convert the binary data into JSON format.
3. Add Google Cloud Storage node and specify the necessary details such as the bucket name and the file name that is to be uploaded on GCS.

![Screenshot_2024-03-18_at_11_36_12_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3b5c71af-5e9f-bebe-2cc0-17b717e477ed.png)
4. Connect the nodes and execute the workflow.

![Screenshot_2024-03-18_at_11_35_50_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7355cfe3-5cdf-6029-35a5-ef6851dce4b6.png)
5. Once the workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters | Description |
| --- | --- |
| Google Cloud Storage | Create a new account in Google Cloud Storage. Refer to the [setting up credentials section](/v1/docs/configuring-private-cloud-storage-on-google-cloud-storage) to understand how to set up the account. |
| Bucket Name | Specify the bucket name. |
| Operation | Specify the operation to perform. |
| List | Choose this option to get a list of the objects. |
| Upload | Choose this operation to upload an object to Google Cloud Storage |
| Download | Choose this operation to download an object from Google Cloud Storage |
| Prefix | Specify the prefix of the object. |
| Delimiter | Use the delimiter argument to restrict the results to only the **files** in the given **folder**. The entire tree under the prefix is returned without the delimiter. |
| Object Name | Specify the name of the object. |
| Property Name | Specify the name of the binary property to which to write the data of the read file. |

#### Setting up credentials

Use the following credentials to set up credentials for Google Cloud Storage.

| Parameters | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself. |
| Project ID | Specify the project name for Google cloud storage, for example, sdi-scans. |
| Service Account | Specify the complete JSON from the service account’s key file’s JSON. |
