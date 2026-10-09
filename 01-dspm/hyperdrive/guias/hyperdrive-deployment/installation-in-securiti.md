---
title: "Installation of Hybrid Outpost"
slug: "installation-in-securiti"
description: "Learn how to configure and install Hybrid Outpost in Securiti and AWS with our step-by-step guide and demo video for seamless deployment."
updated: 2026-09-28T13:08:36Z
published: 2026-09-28T13:08:36Z
canonical: "helpcenter.securiti.ai/installation-in-securiti"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Installation of Hybrid Outpost

The Hybrid Outpost deployment proceeds with the following flow:

- Configuring Outpost in Securiti
- Installing Outpost in AWS

### Configuring Outpost in Securiti

You can watch the following demo video to understand the installation process for Outpost in Securiti:

[Embedded content](https://app.storylane.io/demo/c1ddozwtsx5v?embed=inline)

To install the Hybrid Outpost, proceed with the following main steps below:

#### 1. Accessing Hybrid Outpost page

To access the Hybrid Outpost page for installation, proceed with the following steps.

1. In Securiti, from the upper left corner of the navigation bar, click the **Jewel** icon.
2. From the Platform Services section, click **Settings** > **Deployment** > Securiti **Outpost**.
3. Near the top right corner of the Securiti **Outpost** page, click **+ New Outpost**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/outpost-installation-image-g79ryczt.png)

It opens the **New Outpost** popup where you install the Hybrid Outpost.

#### 2. Adding description of Hybrid Outpost

On the **New Outpost** popup, configure the following parameters for describing your Hybrid Outpost:

| Parameters | Description |
| --- | --- |
| Instance Name | Enter a unique name for this specific Hybrid Outpost deployment. For example, `Outpost-tenant12345-OutpostID12345`. |
| Description | Enter the description for your Hybrid Outpost deployment. |
| Primary Owner | Select the email of the primary owner or admin from the menu. The primary owner receives all the emails regarding all the updates on that specific Outpost deployment. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VI0AALU6.png)

#### 3. Configuring updating setting

You can configure your Hybrid deployment to automatically update whenever

Your Hybrid deployment receives two kinds of updates, and the **Enable Auto-update** checkbox setting controls only one of them. The two updates are:

- Hybrid Outpost application update
- Hybrid Outpost infrastructure update

The Enable Auto-update check manages the application updates for Hybrid Outpost.

- If you mark the checkbox, Securiti installs every new application release in your Hybrid deployment as it becomes available. It requires no action from your side.
- If you leave the checkbox, you must check for new releases and apply each one yourself. For more information, see [Upgrading Hybrid deployment with Outpost](/latest/docs/upgrading-hybrid-deployment-with-outpost#upgrade).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-I9OZMH9Z.png)

The primary owner you selected in the previous step receives an email for every update to this deployment. Infrastructure-level upgrades are always manual, whether or not you check Enable Auto-update. To apply one, you must download a new template and update your CloudFormation stack with it. For more information, see [Upgrading Hybrid deployment with Outpost](/latest/docs/upgrading-hybrid-deployment-with-outpost#upgrading-hybrid-outpost-deployment).

#### 4. Configuring Advanced Settings

The **Advanced Settings** section lets you control how your Hybrid deployment connects to your network and how it creates IAM roles which it uses. Every setting has a default selection, so you can skip this section and deploy with the defaults.

**Advanced Settings** contains the following three categories of settings:

| Setting | Description |
| --- | --- |
| Privilege Analysis Configuration | It determines how the data scanning nodes reach the internet, and the source IP address their outbound requests carry. The default is Single Static Elastic IP (EIP). |
| Network Infrastructure Strategy | It lets you place the Hybrid deployment in a VPC and subnets that your organization already manages, instead of letting the CloudFormation template provision a new network. By default, the template provisions a new network. |
| IAM Provisioning Strategy | It determines who creates the IAM roles that the Hybrid deployment requires: - CloudFormation template - your own IAM team. The default is Fully Automated. |

You must select these settings before you download the template. Each one determines how the CloudFormation template builds your deployment, so changing it later requires a CloudFormation stack update.

If you select any other value than the default, you must proceed to [Advanced Settings of Hybrid deployment with Outpost - AWS](/latest/docs/advance-settings-of-hybrid-outpost-aws) first.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KJOYUNV8.png)

#### 5. Selecting cloud region

In the **Deployment** area, you can only select your cloud region. It has the following visible fields out of which you can only modify **Region** parameter.

| Parameters | Description |
| --- | --- |
| Cloud Provider | Continue with **Amazon Web Services** as the Cloud Provider, Securiti automatically selects it as the only supported option. |
| External ID | Securiti automatically generates the External ID, an identifier required to assume external roles in your AWS account. |
| Region | Select the region from the menu where you intend to deploy the CloudFormation stack. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0RXM0P1E.png)

