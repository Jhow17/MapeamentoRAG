---
title: "AWS SNS"
slug: "aws-sns-regular-node"
updated: 2026-02-08T12:40:06Z
published: 2026-02-08T12:40:06Z
canonical: "helpcenter.securiti.ai/aws-sns-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# AWS SNS

AWS SNS (Amazon Simple Notification Service) is a cloud-based service within the Amazon Web Services suite. It's designed for mass message delivery and communication between different applications and services. It can send out notifications via various channels including SMS, email, HTTP endpoints, and even mobile push notifications.

The AWS SNS node in the Workflows module publishes a message to a topic of your choice with the set subject and message content.

#### Prerequisites

You must have valid AWS credentials set to use the node. See the [Setting up credentials section](/v1/docs/aws-sns).

#### Example use case

As an example, let’s create a use case where an AWS SNS node publishes alerts for risk-bearing assessments in Securiti. With this workflow, the relevant teams are alerted as soon as risks are detected, minimizing the window of exposure. Additionally, as the system grows, or more vulnerabilities are monitored, SNS can handle the notification volume.

The following nodes are used in this use case:

1. Assessment Trigger Node
2. AWS SNS Node

#### Automating risk alerts via AWS SNS

1. Add the Assessment trigger node such that the node triggers every time an assessment has a response with high risk attached to it.
2. Attach the AWS SNS node to publish the message to a topic where the subscribers are the team members who are responsible for looking into the risks.

![Screenshot_2024-02-27_at_1_32_33_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-03d56d6f-a3af-aba8-a91a-c95db23791ca.png)
3. Connect and execute the workflow.

![Screenshot_2024-02-27_at_1_33_36_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fffffbd5-dca5-acfa-d2eb-bc6824b7685e.png)
4. Execute the workflow and on any event trigger, the workflow node provides a successful response. Once the workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| AWS Credentials | Choose or create credentials to access the AWS instance. Refer to the [setting up credentials section](/v1/docs/aws-sns) to understand how |
| Operation | Publish | Publish a message to a topic |
| Topic | Specify the topic you want to publish to. |
| Subject | Specify the subject when the message is delivered to email endpoints |
| Message | Specify the message you want to send |

#### Setting up credentials

To set up credentials to use the node, open your AWS Management console and choose **Security Credentials** from the menu on top right. Create a new Access key from there and collect the **Secret Access key**, **Access Key ID** and **Session Token**.

| Parameters | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself. |
| Region | Specify the region of your AWS account, for example, us-west. |
| Secret Access Key | Specify the Secret access key, selected from your AWS account. |
| Access Key ID | Specify the Access Key ID, selected from your AWS account. For example, *AKIASLVL6RD3RSJZBERS*. |
| Session Token | Specify the session token for your AWS account. This is an optional field. |
| Nodes with access | Add the nodes who can access using the credentials and mark the checkbox to select them. |
