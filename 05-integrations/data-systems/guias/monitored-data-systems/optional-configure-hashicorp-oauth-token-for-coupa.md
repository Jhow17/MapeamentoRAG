---
title: "(Optional) Configure HashiCorp OAuth token for Coupa"
slug: "optional-configure-hashicorp-oauth-token-for-coupa"
updated: 2026-07-07T06:33:43Z
published: 2026-07-07T06:33:43Z
canonical: "helpcenter.securiti.ai/optional-configure-hashicorp-oauth-token-for-coupa"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Configure HashiCorp OAuth token for Coupa

If you want to use Hashicorp credential vaults to store and manage OAuth credentials for the Coupa data system:

1. If you haven’t already done so, configure the Hashicorp Vault as described in [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
2. Using the settings in the following Table, use Postman ([https://www.postman.com](https://www.postman.com)) or a similar tool to initialize the access Token flow for the data system, as shown below.

| Setting | Value |
| --- | --- |
| Client ID | The Consumer Key you recorded earlier |
| Client Secret | The Consumer Secret you recorded earlier |
| Scopes | The *read* scopes you enabled earlier |
3. Do the following to configure the access Token in the vault.
  1. To create the server for client credentials flow:

```plaintext
vault write oauth2/servers/coupa-example \
    provider=custom \
    provider_options=token_url=https://{{instance_id}}.coupahost.com/oauth2/token \
    client_id={{client id}} \
    client_secret={{client secret}} \
```
  2. To get and write the credentials on the desired path:

```plaintext
vault write oauth2/self/coupa-auth \
    server=coupa-example \
    scopes={{comma separated scopes}}
```
  3. To verify by reading the access Token from the path mentioned above:

```plaintext
vault read oauth2/self/coupa-auth
```
4. Proceed to [Connecting Coupa (Self-hosted) with Securiti](/latest/docs/connecting-coupa-self-hosted-with-securiti).
