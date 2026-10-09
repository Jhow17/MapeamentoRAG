---
title: "Creating IRSA Role and establish trust relationship"
slug: "irsa-authentication-steps-for-iam-role-in-securitii"
description: "Learn the steps to configure IAM Roles for Service Accounts (IRSA) for EPODv2 connectors on AWS EKS."
updated: 2026-04-27T12:06:34Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/irsa-authentication-steps-for-iam-role-in-securitii"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Creating IRSA Role and establish trust relationship

This article covers following topics:

- Overview of IRSA
- EPod V2 service accounts
- Service account to sub condition mapping
- Creating and configuring an IRSA role in AWS
- Establishing a trust relationship between the IRSA role and the existing SCAN_MASTER role
- Troubleshooting
- FAQs

## Overivew of IRSA

IAM Roles for Service Accounts (IRSA) is an AWS-native mechanism that lets individual Kubernetes pods to assume dedicated IAM roles, rather than inheriting permissions from the underlying Elastic Kubernetes Service (EKS) node's IAM role. For Elastic Pods (EPods) V2, customers running on AWS EKS, IRSA provides connector-level AWS identity. Each connector type gets its own IAM role with scoped permissions, following the principle of least privilege.

Without IRSA, all pods on an EKS node share the same IAM identity, derived from the EC2 instance profile. With IRSA, each connector pod utilizes its Kubernetes service account to exchange a short-lived token for AWS credentials scoped to a specific IAM role.

Use the following diagram to understand how IRSA credential chain works:

![Flowchart illustrating the IRSA role assumption process for AWS resources in EKS.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ChatGPT Image Apr 25, 2026, 03_33_46 PM.png)

> [!NOTE]
> Note
> 
> The AWS SDK automatically picks up IRSA credentials when the service account annotation is present.

## EPod V2 service accounts

EPod V2 utilizes the following Kubernetes service accounts, each requiring a dedicated IRSA role. The table describes the workloads associated with each service account.

| Service account name | Purpose |
| --- | --- |
| securiti-config-controller | Runs diagnostic routines via securitictl |
| securiti-connector-aws-s3 | Handles authentication, scan jobs, diagnostics, calculate size, and manage on-demand pods |
| securiti-download-worker | Manages file download operations |
| securiti-connector-policy | Supports policy enforcement and quarantine operations |
| securiti-file-quarantine-revert-worker | Handles the reverting of quarantined files |
| securiti-iaas-connector | Conducts inventory scans across AWS infrastructure |

## Service account to sub condition mapping

If you opt to enumerate service accounts explicitly in the trust policy instead of using the `securiti-*` wildcard, utilize the exact `sub` values from the table below. A single character mismatch will cause `sts:AssumeRoleWithWebIdentity` to be denied.

| Service Account Name | sub Condition Value |
| --- | --- |
| securiti-config-controller | system:serviceaccount:securiti:securiti-config-controller |
| securiti-connector-aws-s3 | system:serviceaccount:securiti:securiti-connector-aws-s3 |
| securiti-download-worker | system:serviceaccount:securiti:securiti-download-worker |
| securiti-connector-policy | system:serviceaccount:securiti:securiti-connector-policy |
| securiti-file-quarantine-revert-worker | system:serviceaccount:securiti:securiti-file-quarantine-revert-worker |
| securiti-iaas-connector | system:serviceaccount:securiti:securiti-iaas-connector |

Replace `securiti` with your actual EPODv2 namespace if it differs from the default.

## Step 1- Creating and configuring an IRSA role in AWS

> [!NOTE]
> Note
> 
> You must create one IRSA role that all service accounts can utilize.

### Prerequisites

Before starting, you must have:

- An EKS cluster with the OpenID Connect (OIDC) provider enabled
- An AWS Command Line Interface (CLI) installed and configured with sufficient IAM permissions:
  - `iam:CreateRole`
  - `iam:PutRolePolicy`
  - `iam:UpdateAssumeRolePolicy`
- The name of the Kubernetes namespace where EPod V2 is installed. The default value is:
  - `default: securiti`
- The name of your EKS cluster
- The Amazon Resource Name of your existing CONNECTOR_SCAN_MASTER role. For more information, see Securiti CloudFormation Template for Master Roles in [Obtain credentials for role based authentication in Amazon S3](/latest/docs/obtain-credentials-for-role-based-authentication-in-amazon-s3).

