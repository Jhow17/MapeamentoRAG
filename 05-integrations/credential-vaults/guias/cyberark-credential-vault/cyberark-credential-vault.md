---
title: "CyberArk credential vault"
slug: "cyberark-credential-vault"
status: "update"
updated: 2026-08-27T13:20:31Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/cyberark-credential-vault"
stale: true
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# CyberArk credential vault

CyberArk Central Credential Provider (CCP) secures, stores, and tightly controls access to passwords and usernames, known as "secrets". When a data system is set up for CyberArk-based authentication, Securiti requests credentials from CyberArk through a mutual authentication mechanism. CyberArk then provides Securiti with the "secrets" for the data system, and Securiti uses these credentials to authenticate to that data system.

Securiti supports IP-based and certificate-based mutual authentication for CyberArk credential vaults. You can use these credential vaults to manage privilege account secrets for data systems that you integrate with Securiti.

> [!NOTE]
> **Note**
> 
> - The Credential Vaults feature is available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your Securiti tenant.
> - Securiti currently supports **CyberArk Credential Provider** for secure credential management for keyring functionality.
> - You can only activate CyberArk Vault instances through Securiti pods. When you activate the CyberArk Vault instance, Securiti automatically ensures the necessary CyberArk packages are activated on every active pod cluster on your Securiti instance.

## Roles and permissions

Securiti implements role-based access control on actions that can be performed for credential vaults and keyrings, such as keyring creation. For more information on roles and their permissions, see [Data Systems RBAC permissions](/v1/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-default-roles).

### 1. Configure an application for Securiti in CyberArk

1. Log in to CyberArk with your admin credentials.
2. On the left menu bar, click **Applications**.
3. Near the upper right corner of the page, click **Add Application**.
4. On the **Add Application** pop-up, apply the following settings, then click **Add**:

| Setting | Description |
| --- | --- |
| Name | Enter **SECURITI** |
| Business Owner | Configure name, email, and phone to suit |
| Location | Configure to suit |
| Access Permitted |
| Expiration Date |
| Disabled | Leave unmarked |
5. On the **Applications** list, click the new entry for Securiti, then click the **Allowed Machines** tab.
6. Click **Add**.
7. On the **Add allowed machine** pop-up, enter the following:
  - **Pod address of the machine:** For EDSS nodes where IP addresses are suspect to change, provide the client IP addresses, hostnames or DNS names of the machines permitted to access the Securiti application.
  - **Internal IPs:** Enter the internal IP addresses for Securiti pods in the same network.
  - **Public IPs:** Enter the public IPs or FQDNs for pods outside your network, such as in AWS.

### 2. Create an AIMWebService application

If you do not already have an AIMWebService application, create one as described in [1. Configure an application for Securiti in CyberArk](/v1/docs/cyberark-credential-vault), with one exception: "do not add allowed machines".

### 3. Setting up authentication for CyberArk

CyberArk Credential Provider (CCP) supports the following authentication methods for integrating with Securiti:

- IP-based Allowed Machines: This method requires you to allowlist the IP addresses of machines that request credentials from the CCP.
- Certificate-based authentication (Certificate Serial Number): This method uses digital certificates to authenticate the identity of the client machine to the CCP. We recommend you use this authentication method for more secure connection.

For more information on enabling certificate-based authentication with CyberArk, see [Using mTLS authentication with CyberArk](about:blank)

### 3. Create accounts and safes in CyberArk

Create one account for each data system type, and within it create a safe for each data store instance. To add an account and safe:

1. In CyberArk, on the left menu bar, click **Accounts**.
2. Near the upper right corner of the page, click **Add Account**.
3. On the Add Account page, click **Windows Domain Account**.
4. Click **Create Safe**.
5. On the **Create Safe** popup, enter a descriptive name for the safe, for example "Postgres."
6. On the **Define Account Properties** page, enter the data system credentials to store in the CyberArk Vault to authenticate with the Securiti’s connector.

> [!NOTE]
> **Note**
> 
> Data system credentials like "Client ID" and "Client Secret" are stored in the **Username** and **Password** fields in the CyberArk Vault.

![cyberark_storecreds.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf5afc1b-7b98-1e15-fc99-0f01388e5808(3).png)
7. Use the **Add Allowed Machine tools** to add client IPs, Hostnames, or DNS for the machine from which you access CyberArk.
8. On the **Accounts View** page, click the new account you just created, then click **Additional details & actions in classic interface**.
9. On the **Account Details** page, record the **Safe** and **Name** parameters to use later when you create a keyring for the data system.
10. In CyberArk, click **Policies**, and on the Policies page click **Access Control (Safes)**.
11. On the **Access Control (Safes)** page, click the safe you just created, then near the lower right corner click **Members**, then add the following members:

For each of these members, on the **Add Safe Membe**r pop-up, mark the checkbox for **Allow Safe without confirmation**.
  - `AIMWebService`
  - `Prov_COMPONENTS`
  - `SECURITI` (the application you created earlier)

### 4. Configure the CyberArk vault instance in Securiti

