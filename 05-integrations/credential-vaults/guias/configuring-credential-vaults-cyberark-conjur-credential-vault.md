---
title: "CyberArk Conjur credential vault"
slug: "configuring-credential-vaults-cyberark-conjur-credential-vault"
updated: 2026-05-15T07:28:16Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/configuring-credential-vaults-cyberark-conjur-credential-vault"
stale: true
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# CyberArk Conjur credential vault

CyberArk Conjur is an open-source secrets management solution designed for securely storing and retrieving secrets like passwords, tokens, and API keys. Securiti supports integration with Conjur to retrieve secrets, such as API keys and passwords, directly from your Conjur vault at runtime, avoiding storing them within the Securiti platform.

> [!NOTE]
> **Note**
> 
> - The Credential Vaults feature is available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your Securiti tenant.
> - You can only activate CyberArk Conjur Vault instances through Securiti pods. When you activate the CyberArk Conjur vault instance Securiti automatically ensures the necessary CyberArk packages are activated on every active pod cluster on your Securiti instance.
> - Securiti supports only **API Key** authentication method for integrating with CyberArk Conjur.

## Roles and permissions

Securiti implements role-based access control on actions that can be performed for credential vaults and keyrings, such as keyring creation. For more information on roles and their permissions, see [Data Systems RBAC permissions](/v1/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-default-roles).

This document explains how to set up and configure CyberArk Conjur for secret storage and enable its integration within the Securiti, using the Conjur CLI. Following procedures are covered in this topic:

- Prerequisites for CyberArk Conjur vault integration
- Supported data systems for CyberArk Conjur vault
- Defining a Conjur policy
- Loading the policy and acquiring credentials
- Storing secrets in Conjur
- Configuring CyberArk Conjur vault instance in Securiti
- Creating a keyring for CyberArk Conjur in Securiti

### Prerequisites for CyberArk Conjur vault integration

Before configuring CyberArk Conjur in Securiti, ensure the following prerequisites are complete:

