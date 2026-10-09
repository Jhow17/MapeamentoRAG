---
title: "Obtain authentication credentials from MinIO"
slug: "obtain-authentication-credentials-from-minio-s3-compatible-storage-en"
updated: 2026-06-22T13:54:43Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/obtain-authentication-credentials-from-minio-s3-compatible-storage-en"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain authentication credentials from MinIO

> [!NOTE]
> Note
> 
> - Policy creation is a prerequisite for creating a MinIO user. Ensure the policy includes the required permissions, as it must be assigned to the user.
> - This procedure assumes you have the privileges to create a user and assign policies in MinIO.

To create a user and assign a policy in MinIO, perform the following steps:

1. Log in to your MinIO account.
2. Create a policy and assign permissions to the policy:
  - To create a policy:
    1. On the left sidebar, click **Access**.
    2. On the top right of the **IAM Policies** page, click **Create Policy +**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/obtain-authentication-credentials-from-minio-s3-compatible-storage-en-image-f1ctr28z.png)
    3. On the **Create Policy** page, add the following parameters:|

| Parameter | Explanation |
| --- | --- |
| Policy Name | Add a convenient name for the custom policy. See the example below. *securiti-custom-policy* |
| Write Policy | Add a custom policy in the Write Policy section to assign the following permissions: - s3:ListBucket - s3:GetObject - s3:GetObjectTagging Paste the following policy to assign the above permissions: { "Version": "2012-10-17", "Statement": [ { "Effect": "Allow", "Action": [ "s3:ListBucket", "s3:GetObject", "s3:Get0bjectTagging" 1, "Resource": [ "arn:aws: s3:::*" ] } ] } |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/obtain-authentication-credentials-from-minio-s3-compatible-storage-en-image-xw30u6mu.png)
    4. Click **Save**. It shows you the newly added policy in the IAM Policies list, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/obtain-authentication-credentials-from-minio-s3-compatible-storage-en-image-y4bh96ce.png)
3. Create a user and assign the policy that you created above.
  1. On the left sidebar, choose **Identity** > **Users**.
  2. On the top right of the **Users** page, click **Create User +**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/obtain-authentication-credentials-from-minio-s3-compatible-storage-en-image-jd47e62n.png)
  3. On the **Create User** page, add the following parameters:

| Parameter | Explanation |
| --- | --- |
| User Name | Add a convenient name for the user. See the example below. *minio-user-access* Record the **User Name** to use it later as a **Token** for connector activation. |
| Password | Add a secure password for the user. See the example below. *minio-user-key* Record the **Password** to use it later as a **Secret** for connector activation. |
| Assign Policy | Mark the checkbox for the policy you want to assign to the user. You can select the policy you created above, as shown below. |
  4. Click **Save**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/obtain-authentication-credentials-from-minio-s3-compatible-storage-en-image-9ll384qp.png)
4. Proceed to [Connecting S3 Compatible Storage with Securiti](/latest/docs/connecting-s3-compatible-storage-with-securiti).
