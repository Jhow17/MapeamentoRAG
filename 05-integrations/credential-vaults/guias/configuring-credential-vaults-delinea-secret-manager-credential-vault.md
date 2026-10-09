---
title: "Delinea Secret Manager credential vault"
slug: "configuring-credential-vaults-delinea-secret-manager-credential-vault"
updated: 2026-04-28T04:12:34Z
published: 2026-04-28T04:12:34Z
canonical: "helpcenter.securiti.ai/configuring-credential-vaults-delinea-secret-manager-credential-vault"
stale: true
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# Delinea Secret Manager credential vault

Securiti supports credential vaults that you can use to manage privilege account secrets for data systems that you integrate with Securiti.

> [!NOTE]
> **Note**
> 
> The Credential Vaults feature is available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your Securiti tenant.

Delinea Secret Manager helps you manage, retrieve, and rotate your passwords, credentials, and other secrets throughout their life cycles.

It lets you replace hard coded credentials in your code, including passwords, with an API call to Secrets Manager to retrieve the secret programmatically. This helps ensure the secret cannot be compromised by someone examining your code, because the secret no longer exists in the code. You can also configure Secrets Manager to automatically rotate the secret for you according to a specified schedule. This lets you replace long-term secrets with short-term ones, significantly reducing the risk of compromise.

> [!NOTE]
> **Important**
> 
> You can only activate Delinea Secret Manager Vault instances through Securiti Pods and Elastic Pod clusters. Activating the Delinea Secret Manager Vault instance automatically ensures the necessary Delinea Secret Manager packages are activated on every active Pod Cluster on your Securiti instance.

Following credentials are required for setting up a Delinea Secret Server Cloud instance in Securiti.

- Username
- Password
- Server URL
- Secret ID

## Roles and permissions

Securiti implements role-based access control on actions that can be performed for credential vaults and keyrings, such as keyring creation. For more information on roles and their permissions, see [Data Systems RBAC permissions](/v1/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-default-roles).

### 1. Creating user role in Delinea Secret Server (DSS)

> [!NOTE]
> **Note**
> 
> You must have "View Secret"permission for authentication to Delinea Secret Server (DSS).

1. In your DSS console, from the left navigation menu, go to **Access > Users** to create a new user in DSS.

![vault_delinea_users1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ee0648ed-5156-ce5f-783e-5b5774ae34d5(3).png)
2. Click **Create user** and add the necessary details for your account.
3. Mark the checkbox for **Application User** and **Enabled**. Save the password for later use. Click **Add User**

![vault_delinea_adduser2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-39004448-3708-3cbe-e45c-a3a229441fbf(3).png)
4. On the **Users** tab, click **Roles** to view the role assigned to you by default. By default, DSS assigns User role to the newly created users.

![vault_delinea_roles3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b89baa54-d1b6-cdb3-3d67-8c24f08f2d71(3).png)
5. Follow the procedure below to create a user role with least privilege access and assign permissions.
  1. In the left navigation menu, go to **Access > Roles** to create a new role. The page displays a list of all available roles.

![vault_delinea_allroles4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-67521783-404c-cdf4-88f3-1d7ccbc1c248(3).png)
  2. From the upper right corner of the **Roles** page, click **Create Role**, choose a name for your role and click **Create role**.

![vault_delinea_createrole5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c714dca0-ac06-9bea-19f1-6ae393605dfa(3).png)
  3. Select your role and click **Permissions** tab to view the assigned permissions to your role. By default, newly created roles do not have any assigned permissions.

![vault_delinea_permissionstab6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-171b89be-8934-76a6-e15b-85ad096cb185(3).png)
  4. On the upper right corner of your role permissions, click **Edit** and select **Unassigned** from the menu.
  5. Add **View Secret** permission to view the contents of a secret.

![vault_delinea_viewsecretpermission7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e5e67dae-92be-e0c1-e4a7-3e0f4873384d(3).png)
  6. Click **Save**.
6. Assign the user role with correct permissions your account by selecting **Access > Users**.
7. On the **Roles** tab, click **Edit** and select the newly created role from the menu.
8. Unselect any other role and click **Save**.

![vault_delinea_assignrole8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-caf094e8-f87a-29d0-a829-79d400b9d58d(3).png)

### 2. Acquiring server URL and secret ID in Delinea Secret Server (DSS)

To authenticate and retrieve secrets from the Delinea Secret Server (DSS), following parameters are required.

- Server URL
- Secret ID

Follow the matching procedure below to acquire these parameters in DSS.

> [!NOTE]
> **Note**
> 
> You must share the secret with the user authenticating the vault in order to retrieve a secret from the DSS.

1. On the left menu, go to **Secrets** and in the **All Secrets** section, select the secret that needs to be shared.

![vault_delinea_allsecrets9.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-68d2840d-c7e0-d396-dfa1-c2c581c274c4(3).png)
2. Click on the secret and from the top row, click **Sharing**. By default the secret is shared with the Admin user or the user that has created the secret.

![vault_delinea_sharingtab10.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fc188b2a-6a48-bd8b-d5c2-ca4d880cda67(3).png)
3. Click **Edit** and select **Unassigned** from the menu. Choose the user to share secret with.

![vault_delinea_sharingwuser11.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c8c9bcb3-1731-fb43-3dac-a0aaab38f5f3(3).png)
4. From the menu, select **View as Secret** permission and click **Save**.
5. Select the secret and from the search bar of the page, acquire the Server URL and Secret ID as follows.

