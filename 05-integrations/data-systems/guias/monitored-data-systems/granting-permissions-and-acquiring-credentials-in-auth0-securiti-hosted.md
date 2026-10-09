---
title: "Granting permissions and acquiring credentials in Auth0 (Securiti Cloud)"
slug: "granting-permissions-and-acquiring-credentials-in-auth0-securiti-hosted"
updated: 2026-09-11T13:03:04Z
published: 2026-09-11T13:03:04Z
canonical: "helpcenter.securiti.ai/granting-permissions-and-acquiring-credentials-in-auth0-securiti-hosted"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Granting permissions and acquiring credentials in Auth0 (Securiti Cloud)

1. Log in to the [Auth0 application](https://auth0.com/signup).
2. On the left sidebar, click **Applications** > **Applications**.

![step-2-cred-Auth0.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ee2b80af-f4a1-aac6-be02-eeb980e53f1b.png)
3. On the **Applications** page, click **+ Create Application**.

![step-3-cred-auth.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-20c5d98d-f3a0-de85-9fa8-47356456a028.png)
4. On the **Create Application** popup, do the following:

![step-4-cred-auth0.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-73d2cdce-858c-9665-73ec-a8a3ef4b6891.png)
  1. Enter the **Name** of your new App.
  2. Select **Machine to Machine Applications.**
  3. Click **Create**.
5. On the **Authorize Machine to Machine Application** popup, select **Auth0 Management API** from the menu.

![step-5-cred-auth.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f0f5d411-92b4-427d-76db-de955b48fc83.png)

> [!NOTE]
> **Important**
> 
> When configuring and using the Auth0 connector, be mindful of the following **Management API** rate limits based on your subscription plan as shown in the screenshot below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(623).png)
> 
> These rate limits apply per endpoint and on a per-tenant basis. If the limit is exceeded, API requests may be throttled or fail.
6. Under the **Permissions** section, mark the checkboxes for the following permissions.

Click **Authorize**. It redirects you to your newly created Auth0 application page.
  - read:users
  - read:organizations_summary
  - read:organizations
  - read:organization_members
7. On your Auth0 application page, click the **Settings** tab, and save the following information for later use:

You need these parameters to authenticate and activate the connector in Securiti.

![step-7-cred-auth0.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bdbfc0e5-6a1a-4213-0604-991e2dd3a574.png)
  - **Domain**
  - **Client ID**
  - **Client Secret**.
8. Scroll down to the **Advanced Setting** menu, and click the **Grant Type** tab. Mark the **Client Credentials** checkbox if not already marked by default.

![step-8-cred-auth0.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-62b0ecc2-088f-2922-bf6f-0626e27949c1.png)
9. Proceed to [Connecting Auth0 (Securiti Cloud) with Securiti](/latest/docs/connecting-auth0-securiti-cloud-with-securiti).
