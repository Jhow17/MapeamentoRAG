---
title: "Obtain the access token in Quickbase"
slug: "obtain-the-access-token-in-quickbase"
updated: 2026-07-09T04:55:52Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/obtain-the-access-token-in-quickbase"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain the access token in Quickbase

## Acquiring Credentials in Quickbase

Quickbase uses the following parameters for Connector Activation.

- Realm name (Domain name)
- User Token

### Steps to acquire the Credentials

> [!NOTE]
> **Note**
> 
> This procedure assumes you have an admin account in Quickbase or you have authorization to create a Token.

Use the matching procedure below to acquire the Credentials.

1. Log in to your [Quickbase](/docs/https//proton-6243.quickbase.com/) account.
2. On the Quickbase Dashboard in the upper right corner, click on the username menu, and choose **My preferences.**

![step2-token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c832f32d-8c4d-13e1-644b-bef2aabaacec.png)
3. On the **My preferences** page in the **My User Information** section, click on **Manage User Tokens** link.

![step3-token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-50a29a8f-813f-56f1-9b88-6ddba7605b97.png)
4. On the **My Users Token** page in the top right corner, click **+ New user Token**.

![step4-token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b9241322-1853-e0d6-ae37-75c173fbba66.png)
5. Enter the following information on the **Create a new Token** page:

| Parameters | Description |
| --- | --- |
| Name | Enter the convenient name of the Token according to your preference. |
| (Optional) Description | Enter the description of the Token and related applications. |
| Assign Token to apps | Select the apps from the **Assign Token to apps** menu you want to assign them a Token. |

On the right top corner of the page, click **Save** to generate the Token

![step5-token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86e0e736-9493-519c-70eb-5e8ea8cdd237.png)
6. Go back to the **My Users Token** page, copy the **Token** for your newly created app, and save it for the Connector Activation.

![step6-token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1074fd62-cd61-478f-158a-d15ce5b4925f.png)
7. From the URL, save the Domain name (Realm Name) provided by Quickbase for Connector Activation. It ends with quickbase.com.

![url-quickbase.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bcde8fd3-bede-2439-65f1-4b1dd418d51a.png)
8. Proceed to [Connect Quickbase connector with Securiti](/latest/docs/connect-quickbase-connector-with-securiti).
