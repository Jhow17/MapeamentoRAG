---
title: "Acquire authentication credentials in Okta"
slug: "acquire-authentication-credentials-in-okta"
updated: 2026-07-31T07:35:11Z
published: 2026-07-31T07:35:11Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-okta"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Okta

1. Log in to Okta admin.
2. Okta uses **Organization Url** and **API Token** for Connector Activation.

> [!WARNING]
> **Important**
> 
> The Organization Url is the same you've used to log in to the Okta admin page, as shown below.
> 
> https://<Organization Url>-[admin.okta.com/](/v1/docs/securiti-pods-and-elastic-pods)
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(628).png)
> 
> Record the URL to use later.
3. To acquire API Token:
  1. Select **Security > API** on the Okta left-hand side menu.

![security.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8e47fa03-6c2e-1781-d19e-1fa3cad9c507.png)

![API.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-939b9393-33ce-9424-e38b-80d3f4144d86.png)
  2. Select the **Tokens** tab and click **Create Token** on the API page, as shown below.

![create_token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa1576e2-5197-9661-4dae-f35987cdf0ca.png)
  3. Enter a name for your Token on the following pop-up and click **Create Token**, as shown below.

![enter_a_name_for_your_token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-afa74c36-9485-e30e-7719-45517aee1821.png)
  4. Record the generated API Token to use later.

![record_API_token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1af9b926-e7af-8b95-2766-d03611d79a1c.png)
4. Proceed to [Connect Okta connector with Securiti](/latest/docs/connecting-okta-connector-with-securiti).
