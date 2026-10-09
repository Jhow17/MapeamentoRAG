---
title: "Managing Webhook URLs"
slug: "managing-credentials-managing-webhook-urls"
updated: 2026-04-06T08:36:41Z
published: 2026-04-06T08:36:41Z
canonical: "helpcenter.securiti.ai/managing-credentials-managing-webhook-urls"
area: integrations
modulo: webhooks
tipo: guia
data_captura: 2026-10-08
---

# Managing Webhook URLs

You use Webhook URLs to integrate Securiti with other applications, usually using workflows as described in [Building and using workflows](/latest/docs/workflow-orchestration).

To create a new Webhook URL:

1. In Securiti, in the left main navigation menu, click the jewel icon and select **Integrations.**
2. In the **Integrations** page, from the left menu, select **Webhooks.**
3. On the Webhooks page, near the upper right corner click **Generate Webhooks URL**.
4. On the **Webhooks URL Parameters** popup, in the **Basic Information** section, apply the following settings:

| Setting | Description |
| --- | --- |
| Source App |  |
| Name |  |
| Description |  |
| Target Endpoint |  |
5. In the **Security & Authentication**, provide the credentials based on the selected authentication type.
  - For **Signature Based** authentication, provide the following credentials:
    - Signature Secret Key: Enter the shared secret used to generate the signature, preferably a random string with high entropy. For example, `mySuperSecretKey123`
    - Signature Header Name: Enter the HTTP header name that carries the generated signature. For example, `X-Securiti-Signature`
    - Signature Algorithm: Choose the hashing algorithm used to generate the signature from the menu, such as `Hmac-SHA1 Base64`
    - (Optional)Signature/Payload Send Time Header: Enter the header name used to send the timestamp of the webhook request. For example, `X-Securiti-Timestamp`
  - For **Key Based** authentication, provide the following credentials:
    - Access Key: Enter the authentication key used to validate the webhook request. For example, `abc123WebhookKey`
    - Header Name: Enter the HTTP header name that carries the access key. For example, `X-API-KEY`
    - (Optional) Signature/Payload Send Time Header: Enter a timestamp header to send the request time.
6. Click **Generate Webhooks URL**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/webhookURL.png)
7. At the bottom of the popup, copy the new Webhook URL to the clipboard to use later.

A webhook is a method for web applications to communicate with each other by sending automated, real-time data or notifications when specific events occur. It lets one application instantly trigger actions or updates in another.

## Related

- [Managing Securiti API keys](/managing-credentials-managing-securiti-api-keys.md)
- [Managing SSH keys](/managing-ssh-keys.md)
- [Using keyrings in Securiti](/creating-keyrings.md)
- [Creating keyrings for HashiCorp](/hashicorp-credential-vault-creating-keyrings-for-hashicorp.md)
