---
title: "(Optional) Configure the Hashicorp OAuth token for Microsoft Dataverse"
slug: "optional-configure-the-hashicorp-oauth-token-for-microsoft-dataverse"
updated: 2026-07-20T20:15:44Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/optional-configure-the-hashicorp-oauth-token-for-microsoft-dataverse"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Configure the Hashicorp OAuth token for Microsoft Dataverse

> [!WARNING]
> **Important**
> 
> Before obtaining the refresh Token, we assume you have performed the steps for each Table you want to scan as outlined in the [Grant permissions and obtain credentials in Microsoft Dataverse](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-dataverse).

If you want to use Hashicorp credential vaults to store and manage OAuth Credentials for the Microsoft Dataverse Self-hosted Data system:

1. If you haven’t already done so, configure the Hashicorp Vault as described in [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault), with specific attention to the subsection on OAuth Authentication.
2. For the settings in the following Table, use Postman ([https://www.postman.com](https://www.postman.com)) or a similar tool to initialize the access Token flow for the Data system, as shown below.

| Setting | Value |
| --- | --- |
| Callback URL | Add the Callback URL you added as Redirect URl in the Microsoft Dataverse app creation procedure |
| Auth URL | https://login.microsoftonline.com/{{account_id}}/oauth2/authorize |
| Access Token URL | https://login.microsoftonline.com/{{account_id}}/oauth2/v2.0/Token |
| Client ID | The Client ID you recorded earlier |
| Client Secret | The Client Secret you recorded earlier |
| Scopes | ```plaintext {{host_url}}/.default offline_access ``` |

![hashicorp-credentials.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-55953c70-be2f-d5ff-083f-69fa87db3831.png)
3. Scroll down to **Advanced** section. Under the **Token Request**, set the scope as follows:

| Setting | Description |
| --- | --- |
| Key | Add scope in the Key. |
| Value | Set the value as {{host_url}}/.default offline_access. See the example below. *https://orgb341e717.api.crm.dynamics.com/.default offline_access* |
| Send In | Select the Request Body from the menu. |

![postman-scopes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba414053-a7c1-74a5-31c0-f1978a34790b.png)
4. Click **Get New Access Token**. It redirects you to the Microsoft Dataverse consent page.
5. Use these commands in the vault plugin to initiate the Token refresh flow:

```plaintext
vault write my-secrets/servers/microsoft_dataverse 
provider=custom client_id={{client_id}} 
client_secret={{client_secret}} 
provider_options=token_url={{token_url}}

vault write my-secrets/creds/microsoft_dataverse 
server=microsoft_dataverse grant_type=refresh_token 
refresh_token={{refresh_token}
```
6. Proceed to [Connect Microsoft Dataverse connector with](/latest/docs/connect-microsoft-dataverse-connector-with-securiti) Securiti.
