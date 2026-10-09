---
title: "Azure Key Vault"
slug: "configuring-credential-vaults-azure-key-vault"
updated: 2026-08-31T21:00:01Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/configuring-credential-vaults-azure-key-vault"
stale: true
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# Azure Key Vault

Securiti supports credential vaults that you can use to manage privilege account secrets for data systems that you integrate with Securiti.

> [!NOTE]
> **Note**
> 
> The Credential Vaults feature is available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your Securiti tenant.

Azure Key vault helps you manage, retrieve, and rotate your passwords, credentials, and other secrets throughout their life cycles.

It lets you replace hard coded credentials in your code, including passwords, with an API call to Azure Key vault to retrieve the secret programmatically. This helps ensure the secret cannot be compromised by someone examining your code, because the secret no longer exists in the code. You can also configure Azure key vault to automatically rotate the secret for you according to a specified schedule. This lets you replace long-term secrets with short-term ones, significantly reducing the risk of compromise.

> [!NOTE]
> **Important**
> 
> You can only activate Azure Key Vault instances through Securiti Pods and Elastic Pod clusters. Activating the Azure Key Vault instance automatically ensures the necessary Azure Key Vault packages are activated on every active Pod Cluster on your Securiti instance.

Following credentials are required for setting up an Azure Key Vault Cloud instance in Securiti.

- Azure Vault Name
- Azure Vault Tenant ID
- Client ID
- Secret Key

## Roles and permissions

Securiti implements role-based access control on actions that can be performed for credential vaults and keyrings, such as keyring creation. For more information on roles and their permissions, see [Data Systems RBAC permissions](/v1/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-default-roles).

### 1. Registering application in Microsoft Entra ID

