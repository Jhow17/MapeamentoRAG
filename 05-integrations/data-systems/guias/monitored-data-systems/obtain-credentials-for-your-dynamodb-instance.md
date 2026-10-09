---
title: "Obtain credentials for your DynamoDB instance"
slug: "obtain-credentials-for-your-dynamodb-instance"
updated: 2026-08-28T08:17:14Z
published: 2026-08-28T08:17:14Z
canonical: "helpcenter.securiti.ai/obtain-credentials-for-your-dynamodb-instance"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials for your DynamoDB instance

Before you can activate the DynamoDB connector, you must obtain credentials from your AWS Management Console:

1. Log in to your AWS Management console with administrative credentials at <*https://signin.aws.amazon.com*>.

![DynamoDB_Login.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3ff37319-a89a-2f35-6c9c-d5b7c437f9ce.png)
2. Navigate to the **console's Identity and Access Management (IAM)** section.

![DynamoDB_FindIAM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b1fd668e-0e60-8340-7f32-0d3bb2946145.png)
3. In the left sidebar, click **Users** and select the user account you want to synchronize with Securiti.

![DynamoDB_FindUsers.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b1e8a05a-ef0c-f699-eb4e-79a49428cbbc.png)

Amazon shows the summary page for the user.
4. Navigate to the **Security** tab and record the **Access** and **Secret** keys to use later.

![DynamoDB_Credentials2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-48b54037-77ad-7553-4ca5-1c74b30e8631.png)
5. For the Role-based authentication, do the following:
  1. Near the upper right corner of the IAM dashboard, select **Roles** and click **Create role**.

![create_roles.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-975b0e57-c20e-e4db-e808-60f8ea0b3755.png)
  2. On the Select trusted entity page, choose **AWS service** as your "Trusted entity type," and near the bottom of the page, mark the **EC2** radio button for "Common use cases."

![trusted_entity.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d0fd58ea-0459-d28f-322a-2a16515bda56.png)

Click **Next**
  3. Click **Create policy** on the Add permissions page.

![add_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9a6668d5-6df1-5bf0-a06e-7093c1a4b7ed.png)
  4. Add the permissions for the role you created in the previous step, as shown in the example below.

```plaintext
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowDynamoDBTableGetAndScanPermission",
            "Effect": "Allow",
            "Action": [
                "dynamodb:BatchGetItem",
                "dynamodb:DescribeStream",
                "dynamodb:DescribeTable",
                "dynamodb:GetItem",
                "dynamodb:GetRecords",
                "dynamodb:GetShardIterator",
                "dynamodb:PartiQLSelect",
                "dynamodb:Query",
                "dynamodb:Scan"
            ],
            "Resource": "arn:aws:dynamodb:*:162495629559:table/*"
        },
        {
            "Sid": "AllowDynamoDBListPermission",
            "Effect": "Allow",
            "Action": [
                "dynamodb:ListTables",
                "dynamodb:ListGlobalTables",
                "dynamodb:ListStreams"
            ],
            "Resource": "*"
        }
    ]
}
```

![JSON_input.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-64d55da9-a5fb-59c1-6d25-8c7017367d7d.png)
  5. Enter a name for that role, for example, "SECURITI-DYNAMODB-SCAN-ROLE."

![enter_name_create_policy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fcc29e2-6141-0b1e-19fd-c19adea0b8cd.png)

Near the bottom of the page, click "Create policy."
  6. After creating the role, complete the following additional AWS setup to allow the pod to authenticate successfully:

For the console steps to attach the IAM role and create an inline policy, see [Attach IAM Role and create a policy for the EC2 instance](/latest/docs/attach-iam-role-and-create-policy-for-ec2-instance). Use the JSON shown above.
    1. In the EC2 console, select the instance, then choose **Actions** > **Security** > **Modify IAM role**, and select the role you created to attach it to the EC2 instance hosting the pod.
    2. Add a statement to the role's trust policy that allows the role to assume itself, in addition to the existing `ec2.amazonaws.com` trust statement:

```plaintext
{
  "Effect": "Allow",
  "Principal": { "AWS": "arn:aws:iam::<account-id>:role/<role-name>" },
  "Action": "sts:AssumeRole"
}
```
    3. Add an inline policy on the role granting it permission to call `sts:AssumeRole` on itself:

```plaintext
{
  "Effect": "Allow",
  "Action": "sts:AssumeRole",
  "Resource": "arn:aws:iam::<account-id>:role/<role-name>"
}
```

1. Proceed to [Connecting Amazon DynamoDB (self-hosted) with Securiti](/latest/docs/new-ui-connecting-amazon-dynamodb-self-hosted-with-securiti), or [Connecting Amazon DynamoDB (Securiti cloud) with Securiti](/latest/docs/new-ui-connecting-amazon-dynamodb-securiti-cloud-with-securiti).