- We assume you have set up your Conjur OSS Environment and have a working CyberArk Conjur instance, as described in [Conjur's Quick Start guide](/v1/docs/securiti-pods-and-elastic-pods) (steps 1-5).
- You must have an admin account in CyberArk Conjur

### Supported data systems for CyberArk Conjur vault

Currently, Securiti supports CyberArk Conjur credential vault for the following data systems:

- [Amazon Redshift](/v1/docs/securiti-pods-and-elastic-pods)
- [Salesforce CRM](/v1/docs/salesforce-crm-connectors)
- [Snowflake](/v1/docs/securiti-pods-and-elastic-pods)
- [Oracle Eloqua](/latest/docs/oracle-eloqua)

### Defining a Conjur policy

You must define a policy in YAML format for each set of secrets you want to manage. The policy specifies which users or applications (hosts) have permission to access specific secret variables.

The sample below shows a policy that defines a human user (`Dave`), a non-human application (`myDemoApp`), and a secret variable (`secretVar`) with appropriate permissions.

```yaml
- !policy
  id: BotApp
  body:
    - !user Dave
    - !host myDemoApp
    - !variable secretVar
    - !permit
      role: !user Dave
      privileges: [read, update, execute]
      resource: !variable secretVar
    - !permit
      role: !host myDemoApp
      privileges: [read, execute]
      resource: !variable secretVar
```

### Loading the policy and acquiring credentials

Log in to your Conjur instance as an admin and load the policy you just defined, as described in [CyberArk Conjur's documentation to define policy](/v1/docs/securiti-pods-and-elastic-pods).

1. Log in to Conjur as admin using the below CLI command:

```bash
conjur login -i admin
```
2. Load the policy into the root branch. This command also generates API keys for the roles defined in the policy.

```bash
conjur policy load -b root -f policy/BotApp.yml > my_app_data
```

Conjur generates the following API keys and stores them in a file, `my_app_data`:
  - An API key for Dave, the human user. This key is used to authenticate user Dave to Conjur.
  - An API key for BotApp, the non-human identity. This key is used to authenticate BotApp application to Conjur.
3. After the policy is loaded, Conjur outputs a JSON object containing the API keys for the new roles, as shown below.

```json
{
  "created_roles": {
    "myConjurAccount:host:BotApp/myDemoApp": {
      "id": "myConjurAccount:host:BotApp/myDemoApp",
      "api_key": "************"
    },
    "myConjurAccount:user:Dave@BotApp": {
      "id": "myConjurAccount:user:Dave@BotApp",
      "api_key": "************"
    }
  },
  "version": 1
}
```

From this output, you must record the following values to configure the vault in Securiti:
  - **Host URL**: The URL of your CyberArk Conjur server.
  - **Account Name**: Your Conjur account name (e.g., `myConjurAccount` in `myConjurAccount:user:Dave@BotApp`).
  - **Username**: Your Conjur account username (e.g., `Dave@BotApp` in `myConjurAccount:user:Dave@BotApp`).
  - **API Key**: The API key associated with the user role.

### Storing secrets in Conjur

As the policy is defined and loaded in Conjur, you can store your data system credentials as secrets in CyberArk Conjur. For more information, see [CyberArk Conjur's documentation on storing secrets](/v1/docs/securiti-pods-and-elastic-pods).

To store a secret in Conjur:

1. Log into Conjur as the user defined in the policy (e.g., Dave).

```bash
conjur login -i Dave@BotApp
```
2. To verify that you logged in successfully, run the below command:

```bash
client conjur whoami
```

The terminal returns the following output on successful login:

```bash
{"account":"myConjurAccount","username":"Dave@BotApp"}
```
3. Store your data system credentials in the secret variable you created when defining the policy, as shown below:

```bash
conjur variable set -i BotApp/secretVar -v ${secretVal}
```

See an example below for storing Client ID and Client Secret as `salesforce-client-id` and `salesforce-client-secret`, for Salesforce CRM.

```bash
# Store the Salesforce Client ID
conjur variable set -i BotApp/salesforce-client-id -v "YOUR_SALESFORCE_CLIENT_ID"

# Store the Salesforce Client Secret
conjur variable set -i BotApp/salesforce-client-secret -v "YOUR_SALESFORCE_CLIENT_SECRET"
```

### Configuring CyberArk Conjur vault instance in Securiti

1. In Securiti, open the main menu and select **Integrations > Credential Vaults**.
2. On the Credential Vaults page, near the upper right corner of the page, click **Add Integration** to create a new instance.
3. From the catalog of available credential vaults, select **CyberArk Conjur**.
4. On the **Basic Information** tab, enter a name and location for the CyberArk Conjur vault instance, and if you want, also choose additional co-owners (by default you are the owner).
5. Click **Create Instance & Continue**.
6. On the **Authentication** tab, select a pod(s) from the **Pod Configuration** menu where a vault authenticates.

> [!NOTE]
> Note
> 
> - Securiti authenticates the vault only on the pods you select. You can choose all pods, a single pod, or multiple pods for a vault instance. If you select **ALL**, Securiti runs vault authentication across all pods.
> - You can update pod selection after creation without recreating the vault configuration.
> - Only vaults associated with the same pod as the data system connector appear as available keyrings during connector configuration.
7. On the **Authentication** tab, apply the following settings, then click **Test and Save**.

| Setting | Description |
| --- | --- |
| Authentication Method | Select **API Key** from the menu. |
| Server URL | Enter the CyberArk Conjur Server or host URL that you acquired from [the output when loading the policy](/v1/docs/cyberark-conjur-credential-vault). The URL must start with htps://, for example `https://1.1.1.1:8080` |
| Account Name | Enter the CyberArk Conjur account name that you acquired from [the output when loading the policy](/v1/docs/cyberark-conjur-credential-vault). For example, `myConjurAccount` |
| Username | Enter the CyberArk Conjur username that you acquired from [the output when loading the policy](/v1/docs/cyberark-conjur-credential-vault). For example, `Dave@BotApp` |
| API Key | Enter the API Key that you acquired from [the output when loading the policy](/v1/docs/cyberark-conjur-credential-vault). |
8. On the **Test Connection** popup, click **Yes, proceed with testing**. Securiti validates the authentication information.
9. View the connection status in the **Overview** tab.

### Creating a keyring for CyberArk Conjur in Securiti

Create keyrings for CyberArk Conjur that point to the connector secrets that you have placed in your key vault:

1. In System Settings, open **Integrations > Credentials > Keyrings** and click **Create Keyring**.
2. On the **Add Keyring** popup, apply the following settings, then click **Add Keyring**:

| Setting | Description |
| --- | --- |
| Keyring Name | Enter a descriptive name for the keyring. |
| Keyring Description | (Optional) Enter a description for the keyring. |
| Keyring Type | Choose **CyberArk Conjur**. |
| Connector Type | Choose the type of data system for the keyring. |
| Vault Instance | Choose the CyberArk Conjur credential vault you configured earlier. |
| Secret Path | Enter the policy ID of the policy you loaded in Conjur, as described in [Loading the policy](/v1/docs/cyberark-conjur-credential-vault). For example, `BotApp` |
| Credentials Key Name | Enter the key variable names for your data system credentials stored as secrets, in the following fields. - **Consumer Key**: Specify the variable name of your secret such as, `salesforce-client`. - **Consumer Secret Key**: Specify the variable name of your secret such as, `salesforce-secret`. |

![Screenshot_2025-06-13_at_1_30_44_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-46721a85-ab39-922d-525c-f4000dfd0303(3).png)

For each such data system where you want to use CyberArk Conjur, you must enable the keyring option during connector activation:

1. In Securiti, open **System Settings** and choose **Integrations > Data Systems > Monitored**.
2. Create a new data system instance, and on the Connector tab apply the following settings, then click **Authenticate & Activate Connector**:

| Setting | Description |
| --- | --- |
| Use Keyring | Enable the toggle. |
| Keyring Type | Choose **CyberArk Conjur**. |
| Keyring | Choose the keyring you created earlier. |

## Related

- [HashiCorp credential vault](/configuring-credential-vaults-hashicorp-credential-vault.md)
- [Configuring HashiCorp vault instance in Securiti](/hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti.md)
- [Creating keyrings for HashiCorp](/hashicorp-credential-vault-creating-keyrings-for-hashicorp.md)
