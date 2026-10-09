---
title: "Creating an AWS IaaS instance (version 1.110 and earlier)"
slug: "creating-an-aws-iaas-instance-version-1110-and-earlier"
updated: 2026-02-09T12:18:47Z
published: 2026-02-09T12:18:47Z
canonical: "helpcenter.securiti.ai/creating-an-aws-iaas-instance-version-1110-and-earlier"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Creating an AWS IaaS instance (version 1.110 and earlier)

You integrate Securiti with AWS to accomplish a wide variety of Sensitive Data Intelligence functions, including but not limited to:

- Asset discovery, including shadow assets
- Posture management and remediation
- Discovery scans

For this integration, Securiti creates the service account described in the table below:

| Name | Feature | IAM role | Permissions |
| --- | --- | --- | --- |
| Clickthrough-stack-vmd8dehl-IamUser-1AFHN8EDGLL7R | Native Asset Discovery | SECURITI_ASSET_DISCOVERY_MASTER_ROLE_*<8-HEX-CHARS>* SECURITI_ASSET_DISCOVERY_MEMBER_ROLE_*<8-HEX-CHARS>* | Security Audit (Built in AWS template) |
| Clickthrough-stack-vmd8dehl-IamRWUser-GQO4B55XPKS8 | Security Posture Scan | SECURITI_CONFIGURATION_SCAN_MASTER_ROLE_*<8-HEX-CHARS>* SECURITI_CONFIGURATION_SCAN_MEMBER_ROLE_*<8-HEX-CHARS>* | Security Audit (Built in AWS template) |

In general, the process is:

1. Activate IaaS integration using one-click activation as described in [Creating an AWS IaaS instance](/v1/docs/creating-an-aws-iaas-instance-version-1110-and-earlier).
2. Activate Securiti pods in AWS to scan specific data systems.
3. Perform discovery scans as described in [Discovery Scans](/v1/docs/discovery-scans).
4. If you want to deploy a centrally managed pod to a primary AWS account and use that pod to connect with and scan assets in multiple member AWS accounts, perform the procedure in [Activation on multiple AWS IaaS accounts](/v1/docs/creating-an-aws-iaas-instance-version-1110-and-earlier).

### AWS permissions and prerequisites

The account used to deploy the AWS CloudFormation stack requires different permissions depending on the activation method selected and the features enabled.

- If the keys/secrets option is used, the account performing activation needs read/write access to:
  - AWS::cloudformation::CreateStack
  - AWS::IAM (Identity and Access Management)::AccessKey
  - AWS::SecretsManager::Secret
  - Custom::Function
  - AWS::IAM (Identity and Access Management)::Role
  - AWS::Lambda::Function
  - AWS::IAM (Identity and Access Management)::User
  - AWS::Logs::LogGroup
- If you use the assumable IAM (Identity and Access Management) roles option, the account performing activation must have read/write access to:
  - AWS::cloudformation::CreateStack
  - AWS::IAM (Identity and Access Management)::Role
  - AWS::Lambda::Function
  - AWS::Logs::LogGroup
  - AWS::IAM (Identity and Access Management)::ManagedPolicy

You also can download a copy of the CloudFormation template in YAML format prior to deploying, and review all of the resources that are provisioned. The specific resources deployed may change depending on the features enabled during activation.

> [!NOTE]
> **Note**
> 
> If you are using the assumable IAM roles option, you must enable the AWS Security Token Service (STS) in every region where you want to discover and scan assets.
> 
> If you have not enabled STS for certain regions, perhaps because you have no assets in those regions, you may encounter error messages similar to the following one in the Audit Trail logs for the IaaS connector:
> 
> ```plaintext
> Region eu-south-2 error - operation error STS: AssumeRole, https response error StatusCode: 403, RequestID: 1f8d2ca9-928c-4d8e-9db0-5dfa5c302604, api error InvalidClientTokenId: The security token included in the request is invalid
> ```
> 
> Where these messages refer to regions where you do not need to discover and scan assets, you can safely ignore them.

### AWS IaaS integration roles and permissions

When you integrate AWS accounts into Securiti using IAM roles, Securiti creates several IAM roles in that account that it assumes in order to perform various functions. Securiti also creates policies that allow it to assume these roles. What roles and permissions it creates depends on what functions you select in the Add a Cloud Account popup.

The following diagram shows the different roles, and illustrates their function.

![Securiti_AWS_Roles_BobK2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-84331c5e-8503-a873-4e61-172749c94454.png)

As the diagram shows, Securiti creates the roles described in the table below in the master AWS account, and as applicable in any member AWS accounts that you have integrated. The actual role names include a random string at the end, for example "CONFIGURATION_SCAN_MASTER_AEI3GHY."

