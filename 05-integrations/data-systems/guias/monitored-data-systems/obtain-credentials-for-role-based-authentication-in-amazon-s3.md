---
title: "Obtain credentials for role based authentication in Amazon S3"
slug: "obtain-credentials-for-role-based-authentication-in-amazon-s3"
updated: 2025-12-06T14:09:58Z
published: 2025-12-06T14:09:58Z
canonical: "helpcenter.securiti.ai/obtain-credentials-for-role-based-authentication-in-amazon-s3"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials for role based authentication in Amazon S3

In addition to the key based and inventory based authentication, Amazon S3 data systems provide role based authentication method to establish a successful connection in Securiti.

Use the matching procedure below.

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

## Related

- [Connecting Amazon S3 with Securiti](/connecting-amazon-s3-with-securiti.md)
- [Configure discovery scans in Amazon S3](/configure-discovery-scans-in-amazon-s3.md)
- [Configuring Data Inventory Sync for Amazon S3 (Self-hosted)](/configuring-data-inventory-sync-for-amazon-s3-self-hosted.md)
- [Fulfilling DSR requests for Amazon S3](/fulfilling-dsr-requests-for-amazon-s3.md)
