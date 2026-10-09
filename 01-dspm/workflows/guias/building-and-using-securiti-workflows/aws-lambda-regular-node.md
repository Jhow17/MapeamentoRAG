---
title: "AWS Lambda"
slug: "aws-lambda-regular-node"
updated: 2026-01-09T00:48:33Z
published: 2026-01-09T00:48:33Z
canonical: "helpcenter.securiti.ai/aws-lambda-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# AWS Lambda

AWS Lambda is a serverless compute service offered by Amazon Web Services (AWS) that allows developers to run code in response to events without needing to manage servers or runtime environments.

In Securiti’s Workflows module, an AWS Lambda node is used to integrate AWS Lambda functions into automated workflows. This node acts as a bridge to trigger Lambda functions and utilize their compute capabilities within a broader automated process.

Please refer to the [node configurations section](/v1/docs/aws-lambda) to understand the node working and properties.

#### Prerequisites

You must configure the node with the necessary AWS credentials to access the AWS Lambda node. Please refer to the [Setting up credentials for Key Based authentication](/v1/docs/aws-lambda) section.

#### Example use case

As an example, let’s create a workflow that gets triggered on new items uploaded on the AWS S3 bucket. You need to resize, optimize, or add watermarks to images/videos uploaded to a storage system like S3.

The workflow calls an AWS Lambda node, which contains image/video processing code.Lambda processes the file and returns the modified output that is uploaded back on a separate location, in this case Google Drive.

The following nodes are used in this use case:

1. [Amazon S3 Trigger Node](/v1/docs/aws-s3)
2. AWS Lambda Node
3. [Google Drive Node](/v1/docs/google-drive)

#### Image and video processing using AWS Lambda

1. Start the workflow with an Amazon S3 Trigger node that gets triggered on a polling interval.
2. Using the AWS Lambda node, invoke a function that optimizes the image size and add a watermark.

![AWS-Lambda.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-40b2811e-6866-6ef4-628f-9f77b64590bd.png)
3. Upload the updated image on Google Drive using the Google Drive node.
4. Connect the nodes and execute the workflow.

![Screenshot_2024-05-07_at_9_08_45_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1cf884c9-f39e-c900-0d36-a06e5b9613ad.png)
5. Once the workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| AWS Credentials | Choose or create credentials to access the AWS instance. Please refer to the [Setting up credentials for Key Based authentication](/v1/docs/aws-lambda) section. |
| IAM Role Based Credentials | Choose or create an IAM role to grant the AWS Lambda node access to AWS resources. Please refer to the [Setting up credentials for IAM Role Based authentication](/v1/docs/aws-lambda) section. > [!NOTE] > **Note** > > IAM Role Based authentication is currently supported only on Securiti AWS cloud. |
| Operation | Invoke | Invoke a function |
| Function | The function to invoke |
| Qualifier | Specify a version or alias to invoke a published version of the function |
| Invocation Type | Wait for results | Invoke the function synchronously and wait for the response |
| Continue Workflow | Invoke the function and immediately continue the Workflow |
| JSON Input | The JSON that you want to provide to your Lambda function as input |

#### Setting up credentials for Key Based authentication

To set up credentials to use the node, open your AWS Management console and choose **Security Credentials** from the menu on top right. Create a new Access key from there and collect the **Secret Access key**, **Access Key ID** and **Session Token**.

| Parameters |
| --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself |
| Region | Specify the region of your AWS account, for example, us-west. |
| Access Key ID | Specify the Access Key ID, selected from your AWS account. For example, AKIASLVL6RD3RSJZBERS |
| Secret Access Key | Specify the Secret access key, selected from your AWS account. |
| Session Token | Specify the session token for your AWS account. This is an optional field. |
| Nodes with access | Add the nodes that can access using the credentials and mark the checkbox to select them. |

#### Setting up credentials for IAM Role Based authentication

To set up credentials to use the node, configure your Lambda function to assume an IAM role that has the necessary permissions to perform required actions. Attach the IAM role to the Lambda function and ensure its trust policy allows the Lambda service to assume the role. When invoked, the function automatically uses the temporary security credentials associated with the IAM role—no manual key configuration is required. For more information, see [Create IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html).

| Parameters |
| --- |
| Credentials Name | Provide a valid name of the credentials. |
| Region | Specify the region of your AWS account, for example, us-west. |
| Role ARN | Specify the ARN of the IAM role that grants the Lambda function the necessary permissions to execute. |
| Role Name | Enter the role name as retrieved from the AWS console. Add "Securiti" as a prefix in the role name. |
| Nodes with access | Add the nodes that can access using the credentials and mark the checkbox to select them. |

> [!NOTE]
> **Note**
> 
> - For the role name, use the following format for regex: [//w+=,.@-]* with a maximum length of 64 characters. This ensures that the extracted values follow the expected pattern and remain within the allowed length limit.
> - AWS Lambda functions can only be executed using IAM role based authentication if the tenant’s ID is explicitly specified as the external Id in the IAM policy.
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
> ```json
> {
>     "Version": "2012-10-17",
>     "Statement": [
>         {
>             "Effect": "Allow",
>             "Principal": {
>                 "AWS": [
>                     "arn:aws:iam::123456789012:role/example-role-one",
>                     "arn:aws:iam::123456789012:role/example-role-two"
>                 ]
>             },
>             "Action": "sts:AssumeRole",
>             "Condition": {
>                 "StringEquals": {
>                     "sts:ExternalId": [
>                         "12345678",
>                         "abcdef12"
>                     ]
>                 }
>             }
>         }
>     ]
> }
> ```

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
