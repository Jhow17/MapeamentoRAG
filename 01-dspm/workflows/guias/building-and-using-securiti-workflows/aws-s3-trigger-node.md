---
title: "AWS S3"
slug: "aws-s3-trigger-node"
updated: 2025-10-30T19:10:19Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/aws-s3-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# AWS S3

An AWS S3 node within a workflows module allows you to interact with your Amazon Simple Storage Service (S3) buckets directly within your workflows. The AWS S3 trigger node establishes a connection to a designated Amazon S3 bucket and monitors it for any updates on the specified interval. You define the following items to configure the node:

- The authentication type to establish the connection with the Amazon S3 bucket.
- The AWS S3 bucket to be monitored along with the prefix i.e. the folder path.
- The polling interval i.e. how frequently to check the AWS S3 bucket (e.g., every 5 minutes).

Refer to the [Node configurations section](/v1/docs/aws-s3) to understand the node working and properties.

#### Prerequisites

You must have valid AWS credentials set to use the node. See the [Setting up credentials for Key Based authentication](/v1/docs/aws-s3) section.

#### Example use case

As an example, lets create a Workflow that demonstrates how an AWS S3 node can integrate with Slack to provide real-time updates on changes within an S3 bucket. An AWS S3 node, configured to monitor a specific S3 bucket (or a designated folder within it), acts as the trigger for the Workflow. The node is triggered periodically for example after every 5 hours. The **Slack node** then connects to the Workflow to send the updates to the relevant team.

The following Nodes are used in this Workflow:

1. AWS S3 Trigger node
2. [Slack Node](/v1/docs/slack)

#### Getting alerts based on the updates in files

1. Add the AWS S3 node and set the configurations as shown below. Note that the polling interval is the time after which the node checks the specified file for any updates.

![Screenshot_2024-03-19_at_4_35_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc0cfeb9-724d-5ab9-d6a9-dcdef8f8d141.png)
2. Add Slack node to notify the relevant people every time the node is triggered. In this case a message is sent to a channel, notifying the users that a file has been accessed or modified.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-03-19_at_4_35_20_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-372fdab4-e321-3b08-57df-baf66f16f4f4.png)
4. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| AWS credentials | Choose or create credentials to access the AWS instance. Please refer to the [Setting up credentials for Key Based authentication](/v1/docs/aws-s3) section. |
| IAM Role Based Credentials | Choose or create an IAM role to grant the AWS S3 node access to AWS resources. Please refer to [Setting up credentials for IAM Role Based authentication](/v1/docs/aws-s3) section. > [!NOTE] > **Note** > > IAM Role Based authentication is currently supported only on Securiti AWS cloud. |
| Bucket | Specify the name of the S3 bucket on which to operate. |
| Prefix | Specify the path for object location that is to be monitored. |
| Polling Interval | Specify the Polling interval value. |
| Unit | Specify the polling interval units. |

#### Setting up credentials for Key Based authentication

To set up credentials to use the node, open your AWS Management console and choose **Security Credentials** from the menu on top right. Create a new Access key from there and collect the **Secret Access key**, **Access Key ID** and **Session Token**.

| Parameters |
| --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself |
| Region | Specify the region of your AWS account, for example, *us-west*. |
| Secret Access Key | Specify the Secret access key, selected from your AWS account. |
| Access Key ID | Specify the Access Key ID, selected from your AWS account. For example, *AKIASLVL6RD3RSJZBERS* |
| Session Token | Specify the session token for your AWS account. This is an optional field. |
| Nodes with access | Add the Nodes who can access using the credentials and mark the checkbox to select them |

#### Setting up credentials for IAM Role Based authentication

To set up credentials to use the node, configure your S3 function to assume an IAM role that has the necessary permissions to perform required actions. Attach the IAM role to the S3 function and ensure its trust policy allows the S3 service to assume the role. When invoked, the function automatically uses the temporary security credentials associated with the IAM role—no manual key configuration is required. For more information, see [Create IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html).

| Parameters |
| --- |
| Credentials Name | Provide a valid name of the credentials. Add "Securiti" as a prefix in the credentials name. |
| Region | Specify the region of your AWS account, for example, us-west. |
| Role ARN | Specify the ARN of the IAM role that grants the S3 function the necessary permissions to execute. |
| Role Name | Enter the role name as retrieved from the AWS console. |
| Nodes with access | Add the Nodes that can access using the credentials and mark the checkbox to select them. |

> [!NOTE]
> **Note**
> 
> - Use the following format for regex: [//w+=,.@-]* with a maximum length of 64 characters. This ensures that the extracted values follow the expected pattern and remain within the allowed length limit.
> - AWS S3 functions can only be executed using IAM role based authentication if the tenant’s ID is explicitly specified as the external Id in the IAM policy.
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
> 
> - Here is a sample IAM role policy.
> 
> ```plaintext
> {
>     "Version": "2012-10-17",
>     "Statement": [
>         {
>             "Sid": "VisualEditor0" 
>             "Effect": "Allow",
>             "Action": [
>                 "s3:PutObject",
>                 "s3:GetObject",
>                 "s3:ListBucket"
>             ],
>             "Resource": "arn:aws:s3:::securiti-prod-appliance-123456789101"
>         }
>     ]
> }
> ```

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
