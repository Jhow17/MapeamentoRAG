---
title: "Creating keyrings for HashiCorp"
slug: "hashicorp-credential-vault-creating-keyrings-for-hashicorp"
updated: 2026-08-10T12:31:51Z
published: 2026-08-10T12:31:51Z
canonical: "helpcenter.securiti.ai/hashicorp-credential-vault-creating-keyrings-for-hashicorp"
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# Creating keyrings for HashiCorp

After configuration and activation of your HashiCorp vault instance, you can create keyring to store and access your data system connector's secrets placed in the vault. For more information on keyrings, see [Using keyrings](/latest/docs/managing-credentials-using-keyrings).

This topic includes following sections.

- HashiCorp keyring creation process
  - Common keyring settings
  - Connector specific keyring settings
- Keyring settings for data system connectors

### Keyring settings

In System Settings, open **Integrations > Credentials > Keyrings** and click **Create Keyring**.

#### Common settings

On the **Add Keyring** modal, apply the following settings, then click **Add Keyring**:

| Setting | Description |
| --- | --- |
| Keyring Name | Enter a descriptive name for the keyring. |
| Keyring Description | (Optional) Enter a description for the keyring. |
| Keyring Type | Choose **HashiCorp**. |
| Connector Type | Choose the type of data system for the keyring. |
| Vault Instance | Choose the HashiCorp credential vault you configured earlier. |
| Secrets Engine | (Optional) Choose the HashiCorp vault secret engine version you are using. The default is Secret Engine Version 1. When using AWS Secrets Engine, enter **KV Version 2** as the secrets engine. |
| Secrets Engine Path (Secrets Engine Version 2 only) | (Optional) Enter the secret engine path where the secrets engine is accessible. The path must be unique across all secrets engines. This path defaults to the type of the secrets engine. Securiti uses the path you enter to add the keyword `data` in the correct spot in the credential path, as required for the KV Version 2 secrets engine. For example, if you enter the Secrets Engine Path `v2/kv` and the Credential path `v2/kv/static/securiti-ai/gbq`, when Securiti accesses the credential vault to request the credentials it passes the path `v2/kv/data/static/securiti-ai/gbq`. If you leave this field empty, Securiti passes the Credential Path string as-is when it accesses the credential vault. > [!WARNING] > **Important** > > Leave the Secrets Engine Path field empty when using AWS Secrets Engine. |
| Credential Path | Enter the path for the vault where you have stored the key/secret pairs. The credentials path follows the below format. `&lt;engine&gt;/creds/&lt;role-name&gt;` See an example below. `aws/creds/securiti-testrole` > [!WARNING] > **Important** > > The required credentials must be stored in the vault already and should be accessible at the provided path. **Connectors using OAuth plugin**: For connectors using HashiCorp's OAuth plugin, Securiti dynamically retrieves the credentials. For multiple accounts requiring different credential paths, you must configure separate keyrings. Keyrings can be linked to connectors in the following ways: - Multiple connectors can share the same keyring. - A connector can only have one keyring linked at a time, which can be updated during the reconfiguration process. |
| Credentials Key Name | Enter the key variable names for your credentials stored in HashiCorp that you recorded in [Storing key/secret pairs in HashiCorp](/v1/docs/managing-data-system-credentials-in-hashicorp-vault). This field varies depending on the data system selected in the **Connector Type** field. See an example below. ![hashicorp_keys_keyring.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-73c23a57-6cf6-57b9-78c9-8a7807ac45f0(3).png) |

#### Connector specific settings

Your credential keys and authentication settings vary based on the selected connector type. See the sections below to read about the settings specific to your connector.

#### Alfresco

If your **Connector Type = Alfresco**, provide values for the following fields:

- **Credentials Key Name**: Enter the key variable names for your user and password key stored in HashiCorp.

#### Alibaba Cloud OSS

If your **Connector Type = Alibaba Cloud OSS**, provide values for the following fields:

