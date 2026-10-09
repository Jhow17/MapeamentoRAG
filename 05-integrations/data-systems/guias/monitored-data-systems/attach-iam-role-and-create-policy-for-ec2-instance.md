---
title: "Attach IAM Role and create a policy for the EC2 instance"
slug: "attach-iam-role-and-create-policy-for-ec2-instance"
updated: 2026-07-04T22:18:35Z
published: 2026-07-04T22:18:35Z
canonical: "helpcenter.securiti.ai/attach-iam-role-and-create-policy-for-ec2-instance"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Attach IAM Role and create a policy for the EC2 instance

This topic covers the procedure to attach an IAM Role and create a policy for the EC2 instance.

1. **Attach the IAM Role to Your EC2 Instance**
  - For launching a new EC2 instance:
    1. When configuring the instance in the EC2 console, under **IAM role**, select your role as `EC2-RDS-IAM-Connect-Role`. For more information, see [Bytebase documentation](https://docs.bytebase.com/introduction/what-is-bytebase).
  - For existing EC2 instance:
    1. On your EC2 instance, choose **Actions** > **Security** > **Modify IAM role**.
    2. Attach the IAM role , as shown below. For instance, `SECURITI_C1_DEMO_MGMT_CLOUD`. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/attach-iam-role-and-create-policy-for-ec2-instance-image-vuj9ymxw.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/attach-iam-role-and-create-policy-for-ec2-instance-image-16n3nnat.png)
2. **Create an IAM Policy to Allow RDS IAM DB Connect.** To enable IAM authentication for Amazon RDS, you must create an IAM policy that grants the rds-db:connect permission for a specific database user.
  1. [Create the PostgreSQL database use](/latest/docs/obtain-permissions-and-authentication-credentials-in-amazon-rds-for-postgresql)r that will use IAM authentication.
  2. Create a custom IAM policy that allows database access for this user, as shown below.

```plaintext
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "rds-db:connect"
      ],
      "Resource": [
        "arn:aws:rds-db:<region>:<account>:dbuser:<resource id>/iamuser"
      ]
    }
  ]
}
```

Replace the following parameters:

| Parameter | Description |
| --- | --- |
| REGION | Replace it with the actual region, for instance us-east-1. |
| ACCOUNT_ID | Replace with your AWS account number. |
| DB_RESOURCE_ID | Replace with the resource ID of the RDS instance. you can get in the RDS console under **Configuration** > **DB resource ID.** |
| db_user_name | Replace with the PostgreSQL username you created in |
3. Create this policy in the Console:
  1. On your EC2 instance, choose the **security** tab.
  2. Click **IAM > Role** > **Permission** tab.
  3. On the **Permissions** tab, click **Add permissions** > **Create inline policy**.
  4. Select the **JSON** tab and paste the above JSON.
  5. Save it. **![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/attach-iam-role-and-create-policy-for-ec2-instance-image-s42cc8dh.png)![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/attach-iam-role-and-create-policy-for-ec2-instance-image-jpqqteed.png)**
4. Create reate this policy in the Console:
  1. Make sure the trust relationship includes your IAM role. In this example:
    1. Role name: SECURITI_C1_DEMO_MGMT_CLOUD
    2. AWS account ID: 162495629559 Use the following trust policy as a reference:

```plaintext
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::162495629559:role/SECURITI_C1_DEMO_MGMT_CLOUD"
      },
      "Action": "sts:AssumeRole"
    },
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "ec2.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```
