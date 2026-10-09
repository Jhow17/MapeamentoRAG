---
title: "(Optional) Configure the Hashicorp OAuth token for Dropbox"
slug: "optional-configure-the-hashicorp-oauth-token-for-dropbox"
updated: 2026-03-10T05:11:16Z
published: 2026-03-10T05:11:16Z
canonical: "helpcenter.securiti.ai/optional-configure-the-hashicorp-oauth-token-for-dropbox"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Configure the Hashicorp OAuth token for Dropbox

If you want to use Hashicorp credential vaults to store and manage OAuth Credentials for the Dropbox Data system:

1. If you haven’t already done so, configure the Hashicorp Vault as described in [Using OAuth tokens for credentials](/v1/docs/managing-data-system-credentials-in-hashicorp-vault).
2. Using the settings in the following Table, use Postman ([https://www.postman.com](https://www.postman.com)) or a similar tool to generate a refresh Token for the Data system using the authorization_code grant flow as shown below.

| Setting | Value |
| --- | --- |
| Client ID | The App Key you recorded earlier |
| Client Secret | The App Secret you recorded earlier |
| Auth URL | https://www.dropbox.com/oauth2/authorize?token_access_type=offline |
| Access Token URL | https://api.dropboxapi.com/oauth2/Token |

![image7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-802049d8-2e5b-3461-20ce-ddbae029c48e.png)
3. Click **Sign In** to authorize the Token request.

![image3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bca93d76-403e-82f8-6d16-3c2a8b127812.png)
4. After postman provides you with the refresh Token, configure that refresh Token in the Hashicorp vault to initiate the refresh Token flow using the two commands shown in this example:

```plaintext
vault write my-secrets/servers/dropbox provider=custom client_id={{client_id}} client_secret={{client_secret}} provider_options=token_url=https://api.dropboxapi.com/oauth2/token
vault write my-secrets/creds/dropbox server=dropbox grant_type=refresh_token refresh_token={{refresh_token}} provider_options=custom_token_expiry=900
```

1. Proceed to [Activate the Dropbox connector in Securiti](/v1/docs/activate-the-dropbox-connector-in-securiti), [(New UI) Connecting Dropbox (self-hosted) with Securiti](/latest/docs/new-ui-connecting-dropbox-with-securiti), or [(New UI) Connecting Dropbox (Securiti cloud) with Securiti](/latest/docs/new-ui-connecting-dropbox-securiti-cloud-with-securiti)
