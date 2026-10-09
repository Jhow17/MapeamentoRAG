---
title: "Storing data system credentials in HashiCorp vault"
slug: "storing-data-system-credentials-in-hashicorp-vault"
updated: 2026-01-23T16:01:25Z
published: 2026-01-23T16:01:25Z
canonical: "helpcenter.securiti.ai/storing-data-system-credentials-in-hashicorp-vault"
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# Storing data system credentials in HashiCorp vault

In HashiCorp, you configure the key secret pairs that Securiti uses to access each data system, as shown in the examples below. Before creating a secret, you must create a credential path that refers to the path to the credentials in the vault. The `{{credential_path}}` can be any string, i.e., a user-defined path inside the HashiCorp vault. We recommend following the convention `[secret/{application name}/creds]`.

A credential path points to a location in your HashiCorp Vault where all necessary credentials, such as client ID, client secret, and tenant ID are securely stored. Securiti retrieves these secrets dynamically from the specified credential path when provided during the [keyring creation process](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp). Record the value of `{{credential_path}}` to use later when [Creating keyrings for HashiCorp](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp) that point to the connector secret stored in the vault.

For data systems supporting the OAuth plugin, you must first install and set up the plugin in your HashiCorp Vault instance as described in Setting up the OAuth plugin with HashiCorp.

## 1. Storing credentials as key secret pairs in HashiCorp

Credentials can be stored as keys in the HashiCorp vault using either the HashiCorp CLI or directly from the HashiCorp UI.

First, acquire and save the authentication credentials for your data system. For example, the Account key and Account Name key for the Azure Files data system.

### Storing credentials using the HashiCorp application

To store your keys in the HashiCorp vault using the application.

1. In your HashiCorp vault, from the left menu, select Secrets Engine.

![Configuration page displaying various secret engines and their paths for management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/hashicorp_secretsengine.png)
2. From the upper right corner, click Create secret for a new secret.

![Configuration page displaying various secret engines and options for managing secrets.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/hashicorp_createsecret.png)
3. On the Create Secret page, enter your credential path and the key-value pairs for each credential to store in the vault.

![Interface for creating a secret with fields for path and secret data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/hashicorp_createsecret_page.png)
4. Click **Add** to store multiple credentials as keys in the vault.

![Creating a secret in the application with account name and key fields.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/hashicorp_addkeys.png)
5. Click **Save** to store your keys in the vault.

![Secrets management interface displaying account keys and names for Azure files.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/hashicorp_savedsecrets.png)
6. Search for your credential path to access the secret. You can also add keys and store additional credentials within the same secret.
7. Save the key variable names to use later when creating keyrings. For more information, see [Creating keyrings for HashiCorp.](/v1/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp)

### Storing credentials using HashiCorp CLI

To store the credentials as keys using HashiCorp CLI.

- Run the below command to set key-value pairs for each credential to store at your specified credential path:

`vault kv put {{credential_path}} user-key={{username}} password-key={{password}}`

The vault CLI command to store credentials varies depending on your data system's authentication method and required credentials.

Save the key variable names to use later when creating keyrings. For more information, see [Creating keyrings for HashiCorp.](/v1/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp)

### Storing files in HashiCorp vault

You can store your files having formats such as JSON or keytab in the vault by encoding them in base64 format. To store your files as keys:

1. In HashiCorp CLI, run the following command to encode your keytab file.

`base64 --input &lt;file_name&gt;.keytab &gt; output.txt`

For JSON file, use the command below:

`base64 --wrap=0 file.json &gt; file.txt`

1. Copy the base64 string generated, as shown below.

![Terminal commands displaying file operations and base64 encoding for a keytab file.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/hashicorp_base64encoding.png)
2. To store your keytab or JSON file as a key in the vault, choose one of the following methods based on your preferred interface: CLI or application.
  - Using HashiCorp CLI:

In HashiCorp CLI, run the put command as shown below:

`vault kv put {{credential_path}}`

`creds_file=&lt;base64_encoded_credential_file&gt;`
  - Using HashiCorp application:

To store your keytab or any other base64 encoded file as a key in the HashiCorp vault application:
    1. In **Secrets Engines**, search for your credentials path and from the upper right corner of the page, click Create new version.

