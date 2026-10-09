---
title: "Understanding CF Templates for Stack Deployment"
slug: "understanding-cf-templates-for-stack-deployment"
updated: 2026-06-22T08:00:09Z
published: 2026-06-22T08:00:09Z
canonical: "helpcenter.securiti.ai/understanding-cf-templates-for-stack-deployment"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Understanding CF Templates for Stack Deployment

When the stacks are successfully deployed, they grant the necessary permissions to the Securiti platform to perform scans using the CloudFormation (CF) templates. In this section, you'll learn more about how these templates work and their role in enabling secure scans.

### Securiti Cloud requirements for AWS

If **Securiti Cloud** is selected, all scanning activities are conducted within the Securiti Cloud environment. The only CloudFormation template that needs to be deployed is the **aws-account-onboarding-cf-template.yaml**.

No additional actions are required from the customer.

For more details, see to the [Navigating through CF Templates](/latest/docs/understanding-cf-templates-for-stack-deployment#navigating-through-cf-templates).

### My Cloud requirements for AWS

We recommend that you provision a separate AWS account to host the scanning pods that we automatically deploy for a clear separation and easy management of the infrastructure. However, you can choose to use your existing accounts as well. For this purpose, Securiti provides the following CloudFormation templates through the My Cloud provisioning option:

- VPC.yaml
- Securiti-pod-roles.yaml

You can use these templates to configure the required roles and set up the VPC in your preferred region. The VPC.yaml template automatically provides the above-required secret and needed baseline resources.

> [!NOTE]
> **Note**
> 
> You can also use your own VPC, Subnets, and KMS keys but you must populate the above secret in that case.

For more details on the list of permissions enabled for each service, refer to the sections below.

### Navigating through CF templates

Once the templates are downloaded, you can view all the policies and roles attached to Securiti's master and member roles, as well as the cloud service permissions required. These templates are thoroughly documented, with detailed comments explaining the purpose behind each permission.

For example, in the **aws-account-onboarding-cf-template.yaml**, the **Securiti_CONNECTOR_SCAN_MEMBER_ROLE_POLICY** allows Securiti to assume the member role (in the account where assets are located) and perform sensitive data discovery.

### Updating CloudFormation Template

You can update the CloudFormation stack either through the **AWS Management Console** **(UI)** or by using the **AWS Command Line Interface (CLI)**.

> [!NOTE]
> **Important**
> 
> If you selected **Account** as the scope during onboarding, it is recommended to execute the CloudFormation template via the CLI to avoid manual configuration steps when updating the stack after editing the connector settings. If you choose to use the AWS Console instead, ensure that the modified settings are enabled and the required permissions are added in the CloudFormation stack.

#### Updating CloudFormation Template via AWS Console (UI)

To update the CF template via AWS Console (UI):

1. Sign in to the AWS Console for your account.
2. In the Services menu, search for and open **CloudFormation**.
3. Locate the existing Securiti stack in the **Stacks** list.
4. Select the stack and choose **Update Stack** > **Make a direct update**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(209).png)
5. On the **Update stack page**, apply the following settings:
  1. Under the **Prerequisite** - **Prepare template** section choose **Replace existing template**.
  2. Under the **Specify template** section, choose **Upload a template file** and select the appropriate template file.

Review parameters and manually set enable/disable values if you encounter errors.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(210).png)

1. Review parameters and manually set enable/disable values if you encounter errors.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(211).png)

> [!NOTE]
> **Note**
> 
> AWS retains existing parameter values unless explicitly changed. If you encounter validation errors, ensure all required parameters are set correctly.

1. Verify the changes and wait until the stack update is complete.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(212).png)

#### Updating CloudFormation Template via AWS CLI

To update the CF template via AWS CLI:

1. **Upload template to S3**:
  1. Upload the CloudFormation template file to your S3 bucket.
  2. Copy the S3 URL of the uploaded template.
  3. Use this URL in the `--template-url` parameter.
2. **Find the stack name:**
  1. Go to CloudFormation console.
  2. Find your Securiti stack.
  3. Copy the stack name.
  4. Use this name in the `--stack-name` parameter
3. **Run the CLI Command:**
  1. Use the following syntax to update the stack:

```bash
```bash
aws cloudformation update-stack \  
--stack-name <REPLACE_WITH_YOUR_STACK_NAME> \  
--template-url <REPLACE_WITH_S3_URL_OF_TEMPLATE> \  
--capabilities CAPABILITY_NAMED_IAM
```
```
