---
title: "(Optional) Configure the HashiCorp OAuth token for Microsoft Teams"
slug: "optional-configure-the-hashicorp-oauth-token-for-microsoft-teams"
updated: 2026-06-23T06:58:29Z
published: 2026-06-23T06:58:29Z
canonical: "helpcenter.securiti.ai/optional-configure-the-hashicorp-oauth-token-for-microsoft-teams"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Configure the HashiCorp OAuth token for Microsoft Teams

If you want to use HashiCorp credential vaults to store and manage OAuth Credentials for the Microsoft Teams Data system:

1. If you haven’t already done so, configure the HashiCorp Vault as described in [HashiCorp credential vault](/v1/docs/hashicorp-credential-vault), and perform the procedure in the subsection on OAuth Authentication.
2. Do the following to configure the access Token in the vault.
  1. Create the server for client Credentials flow:

```plaintext
vault write oauth2/servers/microsoft_teams \ 
provider=microsoft_azure_ad \
client_id={{CLIENT_ID}} \
client_secret={{CLIENT_SECRET}} \
provider_options=tenant={{tenant_id}}
```
  2. Get and write the Credentials on the desired path:

```plaintext
ault write oauth2/self/microsoft_teams server=microsoft_teams
scopes=https://graph.microsoft.com/.default
```
  3. Verify by reading the access Token from the path mentioned above, and making sure it returns a valid Token:

```plaintext
vault read oauth2/self/microsoft_teams
```
3. Proceed to [Connecting Microsoft Teams with Securiti](/latest/docs/new-ui-creating-microsoft-teams-self-hosted-connector-instance).
