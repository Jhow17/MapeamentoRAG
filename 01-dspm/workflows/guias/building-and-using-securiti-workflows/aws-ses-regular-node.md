---
title: "AWS SES"
slug: "aws-ses-regular-node"
updated: 2026-01-09T06:45:05Z
published: 2026-01-09T06:45:05Z
canonical: "helpcenter.securiti.ai/aws-ses-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# AWS SES

An AWS SES (Simple Email Service) node in a workflow acts as a tool for sending emails directly through Amazon's SES service within your automated processes. The primary function of an AWS SES node in a workflow is to initiate the sending of emails. It connects to your AWS account and leverages the SES service to deliver messages.

See [Node configurations section](/v1/docs/aws-ses) to understand the node working and properties.

#### Prerequisites

You must have valid AWS credentials set to use the node. See the [Setting up credentials section.](/v1/docs/aws-ses)

#### Example use case

As an example, let’s create a use case where you want to be proactively notified when critical parts of your system or infrastructure encounter errors or downtime. There is a topic called *system_alerts* that listens to any alerts in the system and triggers the **AWS SNS trigger** node.

Add the AWS SES node to send an email with the relevant error details such as error message, timestamp etc. The AWS SES node then sends the constructed notification email to administrators, on-call teams, or relevant stakeholders. Hence, this use case provides a robust way to deliver important system health updates.

The following nodes are used in this use case:

1. [AWS SNS Trigger Node](/v1/docs/aws-sns)
2. AWS SES Node

#### Automated email notifications based on system alerts

1. Add AWS SNS trigger node and set the topic to system_alerts.
2. Add an AWS SES node and set the configurations such that the system alert message is extracted from the previous node and sent as the body of the email.

![Screenshot_2024-04-02_at_5_13_26_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2fb5b909-2cf9-e162-8b58-bc2c9669e37b.png)
3. Connect the nodes and execute the workflow.

![Screenshot_2024-04-02_at_5_14_00_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c7ef66a5-eced-1434-0808-739612cf0147.png)
4. Once the workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| AWS Credentials | Choose or create credentials to access the AWS instance |
| Operation | Send Email | Send email |
| Is Body HTML | Enable for HTML email body, disable for plain text. |
| Subject | Specify the email subject. |
| From email | Specify the address that appears in From. |
| To Addresses | Specify one or more addresses to which to send the email. |
| Additional fields | Bcc Addresses | Specify the Bcc recipients of the email. |
| Cc Addresses | Specify the Cc recipients of the email |
| Configuration Set Name | Specify the name of the configuration set to use when you send an email using SendEmail |
| Reply To Addresses | Reply-to email address(es) for the message |
| Return Path | Specify the Email address that bounces and complaints are forwarded to when feedback forwarding is enabled |
| Return Path Arn | This parameter is used only for sending authorization |
| Source Arn | This parameter is used only for sending authorization |

#### Setting up credentials

To set up credentials to use the node, open your AWS Management console and choose Security Credentials from the menu on top right. Create a new **Access key** from there and collect the **Secret Access key**, **Access Key ID** and **Session Token**.

| Parameters |
| --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself |
| Region | Specify the region of your AWS account, for example, us-west. |
| Secret Access Key | Specify the Secret access key, selected from your AWS account. |
| Access Key ID | Specify the Access Key ID, selected from your AWS account. For example, *AKIASLVL6RD3RSJZBERS* |
| Session Token | Specify the session token for your AWS account. This is an optional field. |
| Nodes with access | Add the nodes who can access using the credentials and mark the checkbox to select them |
