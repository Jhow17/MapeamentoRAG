---
title: "Obtain credentials for role based authentication in Amazon Redshift"
slug: "obtain-credentials-for-role-based-authentication-in-amazon-redshift"
updated: 2026-07-30T07:41:53Z
published: 2026-07-30T07:41:53Z
canonical: "helpcenter.securiti.ai/obtain-credentials-for-role-based-authentication-in-amazon-redshift"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials for role based authentication in Amazon Redshift

In addition to the Basic authentication, Amazon Redshift data systems supports IAM role based authentication method to establish a successful connection in Securiti.

Use the matching procedure below.

> [!NOTE]
> **Note**
> 
> This procedure assumes you have the AWS Master and Member account IDs before connector activation. You can either create these roles manually or use the sample Cloud Formation (CF) template before connector activation.

1. Create a sample CF template:
  1. The below template is the CloudFormation template to create redshift master role and instance profile on account where the appliance is located.

Replace existing <*AWS Master Account ID*> and <*AWS Member Account IDs*> with your AWS Master and Member IDs respectively, as shown below.

```plaintext
AWSTemplateFormatVersion: "2010-09-09"
Description: CloudFormation template to create Redshift master role in appliance

Parameters:
  MemberAccountId:
    Description: The AWS account ID where the Redshift cluster is located
    Type: String

Resources:
  SecuritiRedshiftScanMasterPolicy:
    Type: AWS::IAM::ManagedPolicy
    Properties:
      ManagedPolicyName: SECURITI_CONNECTOR_REDSHIFT_MASTER_POLICY
      Description: Allows access to assume connector member roles in customer's account(s)
      Path: /
      PolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Effect: Allow
            Action: sts:AssumeRole
            Resource: 
              - Fn::Sub: arn:aws:iam::${MemberAccountId}:role/SECURITI_CONNECTOR_REDSHIFT_SCAN_ROLE

  SecuritiRedshiftScanMasterRole:
    Type: AWS::IAM::Role
    Properties:
      RoleName: SECURITI_CONNECTOR_REDSHIFT_MASTER_ROLE
      Path: /
      ManagedPolicyArns:
        - !Ref SecuritiRedshiftScanMasterPolicy

  SecuritiRedshiftScanMasterInstanceProfile: 
    Type: AWS::IAM::InstanceProfile
    Properties: 
      InstanceProfileName: SECURITI_CONNECTOR_REDSHIFT_MASTER_IP
      Path: /
      Roles: 
        - !Ref SecuritiRedshiftScanMasterRole

Outputs:
  SecuritiRedshiftScanMasterRoleARN:
    Description: ARN of the Connector Scan Master Role
    Value: !GetAtt SecuritiRedshiftScanMasterRole.Arn
```
  2. For the Member CloudFormation template to create member role to access Redshift on account where the Redshift cluster is located, replace the existing <*AWS Master Account ID*> with your AWS Master Account ID.

```plaintext
AWSTemplateFormatVersion: "2010-09-09"
Description: CloudFormation template to create Redshift member role to access Redshift in the same account

Parameters:
  RegionName:
    Description: The AWS region where the Redshift cluster is located
    Type: String
  MasterAccountId:
    Description: The AWS account ID where the appliance is located
    Type: String
  ClusterName:
    Description: The name of the Redshift cluster
    Type: String

Resources:
  SecuritiRedshiftScanMemberPolicy:
    Type: AWS::IAM::ManagedPolicy
    Properties:
      ManagedPolicyName: SECURITI_CONNECTOR_REDSHIFT_SCAN_POLICY
      Description: Allows access for Redshift.
      Path: '/'
      PolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Sid: AllowRedshiftCredentialsAccess
            Effect: Allow
            Action:
              - redshift:GetClusterCredentials
            Resource: 
              - Fn::Sub: arn:aws:redshift:${RegionName}:${AWS::AccountId}:dbgroup:${ClusterName}/*
              - Fn::Sub: arn:aws:redshift:${RegionName}:${AWS::AccountId}:dbname:${ClusterName}/*
              - Fn::Sub: arn:aws:redshift:${RegionName}:${AWS::AccountId}:dbuser:${ClusterName}/*

  SecuritiRedshiftScanMemberRole:
    Type: AWS::IAM::Role
    Properties:
      RoleName: SECURITI_CONNECTOR_REDSHIFT_SCAN_ROLE
      Path: /
      ManagedPolicyArns:
        - !Ref SecuritiRedshiftScanMemberPolicy
      AssumeRolePolicyDocument:
        Version: "2012-10-17"
        Statement:
          - Effect: Allow
            Action: sts:AssumeRole
            Principal:
              AWS: 
                - Fn::Sub: arn:aws:iam::${MasterAccountId}:role/SECURITI_CONNECTOR_REDSHIFT_MASTER_ROLE

Outputs:
  SecuritiRedshiftScanMemberRoleARN:
    Description: ARN of the Connector Scan Member Role
    Value: !GetAtt SecuritiRedshiftScanMemberRole.Arn
```
2. Deploy the Master and Member CF template using AWS CloudFormation.
3. Assign the newly created instance profile to your Securiti scanning appliance.

> [!NOTE]
> **Note**
> 
> You must do so if the pod you configured is in AWS.

![redshift_assignrole_instance.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cfd4ae7e-3e74-be7e-290d-6e5d547cecd8.png)

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
4. Proceed to [Connecting Amazon Redshift with Securiti](/latest/docs/connecting-amazon-redshift-with-securiti).