- **Credentials Key Name**: Enter the key variable names for your token ID and secret stored in HashiCorp.

#### 

#### Amazon Document DB

If your **Connector Type = Amazon Document DB**, provide values for the following fields:

- **Credentials Auth Key**: Enable the **Use SSH** toggle if you want to establish connection with DocumentDB clusters outside VPC. The toggle is disabled by default.
- **Credentials Key Name**: Enter the key variable names for your user and password key stored in HashiCorp.

#### Amazon MSK

If your **Connector Type = Amazon MSK**, provide values for the following fields:

- **Credentials Auth Key**: Select the **Authentication Type** and **Glue Authentication Type** for your connector. Select one of the following authentication types from the menu.

You can select either **IAM Roles** or **IAM Keys** in the Glue authentication type.
  - Plain Text
  - SSL Without Client Authentication
  - SSL With Client Authentication
  - SASL plain text
  - SASL SSL
- **Credentials Key Name**: The credential keys vary depending upon the selection authentication type and glue authentication type. The table below describes credential keys required for each authentication type.

| Authentication Type | Glue Authentication Type | Credentials |
| --- | --- | --- |
| Plain Text | IAM Keys | Enter the key variable names for the following credentials stored in HashiCorp. - AWS Access Key - AWS Secret Key |
| IAM Roles | None |
| SSL Without Client Authentication | IAM Keys | Enter the key variable names for the following credentials stored in HashiCorp. - Truststore Password Key - AWS Access Key - AWS Secret Key |
| IAM Roles | Enter the key variable names for the following credentials stored in HashiCorp. - Truststore Password Key |
| SSL With Client Authentication | IAM Keys | Enter the key variable names for the following credentials stored in HashiCorp. - Truststore Password Key - Keystore Password Key - AWS Access Key - AWS Secret Key |
| IAM Roles | Enter the key variable names for the following credentials stored in HashiCorp. - Truststore Password Key - Keystore Password Key |
| SASL plain text | IAM Keys | Enter the key variable names for the following credentials stored in HashiCorp. - User Id Key - User Secret Key - AWS Access Key - AWS Secret Key |
| IAM Roles | Enter the key variable names for the following credentials stored in HashiCorp. - User Id Key - User Secret Key |
| SASL SSL | IAM Keys | Enter the key variable names for the following credentials stored in HashiCorp. - Truststore Password Key - User Id Key - User Secret Key - AWS Access Key - AWS Secret Key |

#### Amazon RDS for MySQL

If your **Connector Type = Amazon RDS for MySQL**, provide values for the following fields:

- **Credentials Key Name**: Enter the key variable names for your user and password key stored in HashiCorp.

#### Amazon RDS for PostgreSQL

If your **Connector Type = Amazon RDS for PostgreSQL**, provide values for the following fields:

- **Credentials Key Name**: Enter the key variable names for your user and password key stored in HashiCorp.

#### Amazon Redshift

If your **Connector Type = Amazon Redshift**, provide values for the following fields:

- **Credentials Key Name**: Enter the key variable names for your user and password key stored in HashiCorp.

#### Amazon S3

If your **Connector Type = Amazon S3**, provide values for the following fields:

- **Credentials Auth Key**: Select the **Authentication Type** for your connector. Select one of the following authentication types from the menu.
  - IAM Keys
  - S3 Inventory
  - Auto-Generate Dynamic Credentials
- **Credentials Key Name**: The credential keys vary depending upon the selection of the authentication type. The table below describes credential keys required for each authentication type.

| Authentication Type | Credentials |
| --- | --- |
| IAM Keys | Enter the key variable names for the following credentials stored in HashiCorp. - Token Id Key - Token Secret Key |
| S3 Inventory | Enter the key variable names for the following credentials stored in HashiCorp. - Token Id Key - Token Secret Key - Inventory Token Id Key - Inventory Token Secret Key |
| Auto-Generate Dynamic Credentials | Enter the key variable names for the following credentials stored in HashiCorp. - Token Id Key - Token Secret Key - Session Token Key |