### Retrieving your OIDC provider URL

> [!NOTE]
> Note
> 
> You must retrieve OIDC provided URL to configure the trust relationship between AWS IAM and your Kubernetes service account. OIDC provide URL is required for every EKS cluster.

You can retrieve using one the two options provided below:

- #### Using AWS CLI

```plaintext
aws eks describe-cluster \
  --name <YOUR_CLUSTER_NAME> \
  --query "cluster.identity.oidc.issuer" \
  --output text
```

See the example output.

```plaintext
https://oidc.eks.us-east-1.amazonaws.com/id/EXAMPLED539D4633E53DE1B71EXAMPLE
```

Remove the `https://` prefix from the example URL and save the remaining value as `OIDC_PROVIDER_URL` for use in the next step.
- #### Using AWS console
  1. Navigate to EKS > **Clusters** → <your-cluster>.
  2. On you cluster page, click the **Configuration** tab.
  3. On the **Configuration** tab, copy the value under **OpenID Connect provider URL.** See the example below.

```plaintext
https://oidc.eks.us-east-1.amazonaws.com/id/EXAMPLED539D4633E53DE1B71EXAMPLE
```
  4. Remove the `https://` prefix from the example URL and save the remaining value as `OIDC_PROVIDER_URL` for use in the next step.

### Creating an IAM role that trusts your EKS service accounts

Create an IAM role that trusts your EKS service accounts using the OIDC provider, enabling pods to assume the role securely.

> [!NOTE]
> Note
> 
> The trust policy must allow all six EPODv2 service accounts to assume this role. All Securiti owned kubernetes service accounts are added as wild card-based sub-condition.

Use one of the following options to create the IRSA role.

- Using AWS CLI
  1. Run the following command using AWS CLI.

```plaintext
ACCOUNT_ID=$(aws sts get-caller-identity --query Account --output text)\
CLUSTER_NAME=<YOUR_CLUSTER_NAME>\
OIDC_PROVIDER_URL=<OIDC_PROVIDER_URL_WITHOUT_HTTPS>\
NAMESPACE=securiti          # or your custom EPODv2 namespace\
ROLE_NAME=${CLUSTER_NAME}-securiti-epodv2-irsa\
MASTER_ROLE_ARN=arn:aws:iam::${ACCOUNT_ID}:role/SECURITI_S3_MASTER_ROLE_EPOD_V2\
\
# 1. Write the trust policy allowing all six EPODv2 service accounts\
cat > irsa-trust-policy.json <<EOF\n{\n  "Version": "2012-10-17",\n  "Statement": [\n    {\n      "Effect": "Allow",\n      "Principal": {\n        "Federated": "arn:aws:iam::${ACCOUNT_ID}:oidc-provider/${OIDC_PROVIDER_URL}"\n      },\n      "Action": "sts:AssumeRoleWithWebIdentity",\n      "Condition": {\n        "StringEquals": {\n          "${OIDC_PROVIDER_URL}:aud": "sts.amazonaws.com"\n        },\n        "StringLike": {\n          "${OIDC_PROVIDER_URL}:sub": "system:serviceaccount:${NAMESPACE}:securiti-*"\n        }\n      }\n    }\n  ]\n}\nEOF\n\
# 2. Create the role\
aws iam create-role \ 
  --role-name ${ROLE_NAME} \ 
  --assume-role-policy-document file://irsa-trust-policy.json\
\
# 3. Grant it permission to assume the SCAN_MASTER role\
aws iam put-role-policy \ 
  --role-name ${ROLE_NAME} \ 
  --policy-name AssumeSecuritiMasterRole \ 
  --policy-document "{\n    \"Version\": \"2012-10-17\",\n    \"Statement\": [{\n      \"Effect\": \"Allow\",\n      \"Action\": \"sts:AssumeRole\",\n      \"Resource\": \"${MASTER_ROLE_ARN}\"\n    }]\n  }"\
\
# 4. Note the role ARN — you will need it in Parts 2 and 3\
aws iam get-role \ 
  --role-name ${ROLE_NAME} \ 
  --query "Role.Arn" \ 
  --output text
```

