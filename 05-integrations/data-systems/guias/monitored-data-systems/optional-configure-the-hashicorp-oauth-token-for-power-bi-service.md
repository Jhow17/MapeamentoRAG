---
title: "(Optional) Configure the Hashicorp OAuth token for Power BI Service"
slug: "optional-configure-the-hashicorp-oauth-token-for-power-bi-service"
updated: 2026-07-31T09:47:05Z
published: 2026-07-31T09:47:05Z
canonical: "helpcenter.securiti.ai/optional-configure-the-hashicorp-oauth-token-for-power-bi-service"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Configure the Hashicorp OAuth token for Power BI Service

> [!WARNING]
> Important
> 
> To authenticate Power BI Service connector through Service Principal authentication, you must configure the OAuth as described in [Configuring OAuth token for Microsoft 365 applications](https://helpcenter.securiti.ai/docs/storing-data-system-credentials-in-hashicorp-vault#configuring-oauth-token-for-microsoft-365-applications).

If you want to use Hashicorp credential vaults to store and manage OAuth Credentials for the Power BI Service Data system:

1. If you haven’t already done so, configure the Hashicorp Vault as described in [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault), with specific attention to the subsection on OAuth Authentication.
2. Using the settings in the following Table, use Postman ([https://www.postman.com](https://www.postman.com)) or a similar tool to generate a refresh Token for the Data system using the authorization_code grant flow as shown below.

| Setting | Value |
| --- | --- |
| Client ID | The Consumer Key you recorded earlier |
| Client Secret | The Consumer Secret you recorded earlier |
| Auth URL | https://login.microsoftonline.com/{{account_id}}/oauth2/authorize |
| Access Token URL | https://login.microsoftonline.com/{{account_id}}/oauth2/v2.0/Token |
| Callback URL | Add the callback URL displayed in Redirect URLs of your app. |

![powerbi_postmanparams.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-daf3a99c-508a-307a-81e8-47fcce6b755d.png)
3. Click **Advanced** and set scope in the **Token Request** section. Eg; *https://analysis.windows.net/powerbi/api/.default offline_access*

![powerbi_generatetoken.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-124b7e2a-d143-6412-2e31-b24795361a22.png)
4. After postman provides you with the refresh Token, configure that refresh Token in the Hashicorp vault to initiate the refresh Token flow using the two commands shown in this example:

```plaintext
vault write my-secrets/servers/powerbi_service provider=custom client_id={{client_id}} client_secret={{client_secret}} provider_options=token_url={{token_url}}
vault write my-secrets/creds/powerbi_service server=powerbi_service grant_type=refresh_token refresh_token={{refresh_token}}
```
5. Proceed to [Connecting Power BI Service with Securiti](/latest/docs/connecting-power-bi-service-with-securiti).