#### Apache Hive

If your **Connector Type = Apache Hive**, provide values for the following fields:

- **Credentials Key Name**: Enter the key variable names for your user and password key stored in HashiCorp.

#### Azure Blob Storage

If your **Connector Type = Azure Blob Storage**, provide values for the following fields:

- **Credentials Auth Key**: Select the **Authentication Type** for your connector. Select one of the following authentication types from the menu.
  - Storage Account
  - Service Principal
  - Service Principal with Certificate
- **Credentials Key Name**: The credential keys vary depending upon the selection authentication type. The table below describes credential keys required for each authentication type.

| Authentication Type | Credentials |
| --- | --- |
| Storage Account | Enter the key variable names for the following credentials stored in HashiCorp. - Account Key |
| Service Principal | Enter the key variable names for the following credentials stored in HashiCorp. - Client Id Key - Secret Key |
| Service Principal with Certificate | Enter the key variable names for the following credentials stored in HashiCorp. - Client Id Key - Service Principal Certificate Key - Service Principal Private Key |

#### Azure Cosmos DB for MongoDB

If your **Connector Type = Azure Cosmos DB for MongoDB**, provide values for the following fields:

- **Credentials Key Name**: Enter the key variable names for your user and password key stored in HashiCorp.

#### Azure Data Lake Storage (ADLS) Gen2

If your **Connector Type = Azure Data Lake Storage (ADLS) Gen2**, provide values for the following fields:

- **Credentials Key Name**: Enter the key variable names for your Account key stored in HashiCorp.

#### Azure Files

If your **Connector Type = Azure Files**, provide values for the following fields:

- **Credentials Auth Key**: Select the **Authentication Type** for your connector. Select one of the following authentication types from the menu.
  - Storage Account
  - Service Principal
- **Credentials Key Name**: The credential keys vary depending upon the selection authentication type. The table below describes credential keys required for each authentication type.

| Authentication Type | Credentials |
| --- | --- |
| Storage Account | Enter the key variable names for the following credentials stored in HashiCorp. - Account Name Key - Account Key |
| Service Principal | Enter the key variable names for the following credentials stored in HashiCorp. - Account Name Key - Client Id Key - Secret Key |

#### Cassandra

If your **Connector Type = Cassandra**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### Confluence Data Center

If your **Connector Type = Confluence Data Center**, provide values for the following fields:

- **Credentials Key Name**: Enter the key variable names for your Personal Access Token key stored in HashiCorp.

#### Confluent Kafka

If your **Connector Type = Confluent Kafka**, provide values for the following fields:

- **Credentials Auth Key**: Configure the following settings.
  - **Authentication Type**: Select one of the following authentication types from the menu.
    - Plain Text
    - SSL Without Client Authentication
    - SSL With Client Authentication
    - SASL plain text
    - SASL SSL
  - **Schema registry protected by basic authentication**: Mark the checkbox to use schema registry credentials. When enabled, you must provide key variable names in HashiCorp for the following credentials in the **Credentials Key Name** section.
    - Schema Registry Username Key
    - Schema Registry Password Key
  - **Decrypt files protected with Client-Side field level encryption**: Enable the toggle to use a KMS provider such as AWS and its credentials. When enabled, you must provide key variables names in HashiCorp for the following credentials in the **Credentials Key Name** section.

> [!NOTE]
> **Note**
> 
> Currently, only AWS is supported as a KMS provider.
    - KMS AWS Key
    - KMS AWS Secret Key
- **Credentials Key Name**: The credential keys vary depending upon the selection authentication type. The table below describes credential keys required for each authentication type.

