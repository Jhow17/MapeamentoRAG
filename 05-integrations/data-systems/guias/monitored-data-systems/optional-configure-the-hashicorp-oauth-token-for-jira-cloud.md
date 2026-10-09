---
title: "(Optional) Configure the Hashicorp OAuth token for Jira Cloud"
slug: "optional-configure-the-hashicorp-oauth-token-for-jira-cloud"
updated: 2025-11-03T10:33:02Z
published: 2025-11-03T10:33:02Z
canonical: "helpcenter.securiti.ai/optional-configure-the-hashicorp-oauth-token-for-jira-cloud"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Configure the Hashicorp OAuth token for Jira Cloud

If you want to use Hashicorp credential vaults to store and manage OAuth Credentials for the Jira Cloud Self-hosted Data system:

> [!NOTE]
> **Important**
> 
> Before obtaining the refresh Token, we assume you have performed the steps for each site you want to scan as outlined in the [Prerequisites topic for Jira Cloud](/v1/docs/create-an-app-and-obtain-credentials-for-jira-cloud-self-hosted-connector).

1. If you haven’t already done so, configure the Hashicorp Vault as described in [Using OAuth tokens for credentials](/v1/docs/managing-data-system-credentials-in-hashicorp-vault).
2. Using the settings in the following Table, use Postman ([https://www.postman.com](https://www.postman.com)) or a similar tool to initialize the access Token flow for the Data system, as shown below.

| Setting | Value |
| --- | --- |
| Client ID | The Consumer Key you recorded earlier |
| Client Secret | The Consumer Secret you recorded earlier |
| Auth URL | https://auth.atlassian.com/authorize |
| Access Token URL | https://auth.atlassian.com/oauth/Token |
| Callback URL | The Jira app creation URL you used earlier |
| Scopes | ```plaintext offline_access read:jira-work read:jira-user ``` |

![hashicorp_oauth_token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ace04149-fbac-f6bc-8dcf-9b57bfe55241.png)

Click **Get New Access Token**. It redirects you to the Jira consent page.

Select any site from the menu on the page.
3. Use these commands in the vault plugin to initiate the Token refresh flow:

```plaintext
vault write my-secrets/servers/jira_cloud provider=custom client_id={{client_id}}
client_secret={{client_secret}}
provider_options=token_url=https://auth.atlassian.com/oauth/token

vault write my-secrets/creds/jira_cloud server=jira_cloud
grant_type=refresh_token refresh_token={{refresh_token}}
```
4. Proceed to [Activate the Jira Cloud (self-hosted) connector in Securiti](/v1/docs/activate-the-jira-cloud-self-hosted-connector-in-securiti).