![Vault interface displaying secrets with options to create a new version.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/hashicorp_searchpath.png)
    2. Add your secrets as key-value pairs. For keytab file, paste the base64 string you copied earlier, as shown below.

![Creating a new version of a secret with highlighted keytab field and save button.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/hashicorp_createnewversion.png)
    3. Click **Save**.
    4. Record the key variable name for your file to use later when [creating keyrings](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp).

## 2. Configuring the OAuth token for data systems

> [!NOTE]
> Note
> 
> This procedure is required only for data systems supporting OAuth plugin with HashiCorp for storing credentials.

### Prerequisites

- We assume you have installed and set up the OAuth plugin as described in [Setting up the OAuth plugin with HashiCorp](/latest/docs/installing-and-setting-up-oauth2-secrets-engine).
- You must have the credentials for your application such as client ID, client secret.

Once the OAuth plugin is installed, the next step is to configure it for your specific SaaS application. The sections below describe the procedures for the supported applications.

  

### Configuring OAuth token for Microsoft 365 applications

We assume you have the OAuth credentials for your application before following the procedure below:

1. Initialize the access token flow: Using the settings in the following table, use [Postman](https://www.postman.com) or a similar tool to initialize the access token flow for the data system, as shown below.

| **Setting** | **Value** |
| --- | --- |
| Client ID | The MSFT client ID for your application such as for SharePoint. |
| Client Secret | The MSFT client secret for your application such as for SharePoint. |
| Tenant ID | The MSFT application tenant ID to build OAuth token endpoint. For example: `123e4567-e89b-12d3-a456-426614174000` |
2. Connect to the HashiCorp vault server: Connect to HashiCorp Vault server's command line, for example, via SSH. You must then set the VAULT_ADDR environment variable so the CLI can communicate with your Vault instance. Adjust the IP address and port as needed for your environment, as shown below.

`export VAULT_ADDR=http://&lt;your-vault-ip&gt;:8200`
3. Enable the plugin at secrets path: After registering the plugin under the name `vault-plugin-secrets-oauthapp`, enable the registered plugin as a secrets engine at a dedicated path, as shown below. This path will be the root for all configurations related to this plugin.

`vault secrets enable -path=securiti/oauth_secrets/ `

`vault-plugin-secrets-oauthapp`

For more information, see [HashiCorp’s documentation to enable plugin](https://developer.hashicorp.com/vault/docs/plugins/register?#step-3-enable-the-plugin).
4. **Configure the application server**: Next, create a server configuration for the specific SaaS application such as, SharePoint you want to integrate. This command securely stores the application's authentication details for the plugin to use when generating tokens.
  1. Use the vault write command to create the server configuration for client credentials flow. The command uses the following path structure:

`[mount_path]/servers/[your_server_name]`

The below command creates `oauth_secrets/servers/Off365` configuration in the OAuth secrets engine plugin. First, the plugin is mounted at `oauth_secrets` path. Next, you create a server named `Off365`, as shown below.

```plaintext
vault write oauth_secrets/servers/Off365 \
provider=custom \
provider_options=token_url=https://login.microsoftonline.com/{MSFT Tenant ID}/oauth2/v2.0/token \
client_id={ Application client id } \
client_secret={ Application  client secret } \
```

  

You must replace `{MSFT Tenant ID},{ Application client id },`and `{Application client secret}` with your MSFT’s tenant ID, Client ID and Client Secret respectively.

This server stores the provider type, tenant, and client credentials. The plugin later uses this configuration to mint and refresh tokens automatically.
  2. Create a Graph token credential using app-only (default):

`vault write oauth_secrets/self/o365 server=Off365 scopes=https://graph.microsoft.com/.default`
  3. Verify by reading the access token from the path mentioned above:

`vault read oauth_secrets/self/o365`
5. Use this path as the credential path for your HashiCorp keyring. For more information, see [Creating keyrings for HashiCorp.](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp)

## 3. Creating credential read policies

Proceed to create credential read policies for the credential paths in HashiCorp for your data system credentials. For more information, see [Creating credential read policies](/latest/docs/creating-credential-read-policies-1)