| Authentication Type | Credentials |
| --- | --- |
| Plain Text | None. Provide the key variable names in HashiCorp, for KMS provider or schema registry credentials if the respective options are enabled. |
| SSL Without Client Authentication | Enter key variable name for the **Truststore Password Key** stored in HashiCorp. Provide the key variable names in HashiCorp, for KMS provider or schema registry credentials if the respective options are enabled. |
| SSL With Client Authentication | Enter the key variable names for the following credentials stored in HashiCorp. - Truststore Password Key - Keystore Password Key Provide the key variable names in HashiCorp, for KMS provider or schema registry credentials if the respective options are enabled. |
| SASL plain text | Enter the key variable names for the following credentials stored in HashiCorp. - User Id Key - User Secret Key Provide the key variable names in HashiCorp, for KMS provider or schema registry credentials if the respective options are enabled. |
| SASL SSL | Enter the key variable names for the following credentials stored in HashiCorp. - Truststore Password Key - User Id Key - User Secret Key Provide the key variable names in HashiCorp, for KMS provider or schema registry credentials if the respective options are enabled. |

#### Couchbase NoSQL

If your **Connector Type = Couchbase NoSQL**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### Coupa

If your **Connector Type = Coupa**, no additional values are required other than the credential path provided already.

During authentication, Securiti dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system.

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### Databricks

If your **Connector Type = Databricks**, provide values for the following fields:

- **Credentials Auth Key**: Select your **Authentication** method from the menu. Currently, **Personal Access Token** authentication is supported only.
- **Credentials Key Name**: Provide key variable name for the Access Token key stored in HashiCorp vault.

#### Dropbox

If your **Connector Type = Dropbox**, no additional values are required other than the credential path provided already.

During authentication, Securiti dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system.

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### G Suite Google Drive

If your **Connector Type = G Suite Google Drive**, provide values for the following fields:

- **Credentials Key Name**: Provide key variable name for the Service Account key stored in HashiCorp vault.

#### Google BigQuery

If your **Connector Type = Google BigQuery**, provide values for the following fields:

- **Credentials Key Name**: Provide key variable name for the Credentials File key stored in HashiCorp vault.

#### Google Cloud Storage

If your **Connector Type = Google Cloud Storage**, provide values for the following fields:

- **Credentials Auth Key**: Select your **Authentication Type** from the menu. Currently, **Credentials File** authentication is supported only.
- **Credentials Key Name**: Provide key variable name for the Credentials File key stored in HashiCorp vault.

#### HDFS

If your **Connector Type = HDFS**, provide values for the following fields:

- **Credentials Auth Key**: Select the **Authentication Type** for your connector. Select one of the following authentication types from the menu.
  - No authentication
  - Keytab
  - Password
- **Credentials Key Name**: The credential keys vary depending upon the selection authentication type. The table below describes credential keys required for each authentication type.

| Authentication Type | Credentials |
| --- | --- |
| No authentication | Provide the key variable names for the following credentials stored in HashiCorp. - User Key |
| Keytab | Provide the key variable names for the following credentials stored in HashiCorp. - Kerberos Principal for Namenode Key - Kerberos Principal for User Key - Kerberos Keytab Key |
| Password | Provide the key variable names for the following credentials stored in HashiCorp. - Kerberos Principal for Namenode Key - Kerberos Principal for User Key - Kerberos User Password Key |

#### HP NonStopSQL

If your **Connector Type = HP NonStopSQL**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### IBM Db2

If your **Connector Type = IBM Db2**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### IBM Db2 zOS

If your **Connector Type = IBM Db2 zOS**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### Jira Software

If your **Connector Type = Jira Software**, no additional values are required other than the credential path provided already.

During authentication, dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system.

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### Jira Software Data Center

If your **Connector Type = Jira Software Data Center**, no additional values are required other than the credential path provided already.

During authentication, Securiti dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system.

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### Kafka

If your **Connector Type = Kafka**, provide values for the following fields:

- **Credentials Auth Key**: Configure the following settings.
  - **Authentication Type**: Select one of the following authentication types from the menu.
    - Plain Text
    - SSL Without Client Authentication
    - SSL With Client Authentication
    - SASL plain text
    - SASL SSL
  - **Schema registry protected by basic authentication**: Mark the checkbox to use schema registry credentials. When enabled, you must provide values for the following credentials in the **Credentials Key Name** section.
    - Schema Registry Username Key
    - Schema Registry Password Key