*<server-url>/app/#/<secret-id>/general*

You can fetch the following parameters from this page.

![vault_delinea_credentials12.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c30cda5f-f495-c5a6-7276-3eb376cb8026(3).png)

See an example below.

https://securiti-ai.secretservercloud.com/app/#/secrets/11/general

In the above example, "securiti-ai.secretservercloud.com" is the server URL and 11 is the secret ID.
  - Username (record it for later use in the **User Key** field when creating keyring)
  - Password (record it for later use in the **Password Key** field when creating keyring)
  - Server URL
  - Secret ID

### 3. Configure the Delinea Secret Manager vault instance in Securiti

1. In Securiti, open the main menu and select **Integrations > Credential Vaults**.
2. On the Credential Vaults page, near the upper right corner of the page, click **Add Integration** to create a new instance.
3. From the catalog of available credential vaults, select **Delinea Secret Manager**.
4. On the **Basic Information** tab, enter a name and location for the Delinea Secret Manager vault instance, and if you want, also choose additional co-owners (by default you are the owner).
5. Click **Create Instance & Continue**.
6. On the **Authentication** tab, select a pod(s) from the **Pod Configuration** menu where a vault authenticates.

> [!NOTE]
> Note
> 
> - Securiti authenticates the vault only on the pods you select. You can choose all pods, a single pod, or multiple pods for a vault instance. If you select **ALL**, Securiti runs vault authentication across all pods.
> - You can update pod selection after creation without recreating the vault configuration.
> - Only vaults associated with the same pod as the data system connector appear as available keyrings during connector configuration.

For authentication method, select **Basic**.
7. Specify the following for your Delinea Secret Server instance.

| Setting | Description |
| --- | --- |
| Username | Enter the username for your Delinea Secret Server account. The username uses a string value. See an example below. *john.doe* |
| Password | Enter the password for your Delinea Secret Server account. |
| Server URL | Specify the value for server URL you acquired in the Delinea Secret Server portal, in [step 5 of the procedure above](/v1/docs/delinea-secret-manager-credential-vault). See an example below. *securiti-secretservercloud.com* |
8. Click **Test and Save**.
9. On the Test Connection popup, click **Yes, proceed with testing**. Securiti validates the authentication information.
10. View the connection status in the **Overview** tab.

### 4. Create keyrings for Delinea Server

Create keyrings that point to the connector secrets that you have placed in your key vault:

1. In System Settings, open **Integrations > Credentials > Keyrings** and click **Create Keyring**.
2. On the Add Keyring popup, apply the following settings, then click **Add Keyring**:

| Setting | Description |
| --- | --- |
| Keyring Name | Enter a descriptive name for the keyring. |
| Keyring Description | (Optional) Enter a description for the keyring. |
| Keyring Type | Choose **Delinea Secret Manager**. |
| Connector Type | Choose the type of data system for the keyring. For Delinea Secret Manager, choose **SMB**. |
| Vault Instance | Choose the Delinea Secrets Manager credential vault you configured earlier. |
| Secret ID | Specify the secret ID you acquired in Delinea Secret Manager, described in [step 5 of the procedure above](/v1/docs/delinea-secret-manager-credential-vault). |
| User Key | Enter the field slug name configured in Delinea Secret Manager. The user key value is case sensitive. |
| Password Key | Enter the password configured in Delinea Secret Manager. |

![Addkeyring_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-55baecbf-314c-f87f-2d5c-f1ae78c96210(7).png)

[](/v1/docs/securiti-pods-and-elastic-pods)

#### Storing separate quarantine credentials for SMB

You can store separate credentials for quarantine flow operations in SMB in the credentials vault. To store Privileged User Key and Privileged Password Key in your credential vault or keyring.

1. On the Add Keyring popup, configure settings to suit and select **SMB** in the **Connector Type** field.
2. In the **Use separate credentials for Quarantine** field in **Credentials Auth Key** section, select **Yes**.
3. In the **Credentials Key Name** section, enter your Privileged User Key and Privileged Password Key in the respective fields

![select_Quarantine.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-89345daa-f131-ae6b-dcb7-2e5e37f99e61(3).png)

#### 

### 5. Keyring settings in connectors

Currently, Securiti supports Delinea Secret Manager keyring storage for the following data systems:

- SMB
- SQL Server

For each data system where you want to use Delinea Secret Manager:

1. In Securiti, open **System Settings** and choose **Integrations > Data Systems > Monitored**.
2. Create a new data system instance, and on the Connector tab apply the following settings, then click **Authenticate & Activate Connector**:

| Setting | Description |
| --- | --- |
| Use Keyring | Enable the toggle. |
| Keyring Type | Choose **Delinea Secret Manager**. |
| Keyring | Choose the keyring you created earlier in [4. Create keyrings for Delinea Server](/v1/docs/delinea-secret-manager-credential-vault). |

Similar to a pod, except that it features auto-scaling so you don't have to add secondary nodes to increase its processing capacity.

An application running on a server or compute instance that connects with your on-premises or private data systems to:

- Intelligently scan them to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account
- Act as a hop-off point for DSR requests for your on-premises and user-defined data systems

A cluster is comprised of a primary node and up to nine secondary nodes.

## Related

- [GCP Secret Manager credential vault](/configuring-credential-vaults-gcp-secret-manager-credential-vault.md)
- [CredStash credential vault](/configuring-credential-vaults-credstash-credential-vault.md)
