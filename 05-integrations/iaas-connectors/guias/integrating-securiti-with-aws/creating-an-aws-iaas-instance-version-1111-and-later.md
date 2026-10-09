---
title: "Creating an AWS IaaS instance (version 1.111 and later)"
slug: "creating-an-aws-iaas-instance-version-1111-and-later"
status: "update"
updated: 2026-07-15T06:25:45Z
published: 2026-07-15T06:25:46Z
canonical: "helpcenter.securiti.ai/creating-an-aws-iaas-instance-version-1111-and-later"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Creating an AWS IaaS instance (version 1.111 and later)

> [!NOTE]
> **Important**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

Creating an AWS IaaS instance is essential for enabling automated discovery, classification, and protection of data across your cloud environment. By setting up and activating the instance, you ensure that Securiti has the necessary permissions to monitor, manage the security posture, and apply privacy controls to the data within your AWS infrastructure.

### Prerequisites

The user account or credentials used to deploy the AWS CloudFormation stack must have Admin Role privileges. The user who is provisioning the stack must have the following privileges:

- You must have **Admin Role** privileges to deploy the AWS CloudFormation stack.
- Additionally, you must have the following access privileges to provision the stack:
  - Full CloudFormation Access
  - Full IAM Role Access
- In case of **My Cloud**, ensure you have pod roles deployed before onboarding the connector.
- You have the subscription to the following module to enable the scanning features they support:

| Purpose | Module Requires |
| --- | --- |
| Pod Activation | [System Settings](/v1/docs/getting-started-with-system-settings) |
| Sensitive Data Scan | [Sensitive Data Intelligence](/v1/docs/using-sensitive-data-intelligence) |
| Posture Scan & Auto-remediation | [Security Posture Management](/v1/docs/using-security-posture-management) |
| Dark Asset Discovery for VM Snapshots | [Data Mapping Automation](/v1/docs/using-data-mapping-automation) |
| Access Entitlement Scan | [Data Access Governance](/v1/docs/data-access-governance-dag-overview) |
| Content Classification | [Sensitive Data Intelligence](/v1/docs/using-sensitive-data-intelligence) |
| Visualize Scan Results | 1. [Graph Explorer](/v1/docs/using-graph-explorer) 2. [Data Command Graph](/v1/docs/using-data-command-graph) 3. [Inventory](/v1/docs/data-access-governance-data-command-center-rbac-permissions-and-roles) 4. [Reporting](/v1/docs/using-graph-reporting-dashboards) |

> [!NOTE]
> **Note**
> 
> If these modules are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether these are included in your plan and whether your tenant meets the eligibility requirements for thier activation.

#### Prerequisites for My Cloud

Securiti scanning from **My Cloud** feature lets you scan your data in assets on your infrastructure through automatic pod deployment. You just provide Securiti with the permissions required for pod deployment to scan your data. This deployment process ensures seamless integration with your on-premises or private data systems.

To enable My Cloud feature effectively you must set up the following baseline infrastructure:

- Virtual Private Cloud (VPC)
- Subnets
- Network Address Translation (NAT)
- Key Management Service (KMS) Key
- EC2 Security Group, Amazon Machine Image (AMI), and PEM Key

> [!NOTE]
> **Note**
> 
> This is a one-time infrastructure configuration. It is used across several connectors for launching pods to scan resources.

Securiti uses a specific secret within each AWS region that specifies parameters for system pod launch to scan resources.

> [!NOTE]
> **Important**
> 
> This secret must have the following name **/securiti/pod/baseline-infra** and it contains the following parameters as a JSON object.

```json
{
                                "EC2_AMI_ID": "ami-02b92c281a4d3dc79",
                                "EC2_IAM_ROLE": "SECURITI_POD_ROLE",
                                "EC2_INSTANCE_TYPE": "m5.4xlarge",
                                "EC2_SUBNET": "subnet-05b10af0dfc2d805d",
                                "EC2_PEM_KEY": "securiti-baseline-infra-key",
                                "EBS_KMS_KEY_ID": "d4600874-1785-45cf-9a6d-b4b1bb541629",
                                "EC2_SECURITY_GROUP": "sg-03c05a522f15ab2c8",
                                "DRIVER_S3_LOCATION": "s3://securiti-prod-baseline-infra-artifacts/securiti/pod/drivers/",
                                "VPC_ID": "vpc-065db88b688dd9a8e"
                                }
```

