---
title: "Acquire authentication credentials in Alibaba Cloud OSS"
slug: "acquire-authentication-credentials-in-alibaba-cloud-oss"
updated: 2026-07-04T22:14:26Z
published: 2026-07-04T22:14:26Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-alibaba-cloud-oss"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Alibaba Cloud OSS

1. Log in to the Alibaba Cloud portal.
2. Alibaba OSS uses the following input params for connector activation:
  - AccessKey Token
  - AccessKey Secret
  - Bucket Name
  - Region (Bucket Endpoint)
  - Path (created by the user at the time of uploading data to Alibaba Cloud).
3. Create a bucket:
  1. On the product page, select **Activate OSS**, as shown below.

![activate_oss.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b58e0c63-cbda-91b1-1dd3-66f2d162cba0.png)

Near the upper right corner of the page, select **Console**.
  2. In the upper left corner of the Alibaba Cloud dashboard (referred to herein as a dashboard), click the **menu icon** (three horizontal lines).

![menu_icon.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9ff69e03-e6f8-52ea-caa4-43784495ee99.png)

Then **Products and Services > Storage & CDN > Object Storage Service** (referred herein as OSS console).

![object_storage_service.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9007b996-c11f-9a9f-ba40-592b82187dd7.png)

> [!NOTE]
> **Note**
> 
> You can also use the search bar in Products and Services to find Object Storage Service.
  3. On the OSS console, click **Create Bucket** under Bucket Management, as shown below.

![create_bucket.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-38d8cb0e-eb79-3afb-3d91-dc839c145d5e.png)
  4. Enter **Bucket Name** (used for connector activation), Region (not OSS data center's), and make other appropriate selections.

![enter_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9ab4912c-cbf5-fc56-d80e-7e24b0e46f4a.png)

Click **OK**
  5. On the dashboard, select **Buckets >** (your Bucket) **> Overview** in the left-hand menu.

![buckets.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-562d889b-3c04-de23-f02f-81829da6ded0.png)
  6. Record the region without **.aliyuncs.com** under Endpoint for later use, as shown below.

![endpoint.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-83c6bbe2-0ffc-4977-b1a5-33523feee004.png)
4. Use the following methods to obtain AccessKey Pair, AKA AccessKey Token and Secret.
  - Using Alibaba Cloud account:
    1. Select **Obtain AccessKey** on the OSS console.

![obtain_accesskey.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-67f489ec-13b5-459e-5bc5-f01bdc46de57.png)
    2. Click **Create AccessKey** to generate AccessKey Id and AccessKey Secret.

![accesskey_id_and_secret_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a0999f77-ca46-5380-df88-e57afbd640a6.png)
    3. Record them to use later.
  - Using RAM user:
    1. On the dashboard, select **Products and Services > Monitor and Management > Resource Access Management**.

![resource_access_management.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2846bcf0-7d7b-7456-0005-2dffb0874c47.png)

> [!NOTE]
> **Note**
> 
> You can also use the search bar in Products and Services to find Resource Access Management.
    2. On the following page, select **Users** under RAM on the left-hand menu. Then click **Create User**.

![create_user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c7e753a2-dedf-843b-9b3e-5f0a0f134348.png)
    3. Provide the appropriate Logon Name, Display Name, and mark the **Programmatic Access** checkbox under Access Mode.

![programmactic_access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba4f1062-82cd-725f-fe57-0ce6e1964dc2.png)

Click **OK**
    4. In User Information, record AccessKey Id and AccessKey Secret to use later.

![accesskey_and_secret_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ff8a3e4-4489-b6ac-61a8-bc7f1258db44.png)
    5. Select **Buckets > Access Control > Bucket Policy** on the OSS console and grant Bucket access to the user you created above.

![bucket_policy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-827b0ec6-ac34-183f-b819-8e674111d67c.png)
    6. Click **Configure**, then **RAM Users** under Authorize, as shown below.

![ram_users.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d776bd4-62c8-11a5-146a-583abe70069d.png)

Click **OK**
5. Proceed to [Connecting Alibaba Cloud OSS with Securiti](/latest/docs/connecting-alibaba-cloud-oss-with-securiti).

## Related

- [Configure discovery scans for Alibaba Cloud OSS](/configure-discovery-scans-for-alibaba-cloud-oss.md)
- [Fulfilling DSR requests in Alibaba OSS](/fulfilling-dsr-requests-in-alibaba-oss.md)