#### Downloading installation template

Once you have added the details, click **Prepare & Download Template.** This generates the CloudFormation template and downloads it in your local storage

Once you have downloaded the template, you can provision your AWS infrastructure with this template using one of the following methods:

- [Installing Outpost through AWS console using CloudFormation service](/latest/docs/installation-in-securiti#installing-outpost-through-aws-console-using-cloudformation-service1)
- [Installing Outpost through AWS CLI](/latest/docs/installation-in-securiti#installing-outpost-in-aws-through-cloudformation-template)

### Installing Outpost through AWS console using CloudFormation service

Once the Outpost deployment template is ready, proceed with the following steps:

1. Log in to your AWS console and set your region.
2. In the search bar at the top left of the console, search **CloudFormation**. Once it appears in the results, click it.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/outpost-installation-image-097icrgs.png)

It opens the CloudFormation service page.

1. At the top right corner of the **Stacks** page, click **Create stack** and then choose **With new resources (standard)**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/outpost-installation-image-am2sxebg.png)

It opens the Create stack page.

1. In the **Create Stack** page, choose the following settings:
  1. From the **Prerequisites - Prepare template** section, select **Choose an existing template**.
  2. From the **Specify template** section, select **Upload a template file**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/outpost-installation-image-2v8qbm8a.png)

Once selected, a file upload appears.

1. At the end of the **Specify template** section, click **Choose file** and upload your Outpost template, and click **Next**.

It opens Specify stack details.

1. On the **Specify stack details** page, in **Provide a stack name** section, enter a name for your stack.

> [!NOTE]
> Note
> 
> Securiti recommends the naming convention that it must contain the following field values, so it's easier to segregate from all other processes and helpful in troubleshooting in the cloud:
> 
> - Tenant identifier
> - Outpost ID
> - UniqueSuffix

In the **Parameters** section, it displays the following parameters.

> [!WARNING]
> Important
> 
> It fetches these values from the uploaded template. Therefore, don’t update these values.

