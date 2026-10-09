---
title: "Obtain credentials for role-based authentication in Amazon S3 (Hyperdrive)"
slug: "obtain-credentials-for-role-based-authentication-in-amazon-s3-hyperdrive"
updated: 2026-07-19T18:54:00Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/obtain-credentials-for-role-based-authentication-in-amazon-s3-hyperdrive"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials for role-based authentication in Amazon S3 (Hyperdrive)

Role-based authentication for Amazon S3 in Hyperdrive mode requires different credentials and a different AWS CloudFormation (CF) template depending on your deployment model.

- **Hybrid deployment with Outpost:** Select this tab if you have a dedicated Outpost appliance in your own AWS account. Use this procedure to obtain the credentials and deploy the master and member roles CloudFormation (CF) template required for role-based authentication.
- **Full SaaS deployment:** Select this tab if you are using Securiti's managed cloud environment. Use this procedure to obtain the credentials and deploy the master and member role CloudFormation (CF) template required for role-based authentication.

Choose the tab below that matches your deployment to view the appropriate configuration steps.

**Hybrid deployment with Outpost**

Use the following procedure below to obtain credentials for role-based authentication in Amazon S3 using your own AWS-based Outpost deployment.

> [!NOTE]
> **Note**
> 
> This procedure assumes you have the AWS Master and Member account IDs before connector activation. You need Master and Member account IDs due to following reasons:
> 
> - It is in accordance with AWS best practices.
> - A master account typically manages centralized identity access, authentication, and billing, without hosting actual resources.
> - Member accounts host the workloads while access is controlled through the master account
> 
> However, if you operate within a single account environment, you can set the Master and Member account IDs to be identical in CF template, allowing both templates to deploy in the same account.
> 
> You can either create these roles manually or use the sample Cloud Formation (CF) template before connector activation. See below if you want to use a sample template by Securiti.

1. Record the following for later use:
  - **AWS Master Account ID**
  - **Data Scan Master IAM Role**
  - **AWS Member Account IDs**
  - **Data Scan Member IAM Role**
  - **Inventory Report Bucket** - required when using Native Inventory scanning only
  - **Inventory Report Path** - required when using Native Inventory scanning only
  - **Region**
  - **Bucket(s)**
  - **Path**
2. Create a sample CF template:
  1. Replace existing <*AWS Master Account ID*> and <*AWS Member Account IDs*> with your AWS Master and Member IDs, respectively, as shown below.

```plaintext
AWSTemplateFormatVersion: '2010-09-09'
Description: Sample Template for Securiti CloudFormation Template for Master Roles
Resources:
  SecuritiS3MasterPolicy:
    Type: AWS::IAM::ManagedPolicy
    Properties:
      ManagedPolicyName: SECURITI_S3_MASTER_ROLE_POLICY
      Description: Securiti S3 Scan Master Policy
      Path: /
      PolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Action: sts:AssumeRole
            Effect: Allow
            Resource:
              - 'arn:aws:iam::< MEMBER ACCOUNT ID 1 >:role/SECURITI_S3_MEMBER_ROLE'
              - 'arn:aws:iam::<member account 2>:role/SECURITI_S3_MEMBER_ROLE'
  SecuritiS3MasterRole:
    Type: AWS::IAM::Role
    Properties:
      RoleName: SECURITI_S3_MASTER_ROLE
      ManagedPolicyArns:
        - !Ref 'SecuritiS3MasterPolicy'
      AssumeRolePolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Effect: Allow
            Principal: 
              Service: 'ec2.amazonaws.com'
              AWS:
                - 'arn:aws:iam::< AWS ACCOUNT ID 1 >:root'
            Action: sts:AssumeRole
Outputs:
  SecuritiS3MasterRoleARN:
    Description: ARN of the Securiti S3 Scan Master Role
    Value: !GetAtt 'SecuritiS3MasterRole.Arn'
```
  2. For the Member CF template, replace the existing <*AWS Master Account ID*> with your AWS Master Account ID, and update BUCKET NAME, REGION, ACCOUNT ID, and KMS KEY ID fields as shown below.

```plaintext
AWSTemplateFormatVersion: '2010-09-09'
Description: Sample Template for Securiti CloudFormation Template for Member Roles
Resources:
  SecuritiS3MemberPolicy:
    Type: AWS::IAM::ManagedPolicy
    Properties:
      ManagedPolicyName: 'SECURITI_S3_MEMBER_ROLE_POLICY'
      Description: Securiti S3 Scan Member Policy
      Path: /
      PolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Sid: AllowS3BucketList
            Effect: Allow
            Resource: 'arn:aws:s3:::< BUCKET NAME >'
            Action:
              - s3:ListBucket
          - Sid: AllowS3GetObject
            Effect: Allow
            Action:
              - s3:GetObjectTagging
              - s3:GetObject
            Resource: 'arn:aws:s3:::< BUCKET NAME >/*'
          - Sid: AllowKMSDecrypt
            Effect: Allow
            Action:
              - kms:Decrypt
            Resource: 'arn:aws:kms:< REGION >:< ACCOUNT ID >:key/< KMS KEY ID>'
          - Sid: ListCloudWatchMetrics
            Effect: Allow
            Action:
              - cloudwatch:GetMetricStatistics
            Resource: '*'
  SecuritiS3MemberRole:
    Type: AWS::IAM::Role
    Properties:
      RoleName: 'SECURITI_S3_MEMBER_ROLE'
      ManagedPolicyArns:
        - !Ref 'SecuritiS3MemberPolicy'
      AssumeRolePolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Action: sts:AssumeRole
            Effect: Allow
            Principal:
              AWS: 'arn:aws:iam::< ACCOUNT ID >:root'
Outputs:
  SecuritiS3MemberRoleARN:
    Description: ARN of the Securiti S3 Scan Member Role
    Value: !GetAtt 'SecuritiS3MemberRole.Arn'
```
3. Deploy the Master and Member CF template using AWS CloudFormation.
4. Create an instance profile using AWS CLI or AWS CloudShell with "IAM Master Role" to scan S3 buckets, as shown in the example below.