> [!NOTE]
> Note
> 
> For the `StringLike` condition, the pattern `system:serviceaccount:securiti:securiti-*` matches all six EPODv2 service accounts and nothing else in the securiti namespace, since all EPODv2 service accounts are prefixed with `securiti-`. If you prefer to enumerate them explicitly instead of using a wildcard, replace the `StringLike` block with separate statements — one per service account — each using `StringEquals` with the exact `sub` value from the [reference table](/latest/docs/irsa-authentication-steps-for-iam-role-in-securitii#service-account-to-sub-condition-mapping) at the start of this article.
- Using AWS CloudFormation:
  1. Use a CloudFormation template to create the IRSA role with the required trust policy and permissions.

```plaintext
AWSTemplateFormatVersion: '2010-09-09'
Description: Shared IRSA role for Securiti EPODv2
Parameters:
  EKSClusterName:
    Type: String
    Description: Name of your EKS cluster
  OIDCProviderUrl:
    Type: String
    Description: >-
      OIDC provider URL without https://
      (e.g. oidc.eks.us-east-1.amazonaws.com/id/EXAMPLE)
  KubernetesNamespace:
    Type: String
    Default: securiti
    Description: Namespace where EPODv2 is installed
  ScanMasterRoleName:
    Type: String
    Default: SECURITI_S3_MASTER_ROLE_EPOD_V2
    Description: Name of your existing SCAN_MASTER IAM role
Resources:
  EPODv2IRSARole:
    Type: AWS::IAM::Role
    Properties:
      RoleName: !Sub ${EKSClusterName}-securiti-epodv2-irsa
      AssumeRolePolicyDocument:
        Fn::Sub:
          - |
            {
              "Version": "2012-10-17",
              "Statement": [
                {
                  "Effect": "Allow",
                  "Principal": {
                    "Federated": "arn:aws:iam::${AWS::AccountId}:oidc-provider/${OIDCProviderUrl}"
                  },
                  "Action": "sts:AssumeRoleWithWebIdentity",
                  "Condition": {
                    "StringEquals": {
                      "${OIDCProviderUrl}:aud": "sts.amazonaws.com"
                    },
                    "StringLike": {
                      "${OIDCProviderUrl}:sub": "system:serviceaccount:${KubernetesNamespace}:securiti-*"
                    }
                  }
                }
              ]
            }
          - OIDCProviderUrl: !Ref OIDCProviderUrl
            KubernetesNamespace: !Ref KubernetesNamespace
      Policies:
        - PolicyName: AssumeSecuritiMasterRole
          PolicyDocument:
            Version: '2012-10-17'
            Statement:
              - Effect: Allow
                Action: sts:AssumeRole
                Resource: !Sub arn:aws:iam::${AWS::AccountId}:role/${ScanMasterRoleName}
Outputs:
  IRSARoleArn:
    Description: IRSA Role ARN — use this in your EPODv2 helm override file for all service accounts
    Value: !GetAtt EPODv2IRSARole.Arn
```
  2. **Deploy the Stack:**

Run the following command to create the stack:

```plaintext
aws cloudformation create-stack \
  --stack-name securiti-irsa-role \
  --template-body file://irsa-role.yaml \
  --parameters \
    ParameterKey=EKSClusterName,ParameterValue=<YOUR_CLUSTER_NAME> \
    ParameterKey=OIDCProviderUrl,ParameterValue=<OIDC_PROVIDER_URL_WITHOUT_HTTPS> \
    ParameterKey=KubernetesNamespace,ParameterValue=securiti \
  --capabilities CAPABILITY_NAMED_IAM
# Wait for completion
aws cloudformation wait stack-create-complete \
  --stack-name securiti-irsa-role
# Retrieve the role ARN
aws cloudformation describe-stacks \
  --stack-name securiti-irsa-role \
  --query "Stacks[0].Outputs[?OutputKey=='IRSARoleArn'].OutputValue" \
  --output text
```
- Using AWS Console:
  1. Navigate to **IAM** → **Roles** → **Create role.**
  2. On the **Create role page**, under T**rusted entity type**, choose **Web identity**.
  3. For Identity provider, choose your OIDC provider from the dropdown. See the example below. *oidc.eks.<region>.amazonaws.com/id/<ID>*
  4. For **Audience**, enter `sts.amazonaws.com` .
  5. Add a condition using `StringLike` to match all EPODv2 service accounts:
    - Condition operator: `StringLike`
    - Condition key: <your-oidc-provider>:sub
    - Condition value: `system:serviceaccount:securiti:securiti-*`
  6. Click **Next** and skip adding managed policies.
  7. Add a name of role. See the example below. *<cluster-name>-securiti-epodv2-irsa*
  8. Click **Create role.**
  9. Open the newly created role, under the **Permissions** tab, click **Add** **permissions** → **Create inline policy.**
  10. Choose the JSON editor and paste the following code:

```plaintext
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "sts:AssumeRole",
      "Resource": "arn:aws:iam::<ACCOUNT_ID>:role/SECURITI_S3_MASTER_ROLE_EPOD_V2"
    }
  ]
}
```
  11. Name the policy AssumeSecuritiMasterRole and save
  12. Copy the Role ARN from the role summary. You need this Role ARN for the following procedures:
    - Establish Trust Between the IRSA Role and the SCAN_MASTER Role
    - Configure EPODv2 via Helm Values Override

## Step 2 - Establishing trust between the IRSA role and the SCAN_MASTER role

The SCAN_MASTER role, such as `SECURITI_S3_MASTER_ROLE_EPOD_V2` already exists in your account. By default, it trusts the EC2 service (node IAM role scenario). You need to add one trust statement that allows the IRSA role created in [Step 1](/latest/docs/irsa-authentication-steps-for-iam-role-in-securitii#step-1-creating-and-configuring-an-irsa-role-in-aws) above to assume it.

> [!WARNING]
> Important
> 
> Do not remove any existing trust statements. Only add the new one. Removing the EC2 trust entry breaks deployments that do not utilize IRSA.

Perform the following steps to establish the trust between the IRSA role and the SCAN_MASTER role:

1. Record the IRSA Role ARN. If you haven't already, retrieve it using the following command.

```plaintext
aws iam get-role \
  --role-name <CLUSTER_NAME>-securiti-epodv2-irsa \
  --query "Role.Arn" \
  --output text
```
2. Update the SCAN_MASTER Role Trust Policy. Use one of the following options to update the SCAN_MASTER Role Trust Policy
  - ### Using AWS CLI:
    - Fetch the existing trust policy and save it locally.

```plaintext
MASTER_ROLE_NAME=SECURITI_S3_MASTER_ROLE_EPOD_V2
IRSA_ROLE_ARN=arn:aws:iam::<ACCOUNT_ID>:role/<CLUSTER_NAME>-securiti-epodv2-irsa

# Fetch the current trust policy
aws iam get-role \
  --role-name ${MASTER_ROLE_NAME} \
  --query "Role.AssumeRolePolicyDocument" \
  --output json > current-trust-policy.json
```
    - Open current-`trust-policy.json` adn add the following object to the statement array:

```plaintext
{
  "Effect": "Allow",
  "Principal": {
    "AWS": "arn:aws:iam::<ACCOUNT_ID>:role/<CLUSTER_NAME>-securiti-epodv2-irsa"
  },
  "Action": "sts:AssumeRole"
}
```

The complete updated trust policy should look like this:

```plaintext
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "ec2.amazonaws.com",
        "AWS": "arn:aws:iam::<ACCOUNT_ID>:root"
      },
      "Action": "sts:AssumeRole"
    },
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::<ACCOUNT_ID>:role/<CLUSTER_NAME>-securiti-epodv2-irsa"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```
    - Apply the updated policy.

```plaintext
aws iam update-assume-role-policy \
  --role-name ${MASTER_ROLE_NAME} \
  --policy-document file://updated-trust-policy.json
```
  - #### Using AWS Console
    - Navigate to **IAM** → **Roles** → **.**
    - Open the **Trust relationships** tab.
    - Click **Edit trust policy.**
    - Inside the Statement array, add the following block after the existing entries:

```plaintext
{
  "Effect": "Allow",
  "Principal": {
    "AWS": "arn:aws:iam::<ACCOUNT_ID>:role/<CLUSTER_NAME>-securiti-epodv2-irsa"
  },
  "Action": "sts:AssumeRole"
}
```
    - Click **Update policy**.

After saving, the trust policy should list at least two statements:
      - The original one and the new one trusting the IRSA role.

## Step 3: Configuring EPods V2 using Helm values override

With the IAM role in place, pass the IRSA role ARN to the EPODv2 Helm chart using a values override file. The same ARN is utilized for all six service accounts; the chart annotates each one with it, and EKS injects the IRSA credentials into the corresponding pods automatically.

1. Download the `values.yaml` from Securiti EPODv2 instance and add the additional key values, mentioned below.

```plaintext
global:
    irsa:
      annotations:
        eks.amazonaws.com/role-arn: <IRSA_ROLE_CREATED_EARLIER>
```
2. Apply it during your next Helm upgrade:

```plaintext
helm upgrade securiti-appliance ./helm/appliance \
  -f values.yaml \
  --namespace securiti
```
3. After the successful upgrade, verify the annotation was applied to each service account.

```plaintext
for SA in \
  securiti-config-controller \
  securiti-connector-aws-s3 \
  securiti-download-worker \
  securiti-connector-policy \
  securiti-file-quarantine-revert-worker \
  securiti-iaas-connector; do
    echo "--- ${SA} ---"
    kubectl get serviceaccount ${SA} -n securiti \
      -o jsonpath='{.metadata.annotations.eks\.amazonaws\.com/role-arn}'
    echo
done
```

> [!NOTE]
> Note
> 
> Each service account should return the same IRSA role ARN.

## Step 4 - Verifying that each pod receives the IRSA credentials

1. Once the pods are running, confirm IRSA is active.

```plaintext
# Check that IRSA environment variables are injected into a pod
kubectl exec <POD_NAME> -n securiti -- env | grep AWS
```

Expected output:

```plaintext
AWS_ROLE_ARN=arn:aws:iam::<ACCOUNT_ID>:role/<CLUSTER_NAME>-securiti-epodv2-irsa
AWS_WEB_IDENTITY_TOKEN_FILE=/var/run/secrets/eks.amazonaws.com/serviceaccount/token
```
2. Confirm the pod identity resolves to the IRSA role, not the node role.

```plaintext
kubectl exec <POD_NAME> -n securiti -- aws sts get-caller-identity
```

> [!NOTE]
> Note
> 
> The Arn field should contain your IRSA role name, not the EC2 node instance profile.

## Troubleshooting

### Pod does not have AWS_ROLE_ARN set

The EKS pod mutation webhook injects IRSA credentials only when the service account has the eks.amazonaws.com/role-arn annotation. Verify the annotation exists.

```plaintext
kubectl get serviceaccount <SERVICE_ACCOUNT_NAME> -n securiti -o yaml
```

If the annotation is missing, check if `irsa.enabled: true` is specified in your override file and re-run the Helm upgrade.

### AccessDenied when the workload tries to assume the SCAN_MASTER role

The SCAN_MASTER role's trust policy does not yet include the IRSA role. Review Step 2 and ensure the IRSA role ARN in the trust policy matches exactly with the one created in Step 1 above.

### AccessDenied when calling sts:AssumeRoleWithWebIdentity

The IRSA role's trust policy has a mismatch. Common causes include:

- The `sub` condition pattern does not match the actual service account name or namespace
- The OIDC provider URL included in the trust policy does not correspond to the cluster's OIDC issuer
- The OIDC provider is not registered in IAM

Check the registered OIDC providers.

```plaintext
aws iam list-open-id-connect-providers
```

Confirm that the provider URL from aws eks describe-cluster is present in this list.

### Token file not found inside the pod

1. Check the pod volumes.

```plaintext
kubectl describe pod <POD_NAME> -n securiti | grep -A5 "Volumes"
```
2. Look for a volume named `aws-iam-token`. If it is absent, the EKS pod identity webhook may not be running. Verify with the following.

```plaintext
kubectl get mutatingwebhookconfiguration | grep eks
```

## FAQs

#### What is IAM Roles for Service Accounts (IRSA)?

IAM Roles for Service Accounts (IRSA) is an AWS-native mechanism that allows individual Kubernetes pods to assume dedicated IAM roles instead of inheriting permissions from the underlying EKS node's IAM role.

#### What prerequisites are needed to create an IRSA role?

You need an EKS cluster with the OIDC provider enabled, AWS CLI installed with sufficient IAM permissions, the name of the Kubernetes namespace where EPODv2 is installed, the name of your EKS cluster, and the ARN of your existing CONNECTOR_SCAN_MASTER role.

#### How can I verify that the IRSA is active in my pods?

You can verify that IRSA is active by checking the environment variables in a running pod. Use the command '`kubectl exec &nbsp;-n securiti -- env | grep AWS`' and confirm that the AWS_ROLE_ARN is set to your IRSA role.
