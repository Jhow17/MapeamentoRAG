---
title: "Using keyrings in Securiti"
slug: "creating-keyrings"
updated: 2026-09-10T12:20:44Z
published: 2026-09-10T12:20:44Z
canonical: "helpcenter.securiti.ai/creating-keyrings"
area: integrations
modulo: keyrings
tipo: guia
data_captura: 2026-10-08
---

# Using keyrings in Securiti

## Using the Basic keyring

The **Basic** keyring type is used for storing credentials directly and securely within the Securiti platform itself. It is not an external vault.

Securiti supports the following data systems for the **Basic** keyring type.

- Amazon RDS for PostgreSQL
- Amazon RDS MariaDB
- Databricks
- Google Cloud SQL for MySQL
- Google Cloud SQL for PostgreSQL
- Google Cloud SQL for SQL Server
- PostgreSQL
- Coupa
- NetSuite
- Microsoft Dataverse
- LDAP Active Directory
- SFTP
- SMB

## Creating keyrings

To create a keyring to store your credentials:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon, and choose **Integrations** from the left navigation bar.
2. From the left menu of the **Integrations** page, select **Keyrings**.
3. On the **Keyrings** page, from the upper right corner of the page, click **Add Keyrings**.
4. On the **Add Keyring** popup, specify the following keyring settings, as shown below.

| Setting | Description |
| --- | --- |
| Keyring Name | Enter a name for your keyring. For example, "HashiCorp keyring". |
| (Optional) Keyring Description | Enter a description for your keyring. For example, "This keyring is for Amazon S3 connectors only". |
| Keyring Type | Select one of the following keyring types from the menu: - [AWS Secret Manager](/v1/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) - [Azure Key Vault](/v1/docs/configuring-credential-vaults-azure-key-vault) - Basic - [CyberArk Conjur](/v1/docs/configuring-credential-vaults-cyberark-conjur-credential-vault) - [CredStash Vault](/v1/docs/configuring-credential-vaults-credstash-credential-vault) - [CyberArk Vault](/v1/docs/configuring-credential-vaults-cyberark-credential-vault) - [Delinea Secret Manager](/v1/docs/configuring-credential-vaults-delinea-secret-manager-credential-vault) - [GCP Secret Manager](/v1/docs/configuring-credential-vaults-gcp-secret-manager-credential-vault) - [HashiCorp Vault](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault) |
| Data System Type | Select your data system connector from the menu, for example, "Amazon S3". The supported data system connectors vary for each credential vault. For more information, see your credential vault's documentation. |
| Vault Instance | Select the vault instance for your credential vault that you selected in **Keyring Type**. There can be multiple vault instances for a credential vault, you must select the one storing your credentials. |

![Form for adding keyring details including name, type, and description fields.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/createkeyring_popup.png)
5. For each keyring type selected, you must specify the path to fetch credentials from the vault, as shown below:

| Keyring Type | Secret Identifier | Description | Example |
| --- | --- | --- | --- |
| AWS Secret Manager | Secret name | Specify the the unique name of the secret stored in AWS Secrets Manager. | `prod/database/credentials` |
| Azure Key Vault | No dedicated field | After selecting the Vault Instance, enter the name of the secret from your vault directly into the credential mapping fields i.e, **Credentials Key Name** at the bottom. | `My-Azure-Secret-User` in the **User Key** field |
| Basic | Not Applicable | The **Basic** keyring type is used for storing credentials directly and securely within the Securiti platform itself. It is not an external vault, so you enter the actual secret values (e.g., username and password) directly when prompted. | N/A |
| CyberArk Conjur | Secret Path | Specify the full, unique path to the secret variable as defined in your CyberArk Conjur policy. | `BotApp/salesforce-client-id` |
| CredStash Vault | No dedicated field | After selecting the CredStash vault instance, specify the secret's name directly in the credential mapping fields i.e, **Credentials Key Name** for the connector. | `my-user` in the **User Key** field |
| CyberArk Vault | - Safe - (Optional) Folder - Object | You must specify the following to locate the secret within CyberArk's Central Credential Provider (CCP). - **Safe**: The CyberArk Safe where the account is stored. - (Optional) **Folder**: The folder within the Safe (use "Root" if none) - **Object**: The name of the account object in the Safe. | - **Safe**: `Securiti-Prod` - (Optional) **Folder**: `Databases` - **Object**: `Oracle-DB-Admin` |
| Delinea Secret Manager | Secret ID | Specify the unique numerical ID of the secret as it appears in your Delinea Secret Server instance. | `23` |
| GCP Secret Manager | No dedicated field | After selecting the vault instance, specify the secret's name directly in the credential mapping fields i.e, **Credentials Key Name** for the connector. | `mysql-user` in the **User Key** field |
| HashiCorp | - Secrets Engine - Secrets Engine Path - Credential Path | You must specify the following to locate the secret within HashiCorp. - **Secrets Engine**: Select your secrets engine from the menu. - (Optional) **Secrets Engine Path**: Enter the path where the engine is enabled. - **Credential Path**: Enter the specific path to the secret. | - **Secrets Engine**: `KV Version 2` - (Optional) **Secrets Engine Path**: `securiti/` - **Credential Path**: `secret/workday/azureblob` |
6. In the **Credentials Key Name** section, specify the name of the secret keys storing your data system credentials. These fields vary for each **Connector Type**. For example, **User Key** and **Password Key**.
7. Click **Add Keyring**.

## Using keyrings in data system connectors

To use keyring for a data system connector:

1. In the **Authentication** tab for your data system connector, enable the **Use Keyring** toggle.
2. From the **Keyring Type** menu, select your keyring or search for the required keyring.
3. From the **Keyring** menu, select your keyring instance, as shown below.

![Configuration settings for OneDrive integration, highlighting keyring options and credentials.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/selectkeyring_connectors.png)

##

## Related

- [Managing Securiti API keys](/managing-credentials-managing-securiti-api-keys.md)
- [Managing SSH keys](/managing-ssh-keys.md)
- [Creating keyrings for HashiCorp](/hashicorp-credential-vault-creating-keyrings-for-hashicorp.md)
- [AWS Secrets Manager credential vault](/configuring-credential-vaults-aws-secrets-manager-credential-vault.md)
- [Delinea Secret Manager credential vault](/configuring-credential-vaults-delinea-secret-manager-credential-vault.md)