*aws iam create-instance-profile --instance-profile-name SECURITI_S3_MASTER_ROLE*

*aws iam add-role-to-instance-profile --role-name SECURITI_S3_MASTER_ROLE --instance-profile-name SECURITI_S3_MASTER_ROLE*
5. Assign the newly created instance profile to your Securiti scanning appliance.

> [!NOTE]
> **Note**
> 
> You must do so if the pod you configured is in AWS.

![Assign_instance_profile.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ff76bc4-a9d3-0259-b952-8ae244ef7db2.png)

> [!NOTE]
> **Important**
> 
> If the Pod is running in AWS environment and the underlying VM has IMDSv2 enabled, the hop count of the EC2 instance must be configured to no less than 2, for successful authentication.
> 
> If necessary, use the command below to set the hop count to 2.
> 
> ```plaintext
> aws ec2 modify-instance-metadata-options --instance-id <instance ID> --http-put-response-hop-limit 2
> ```

**Full SaaS deployment**

> [!NOTE]
> Note
> 
> Securiti assumes your Master role using the Securiti AWS Account ID and the External ID you configure.
> 
> - The Master role assumes your Member role in each member account, again using the External ID.
> - The Member role grants access to the target S3 buckets.

Use the following procedure below to obtain credentials for role-based authentication in Amazon S3 using Securiti's managed Full SaaS deployment solution.

1. Record the **Securiti AWS Account ID** that is displayed on the connector authentication page. This 12-digit AWS account ID identifies the Securiti AWS account that assumes the Master role in your AWS account. Use it with the fixed Securiti IAM role name to define the trusted principal in the Master role trust policy:

> [!CAUTION]
> Caution
> 
> This value is environment-specific. Use the value shown on your connector screen.
2. Choose the **External ID** for the authentication using Full SaaS deployment model.

> [!NOTE]
> Note
> 
> Choose a unique, hard-to-guess string for the External ID and treat it as a shared secret.

You must use this exact same value in both of the following:
  - The Master role trust policy as `sts:ExternalId condition`.
  - The connector activation form in the Securiti as **External Id for Master and Member IAM Roles**.

> [!CAUTION]
> Caution
> 
> Ensure that the External ID in the Master role trust policy exactly matches the External ID entered on the connector activation page. Any mismatch prevents Securiti from establishing the connection.
3. Create a sample CF template:

> [!WARNING]
> Important
> 
> In the Full SaaS deployment model, you do not need to create an instance profile or modify the IMDSv2 hop count. Instead, create two IAM roles:
> 
> - A Master role
> - A Member role.
> 
> Securiti reaches your S3 buckets by assuming them through cross-account `sts:AssumeRole`.
> 
> You can create the roles manually or use the sample CloudFormation (CF) templates below. Deploy the Master template once in your master or management account, and the Member template in every account that holds S3 buckets to be scanned.

You can create the roles manually or use the sample CloudFormation (CF) templates below. Deploy the Master template once in your master/management account, and the Member template in every account that holds S3 buckets to be scanned.

> [!NOTE]
> Note
> 
> If you operate in a single-account environment, deploy both templates in the same account and use that same account ID for both the master and member entries on the connector form.
  1. **Create master role CF template** Deploy in your master or management account. Before deploying, replace the following:

| Parameter | Description |
| --- | --- |
| `&lt;SECURITI AWS ACCOUNT ID&gt;` | Securiti AWS Account ID you obtained in step 1 above and recorded from connector activation screen. |
| `&lt;EXTERNAL ID&gt;` | The External ID you chose in step 2 above. |
| `&lt;MEMBER ACCOUNT ID 1&gt;, &lt;MEMBER ACCOUNT ID 2&gt;` | Each of your member account IDs. Add one line per member account. |

