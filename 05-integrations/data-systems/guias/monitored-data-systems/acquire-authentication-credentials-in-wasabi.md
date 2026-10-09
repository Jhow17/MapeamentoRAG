---
title: "Acquire authentication credentials in Wasabi"
slug: "acquire-authentication-credentials-in-wasabi"
updated: 2025-10-31T06:39:46Z
published: 2025-11-03T07:38:02Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-wasabi"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Wasabi

1. Log in to the Wasabi web portal.

The Wasabi Connector takes the following parameters as input:
  - Access key or Token Id
  - Secret key or Token Secret
  - Region
  - Bucket
  - Path (optional)
2. To obtain the Access Key and Secret Key:
  1. On the home page left menu, click **Access Keys**.

![wasabi-access-keys.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-40ad214a-4af2-a3b1-dd24-5ee37d4a4b9b.png)
  2. near the upper right corner of the page, click **Create New Access Key**.

Mark the **Root User** radio button, then click **Create**.

![wasabi-create-new-key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-00cd11db-5f36-0b81-cbbe-8a00ce40d092.png)

Wasabi shows you both Access and Secret keys as shown below.

![access-key-secret-key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-acf6b7b5-701f-598c-02ad-df7f54ca3937.png)
  3. Record the Access and Secret keys to use later.
3. Obtain the Region and Bucket name:
  1. On the home page, click **Buckets** on the left-hand side menu.
  2. From **Bucket List**, record the **Bucket Name** and corresponding **Region** to use later as shown below.

![wasabi-bucket-list.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-134f91ef-add1-02ab-3d6e-e9913efdfed9.png)

> [!NOTE]
> **Note**
> 
> This procedure assumes that the you have the (data) bucket available prior to scanning.

Important points to consider:
    - Bucket List contains multiple buckets and each bucket has an object in it.
    - A bucket can also contain a folder.
    - A folder can contain multiple folders in it.
    - Each folder can contain files in it.
    - The Connector scans one bucket at a time.
4. Proceed to [Activate the Wasabi connector in Securiti](/v1/docs/activate-the-wasabi-connector-in-securiti).