1. In Securiti, open the main menu and select **Integrations > Credential Vaults**.
2. On the Credential Vaults page, near the upper right corner of the page, click **Add Integration** to create a new instance.
3. From the catalog of available credential vaults, select **CyberArk**.
4. On the **Basic Information** tab, enter a name and location for the CyberArk vault instance, and if you want, also choose additional co-owners (by default you are the owner).
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
| Authentication Method | Choose one of the following authentication methods from the menu: - Allowed Machines (IP-based) - Certificate Serial Number > [!WARNING] > Important > > You must place the certificate/key pair on the Securiti pod using securitictl utility, as described in Placing certificate and key file on pod. > > > > Certificate Serial Number authentication is supported on pod versions 1.137.0 and above only. |
| HTTP Protocol | Choose the appropriate http protocol to authenticate with CyberArk. Select HTTP/1.1 or HTTP/2 from the menu. |
| REST web service URL | Enter the URL of your Central Credential Provider web server. The URL must start with htps://, for example `https://10.100.255.255` or `https://ccp-aim-webserv.example.com`. |
| Port | Enter the number of the port for the REST web service. Typically, this is `443`. |
| Application ID | Enter the application name you used when configuring the application in CyberArk, for example **SECURITI**. |
| AIM Service | Enter the name of your AIM Service. Typically the name is `AIMWebService`. |
8. On the Test Connection popup, click **Yes, proceed with testing**. Securiti validates the authentication information.
9. View the connection status in the **Overview** tab.

### 5. Create keyrings

Create keyrings that point to the connector secrets that you have placed in your key vault:

1. In System Settings, open **Integrations > Credentials > Keyrings** and click **Create Keyring**.

![cyberark_keyring.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1ef0e5d8-94db-d1d8-e1a8-58639f6863e4(3).png)
2. On the **Add Keyring** popup, apply the following settings, then click **Add Keyring**:

| Setting | Description |
| --- | --- |
| Keyring Name | Enter a descriptive name for the keyring. |
| Keyring Description | (Optional) Enter a description for the keyring. |
| Keyring Type | Choose **CyberArk Vault**. |
| Connector Type | Choose the type of data system for the keyring. |
| Vault Instance | Choose the CyberArk credential vault you configured earlier. |
| Safe | Choose the safe on the CyberArk Central Credential Provider server that contains the credentials you want to retrieve. |
| Folder | Choose the folder on the CyberArk Central Credential Provider server that contains the credentials you want to retrieve. The default is root. |
| Object | Enter the name of the password object to retrieve within the folder. |

### 6. Configure data systems to use the keyrings

Currently, Securiti supports CyberArk keyring storage for the following data systems:

- [Amazon DocumentDB](/v1/docs/amazon-documentdb-connectors)
- [Amazon RDS for MySQL](/v1/docs/amazon-rds-for-mysql-connectors)
- [Amazon RDS for PostgreSQL](/v1/docs/amazon-rds-for-postgresql-connectors)
- [Amazon RedShift](/v1/docs/amazon-redshift-connectors-1)
- [Amazon S3](/latest/docs/amazon-s3-connectors-1)
- [Azure Cosmos DB for MongoDB](/v1/docs/azure-cosmos-db-connectors-1)
- [Cassandra](/v1/docs/cassandra-connectors)
- [Google Cloud Storage](/latest/docs/google-cloud-storage-connector-1)
- [Google Drive (Google Workspace)](/latest/docs/g-suite-google-drive-connectors)
- HP NonStopSQL
- [IBM Db2](/v1/docs/ibm-db2-and-zos-connectors)
- [IBM Db2 zOS](/v1/docs/ibm-db2-and-zos-connectors)
- [Microsoft 365 Lists](/latest/docs/microsoft-365-lists-connectors-1)
- [Microsoft 365 OneDrive](/v1/docs/microsoft-365-onedrive-connectors)
- [Microsoft 365 Outlook](/latest/docs/microsoft-365-outlook-connectors)
- [MongoDB](/latest/docs/mongodb-connectors)
- [MySQL](/v1/docs/mysql-connectors)
- [Oracle](/v1/docs/oracle-connectors)
- [PostgreSQL](/v1/docs/postgresql-connectors-1)
- [Power BI Service](/latest/docs/power-bi-service-connectors)
- [S3 Compatible Storage](/latest/docs/s3-compatible-storage-connectors)
- [Salesforce CRM](/v1/docs/salesforce-crm-connectors)
- [SMB](/v1/docs/smb-connectors)
- [Shopify](/v1/docs/shopify-connectors)
- [Snowflake](/v1/docs/snowflake-connectors)
- [SQL Server](/v1/docs/microsoft-sql-server-connectors)
- [Teradata](/v1/docs/managing-data-system-connectors)

For each such data system where you want to use CyberArk:

1. In Securiti, open **System Settings** and choose **Integrations > Data Systems > Monitored**.
2. Create a new data system instance, and on the Connector tab apply the following settings, then click **Authenticate & Activate Connector**:

| Setting | Description |
| --- | --- |
| Use Keyring | Enable the toggle. |
| Keyring Type | Choose **CyberArk**. |
| Keyring | Choose the keyring you created earlier in [5. Create keyrings](/v1/docs/cyberark-credential-vault). |
