---
title: "Performing Actions Post AWS Instance Creation"
slug: "performing-actions-post-aws-instance-creation"
updated: 2026-05-20T15:27:45Z
published: 2026-05-20T15:27:45Z
canonical: "helpcenter.securiti.ai/performing-actions-post-aws-instance-creation"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Performing Actions Post AWS Instance Creation

Once an AWS IaaS instance is created on the Securiti platform, users gain access to a variety of post-instance creation actions designed to help manage and secure their cloud environment. These actions enable users to edit configurations, delete instances, discover organization accounts, and reinitiate asset discovery and posture scan.

> [!NOTE]
> **Note**
> 
> An automatic synchronization process runs every 30 minutes to detect accounts that have been added or deleted since the last sync. This process, specific to **Organization** and **Organization Unit** onboarding, ensures that all account data remains current; however, asset discovery is performed according to the predefined schedule or upon manual initiation.

For detailed guidance on creating an AWS IaaS instance, refer to the [Creating an AWS IaaS Instance](/v1/docs/creating-an-aws-iaas-instance-version-1111-and-later) section, which outlines the step-by-step process for setting up your instance on the Securiti platform.

To perform these post activation actions:

1. In Securiti, select the jewel icon and choose **Integrations** from the left navigation bar.
2. On the **Integrations** page, navigate to **IaaS Connectors**.
3. On the **IaaS Connectors** page, you will see a list of existing instances. Click the **More actions** icon next to an instance, or click the instance directly. A menu appears, letting you perform the following actions.

### Editing an AWS Instance

**Scenario**

As a Data Governance Officer, you need to keep AWS instance ownership and scan coverage current after a team restructure. Manually updating owner lists in docs and kicking off separate console scans one by one risks overlooking new accounts and misconfigurations. With Securiti’s post-instance actions, you update co-owners and re-trigger discovery and posture scans in seconds. You eliminate blind spots and stay audit-ready with complete, real-time visibility.

### 

#### Basic Information

In the **Basic Information** tab, under the **Owners** section you can add co-owners by clicking the **+Add co-owner** button.

> [!NOTE]
> **Note**
> 
> Asset discovery email notifications are also sent to co-owners, providing insights into discovered assets. For more information, see [Asset Discovery](/v1/docs/data-security-posture-management-solution).

#### Instance Setup

In the **Instance Setup** tab, under the **Accounts** section you can add new accounts.

> [!NOTE]
> **Note**
> 
> This option is available if the AWS instance scope is set to Account at creation and the instance is activated.

Under the **Accounts** sections, you can selectively reinitiate Asset Discovery and Posture Scan on specific accounts. After an instance is created and the initial scan is complete, select your desired accounts and click the **Initiate Scan** button. This action triggers asset discovery and posture scanning for all selected entities.

> [!NOTE]
> **Note**
> 
> - This feature is supported:
>   - Only for Asset Discovery and Posture Scan.
>   - Only for on-demand reinitiation. Scheduled Asset Discovery and Posture Scan will continue to run automatically for all accounts.
>   - Only for accounts where both the Asset Discovery and Posture Scan are in a **Completed** or **Failed** state. If either scan is in **In Progress** or **Scheduled** state, the option will be disabled.
> - To support this feature, checkboxes are now designated for selecting accounts when reinitiating scans. Account linking is now managed through toggle buttons; disabling an account prevents it from being included in future checks and scans.

Under the **Scan Location** section, you can edit the region for data scan.

Under the **Advanced Settings** section, you can choose to run the following scans;

- Detect Security Posture Misconfigurations
- Activate Security Posture Auto-remediation
- Access Entitlements Scan