| Function | IAM roles created in master AWS account | IAM roles created in member AWS account(s) |
| --- | --- | --- |
| Asset discovery | ASSET_DISCOVERY_MASTER_[XXX] ASSET_DISCOVERY_MEMBER_[XXX] | ASSET_DISCOVERY_MEMBER_[XXX] |
| Cloud Security Posture Management | CONFIGURATION_SCAN_MASTER_[XXX] CONFIGURATION_SCAN_MEMBER_[XXX] | CONFIGURATION_SCAN_MEMBER_[XXX] |
| Data scanning | CONNECTOR_SCAN_MASTER_[XXX] CONNECTOR_SCAN_MEMBER_[XXX] | CONNECTOR_SCAN_MEMBER_[XXX] |

As the diagram and table show, Securiti creates a set of master roles in the master AWS account, and also policies that allow it to assume these various roles. In the master account, and also in any member accounts that you have integrated earlier Securiti also creates a set of member roles, and policies that allow each of those to be assumed by the corresponding master role. In each member AWS account, Securiti creates the member roles and corresponding policies.

As necessary for each of the functions in the table above, Securiti assumes the master role corresponding to that function. This master role, in turn, assumes the corresponding member role, either in the master account, or in a member account. In this member role, Securiti performs the functions of asset discovery, posture management, or data scanning as appropriate.