| Parameter | Description |
| --- | --- |
| S3 Bucket containing CloudFormation templates | The name of the S3 bucket provided by Securiti that holds the nested template files. |
| S3 Key Prefix for templates | The S3 folder path where the nested templates are stored. |
| Stack Name Prefix | A consistent prefix for all resources created by the stack. Do not modify. |
| Owner Email Address | Your email address for resource tagging and identification. |
| AWS Region | The specific AWS Region where you are deploying the Outpost. |
| VPC CIDR Block | The IP address range for the main Virtual Private Cloud (VPC). |
| Public Subnet CIDR | The IP address range for the public subnet (used for external access and NAT components). |
| Private Subnet CIDR | The IP address range for the private subnets (where EKS worker nodes and application pods run). |
| NAT Type | Choose the type of Network Address Translation to provide internet access to private resources. |
| NAT Instance Type | The EC2 instance type to use if `NAT Type` is set to `Instance`. |
| Securiti ECR Registry URL | The ECR registry URL for the Securiti images (used for pull-through cache setup). |
| Securiti KMS Key ARN | The ARN of the KMS key provided by Securiti for S3 encryption. |
| Securiti Image Tag | The specific version/tag of the Securiti Lambda images for deployment tasks. |
| Securiti Helm Charts Version | The specific version of the Helm charts for the application deployment. |
| Tenant ID | Your unique organization ID from the Securiti platform. |
| Outpost ID | The unique identifier for this specific Outpost instance. |
| Bootstrap Token | The JWT secret used for initial Outpost registration and authentication. |
| Application URL | The HTTPS URL of the Securiti Data Command Center platform. |
| UniqueSuffix | A short, unique string to ensure consistent naming across all stack resources. |
| EKS Cluster Version | The Kubernetes version for the EKS cluster. |
| Test Mode | Enables test configurations for easier debugging and administrative access. |
| SSO Admin Role ARN | The ARN of the SSO role granted administrator access to the EKS cluster (only if Test Mode is enabled). |
| Metadata Storage S3 Bucket Name | Name for the metadata S3 bucket. Leave empty to auto-generate. |
| Data Storage S3 Bucket Name | Name for the data storage S3 bucket. Leave empty to auto-generate. |
| Securiti Cross Account Role ARN | Comma-separated list of Securiti cloud roles that are added in your cloud, so that Outpost deployment can access the Securiti cloud resources. |
| External ID for Securiti Cloud Access | The External ID for secure cross-account access is often generated during Outpost registration. |
| Skip Outpost Deployment | Set to `true` to deploy infrastructure and EKS only, skipping the final application deployment step. |