1. Log into [Azure portal](http://portal.azure.com).
2. On Home page, select **Microsoft Entra ID**.
3. Click **Add** to add your Azure application.

![azuresql_addapplication.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-16f74427-daf8-ff38-9dfd-c7c7d73eaee6(3).png)
4. Enter the application name and leave other fields as default.
5. Click **Create.**
6. On the Microsoft Entra ID **Overview** page, record the "Tenant ID" for your azure portal to use later.
7. On the **Overview** page, from the top row, click **Add** and select **App Registration** from the menu.

![azuresql_addapplication.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-16f74427-daf8-ff38-9dfd-c7c7d73eaee6(3).png)
8. Enter your application name and click **Register**.

![azuresql_registerapp_menu.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3f559dc0-0f90-3763-0cca-c9a2fdcf25e8(3).png)

For more information on creating and registering applications, refer to [Microsoft Entra's official documentation.](https://learn.microsoft.com/en-us/entra/verified-id/verifiable-credentials-configure-tenant#register-an-application-in-microsoft-entra-id)

### 2. Creating Service Principal in Azure portal

To authenticate and retrieve secrets from the Azure Key Vault, you must create a service principal. The following parameters represent the service principal:

- Client ID
- Client Secret

Perform the following steps to obtain service principal credentials:

1. On the **Overview** page, Record "Client ID" for your newly registered Entra ID application. ![vault_azurekey_clientID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5619b1a9-00dc-0435-9167-1225bba73b41(3).png)
2. On the left sidebar, select **Certificates & Secrets**.
3. On the **Certificates & Secrets** page, under the **Client secrets** tab, click **+** **New client secret** to add a new secret for authentication.
4. On the **Add a client Secret** popup, enter the description, and select the expiry date.
5. Click **Add.** ![Adding a client secret in IntraID-Securiti application registration settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Vault-Secret.png)

It shows you the list of clients secrets.
6. Under the **Value** column, record the client secret.

> [!NOTE]
> Note
> 
> You must copy the client secret immediately after its creation. Copy icons disappears when you leave this page.

### 3. Creating Azure Key Vault in Azure portal

1. Log into [Azure portal](http://portal.azure.com).
2. Type "key vaults" in the search bar and select **Key vaults**.

![vault_azurekey_vaultsportal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-19594c4e-69f4-d0cf-498e-6d5f3cad9a1e(3).png)
3. On the top left corner of the **Key vaults** page, click **Create**.

![vault_createvault_azureportal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4a157798-dd73-59de-bca3-3acdcb5bc5c1(3).png)
4. In the **Create a key vault** page, enter the vault name and select resource group. Leave other fields as default.

![vault_createvaultmenu_azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f1bfd080-4d1d-847e-c7a8-e5be21a86637(3).png)
5. Click **Next**
6. Under the **Access configuration** tab, mark the radio button for one of the Permission model:
  - Azure role-based access control (recommended)
  - Vault access policy
7. Click **Review + create**. ![Access configuration settings for creating a key vault in Azure platform.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Azure-Key-Vault-Role.png)
8. Proceed to assigning permissions to Azure Key Vault application.

### 4. Assigning permissions in Azure Key Vault to Entra ID application

> [!NOTE]
> Note
> 
> You must assign the required permissions to the Service Principal; otherwise, Securiti doesn’t get access to Vault secrets or gives error in authentication.

Perform the following steps to assign permissions or roles according to Permissions model you selected while creating Azure Key Vault:

- **Azure role-based access control permission model:** To assign `Key Vault Crypto User` and `Key Vault Secrets User` roles to the Entra ID application you created for Azure Key Vault:
  1. On the left sidebar of the your Azure Key Vault, choose **Access control (IAM)**.
  2. On the **Access Control (IAM)** page, click **+ Add** and select **Add role assignment** from the menu. ![Access control interface showing role assignments and options to check access levels.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Role-assignment.png)
  3. On the **Add role assignment** page under the **Role** tab, search and select the `Key Vault Crypto User` role from the list.
  4. Click **Next**. ![Adding role assignment for Key Vault Crypto User in Azure Access Control settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/choose-role.png)
  5. Under the **Members** tab, mark the radio button for **User, group, or service principal** as role assignee.
  6. Click **+ Select members** to assign the above to existing Azure application. It opens a dialogue box on the right side to search and select the Entra ID application.
  7. On the right side of the **Select members** dialogue box, search and select the Entra ID application you created earlier. ![Adding role assignment in Azure Key Vault with member selection options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-member.png)
  8. On the left bottom of the **Add role assignment** page, click **Review + assign**. It assigns the selected role to the Entra ID application used in the Azure Key Vault setup.
  9. Repeat the same steps again to add the `Key Vault Secrets User` assignment to Entra ID application
  10. Once done, click **Review + assign.**
- **For Vault Access policy:** To assign `Get` and `List` permissions to the Entra ID application you created for Azure Key Vault:
  1. **On the left side bar, click Access policies.**
  2. On the top of the **Access policies** page, click **Create**.
  3. On the **Create an access policy** page under the **Permissions** tab, choose the `Get` and `List` permissions for following categories, as shown below:
    - Key Management Operations
    - Select Management Operations
    - Certificate Management Operations
  4. Click **Next**. ![Access policy configuration screen showing key and secret permissions options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Get-List-Policy(1).png)
  5. Under the **Principal** tab, search and select the Microsoft Entra ID application you want to assign the above permissions.
  6. Click **Next**. ![Creating an access policy in the Azure portal, selecting a principal for permissions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-Principal.png)
  7. Under the **Application (optional)** tab, click **Next**.
  8. Under the **Review + create** tab, click **Review + create**.

### 5. Adding secret in Azure key vault

1. Select the Azure vault instance you created in the above procedure.
2. From the left menu of vault page, click **Secrets** below **Objects** section.

![vault_addsecrets_Azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08bc1e94-b914-8fc0-fce9-62712d22a82a(3).png)
3. From the top row, click **Generate/Import**.

![vault_generateimport_azureportal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7ea6f6e8-2f6c-6909-eecc-72bb39417726(3).png)
4. A **Create a secret** screen opens, enter the Unique secret name and secret value you want to store in vault.

![vault_createsecretmenu_azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8db1cc05-6ed6-b225-d9fa-a0c4da594d1f(3).png)

### 6. Configuring the Azure key vault instance in Securiti

1. In Securiti, open **System Settings** and choose **Integrations > Credentials > Credential Vaults**.
2. On the Credential Vaults page, near the upper right corner of the Azure Key Vault tile, click **+** to create a new instance.
3. On the Basic Information tab, Under **Instance Name** section, enter a name for the Azure Key Vault instance.
4. Under the **Instance Location** section, select **Country, State,** and **City** (optional) for the Azure Key Vault instance.
5. Under the **Owners** section, select the **Primary Owner** for this Azure Key Vault instance.
6. Click **Create Instance & Continue**.
7. On the **Authentication** tab, select a pod(s) from the **Pod Configuration** menu where a vault authenticates.

> [!NOTE]
> Note
> 
> - Securiti authenticates the vault only on the pods you select. You can choose all pods, a single pod, or multiple pods for a vault instance. If you select **ALL**, Securiti runs vault authentication across all pods.
> - You can update pod selection after creation without recreating the vault configuration.
> - Only vaults associated with the same pod as the data system connector appear as available keyrings during connector configuration.

For authentication method, select **Basic**.
8. Specify the following for your Azure Key Vault instance.

| Setting | Description |
| --- | --- |
| Vault Name | Enter the vault name for your Azure Key Vault you [created in Azure portal.](/v1/docs/azure-key-vault) The vault name uses a string value. See an example below. *securiti-vault* |
| Tenant ID | Enter the tenant ID for your Entra app you acquired [above](/v1/docs/azure-key-vault). |
| Authentication Type | Select **Service Principal** as the authentication type. |
| Client ID | Specify the client ID you acquired [above](/v1/docs/azure-key-vault). |
| Secret Key | Specify the client secret you acquired [above](/v1/docs/azure-key-vault). |
9. Click **Test and Save**.
10. On the Test Connection popup, click **Yes, proceed with testing**. Securiti validates the authentication information.
11. Click the **Overview** tab, to review and validate the connection.

### 7. Creating keyrings

Create keyrings that point to the connector secrets that you have placed in your key vault:

1. In System Settings, open **Integrations > Credentials > Keyrings** and click **Create Keyring**.
2. On the Add Keyring popup, apply the following settings, then click **Add Keyring**:

| Setting | Description |
| --- | --- |
| Keyring Name | Enter a descriptive name for the keyring. |
| Keyring Description | (Optional) Enter a description for the keyring. |
| Keyring Type | Choose **Azure Key Vault**. |
| Connector Type | Choose the type of data system for the keyring. |
| Vault Instance | Choose the Azure key vault you configured earlier. |
| User Key | Choose the user key configured [when adding secrets to vault in azure portal](/v1/docs/azure-key-vault). |
| Password Key | Choose the password key configured [when adding secrets to vault in azure portal](/v1/docs/azure-key-vault). |

### 8. Configuring data systems to use the keyrings

Currently, Securiti supports Azure Key Vault keyring storage for the following data systems:

- Azure Data Lake Storage (ADLS) Gen2
- Azure Files
- Databricks
- Google Cloud Storage
- IBM Db2
- Microsoft Azure SQL Database
- Microsoft Dynamics 365 Finance & Operations
- Microsoft 365 Lists
- Microsoft 365 SharePoint Online
- MongoDB
- MySQL
- Oracle
- PostgreSQL
- Power BI Service
- SMB
- Snowflake
- SQL Server

For each data system where you want to use Azure Key Vault:

1. In Securiti, open **System Settings** and choose **Integrations > Data Systems > Monitored**.
2. Create a new data system instance, and on the Connector tab apply the following settings, then click **Authenticate & Activate Connector**:

| Setting | Description |
| --- | --- |
| Use Keyring | Enable the toggle. |
| Keyring Type | Choose **azure_key_vault**. |
| Keyring | Choose the keyring you created earlier in [4. Adding secret in Azure key vault](/v1/docs/azure-key-vault). |

Similar to a pod, except that it features auto-scaling so you don't have to add secondary nodes to increase its processing capacity.

An application running on a server or compute instance that connects with your on-premises or private data systems to:

- Intelligently scan them to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account
- Act as a hop-off point for DSR requests for your on-premises and user-defined data systems

A cluster is comprised of a primary node and up to nine secondary nodes.

## Related

- [Delinea Secret Manager credential vault](/configuring-credential-vaults-delinea-secret-manager-credential-vault.md)
- [GCP Secret Manager credential vault](/configuring-credential-vaults-gcp-secret-manager-credential-vault.md)
- [CredStash credential vault](/configuring-credential-vaults-credstash-credential-vault.md)