### 

### Step-by-step instructions

1. In Securiti, select the jewel icon and choose **Integrations** from the left navigation bar.
2. On the **Integrations** page, navigate to **IaaS Connectors**.
3. To create a new instance, click **Add IaaS Connectors** in the top-right corner of the page, and then select **Amazon Web Services**.
4. On the **Amazon Web Services** configurations page provide the following information:

| Section | Parameter | Description |
| --- | --- | --- |
| General Information | Configuration Name | Enter a unique name to identify the instance. For example: aws-s3-data. |
| Primary Owner | Select the Primary owner of the instance responsible for managing the instance. By default the instance creator is set as the primary owner. You can also select the primary owner from the menu. |
| Notify Owners of Discovery Activity | Select this checkbox to send automated email notifications to owners after asset discovery completes. The notification highlights newly discovered assets and includes a link to the Graph for detailed analysis. > [!NOTE] > Note > > - Email notifications are sent only when asset discovery identifies new assets. > - To trigger the email notifications, it is necessary to reschedule and run asset discovery again. > - To enable this feature for existing instances, navigate to the **Instance Setup tab > Advanced Settings > Notify all owners by email when asset discovery is complete**. > - If the feature was enabled during the connector onboarding, you can disable it from the same tab if you no longer wish to receive email notifications. |
| Choose Onboarding Scope | Account | Choose this option to scan a single AWS account by providing its account number. This is suitable for isolated environments or specific account audits. Enter your 12-digit AWS account number. For example: 045712345678. > [!NOTE] > Note > > You can find the account number on the AWS Console page, click on the user information on the top right to find your [account ID](https://docs.aws.amazon.com/accounts/latest/reference/manage-acct-identifiers.html#FindAccountId). |
| Organization Unit | Choose this option to scan all accounts within a specific AWS Organization Unit (OU). Enter the **Master Account ID** and **Organization Unit ID**. For example: r-ex4mple123. To add multiple OUs, click **+ Add Organization Unit**. To include or exclude specific accounts on the basis of tags, click **Add Tag Based Filtering**. > [!NOTE] > Note > > - Securiti discovers AWS accounts within nested organization units. Discovery is not limited to accounts directly under the selected parent organization unit. The platform identifies accounts across the entire organization unit hierarchy. > - In case of Organization and Organization Unit, users can reinitiate asset discovery by clicking **Discover Org Accounts** in the options for a selected connector on the IaaS cloud connector listing. > > The **Discover Org Accounts** option is available only if: > - The AWS instance scope is set to Organization or Organization Unit at the time of creation > - The instance is activated |
| Organization | Choose this option to scan all accounts across your entire AWS organization. Provide the **Master Account ID** and **Organization Root ID**. To include or exclude specific accounts on the basis of tags, click **Add Tag Based Filtering**. |
| Advanced Configuration | Asset Discovery | With this option find, identify, and catalog all assets such as virtual machines, databases, storage buckets, and other cloud resources in your environment. > [!NOTE] > Note > > This option is selected by default. |
| Posture Management | Mark this checkbox to configure your AWS account for security vulnerabilities and identify misconfigurations including access controls, network settings, encryption protocols, and compliance violations. |
| Security Posture Auto-remediation | Mark this checkbox to grant Securiti permissions to auto-remediate posture findings. > [!NOTE] > Note > > You can select this checkbox only after selecting the **Posture Management** checkbox. |
| Discover package on VM snapshots | Mark this checkbox to automatically discover dark assets in your AWS account, scan disks of compute instances, and find installed packages and associated vulnerabilities. To include or exclude specific accounts on the basis of tags, click **Add Tag Based Filtering**. > [!NOTE] > Note > > Enabling this option will automatically deploy a pod in selected deployment location. |
| Sensitive Data Discovery | Mark this checkbox to have Securiti look for specific data elements distributed across different locations, and data systems, on specific schedules and owners. To include or exclude specific accounts on the basis of tags, click **Add Tag Based Filtering**. > [!NOTE] > **Note** > > - Currently, the sensitive data scan scans only public S3 buckets, tagged private S3 buckets, and tagged disks. If no tags are provided, the system only scans public S3 buckets. > - Public S3 buckets are scanned regardless of inclusion or exclusion tags, and scans by default process up to 1,000 files. > - Enabling this option will automatically deploy a pod in selected deployment location. > - If the **Securiti Cloud** is selected, the pod will be deployed in Securiti Hosted account. > - If **My Cloud** is selected, this pod will be automatically deployed on the customer's account (cloud environment). |
| Access Entitlement Discovery | Mark this checkbox to gain intelligence into the users and roles with access to resources and sensitive data in AWS datasets and define controls to limit access to sensitive data. > [!NOTE] > **Note** > > Access Entitlement Scan only supports AWS S3 Buckets and AWS Bedrock Models. For more information about the cloud services for which access entitlement scan is supported, see [List of Supported Cloud Services](/latest/docs/data-security-posture-management-solution#list-of-supported-cloud-native-services). |
| Configure Periodic Discovery | Enable periodic asset discovery and security posture discovery | Select this checkbox to define the period to discover cloud assets and detect security posture misconfigurations automatically. For example, Hourly, Daily, Weekly, Monthly. Click **+ Add Exclusion** if you wish to pause discovery for a certain time period. |
| Choose Deployment Method | Securiti Cloud | Securiti manages the complete discovery infrastructure in our secure cloud environment. No setup is required when choosing this option. You can simply configure your discovery targets and Securiti handles pod deployment, maintenance, and scaling automatically. For more information on when to choose this option, see [Securiti Cloud](/v1/docs/getting-started-with-iaas-cloud). |
| My Cloud Deployment | Deploy Securiti pods directly in your AWS environment for maximum control and data locality. With this option, you maintain full ownership of the discovery infrastructure while Securiti provides the discovery capabilities. For detailed information on when to choose this option, see [My Cloud](/v1/docs/getting-started-with-iaas-cloud). |
| Use Existing Pod | With this option leverage your already deployed Securiti Pods for cross-account discovery. Map your existing pods to discover regions and configure trust relationships to enable discovery across multiple AWS accounts. > [!NOTE] > Note > > - Ensure that the selected pods comply with data residency requirements and do not result in cross-border data transfer violations. > - The regions and pod configurations selected during onboarding cannot be edited later. > - This method currently does not support discovery of dark assets. This means that while onboarding if you choose **Use Existing Pods** as your deployment method then the **Discover package on VM snapshots** option will automatically be disabled. |
| My Cloud Configuration | Enter your 12 digit [AWS Account ID](https://docs.aws.amazon.com/accounts/latest/reference/manage-acct-identifiers.html#FindAccountId) to let Securiti deploy pod on your cloud infrastructure. configure your pod deployment account and download the necessary policy. > [!NOTE] > Note > > This option is visible only when you choose **My Cloud** as your deployment method. |
| Prepare CloudFormation Template | Click **Prepare Template** and then click **Download Template** to download the necessary policy**.** > [!NOTE] > Note > > - This CloudFormation template streamlines onboarding your AWS account to Securiti SaaS by provisioning essential resources, configuring IAM roles, VPC networks and enabling required AWS services. > - This option is visible only when you choose **My Cloud** as your deployment method. |
| Data Discovery Region Scope | Select the region(s) to deploy the pod in for scanning purposes. > [!NOTE] > Note > > - Regions specified are for data discovery purposes only. Asset discovery operates independently of selected regions. Choose regions where your sensitive data is located. |
| Pods Configuration by Region | Specify an existing pod from the list to use for data discovery in the specified region(s). The pod must be active and accessible. Enter the IAM role name that the pod will assume. The name must follow AWS role naming conventions; it must be alphanumeric and can include only letters, numbers, hyphens, and underscores. Lastly, enter the 12-digit [AWS account number](https://docs.aws.amazon.com/accounts/latest/reference/manage-acct-identifiers.html#FindAccountId) where the IAM role is located. > [!NOTE] > Note > > - You can use the same pod for multiple regions. > - Ensure that the selected pods comply with data residency requirements and do not result in cross-border data transfer violations. > - The regions and pod configurations selected during onboarding cannot be edited later. > - This option is visible only when you choose **Use Existing Pod** as your deployment method. |
| View Policy | After you specify the above entities you can view the IAM policy and attach it to the IAM role associated with each selected pod instance. This policy grants necessary permissions for discovery. |
| Deployment Identifiers | External Id | The **External Id** is an identifier auto-generated by Securiti for assuming external roles in your AWS account. This value is not modifiable and is shown for informational purposes. |
| Execution Id | The **Execution Id** is a role suffix auto-generated by Securiti to be added to the roles and policies provisioned by the Securiti cloud in your AWS account. This value is not modifiable and is shown for informational purposes. > [!NOTE] > Note > > - The **Execution Id** and **External Id** help you search for resources deployed via CloudFormation (CF) templates in the AWS Console. You can use these Ids to locate and review resources created during onboarding. > - You can reuse **Execution ID** and **External ID** without redeploying the CF template. This eliminates the need to repeatedly redeploy roles and permissions via the AWS console. > - For instance, if you deactivate a connector and onboard a new one for the same AWS account, you can reuse the Execution ID and External ID to activate the connector by saving the configuration without redeploying the CF template. > - If you have already deployed the CF template in the AWS Console and want to enable additional settings that require new permissions, you must either: Replace the existing template, or manually configure the necessary roles and permissions. |
| Deployment | Click Through | Select this option to have Securiti redirect you to your AWS console, where AWS prompts you to log in if you are not already authenticated. On the **CloudFormation Stack** creation page, leave all the prefilled values as-is, mark the **Acknowledge** checkbox, and click **Create Stack**. |
| Download Template | Select this option to download a copy of the CloudFormation template in YAML format before deploying. Review all the resources that are provisioned and all the required permissions. The required permissions are dependent upon the options selected in the **Advanced Configurations** section. Click **Prepare Template** and then click **Download Template**. |
5. Click **Authorize Account.** This automatically prepares the required template to launch the stack on your AWS account.
6. Click **Go To AWS Management Console.** Securiti redirects you to your AWS console, where AWS prompts you to log in if you are not already authenticated.
7. At the CloudFormation Stack creation page, review all the role parameters, scan parameters, and permissions. Mark the "acknowledge" checkbox, and click **Create Stack.**

> [!NOTE]
> **Note**
> 
> - Please do not modify pre-populated fields as it may cause the stack deployment to fail or may cause subsequent discovery and/or scan operations to fail.
> - During Organization or Organization Unit onboarding, Securiti performs a discovery routine every 30 minutes to detect newly created or deleted accounts. The provided stackset ensures automatic deployment for new accounts. However, the StackSet template includes a signed URL (valid for 7 days). Customers must download this template, upload it to their own bucket, and update the URL in the stackset. This ensures that organization account discovery and stackset deployment continue to work even after 7 days, allowing member roles to be created in newly discovered accounts.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(208).png)
8. On the Securiti Platform, click **Save Configuration**. After the stack deploys, Securiti automatically starts asset discovery and populates the overview dashboard with the scanned results.

Securiti sends automated email notifications upon completing an asset discovery scan. These notifications highlight changes detected in the latest scan, identify newly discovered assets, and include a link to the Graph for detailed analysis.

To view the logs, you can click the created instance and click the **Audit Trail** tab.

> [!NOTE]
> Note
> 
> To see the above process in action, see [interactive demo](/latest/docs/interactive-demos-enabling-dspm-for-aws#demo-1-connect-your-aws-iaas-cloud-with) on how to connect your AWS IaaS cloud with Securiti.

### List of supported AWS assets enabled for data and disk scans

While securiti supports scanning on a wide range of AWS assets, however, the automatic instance activation and discovery scans are currently supported only for S3 buckets.

To see the full list of supported AWS services, visit [Supported AWS Cloud Native Services](/latest/docs/data-security-posture-management-solution#supported-aws-cloud-native-services).

###

## Related

- [Performing Actions Post AWS Instance Creation](/performing-actions-post-aws-instance-creation.md)
- [Visualizing Results of Asset Discovery in Graph Explorer](/visualising-results-of-aws-asset-discovery-in-graph-explorer.md)
- [Deploying Pod](/deploying-pod-aws.md)
- [How it works?](/how-it-works-aws.md)