- **Credentials Key Name**: The credential keys vary depending upon the selection authentication type. The table below describes credential keys required for each authentication type.

| Authentication Type | Credentials |
| --- | --- |
| Plain Text | None. Provide schema registry credentials if the respective options are enabled. |
| SSL Without Client Authentication | Provide the key variable names for the following credentials stored in HashiCorp. - Truststore Password Key Provide schema registry credentials if the respective options are enabled. |
| SSL With Client Authentication | Provide the key variable names for the following credentials stored in HashiCorp. - Truststore Password Key - Keystore Password Key Provide schema registry credentials if the respective options are enabled. |
| SASL plain text | Provide the key variable names for the following credentials stored in HashiCorp. - User Id Key - User Secret Key Provide schema registry credentials if the respective options are enabled. |
| SASL SSL | Provide the key variable names for the following credentials stored in HashiCorp. - Truststore Password Key - User Id Key - User Secret Key Provide schema registry credentials if the respective options are enabled. |

#### Microsoft Azure SQL Database

If your **Connector Type = Microsoft Azure SQL Database**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### Microsoft 365 Lists

If your **Connector Type = Microsoft 365 List**, configure the following Credentials Auth Key and key names.

Under **Credentials Key Name**, provide the key variable names for the following credentials stored in HashiCorp.

- Client ID Key
- Client Secret Key
- Certificate ThumbPrint Key
- Private Key

> [!NOTE]
> Note
> 
> Microsoft 365 Lists Keyrings require the private key to be stored in Base64-encoded format. Before adding the private key to the vault, encode the `.pem` file using the following command:
> 
> `cat test.pem | base64 | tr -d '\n'`
> 
> Store the generated Base64-encoded output as the private key value in the Keyring.

#### Microsoft 365 OneDrive

If your **Connector Type = Microsoft 365 OneDrive**, configure the following Credentials Auth Key and key names, depending on whether HashiCorp Vault is used with the OAuth 2.0 Secrets Engine Plugin.

| **Authentication type** | Credentials |
| --- | --- |
| OAuth 2.0 using Secrets Engine Plugin | - Under **Credentials Auth Key**, enable the **OAuth 2.0 Secrets Engine Plugin** toggle. - Under **Credentials Key Name**, no additional values are required other than the credential path already provided. |
| OAuth 2.0 without Secrets Engine Plugin | - Under **Credentials Auth Key**, keep the **OAuth 2.0 Secrets Engine Plugin** toggle disabled. - Under **Credentials Key Name**, provide the key variable names for the following credentials stored in HashiCorp: - Client ID Key - Client Secret Key |

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### Microsoft 365 Outlook

If your **Connector Type = Microsoft 365 Outlook**, configure the following Credentials Auth Key and key names, depending on whether HashiCorp Vault is used with the OAuth 2.0 Secrets Engine Plugin.

| **Authentication type** | Credentials |
| --- | --- |
| OAuth 2.0 using Secrets Engine Plugin | - Under **Credentials Auth Key**, enable the **OAuth 2.0 Secrets Engine Plugin** toggle. - Under **Credentials Key Name**, no additional values are required other than the credential path already provided. |
| OAuth 2.0 without Secrets Engine Plugin | - Under **Credentials Auth Key**, keep the **OAuth 2.0 Secrets Engine Plugin** toggle disabled. - Under **Credentials Key Name**, provide the key variable names for the following credentials stored in HashiCorp: - Client ID Key - Client Secret Key |

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### Microsoft 365 Outlook Attachments (Legacy)

If your **Connector Type = Microsoft 365 Outlook Attachments (Legacy)**, no additional values are required other than the credential path provided already.

During authentication, Securiti dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system.

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### Microsoft 365 SharePoint Online

