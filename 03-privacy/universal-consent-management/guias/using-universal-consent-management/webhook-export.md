---
title: "Webhook Export"
slug: "webhook-export"
updated: 2026-09-23T08:05:17Z
published: 2026-09-23T08:05:17Z
canonical: "helpcenter.securiti.ai/webhook-export"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Webhook Export

**Scenario**

As a Data Privacy Officer, you must ensure that consent updates collected across channels are consistently shared with connected systems that rely on consent status. However, when these updates remain limited to a single platform, connected systems such as marketing, CRM, or analytics tools may continue using outdated consent information. For instance, when a data subject withdraws consent through your preference center, your marketing system must immediately stop sending communications. With Securiti’s Webhook Export, you can stream consent updates in real time to connected systems, helping you enforce consent accurately, reduce risk, and keep systems aligned with data subject preferences.

You can export the consent records of your data subjects via the **Webhook** **Export** functionality. Webhook Export lets you export the stream of universal consent records to your external platforms in real time directly from the Universal Consent Management module.

> [!NOTE]
> **Note**
> 
> - If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

Webhook only receives **1000** consent records per call and Securiti provides these records in the JSON format. You can configure only one webhook per organizational unit in your Securiti tenant and also delete your webhook from the organizational units. Only the following roles can add, edit and delete the webhook per organization:

- Super Admin
- Organization Admin
- Module Owner

> [!WARNING]
> **Important**
> 
> Streaming consents via webhook is a failsafe operation. Securiti does not return any error or halt the operation if you delete the webhook while the streaming of consents is in progress.
> 
> We send out an alert email notification to the tenant admin if the webhook fails after retrying the operation **50** times. Securiti also sends out daily email notifications to the tenant admin if the webhook degrades.
> 
> You cannot ingest consent records into Securiti using webhooks. Securiti uses webhooks only to send consent records downstream to external systems.

To start exporting the stream of consent records:

1. In Securiti, open **Universal Consent Management** and choose **Advanced Settings** **> Webhook Export**.
2. On the **Webhook Export** page, configure the following authentication options to start exporting the consent records as shown below.

![Webhook_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e6fa7ea0-fcef-b16e-e0f0-698853032b75.png)

| Authentication Setting | Description |
| --- | --- |
| Webhook URL | Enter your complete webhook URL to connect Securiti with your platform. |
| Authentication Scheme | From the menu, choose the appropriate authentication scheme: - Basic - Bearer |
| Status | Mark the **Active** or **Inactive** radio button to update the status of your webhook. |
| Username | Enter your username for authentication. |
| Password | Enter your password for authentication. |
| Token | Enter your bearer token if you are opting for **Bearer** type authentication schema. |

1. Click **Save** near the upper right corner of the page to save your authentication and start receiving the stream of consent records.

> [!NOTE]
> **Note**
> 
> You start receiving the stream of consent records after **60 minutes** of configuring the webhook.
2. You can test the webhook connection to verify that it is working correctly. Click **Test Connection** to validate the connection, as shown below.

![Webhook_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9e30ec02-13ad-7262-eee5-9b0b50b34ae0.png)
3. If you configure the webhook successfully, Securiti displays the **Webhook test results** popup with a **200** response code, as shown below.

![Webhook export interface showing authentication details and test results for a webhook.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/success_code copy.png)

Securiti sends an empty payload, and receives a `HTTP` status code from the webhook endpoint.

To validate the incoming consent records, see a sample JSON consent record below.

```json
[
  {
    "activity_timestamp": 1781000899,
    "attribute_types": [
      "Tuesday",
      "Sunday"
    ],
    "collected_timestamp": 1781000913,
    "consent_granted": true,
    "consent_purpose_external_id": "FPP-1234",
    "consent_purpose_id": 1,
    "consent_purpose_name": "Weekly Newsletters",
    "consent_source": "Mobile App",
    "consent_source_id": 12,
    "consent_status": "GRANTED",
    "custom_parameters": null,
    "expiry_date": "",
    "ip_address": "X.X.X.X",
    "org_unit_id": 1,
    "processing_purpose_id": 1,
    "processing_purpose_name": "Email marketing",
    "source_type": "API-PURPOSE-CONSENT",
    "uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "uuids": "{\"uuid\":\"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\"}"
  },
]
```

## Authentication schemes

The authentication scheme lets you set authentication methods to validate the incoming requests. Securiti lets you configure two type of authentication schemes:

| Scheme | Description |
| --- | --- |
| Basic | Includes username and password. |
| Bearer | Single secret token. For instance, `+bN5u1hpfo36jTktg0IXhZQI0+aFzfRz0MIDSZsCU20=`. |

Whether **Basic** or **Bearer** authentication, Securiti sends them in `HTTP` request headers. The downstream system validates these credentials to verify the legitimacy of the request before processing the payload.

A webhook is a method for web applications to communicate with each other by sending automated, real-time data or notifications when specific events occur. It lets one application instantly trigger actions or updates in another.

A token is a small piece of data, typically in the form of a string, that serves as an authentication or authorization mechanism. It is used to verify the identity of a user or application and grant access to specific resources or functions. Tokens are commonly used for security and access control in API interactions.

## Related

- [Downloading universal consent records from the Legacy Dashboard](/downloading-the-universal-consent-records.md)
- [Understanding the Privacy Platform Integrations](/understanding-the-privacy-platform-integrations.md)
