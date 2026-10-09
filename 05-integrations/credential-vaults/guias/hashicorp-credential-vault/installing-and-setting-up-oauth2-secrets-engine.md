---
title: "Installing and setting up the OAuth 2.0 secrets engine plugin with HashiCorp"
slug: "installing-and-setting-up-oauth2-secrets-engine"
updated: 2026-01-23T16:26:53Z
published: 2026-01-23T16:26:53Z
canonical: "helpcenter.securiti.ai/installing-and-setting-up-oauth2-secrets-engine"
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# Installing and setting up the OAuth 2.0 secrets engine plugin with HashiCorp

> [!NOTE]
> Note
> 
> This procedure is required only for data systems requiring the OAuth plugin with HashiCorp.

## Prerequisites

You must fulfil the following prerequisites before installing the OAuth 2.0 secrets engine plugin:

- You must have a running HashiCorp Vault server with admin access to run `vault plugin register` and `vault secrets enable`. You must set `plugin_directory` and `api_addr` in the Vault server configuration before registering plugins. For more information, see [HashiCorp Developer documentation](https://developer.hashicorp.com/vault/docs/plugins/register)
- You must have a **Go toolchain** to build the plugin from source on a machine that matches your Vault server’s OS/architecture or for which you will cross-compile. For more information, see [HashiCorp Developer](https://developer.hashicorp.com/vault/docs/plugins/register) documentation.

To use HashiCorp Vault for your OAuth credentials, you must install and configure the OAuth plugin with the HashiCorp vault instance. The OAuth plugin lets HashiCorp Vault dynamically generate OAuth access tokens on demand for the supported SaaS applications, as described in the supported data systems for HashiCorp.

## Procedure

To install and set up the OAuth 2.0 secrets engine plugin in your HashiCorp instance:

1. **Obtain the plugin source**: Clone the vault plugin repository from the following Securiti GitHub account to your system:

`https://github.com/securitiai/vault-plugin-secrets-oauthapp`
2. **Build the plugin binary:**
  - If you haven't already done so, install GO on your system as described on this page:

`https://go.dev/doc/install`
  - CD to the cloned repository.
  - Execute the command below in the cloned directory. This produces the executable to register with Vault.

`GOOS=linux GOARCH=amd64 go build -o vault-plugin-secrets-oauthapp ./cmd/vault-plugin-secrets-oauthapp`
3. **Configure Vault server in JSON** (with plugin directory): Execute the following code, as shown below.

```plaintext
{
  "ui": true,
  "disable_mlock": true,
  "api_addr": "http://<HOST>:8200",
  "storage": {
    "file": {
      "path": "/vault/file"
    }
  },
  "listener": [
    {
      "tcp": {
        "address": "0.0.0.0:8200",
        "tls_disable": true
      }
    }
  ],
  "plugin_directory": "/etc/vault/plugins",
  "log_level": "debug"
}
```

You must consider the following points when configuring the vault server:

- The `plugin_directory` cannot be a symlink.
- If `disable_mlock: false`, you must grant `cap_ipc_lock` to the Vault binary and each plugin binary. Hashicorp does not recommend disabling mlock for deployments that do not use integrated storage. For more information on the mlock guidance, see the [Vault configuration parameters documentation.](https://developer.hashicorp.com/vault/docs/configuration)
- You must restart the Vault after changing the server config so the `plugin_directory` is picked correctly.

1. **Compute the plugin checksum**: Compute the plugin checksum from the node that holds `/etc/vault/plugins/oauthapp`:

```plaintext
sha256sum /etc/vault/plugins/oauthapp | awk '{print $1}'
# Save the 64-char hex digest as PLUGIN_SHA256
```

Use this for registration. The Vault verifies the checksum when loading external plugins.
2. ​**​Register the plugin in the Vault catalog​​**: In the vault pod, execute the register command, as shown below.

```plaintext
export VAULT_ADDR=http://<HOST>:8200
# VAULT_TOKEN must have sudo capabilities

vault plugin register \
  -sha256="$PLUGIN_SHA256" \
  secret oauthapp
```

The command registers a `secret-type` plugin named `oauthapp` backed by the oauthapp executable in the plugin directory.

If your binary file name differs from the plugin name, add `-command=&lt;binary-name&gt;` during registration.
3. **Verify the catalog entry**​​: Execute the command below to verify the plugin in the catalog.

```plaintext
vault plugin list secret | grep oauthapp
vault plugin info secret oauthapp
```

  

​The above commands read back the registered plugin details.
4. **Enable (mount) the secrets engine**:​​ Enable the plugin at a mount path of your choice. This example uses ​`oauth2/`​​.

```plaintext
vault secrets enable -path=oauth2 oauthapp
# Output: Success! Enabled the oauthapp secrets engine at: oauth2/
```

  

The above command mounts the registered plugin as a secrets engine at ​`oauth2/​​`.

​To verify, run the command below to list mounts. This shows the enabled secrets engines and their paths.

`vault secrets list`

> [!WARNING]
> Important
> 
> When using the OAuth plugin, Securiti dynamically queries the specified credential path in HashiCorp Vault and uses the stored credentials to request OAuth tokens.
> 
> Each data system may require multiple credentials, such as client ID, client secret, and tenant ID etc. All required credentials should be stored under the same Vault path.
> 
> 
> 
> For example, for Microsoft 365 SharePoint, you can store credentials under the following:
> 
> `vault/securiti/sharepoint`
> 
> The required credentials are stored as keys under this path, as shown below:
> 
> - `vault/securiti/sharepoint/client_id`
> - `vault/securiti/sharepoint/client_secret`
> - `vault/securiti/sharepoint/tenant_id`
> 
> Securiti automatically retrieves these keys during the authentication process.
> 
> You must create separate credential paths for each account if multiple accounts need to be configured. As a result, you must also create multiple keyrings to fetch these credentials.
5. Enable the file permissions check via the environment variable `VAULT_ENABLE_FILE_PERMISSIONS_CHECK,` which lets Vault check if the config directory and files are owned by the user running Vault.

It also checks if there are no write or execute permissions for the group or others. Vault lets operators specify the user and permissions of the plugin directory and binaries using parameters `plugin_file_uid `and `plugin_file_permissions` in the config if an operator needs those to be different.
6. Proceed to [Setting up HashiCorp vault](/latest/docs/hashicorp-credential-vault-authentication-methods-in-hashicorp-vault).