If your **Connector Type = Microsoft 365 SharePoint Online**, configure the following Credentials Auth Key and key names, depending on whether HashiCorp Vault is used with the OAuth 2.0 Secret Engine Plugin.

| Authentication Type | Credentials |
| --- | --- |
| OAuth 2.0 using Secret Engine Plugin | - Under **Credentials Auth Key**, enable the **OAuth 2.0 Secret Engine Plugin** toggle**.** - Under **Credentials Key Name,** no additional values are required other than the credential path provided already. During authentication, Securiti dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system. > [!WARNING] > **Important** > > A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account. |
| OAuth 2.0 without Secret Engine Plugin | - Under **Credentials Auth Key**, keep the **OAuth 2.0 Secret Engine Plugin toggle** disabled**.** - Under **Credentials Key Name,** **provide** the key variable names for the following credentials stored in HashiCorp. - Client ID Key - Client Secret Key - (Optional) Certificate ThumbPrint Key - (Optional) Private Key |

#### Microsoft Dataverse

If your **Connector Type = Microsoft Dataverse**, no additional values are required other than the credential path provided already.

During authentication, Securiti dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system.

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### Microsoft Dynamics 365 CRM (Suite)

If your **Connector Type = Microsoft Dynamics 365 CRM (Suite)**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your Client ID and Client Secret key stored in HashiCorp.

#### Microsoft Teams

If your **Connector Type = Microsoft Teams**, no additional values are required other than the credential path provided already.

During authentication, Securiti dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system.

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### MongoDB

If your **Connector Type = MongoDB**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### MySQL

If your **Connector Type = MySQL**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### NetSuite

If your **Connector Type = NetSuite**, provide values for the following fields:

- **Credentials Key Name**: Provide key variable names for the following keys stored in HashiCorp vault:
  - Consumer Key
  - Consumer Secret Key
  - Token ID Key
  - Token Secret Key

#### OpenText Content Server

If your **Connector Type = OpenText Content Server**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### Oracle

If your **Connector Type = Oracle**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### Oracle Object Storage

If your **Connector Type = Oracle Object Storage**, provide values for the following fields:

- **Credentials Key Name**: Provide key variable names for the following keys stored in HashiCorp vault:
  - Finger Print Key
  - Passphrase Key
  - Credentials Key

#### PostgreSQL

If your **Connector Type = PostgreSQL**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### Power BI Service

If your **Connector Type = Power BI Service**, configure the following Credentials Auth Key and key names, depending on whether HashiCorp Vault is used with the OAuth 2.0 Secret Engine Plugin.

| Authentication Type | Credentials |
| --- | --- |
| OAuth 2.0 using Secret Engine Plugin | - Under **Credentials Auth Key**, enable the **OAuth 2.0 Secret Engine Plugin** toggle**.** - Under **Credentials Key Name,** no additional values are required other than the credential path provided already. During authentication, Securiti dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system. > [!WARNING] > **Important** > > A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account. |
| OAuth 2.0 without Secret Engine Plugin | - Under **Credentials Auth Key**, keep the **OAuth 2.0 Secret Engine Plugin toggle** disabled**.** - Under **Credentials Key Name,** **provide** the key variable names for the following credentials stored in HashiCorp. - Client ID Key - Client Secret Key |

#### Salesforce (Legacy)

If your **Connector Type = Salesforce (Legacy)**, no additional values are required other than the credential path provided already.

During authentication, Securiti dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system.

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### Salesforce CRM

If your **Connector Type = Salesforce CRM**, no additional values are required other than the credential path provided already.

During authentication, Securiti dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system.

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### SFTP

If your **Connector Type = SFTP**, provide values for the following fields:

- **Credentials Auth Key**: Select the **Authentication Type** for your connector. Select one of the following authentication types from the menu.
  - Key Based
  - Password Based
- **Credentials Key Name**: The credential keys vary depending upon the selection authentication type. The table below describes credential keys required for each authentication type.

