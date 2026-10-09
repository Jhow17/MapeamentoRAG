---
title: "Grant permissions and obtain authentication credentials for Securiti for Box"
slug: "grant-permissions-and-obtain-authentication-credentials-for-securiti-for-box"
updated: 2026-06-23T10:07:24Z
published: 2026-06-23T10:07:24Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-authentication-credentials-for-securiti-for-box"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain authentication credentials for Securiti for Box

> [!WARNING]
> **Important**
> 
> - You don't need to create a custom box application for Securiti for Box Connector. You only need an **Enterprise ID** for Connector Activation.
> - You must log in to the Box account with the **admin** role. **Non-admin** or **co-admin** role can cause issues in the Authentication and metadata syncs.

Perform the following steps to grant the necessary Permissions and get Authentication Credentials from Securiti for Box:

1. Log in with your Box account with admin Credentials to access the **Box dashboard**.

> [!WARNING]
> **Caution**
> 
> You must not use co-admin Credentials in login, only admin Credentials are required for accessing box account and avoiding scanning errors
2. For some Box subscriptions (Business Plus and higher), you must log in as administrator and accept a **Custom Terms of Service (ToS)** to let Securiti access your content.

> [!WARNING]
> **Important**
> 
> Securiti skips scanning for user's directly-owned data if the **Custom Terms of Service (ToS)** have not been accepted by that user. However, files owned by a skipped user may still be included in the scan if they are accessed via a collaborator who is within the scan's scope and has accepted the ToS.
3. From the left navigation bar in Admin Console, click **Account & Billing**.
4. On the **Account & Billing** page under the **Account Information** section, record the **Enterprise ID**.

![sfb_enterpriseID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ba334c9-3462-7ff8-d78f-78900ff4c613.png)

1. Proceed to [Connecting Securiti for Box (self-hosted) with Securiti](/latest/docs/new-ui-connecting-securiti-for-box-self-hosted-with-securiti).
