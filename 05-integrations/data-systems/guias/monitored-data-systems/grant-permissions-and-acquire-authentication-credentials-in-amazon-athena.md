---
title: "Grant permissions and acquire authentication credentials in Amazon Athena"
slug: "grant-permissions-and-acquire-authentication-credentials-in-amazon-athena"
updated: 2026-07-01T15:35:10Z
published: 2026-07-01T15:35:10Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-acquire-authentication-credentials-in-amazon-athena"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and acquire authentication credentials in Amazon Athena

1. Log in to AWS Athena.
2. > [!NOTE]
> **Note**
> 
> This procedure assumes that the user has the database available prior to connector activation (where applicable). Also, you have enabled these permissions:
> 
> ```plaintext
> Actions:
> [
>                 "glue:GetTable",
>                 "glue:GetDatabase",
>                 "glue:GetTables",
> ]
> "Resource": [
>                 
>                 "arn:aws:glue:us-west-2:162495629559:database/default",
>                 "arn:aws:glue:us-west-2:162495629559:schema/*",
>                 "arn:aws:glue:us-west-2:162495629559:table/*/*",
>                 "arn:aws:glue:us-west-2:162495629559:catalog"
>             ]
> ```

Take note of the following parameters for connector activation:
  - **AWS Region** is your Athena region.
  - **AWS Access Key** is your account access key that has Athena permissions.
  - **AWS Secret Key** your account secret key that has Athena permissions.
  - **S3 Output Location** is your S3 bucket for result storage. This is the location in Amazon S3 where query and calculation results are stored. For example, the output can be stored in a specified S3 bucket path like `s3://path/to/query/bucket/`.
3. To obtain AWS Access Key and Secret Key:
  1. On the dashboard, select **IAM**.

![01-iam.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b5e5f8f4-42da-9295-fc3d-bb83dd63920f.png)
  2. Under "Users", click **Add user**.

![02-add-user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b5dd01b2-108c-fb53-a87a-ae904f1eacf9.png)
  3. Give your user a name. In **Select AWS access type > Access type**, mark the "Programmatic access" checkbox as shown below.

![03-user-details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ef0a7192-604b-813c-de14-41989fff3006.png)
  4. Click **Next: Permissions**.
  5. On the "Set permissions" page, select **Attach existing policies directly**. Then choose **AmazonAthenaFullAccess** in *Filter policies* as shown below.

![04-user-permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4a27d863-e7da-9f5a-a2a7-1026bc0f1f4e.png)
  6. Click **Next: Tags**
  7. A review page is displayed. Review your choices and click **Create user** as shown below.

![05-review.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b51221db-8640-a377-d04f-d209ceb4c5ee.png)
  8. Save the **Access key ID** and **Secret access key** (*click Show to reveal key*) for later use.

![06-access-keys.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cd80eb7d-bd49-472a-3049-853da283c860.png)
  9. Hit **Close** near the bottom of the page to exit. A "Summary" of your *Security credentials* is displayed.

![07-more-access-keys.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6240ea85-293b-643c-8da9-825df0124b0a.png)
4. Near the top right corner of the Amazon Athena start page, click **Global > US West (Oregon) (us-west-2)** for "AWS Region" as shown below.

![08-athena-region.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e0655d89-e74b-3121-0b82-b36a2fec3b53.png)
5. Proceed to [Connecting Amazon Athena with Securiti](/latest/docs/connecting-amazon-athena-with-securiti).