| Authentication Type | Credentials |
| --- | --- |
| Key Based | Provide the key variable names for the following credentials stored in HashiCorp. - Username Key - Key |
| Password Based | Provide the key variable names for the following credentials stored in HashiCorp. - Username Key - Password Key |

#### Slack

If your **Connector Type = Slack**, no additional values are required other than the credential path provided already.

During authentication, Securiti dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system.

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### SMB

If your **Connector Type = SMB**, provide values for the following fields:

- **Credentials Auth Key**: Select the **Authentication Type** for your connector. Select one of the following authentication types from the menu.
  - NTLM (User/Password)

With the NTLM authentication type, you can use separate credentials for quarantine flow operations in SMB. To do so, from the **Use separate credentials for Quarantine** menu, select **Yes**.
  - Kerberos - Keytab
  - Kerberos - Password
- **Credentials Key Name**: The credential keys vary depending upon the selection authentication type. The table below describes credential keys required for each authentication type.

| Authentication Type | Credentials |
| --- | --- |
| NTLM (User/Password) | Provide the key variable names for the following credentials stored in HashiCorp. - User Key - Password Key Additionally, when storing separate credentials for quarantine, provide key variable names for the following keys: - Privileged User Key - Privileged Password Key |
| Kerberos - Keytab | Provide the key variable names for the following credentials stored in HashiCorp. - Kerberos Configuration File Key - Kerberos Keytab Key |
| Kerberos - Password | Provide the key variable names for the following credentials stored in HashiCorp. - Kerberos Configuration File Key - Kerberos Password Key |

#### Snowflake

If your **Connector Type = Snowflake**, provide values for the following fields:

- **Credentials Auth Key**: Select the **Authentication Type** for your connector. Select one of the following authentication types from the menu.
  - Basic
  - Key Pair Authentication
- **Credentials Key Name**: The credential keys vary depending upon the selection authentication type. The table below describes credential keys required for each authentication type.

| Authentication Type | Credentials |
| --- | --- |
| Basic | Provide the key variable names for the following credentials stored in HashiCorp. - User Name Key - Password Key |
| Key Pair Authentication | Provide the key variable names for the following credentials stored in HashiCorp. - Private Key File Key - User Name Key |

#### SQL Server

If your **Connector Type = SQL Server**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### Sybase ASE

If your **Connector Type = Sybase ASE**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### Teradata

If your **Connector Type = Teradata**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### Wasabi

If your **Connector Type = Wasabi**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your Token Id key and Token Secret key stored in HashiCorp.

#### Workday

If your **Connector Type = Workday**, provide values for the following fields:

- **Credentials Key Name**: Provide the key variable names for your user and password key stored in HashiCorp.

#### Zendesk Support

If your **Connector Type = Zendesk Support**, no additional values are required other than the credential path provided already.

During authentication, Securiti dynamically queries the credential path in HashiCorp Vault to retrieve the required keys. These keys are then used to generate an OAuth token, establishing a secure connection to the data system.

> [!WARNING]
> **Important**
> 
> A keyring can be configured with only one credential path for a specific set of credentials. To manage multiple accounts, you must configure separate keyrings for each account.

#### 

### Keyring settings for data system connectors

You must select and specify your HashiCorp keyring when activating your data system connector. For each self-hosted data system that supports HashiCorp keyring storage, following keyring settings must be configured.

1. In Securiti, open **System Settings** and choose **Integrations > Data Systems > Monitored**.
2. On the **Connector** tab for your data system instance, configure the following settings prior to connector activation.

| Setting | Description |
| --- | --- |
| Use Keyring | Enable the toggle to use keyring for accessing your credentials. |
| Keyring Type | Choose **HashiCorp** from the menu. |
| Keyring | Choose the keyring you created earlier. |

## Related

- [Azure Key Vault](/configuring-credential-vaults-azure-key-vault.md)
- [GCP Secret Manager credential vault](/configuring-credential-vaults-gcp-secret-manager-credential-vault.md)
