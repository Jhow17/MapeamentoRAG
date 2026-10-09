---
title: "Configuring identity verification with Jumio"
slug: "configuring-identity-verification-with-jumio"
updated: 2025-10-30T19:20:25Z
published: 2025-11-03T07:39:28Z
canonical: "helpcenter.securiti.ai/configuring-identity-verification-with-jumio"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Configuring identity verification with Jumio

You can configure Securiti to use Jumio as an identification verification feature for DSR requests. Jumio is an Identity verification provider used by many large retailers. It provides ID verification services using the data subject’s identity documents and a selfie photo.

After you configure this feature, Securiti verifies data subject identities as described for Jumio in [How Securiti verifies data subject identity](/v1/docs/how-securiti-verifies-data-subject-identity).

> [!NOTE]
> **Note**
> 
> This feature is available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to activate this feature for your account.

Once this feature is enabled for your Securiti account, do these procedures in sequence to configure identity verification with Jumio:

### Collect API credentials in Jumio

1. In the Jumio portal, click **Settings**, then choose **API Credentials**.
2. Record both the token and secret for an existing active token for which both Initiate and Retrieve & Delete are enabled as shown below. If you already have such a token, you can use it. If not, create one.

![RN_DSR_Jumio1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7d60340a-bc26-9da4-3ffa-c577c8e8cce3.png)

### Configure the Jumio instance in Securiti

1. In Securiti, open **Data Subject Rights**, then choose **Settings > Identity Verification**.
2. On the card for Jumio, click **Create Instance** and apply these settings:

| Setting | Description |
| --- | --- |
| Instance Name | A descriptive name |
| Service URL | Choose the data center at which your Jumio account is hosted. You can get this information from Jumio support. The available options are: - netverify.com - lon.netverify.com - core-sgp.jumio.com |
| API Token | Paste the API token you recorded in the Jumio portal. |
| API Secret | Paste the API secret you recorded in the Jumio portal. |
| Verification Type | Choose either ID Only or ID and Identity Verification, depending on the services you are subscribed to in Jumio. |
| Capture Method | Choose Camera, Upload, or Camera or Upload, depending on the services you are subscribed to in Jumio. |
| Link Expiry Minutes | Choose the lifespan for the link sent to the data subject in minutes. The minimum is 30 minutes, the maximum is 86400 minutes (60 days). |
| Enable Liveness | (Optional) Enable liveness check if you are subscribed to that feature in Jumio. |

![RN_DSR_Jumio2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d0a60782-9626-9d60-69c3-03d15b970e3a.png)
3. Near the upper right corner of the page click **Test and Activate**. Securiti validates the Jumio credentials and settings, and then activates the instance.

### Configure your DSR forms to use Jumio for identity verification

After configuring the Jumio instance, you next configure your DSR forms to use ID verification by Jumio:

1. In Securiti, open **Data Subject Rights** and choose **Settings > Form Builder**.
2. Choose the form you want to use, or create a new one.
3. On the Form Settings tab, mark the checkbox for **External ID verification** and choose **Jumio** as the ID verification service as shown below.

![RN_DSR_Jumio3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9c331cf7-1371-b89a-3fca-609839706553.png)
4. Configure other form settings to suit.
5. Click **Review & Publish** and then click **Publish** to publish the DSR request form.

## Related

- [How Securiti verifies data subject identity](/how-securiti-verifies-data-subject-identity.md)
