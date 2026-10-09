---
title: "Configuring AWS pod or elastic pod IAM role trust"
slug: "configuring-aws-pod-or-elastic-pod-iam-role-trust"
updated: 2026-02-12T06:20:41Z
published: 2026-02-12T06:20:41Z
canonical: "helpcenter.securiti.ai/configuring-aws-pod-or-elastic-pod-iam-role-trust"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Configuring AWS pod or elastic pod IAM role trust

When you deploy a pod or elastic pod on an EC2 instance to do data scanning in an AWS account, you must manually configure its IAM role so that it can be assumed by the CONNECTOR_SCAN_MASTER that Securiti creates on the account. You do this by creating a policy that lets the pod-role or elasticpod-role assume the CONNECTOR_SCAN_MASTER IAM role that Securiti creates on the AWS account so it can do data scanning. For more information, see [Policies and permissions required for AWS integration](/latest/docs/policies-and-permissions-required-for-aws-integration).

> [!NOTE]
> **Note**
> 
> The procedure explained below apply when the scan location is set to **My Cloud**. For more information on when to choose this option, see [My Cloud](/v1/docs/getting-started-with-iaas-cloud).

1. Log into the AWS console for the AWS account with your admin credentials.
2. In the AWS console, locate the EC2 instance for the pod or elastic pod and record the ARN for its IAM role.
3. In the console, navigate to **IAM > Roles**, and locate and open the connector scan master role.

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
