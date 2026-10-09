---
title: "(Optional) Configure the Hashicorp OAuth token for Salesforce CRM"
slug: "optional-configure-the-hashicorp-oauth-token-for-salesforce-crm"
updated: 2026-07-31T10:47:01Z
published: 2026-07-31T10:47:01Z
canonical: "helpcenter.securiti.ai/optional-configure-the-hashicorp-oauth-token-for-salesforce-crm"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Configure the Hashicorp OAuth token for Salesforce CRM

If you want to use Hashicorp credential vaults to store and manage OAuth Credentials for the Salesforce CRM Data system:

1. If you haven’t already done so, configure the Hashicorp Vault as described in [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault), with specific attention to the subsection on OAuth Authentication.
2. Using the settings in the following Table, use Postman ([https://www.postman.com](https://www.postman.com)) or a similar tool to generate a refresh Token for the Data system using the authorization_code grant flow as shown below.

| Setting | Value |
| --- | --- |
| Client ID | The Consumer Key you recorded earlier |
| Client Secret | The Consumer Secret you recorded earlier |
| Auth URL | https://{{instance_id}}-my.salesforce.com/services/oauth2/authorize |
| Access Token URL | https://{{instance_id}}-my.salesforce.com/services/oauth2/Token |

![image7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-802049d8-2e5b-3461-20ce-ddbae029c48e(2).png)
3. Click **Sign In** to authorize the Token request.

![image3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bca93d76-403e-82f8-6d16-3c2a8b127812(2).png)
4. After postman provides you with the refresh Token, configure that refresh Token in the Hashicorp vault to initiate the refresh Token flow using the two commands shown in this example:

```plaintext
vault write my-secrets/servers/salesforce provider=custom client_id={{client_id}} client_secret={{client_secret}} provider_options=token_url={{token_url}}
vault write my-secrets/creds/salesforce server=salesforce grant_type=refresh_token refresh_token={{refresh_token}} provider_options=token_expiry=900
```
5. Proceed to [Connecting Salesforce CRM with Securiti](/latest/docs/new-ui-connecting-salesforce-crm-with-securiti).