In the case of data scanning, the POD_ROLE or ELASTICPOD_ROLE on the EC2 instance where the pod is deployed assumes the CONNECTOR_SCAN_MASTER role. This role then assumes the CONNECTOR_SCAN_MEMBER role, and uses it to perform data scanning. The pod roles on the EC2 instance automatically have policies that allow them to be assumed by the connector scan master role. However, Securiti cannot automatically configure the trust relationship on the connector scan master role that allows it to assume the pod role. You must configure this trust relationship manually for each pod. For more information, see [Configuring AWS pod IAM role trust](https://helpcenter.securiti.ai/v1/docs/creating-an-aws-iaas-instance-version-1110-and-earlier).

### Creating an AWS IaaS instance

1. In Securiti, open **Sensitive Data Intelligence**.
2. On the Data Systems Overview dashboard that opens by default, near the upper right corner of the page click **+ Add Cloud Account** or open **Sensitive Data Intelligence**, choose **Settings** > **IaaS Cloud**, and click **Create Instance** on Amazon Web Services card.
3. On the Add a Cloud Account popup, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Account Provider | Choose **AWS**. |
| Connector Name | Customize this field if you plan to activate multiple AWS accounts and must differentiate between them. Otherwise, leave it as-is. |
| Create keys/secrets for access | Mark this radio button to create a long-term access key ID plus a secret access key for connectivity. |
| Create assumable IAM roles/policies for access | Mark this radio button to create IAM roles, grant cross-account access to the Securiti cloud, and generate temporary security credentials for connectivity. This option is only available if your Securiti tenant is hosted in the AWS cloud. |
| Initiate asset discovery | Mark to discover assets. |
| Notify all owners by email when asset discovery is complete | Enabled by default to send emails to owners and co-owners after an asset discovery scan completes. The notification includes key insights and a direct link to the Graph for deeper analysis. > [!NOTE] > **Note** > > - Email notifications are sent only when asset discovery identifies new assets. > - To trigger the email notifications, it is necessary to reschedule and run asset discovery again. > - To enable this feature for existing instances, navigate to the **Instance Setup tab > Advanced Settings > Notify all owners by email when asset discovery is complete**. > - If the feature was enabled during the connector onboarding, you can disable it from the same tab if you no longer wish to receive email notifications. |
| Initiate security posture scan | Enable to have Securiti scan AWS for security vulnerabilities |
| Auto-remediate security posture violations | Enable to have Securiti automatically remediates any AWS security vulnerabilities it finds. |
| Data Access Governance | This option is used to gain intelligence into the users and roles with access to resources and sensitive data in GCP and BigQuery datasets and define controls to limit access to sensitive data. |
| Region | Select the AWS region where you would like to run the CloudFormation stack. |
4. Click **Authorize Account**.

Securiti redirects you to your AWS console, where AWS prompts you to log in if you are not already authenticated.
5. At the CloudFormation Stack creation page, leave all the prefilled values as-is, mark the "acknowledge" checkbox, and click **Create Stack**.

![RN_AWS2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3da4cc80-b8fc-3478-90f3-71361a0da344.png)

After the stack deploys, Securiti automatically starts asset discovery and populates the Overview dashboard with them.

### Configuring activated AWS IaaS instance

This section provides instructions about configuring IAM S3 for IaaS.

1. On the IaaS Cloud page, click **View Instance** and select any active instance.
2. On the **Basic Information** tab, you can view the instance name and primary owner details.
3. On the **Instance Setup** tab, you can configure the following settings:

| Parameter | Description |
| --- | --- |
| Enable Access Scan | To enable the data access governance, mark this checkbox. This option is used to gain intelligence into the users and roles with access to resources and sensitive data in GCP and BigQuery datasets and define controls to limit access to sensitive data. |
| Schedule automatic scans to Discover Data Systems and their Security Posture | Select an option from Hourly, Weekly, or Monthly. You can also schedule the scans to exclude from your peak times. |

### AWS pod activation

After you integrate Securiti with AWS and do asset discovery as described in [Creating an AWS IaaS instance](/v1/docs/creating-an-aws-iaas-instance-version-1110-and-earlier), to activate Securiti pods to scan specific data systems for sensitive or personal data:

1. Do one of the following to activate Securiti pods to scan specific data systems for sensitive or personal data:
  - To deploy a new Securiti pod to scan the data systems, see [pods](/latest/docs/securiti-pods-and-elastic-pods) documentation.
  - If you have already deployed a pod in the same region as the data systems you want to scan, follow the procedure below to use that pod.

To use an existing Securiti pod with AWS to scan specific data systems for sensitive or personal data:
    1. If you haven't already done so, open **Sensitive Data Intelligence** to the Overview dashboard.
    2. On the Data Systems tab, choose a subset of AWS assets in the same account or region by marking the checkboxes at their left ends.

After you mark the first checkbox, Securiti only lets you mark additional checkboxes for assets in the same account or region.
    3. Near the upper right corner of the data assets table, click **Connect Data System**.
    4. On the Add or Select a Compute Pod for Discovery popup, apply the following settings. Leave all others as-is:

| Parameter | Description |
| --- | --- |
| Existing Pod | Mark this radio button to use an existing pod. |
| Compute Pod Name | Choose the pod you want to use to connect with the selected data systems. |
    5. Click **Connect**.

After Securiti tests connectivity with the selected AWS Assets, the Assets change to the “Connected” state. You can then define scanning schedules and scopes as described in [Discovery scans](/v1/docs/discovery-scans).Discovery scans
2. Configure pod or IAM role trust as described in [Configuring AWS pod IAM role trust](https://helpcenter.securiti.ai/v1/docs/creating-an-aws-iaas-instance-version-1110-and-earlier).

### Configuring AWS pod IAM role trust

When you deploy a pod on an EC2 instance to do data scanning in an AWS account, you must manually configure its IAM role so that it can be assumed by the CONNECTOR_SCAN_MASTER that Securiti creates on the account. You do this by creating a policy that lets the pod-role or elasticpod-role be assumed by the CONNECTOR_SCAN_MASTER IAM role that Securiti creates on the AWS account so it can do data scanning. For more information, see [Policies and permissions required for AWS integration](/latest/docs/policies-and-permissions-required-for-aws-integration).

1. Log into the AWS console for the AWS account with your admin credentials.
2. In the AWS console, locate the EC2 instance for the pod and record the ARN for its IAM role.
3. In the console, navigate to **IAM** **(Identity and Access Management)** **> Roles**, and locate and open the connector scan master role.

Example scan master role:

```plaintext
arn:aws:iam::523178155304:role/SECURITI_CONNECTOR_SCAN_MASTER_ROLE_blcy92fp
```
4. Click the **Trust relationships** tab, and in the Trusted entities policy, explicitly add an entry to Statement:Principal:AWS that trusts the ARN of the pod's IAM role.

Example scan master role trust relationship with pod role:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": [
          "arn:aws:iam::718391394098:role/EKSNODE",
          "arn:aws:iam::718391394098:root",
          "arn:aws:iam::523178155304:role/PODRole"
        ],
        "Service": "ec2.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```
5. Save your changes.

### Activation on multiple AWS IaaS accounts

If you use multiple AWS accounts to segregate data or business functions, you can easily deploy a centrally-managed pod to a primary AWS account, and use that pod to connect with and scan assets in multiple member AWS accounts. Securiti automatically assumes that the initial AWS account onboarded is the primary account where all pods are deployed.

After activating the first account as described in previous procedures on this topic:

1. On the Instance Setup tab for the account, click **Prepare Template**, then click **Download Template**.
2. Extract the template and parameters files to a local directory.
3. Use the AWS CLI to run the following command on each of the AWS accounts you want to activate as member accounts under this master account.

> [!NOTE]
> **Note**
> 
> The user used to execute the create-stack command must have IAM permissions in AWS so that the template can create roles and policies within the AWS account.
> 
> On macs file:// might be needed for the --template-body and --parameters arguments e.g. file:///tmp/member-template-3.yaml .

```bash
aws cloudformation create-stack --stack-name <aws stack name> 
--template-body <path to the cf yaml file extracted from downloaded zip> 
--parameters <path to the cf params json extracted from downloaded zip> 
--debug  --profile <aws profile> --region us-west-2 
--capabilities CAPABILITY_NAMED_IAM
```

After successful deployment of the stack in each account, the account automatically shows up under the list of accounts on the Instance Setup tab of the IaaS connector.

## Related

- [Performing Actions Post AWS Instance Creation](/performing-actions-post-aws-instance-creation.md)
- [Visualizing Results of Asset Discovery in Graph Explorer](/visualising-results-of-aws-asset-discovery-in-graph-explorer.md)
- [Deploying Pod](/deploying-pod-aws.md)
- [How it works?](/how-it-works-aws.md)