For the details of the roles you see in this section, see [Permissions](/latest/docs/hybrid-deployment-with-outpost#local-tools)w for details on each role.

If you enable **Deploy in existing network infrastructure** setting, you must provide the data for the following parameters:

| Parameter | Description |
| --- | --- |
| Existing VPC ID | The ID of the existing VPC to deploy the Outpost into. |
| Existing Private Subnet IDs (A,B) | The IDs of the two existing private subnets, in different AZs, where EKS worker nodes and application pods run. |
| Existing Public Subnet IDs (A,B) | The IDs of the two existing public subnets, in different AZs, used for external access and NAT components. |
| Existing Private Subnet CIDRs (A,B) | The IP address ranges of the private subnets, in the same order as the Private Subnet IDs. |
| Existing Private Subnet AZs (A,B) | The Availability Zones of the private subnets, in the same order as the Private Subnet IDs. |
| Existing S3 VPC Endpoint ID | The ID of the existing Gateway-type S3 VPC endpoint associated with the private subnets' route tables. |
| Egress Public IP - AZ A | The static public IP address used for internet egress in the first Availability Zone. |
| Egress Public IP - AZ B | The static public IP address used for internet egress in the second Availability Zone. |
| NAT Gateway ID - AZ A | The ID of the existing NAT Gateway in the first Availability Zone. Optional; leave empty to skip NAT cost metrics. |
| NAT Gateway ID - AZ B | The ID of the existing NAT Gateway in the second Availability Zone. Optional; leave empty to skip NAT cost metrics. |
2. Once details are added, click **Next**. It opens the **Configure stack options** page.
3. (Optional) Apply Key tags and Permissions if required.
4. At the end of this page, under the **Capabilities** area, mark both acknowledgements. These are necessary for scalability. Once done, click **Next**.
5. On the **Review and create** page, review the details. Once the review is complete, at the end of this page, click **Submit**. This starts spinning up the cloud resources and starts deployment. Once the deployment is finished, on the Securiti Outpost page in your Securiti platform, the status row shows an **Active** status of this pod.

### Installing Outpost through AWS CLI

You can also deploy the Hybrid Outpost using AWS CLI. Once you download the CloudFormation template for Hybrid Outpost deployment, run the following command.

```bash
aws cloudformation create-stack \
--stack-name <stack-name> \
--template-body file://<path-to-downloaded-template> \
--capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM CAPABILITY_AUTO_EXPAND \
--parameters \
ParameterKey=OwnerEmail,ParameterValue=<owner-email> \
--region <aws-region>
```

It includes the following parameters:

| Parameters | Description |
| --- | --- |
| --stack-name | A unique name for the stack. Securiti recommends including the tenant identifier, Outpost ID, and a unique suffix. |
| --template-body | The local file path to the CloudFormation template downloaded from Securiti. |
| --capabilities | Grants CloudFormation permission to create IAM resources and nested stacks. All three capabilities are required. |
| --parameters ParameterKey=OwnerEmail | The email address used for resource tagging and identification. |
| --region | The AWS Region where you want to deploy the Outpost. |

If you enable **Deploy into existing network infrastructure** during the setup in Securiti, run the following command to enable the Hybrid Outpost with your existing PVC and subnets.

```bash
aws cloudformation create-stack \
--stack-name <stack-name> \
--template-body file://<path-to-downloaded-template> \
--capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM CAPABILITY_AUTO_EXPAND \
--parameters \
ParameterKey=OwnerEmail,ParameterValue=<owner-email> \
ParameterKey=VpcId,ParameterValue=<vpc-id> \
ParameterKey=PrivateSubnetIds,ParameterValue=<private-subnet-id-1>\,<private-subnet-id-2> \
ParameterKey=PublicSubnetIds,ParameterValue=<public-subnet-id-1>\,<public-subnet-id-2> \
ParameterKey=PrivateSubnetCidrs,ParameterValue=<private-cidr-1>\,<private-cidr-2> \
ParameterKey=PrivateSubnetAzs,ParameterValue=<az-1>\,<az-2> \
ParameterKey=S3VpcEndpointId,ParameterValue=<s3-endpoint-id> \
ParameterKey=NATGatewayAEIP,ParameterValue=<nat-eip-1> \
ParameterKey=NATGatewayBEIP,ParameterValue=<nat-eip-2> \
ParameterKey=NATGatewayAId,ParameterValue=<nat-gateway-id-1> \
ParameterKey=NATGatewayBId,ParameterValue=<nat-gateway-id-2> \
--region <aws-region>
```

It includes the following parameters:

| Parameter | Description |
| --- | --- |
| --stack-name | A unique name for the stack. Securiti recommends including the tenant identifier, Outpost ID, and a unique suffix. |
| --template-body | The local file path to the CloudFormation template downloaded from Securiti. |
| --capabilities | Grants CloudFormation permission to create IAM resources and nested stacks. All three capabilities are required. |
| --parameters ParameterKey=OwnerEmail | The email address used for resource tagging and identification. |
| --parameters ParameterKey=VpcId | The ID of the existing VPC to deploy the Outpost into. |
| --parameters ParameterKey=PrivateSubnetIds | The IDs of the two existing private subnets, in different AZs, where EKS worker nodes and application pods run. |
| --parameters ParameterKey=PublicSubnetIds | The IDs of the two existing public subnets, in different AZs, used for external access and NAT components. |
| --parameters ParameterKey=PrivateSubnetCidrs | The IP address ranges of the private subnets, in the same order as PrivateSubnetIds. |
| --parameters ParameterKey=PrivateSubnetAzs | The Availability Zones of the private subnets, in the same order as PrivateSubnetIds. |
| --parameters ParameterKey=S3VpcEndpointId | The ID of the existing Gateway-type S3 VPC endpoint associated with the private subnets' route tables. |
| --parameters ParameterKey=NATGatewayAEIP | The static public IP address used for internet egress in the first Availability Zone. |
| --parameters ParameterKey=NATGatewayBEIP | The static public IP address used for internet egress in the second Availability Zone. |
| --region | The AWS Region where you want to deploy the Outpost. |

## Related

- [Hybrid deployment with Outpost - AWS](/hybrid-deployment-with-outpost.md)
- [Advanced Settings of Hybrid deployment with Outpost - AWS](/advance-settings-of-hybrid-outpost-aws.md)