> [!NOTE]
> **Important**
> 
> If you selected Account as the scope during onboarding, it is recommended to execute the CloudFormation template via the CLI to avoid manual configuration steps when updating the stack after editing the connector settings. If you choose to use the AWS Console instead, ensure that the modified settings are enabled and the required permissions are added in the CloudFormation stack. For more information, see [Updating CloudFormation Template](/latest/docs/understanding-cf-templates-for-stack-deployment#updating-cloudformation-template).

After selecting your desired scans, make sure to save the configuration, then execute the CloudFormation template to apply your changes.

> [!NOTE]
> **Note**
> 
> - This enhancement applies to all scope types: Organization, Organization Unit, and Account.
> - Advanced Settings cannot be modified while new accounts are being added. You need to complete the addition of new accounts before making changes to these settings.
> - New accounts cannot be added while advanced settings have been modified but not yet applied. Save and execute the CloudFormation template for your advanced settings changes before adding new accounts.
> - Once scan settings are enabled, you cannot disable them. Currently, the platform only lets you enable scan settings.
> - Advanced settings can be modified only through the Download Template deployment type, regardless of the deployment method used during onboarding. However, when you add a new member account, both Clickthrough and Download Template deployment options become available.
> - After saving the configuration, asset discovery will reinitiate automatically.
> - You cannot enable Discover Packages on VM snapshots and Detect for Sensitive Data settings during instance edits. Currently, the scans run only once during the initial asset discovery process.

You can also modify the period to discover cloud assets and detect security posture misconfigurations, and enable/disable email notifications.

You can choose to deactivate your instance by selecting **More options** in the upper-right corner of the **Instance Setup** tab.

#### Audit Trail

The **Audit Trail** tab provides a comprehensive log of activities and events, ensuring visibility into key operations.

It records the status of the asset discovery and posture scans at every stage. This includes whether the process is scheduled, initiated, in progress, successfully completed, or has failed. These logs help identify issues and bottlenecks in the discovery process and ensure that all assets in your AWS environment are accounted for. User can also view role validation logs under this tab.

The Audit Trail also detects and logs permission-related errors encountered during asset discovery across a variety of AWS services, including:

- **Compute:** EC2, Lambda, Elastic Kubernetes
- **Storage:** S3 Storage, S3 Glacier, Elastic FileSystem
- **Databases:** DynamoDB, RDS, DocumentDB, Redshift
- **Monitoring and Logging:** CloudWatch, CloudTrail
- **Networking:** CloudFront, Network Firewall
- **Machine Learning:** SageMaker, Bedrock
- **Streaming:** Kinesis, Kafka

These logs help pinpoint configuration or access issues, enabling you to take corrective action promptly to maintain security and ensure proper operation across your AWS environment.

### Deleting an AWS Instance

**Scenario**

As a Data Security Officer, you must retire inactive instances to reduce your attack surface. Manually identifying stale instances and remembering deactivation dates is tedious and risky. In Securiti, you navigate to your AWS instance list, choose an inactive entry, and click Delete. The instance and its assets are safely removed. You maintain a lean environment and lower risk in seconds.

Select **Delete** to remove the instance. A warning message will confirm whether you're sure about the deletion.

> [!NOTE]
> **Note**
> 
> Only inactive instances can be deleted.

You can choose to deactivate your instance by selecting **More options** in the upper-right corner of the **Instance Setup** tab.

### Reinitiating Asset Discovery

**Scenario**

As a Data Security Officer, you need up-to-date asset visibility whenever accounts change. Waiting for scheduled scans takes too long and hides new resources. In Securiti, you open your AWS instance, and reinitiate asset discovery. The platform re-scans assets across your organization immediately and updates your inventory. You get fresh visibility and catch new assets within minutes.

### 

For **Organization** or **Organization Unit** instances, choose **Discover Org Accounts** to reinitiate asset discovery.

> [!NOTE]
> **Note**
> 
> This option is available if the AWS instance scope is set to **Organization** or **Organization Unit** at creation and the instance is activated.

### Reinitiating DSPM

**Scenario**

As a Data Compliance Officer, you must refresh your organization’s security posture after policy updates. Waiting for the next DSPM schedule leaves gaps and delays compliance checks. In Securiti, you open your AWS instance, select Reinitiate DSPM, and confirm. The platform reruns asset discovery and posture scans together, remediates misconfigurations, and links findings. You secure compliance and close gaps in minutes.

### 

Select **Reinitiate DSPM** to reinitiate both asset discovery and the detection of data security posture misconfigurations.

> [!NOTE]
> **Note**
> 
> - If the **Data Security Posture Misconfigurations** checkbox wasn't selected when configuring your AWS instance, only asset discovery runs on your activated instance.
> - Securiti has coupled both the functions (asset discovery and detection of data security posture misconfigurations) because the platform generates Security Posture Findings from detect security posture misconfigurations feature, previously known as posture scan, which has relationships with assets coming from asset discovery. Hence, all assets must be pre-populated before their findings are generated and linked.

### Initiating Access Scan

**Scenario**

As a Data Privacy Officer, you need to audit who can access sensitive S3 buckets before data-sharing initiatives. Manually mapping user permissions across buckets is slow and error-prone. In Securiti, you open your AWS instance, select Initiate Access Scan, and run the check. The platform identifies users with access and flags buckets holding sensitive data. You get a clear access report and reduce privacy risk in minutes.

### 

Select **Initiate access scan** to identify and report which AWS users have access to S3 buckets, along with their specific permissions.

Additionally, it identifies and reports which AWS users have access to S3 buckets containing files with sensitive data.

## Related

- [Creating an AWS IaaS instance (version 1.111 and later)](/creating-an-aws-iaas-instance-version-1111-and-later.md)
- [Creating an AWS IaaS instance (version 1.110 and earlier)](/creating-an-aws-iaas-instance-version-1110-and-earlier.md)