```plaintext
AWSTemplateFormatVersion: '2010-09-09'
Description: Securiti S3 (Shared Outpost) - Master Role
Resources:
  SecuritiS3MasterPolicy:
    Type: AWS::IAM::ManagedPolicy
    Properties:
      ManagedPolicyName: SECURITI_S3_CONNECTOR_MASTER_ROLE_POLICY
      Description: Securiti S3 Scan Master Policy
      Path: /
      PolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Effect: Allow
            Action:
              - 'sts:AssumeRole'
              - 'sts:TagSession'
            Resource:
              - 'arn:aws:iam::<MEMBER ACCOUNT ID 1>:role/SECURITI_S3_MEMBER_ROLE'
              - 'arn:aws:iam::<MEMBER ACCOUNT ID 2>:role/SECURITI_S3_MEMBER_ROLE'
  SecuritiS3MasterRole:
    Type: AWS::IAM::Role
    Properties:
      RoleName: SECURITI_S3_CONNECTOR_MASTER_ROLE
      ManagedPolicyArns:
        - !Ref SecuritiS3MasterPolicy
      AssumeRolePolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Effect: Allow
            Principal:
              AWS: 'arn:aws:iam::<SECURITI AWS ACCOUNT ID>:role/SECURITI_S3_SCAN_ROLE'
            Action: 'sts:AssumeRole'
            Condition:
              StringEquals:
                'sts:ExternalId': '<EXTERNAL ID>'
          - Effect: Allow
            Principal:
              AWS: 'arn:aws:iam::<SECURITI AWS ACCOUNT ID>:role/SECURITI_S3_SCAN_ROLE'
            Action: 'sts:TagSession'
Outputs:
  MasterRoleArn:
    Description: ARN of the Securiti S3 Connector Master Role
    Value: !GetAtt SecuritiS3MasterRole.Arn
```
  2. **Create member role CF template** Deploy in each account that contains S3 buckets to scan. Before deploying, replace the following parameters:

| Parameter | Description |
| --- | --- |
| `&lt;AWS MASTER ACCOUNT ID&gt;` | Your master or management account ID (12 digits). |
| `&lt;BUCKET NAME&gt;` | The S3 bucket Securiti scans. |
| `&lt;REGION&gt;, &lt;ACCOUNT ID&gt;, &lt;KMS KEY ID&gt;` | The region, account ID, and KMS key ID for the bucket's encryption key. Remove the AllowKMSDecrypt statement if the bucket is not encrypted with a customer-managed KMS key. |

```plaintext
AWSTemplateFormatVersion: '2010-09-09'
Description: Securiti S3 (Shared Outpost) - Member Role
Resources:
  SecuritiS3MemberPolicy:
    Type: AWS::IAM::ManagedPolicy
    Properties:
      ManagedPolicyName: SECURITI_S3_MEMBER_ROLE_POLICY
      Description: Securiti S3 Scan Member Policy
      Path: /
      PolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Sid: AllowS3BucketList
            Effect: Allow
            Action:
              - 's3:ListBucket'
            Resource: 'arn:aws:s3:::<BUCKET NAME>'
          - Sid: AllowS3GetObject
            Effect: Allow
            Action:
              - 's3:GetObjectTagging'
              - 's3:GetObject'
            Resource: 'arn:aws:s3:::<BUCKET NAME>/*'
          - Sid: AllowKMSDecrypt
            Effect: Allow
            Action:
              - 'kms:Decrypt'
            Resource: 'arn:aws:kms:<REGION>:<ACCOUNT ID>:key/<KMS KEY ID>'
          - Sid: ListCloudWatchMetrics
            Effect: Allow
            Action:
              - 'cloudwatch:GetMetricStatistics'
            Resource: '*'
  SecuritiS3MemberRole:
    Type: AWS::IAM::Role
    Properties:
      RoleName: SECURITI_S3_MEMBER_ROLE
      ManagedPolicyArns:
        - !Ref SecuritiS3MemberPolicy
      AssumeRolePolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Effect: Allow
            Principal:
              AWS: 'arn:aws:iam::<AWS MASTER ACCOUNT ID>:role/SECURITI_S3_CONNECTOR_MASTER_ROLE'
            Action:
              - 'sts:AssumeRole'
              - 'sts:TagSession'
Outputs:
  MemberRoleArn:
    Description: ARN of the Securiti S3 Scan Member Role
    Value: !GetAtt SecuritiS3MemberRole.Arn
```

> [!NOTE]
> Tip
> 
> Follow these naming and configuration requirements to ensure successful role assumption:
> 
> - Use the same **External ID** in both the Master role trust policy and the connector activation page.
> - Use the same Member role name in every member account.
> - Name the Master role as `SECURITI_S3_CONNECTOR_MASTER_ROLE`.
>   - You might append a suffix, for example, `SECURITI_S3_CONNECTOR_MASTER_ROLE_Prod` because Securiti can assume any role matching `SECURITI_S3_CONNECTOR_MASTER_ROLE`*.
>   - However, we recommend using the default name. If you add a suffix, use the same full role name in the Member role trust policy and on the connector activation page.
> - Name the Member role `SECURITI_S3_MEMBER_ROLE`. This role name is referenced by both the Master role permissions policy and the connector activation page.
4. Once both roles exist, open the Amazon S3 connector in Securiti, select Full SaaS deployment under Outpost and choose Authentication Type > IAM Roles.

Proceed to [Connecting the Amazon S3 with Securiti (Hyperdrive)](/latest/docs/activate-the-amazon-s3-connector-in-securiti-hyperdrive).
