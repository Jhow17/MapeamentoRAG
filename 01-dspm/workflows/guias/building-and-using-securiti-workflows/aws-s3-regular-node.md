---
title: "AWS S3"
slug: "aws-s3-regular-node"
updated: 2026-01-09T00:51:09Z
published: 2026-01-09T00:51:09Z
canonical: "helpcenter.securiti.ai/aws-s3-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# AWS S3

An AWS S3 node within a workflow automation platform allows you to interact with your Amazon Simple Storage Service (S3) buckets directly within your workflows. Here are the core functionalities of an AWS S3 node:

- Uploads files from your local machine or workflow environment up to a designated S3 bucket.
- Downloads files from an S3 bucket and bring them into your workflow for further processing.
- Gets a listing of objects within a specified S3 bucket or path.

Using the S3 node within your workflow, eliminates the need for manual S3 interaction through tools like the AWS Console, saving time and reducing errors. Refer to the [Node configurations section](/v1/docs/aws-s3) to understand the node working and properties.

#### Prerequisites

You must have valid AWS credentials set to use the node. See the [Setting up credentials for Key Based authentication](/v1/docs/aws-s3) section.

#### Example use case

As an example, let’s create a workflow that automates the process of synchronizing files from Google Drive to Amazon S3, ensuring the S3 bucket always reflects the latest version of each file. The workflow starts with a **Google Drive Trigger node** that gets triggered on the specific interval, for example every hour. This node fetches the files from the specified folder.

An AWS S3 node also fetches the existing files from the designated S3 bucket. Then, a **Merge node** compares the files retrieved from Google Drive and AWS S3 and removes the duplicate files. This step ensures only new or updated files from Google Drive are processed further. An AWS S3 node configured with upload permissions then uploads the identified new or updated files from Google Drive to the designated S3 bucket and also eliminates the need of manual file transfer between data systems.

The following nodes are used in this workflow:

1. AWS S3 Node
2. [Google Drive Trigger Node](/v1/docs/google-drive)
3. [Merge Node](/v1/docs/merge)

#### Automating syncing Google Drive with S3

1. Add the Google Drive Trigger node and set the configurations such that the workflow executes everyday.
2. Add AWS S3 node to fetch a list of existing files.

![Screenshot_2024-03-19_at_4_42_04_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-562e1dc2-bf0c-52a7-692d-73f0b85744c2.png)
3. Add Merge node to both the nodes to merge the results of both the nodes and remove the duplicate files. This makes sure that only updated files are a part of the result.
4. Add AWS S3 node and set the operation type to upload to upload the new data to AWS S3.
5. Connect the nodes and execute the workflow.

![Screenshot_2024-03-19_at_4_43_05_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d505097e-778b-f6df-f301-18dadf0315fc.png)
6. Once the workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| AWS Credentials | Choose or create credentials to access the AWS instance. Refer to the [Setting up credentials for Key Based authentication](/v1/docs/aws-s3) section. |
| IAM Role Based Credentials | Choose or create an IAM role to grant the AWS S3 node access to AWS resources. Please refer to the [Setting up credentials for IAM Role Based authentication](/v1/docs/aws-s3) section. > [!NOTE] > **Note** > > IAM Role Based authentication is currently supported only on Securiti AWS cloud. |
| Operation | Upload | Choose this option to upload an object to S3. The maximum file size allowed for uploading via the node is 100 MB. |
| Download | Choose this option to download an object from S3. The maximum file size allowed for downloading via the node is 100 MB. |
| List | Choose this option to list the objects. |
| Bucket | Specify the name of the S3 bucket on which to operate. |
| Prefix | Specify the shared name prefix for the object on which to operate. |
| Object Name | Specify the name of the object on which to operate. |
| Property Name | Specify the name of the binary property to which to write the data of the read file |

#### Setting up credentials for Key Based authentication

To set up credentials to use the node, open your AWS Management console and choose **Security Credentials** from the menu on top right. Create a new Access key from there and collect the **Secret Access key**, **Access Key ID** and **Session Token**.

| Parameters | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself |
| Region | Specify the region of your AWS account, for example, us-west. |
| Secret Access Key | Specify the Secret access key, selected from your AWS account. |
| Access Key ID | Specify the Access Key ID, selected from your AWS account. For example, *AKIASLVL6RD3RSJZBERS*. |
| Session Token | Specify the session token for your AWS account. This is an optional field. |
| Nodes with access | Add the nodes who can access using the credentials and mark the checkbox to select them. |

#### Setting up credentials for IAM Role Based authentication

To set up credentials to use the node, configure your S3 function to assume an IAM role that has the necessary permissions to perform required actions. Attach the IAM role to the S3 function and ensure its trust policy allows the S3 service to assume the role. When invoked, the function automatically uses the temporary security credentials associated with the IAM role—no manual key configuration is required. For more information, see [Create IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html).

| Parameters |
| --- |
| Credentials Name | Provide a valid name of the credentials. |
| Region | Specify the region of your AWS account, for example, us-west. |
| Role ARN | Specify the ARN of the IAM role that grants the S3 function the necessary permissions to execute. |
| Role Name | Enter the role name as retrieved from the AWS console. Add "Securiti" as a prefix in the role name. |
| Nodes with access | Add the nodes that can access using the credentials and mark the checkbox to select them. |

> [!NOTE]
> **Note**
> 
> - For the role name, use the following format for regex: [//w+=,.@-]* with a maximum length of 64 characters. This ensures that the extracted values follow the expected pattern and remain within the allowed length limit.
> - AWS S3 functions can only be executed using IAM role based authentication if the tenant’s ID is explicitly specified as the external Id in the IAM policy.
> 
> ![s3-iam-role-policy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0ce0798a-f797-f887-be41-b0b3b8f8059d.png)
> - Roles for various production environments are as follows:
> 
> | Endpoint | Role |
> | --- | --- |
> | EU | `arn:aws:iam::718391394098:role/securiti-prod-eu-workflow-pod-iam-role` |
> | Jakarta | `arn:aws:iam::718391394098:role/securiti-prod-jakarta-workflow-pod-iam-role` |
> | Montreal | `arn:aws:iam::718391394098:role/securiti-prod-montreal-workflow-pod-iam-role` |
> | Mumbai | `arn:aws:iam::718391394098:role/securiti-prod-mumbai-workflow-pod-iam-role` |
> | Sydney | `arn:aws:iam::718391394098:role/securiti-prod-sydney-workflow-pod-iam-role` |
> | UAE | `arn:aws:iam::718391394098:role/securiti-prod-uae-workflow-pod-iam-role` |
> | US | `arn:aws:iam::718391394098:role/securiti-prod-workflow-pod-iam-role` |
