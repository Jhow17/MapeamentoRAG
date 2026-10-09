---
title: "Connecting SMB with Securiti"
slug: "connecting-smb-with-securiti"
updated: 2026-09-11T11:05:19Z
published: 2026-09-11T11:05:19Z
canonical: "helpcenter.securiti.ai/connecting-smb-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting SMB with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating a data system instance

Perform the following steps to create a Data system instance:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the **Platform Services** section in the navigation, select **Data Systems**. It takes you to the Monitored Data Systems page under Integrations.
4. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
5. On the **Add Integration** page, click the **Self Hosted** tab.
6. From the data system list, choose your relevant data system.
7. On the **Basic Information** tab, apply the following settings:

| **Parameter** | **Description** | **Examples** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the Instance. We recommend using the application name you entered when configuring the application in SMB. | SMB - Data |
| Instance Location | Select one of your preferred Hosting locations from the menu. | - IaaS - SaaS - Private Cloud Storage > [!NOTE] > Note > > IaaS location opens a new menu to select Service Providers. |
| Country | Select the country of hosting location from the menu. | Country: United States |
| State/Region | Select the State or region inside the hosting country. | State: California |
| City | Enter the city name where the hosting server is located. | City: San Jose |
| Owners | Choose additional co-owners for the Instance if you want. By default, you are the Instance owner. | John.doe@securiti.ai |
8. Click **Create Instance & Continue**.

## Authenticating the connector

Before proceeding with the SMB connector authentication, apply these permissions:

> [!NOTE]
> **Note**
> 
> We assume you are the admin of your SMB Instance or have access to the user with admin privileges.
> 
> To include the `created_date` in your files, see the [Troubleshooting for SMB connector](/latest/docs/troubleshooting-for-smb-connector).

- **Read**: Read permission is required for all shares provided in the SMB Configuration. Ensure the user account used for Authentication has read access to the specified SMB shares.
- **Write** (For Quarantine Policy): To apply the quarantine policy, write permission is also required on both the source and destination paths. This ensures that Securiti can securely quarantine documents containing high-level personally identifiable information (PII) in the specified location.

After creating an SMB connector instance, in the **Authentication** tab, authenticate your connector:

1. On the **Authentication** page, select the **Pod** you configured earlier in [Pods and Elastic Pods](/latest/docs/securiti-pods-and-elastic-pods).
2. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data. For more information, see [Configuring PCS Destination](https://helpcenter.securiti.ai/latest/docs/system-settings-configuring-private-cloud-storage).

> [!NOTE]
> Note
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
3. In the **Credentials** section, configure the following settings:

**NTLM (User/Password)**

Use the following table to add credentials for NTLM (User/Password) authentication type:

| Setting | Description |
| --- | --- |
| Host | Enter your server IP address in *xxx.xxx.xxx.xxx* format. See the example below. **192.158.1.38** |
| Share name | > [!WARNING] > **Important** > > Securiti discovers all available network shares in the SMB server if you provide root path "/" here. These shares are listed when defining the scope of the discovery scan. Enter SMB share name beginning with a **forward slash (/)**. See the example below. */smb-share* Replica server and Primary server must have the same Share Name to access the SMB resources successfully. > [!NOTE] > **Note** > > This share name is different from the one you use in quarantine operations for your files. |
| (Optional) Use Keyring | You can Enable the **Use Keyring** toggle if you want to use a Keyring to manage Credentials for the Instance as described in [Using keyrings](/latest/docs/creating-keyrings). For Quarantine flow, separate Credentials can be used via Keyring for SMB. |
| Keyring Type *(Use Keyring enabled)* | Enable the toggle to select Keyring type like **CredStash** Credential vault that you've used previously to store Keyring(s). > [!NOTE] > **Note** > > If you configure this connector for access scans, Securiti doesn't support Keyring-based credentials, regardless of vault type. Access Scan Definitions support only basic NTLM authentication. > > Configure a connector that doesn't use Keyring, or an IAM Metadata Source with NTLM credentials, instead. For more information, see [SMB - NetApp](https://helpcenter.securiti.ai/docs/smb-netapp). |
| Keyring | Select the Keyring you configured. Securiti supports the following vaults as keyrings, for SMB: - [CredStash credential vault](/latest/docs/configuring-credential-vaults-credstash-credential-vault) - [AWS Secrets Manager credential vault](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) - [CyberArk credential vault](/latest/docs/cyberark-credential-vault) - [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) - [Delinea Secret Manager credential vault](/latest/docs/configuring-credential-vaults-delinea-secret-manager-credential-vault) - [Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault) |
| User | If you are not using Keyring, enter your SMB server username.The username uses a string value. See example below. *John Doe* |
| Password | If you are not using Keyring, enter your SMB server password. See the example below. *testpassword@123* |
| Version | Specify the SMB version you acquired in [Acquire authentication credentials in SMB](/latest/docs/acquire-authentication-credentials-in-smb). The version uses a floating point number. See an examplebelow. `2.0` for SMB version 2 or `2.1.1` > [!NOTE] > **Note** > > Starting with Securiti release 1.150, Securiti no longer lets you activate new SMB connectors using SMBv1. Securiti recommends using SMBv2 or SMBv3 for new connectors. > > Existing SMBv1 connector activations continue to work without interruption and don't require reconfiguration, though you can migrate them to SMBv2 or SMBv3 at any time. For more information, see [Upgrading version for SMB connector](/latest/docs/migrating-from-smbv1-to-smbv2-3). |
| Domain | (Optional) Enter the domain name. See [Acquire authentication credentials in SMB](/latest/docs/acquire-authentication-credentials-in-smb) for more information. |
| Domain Controller | Enter the Hostname or IP of the domain controller to use for SID resolution when the file server cannot resolve domain accounts. > [!NOTE] > Note > > To use the Domain Controller configuration, upgrade to Securiti pod version 1.148.0 or higher. |
| Use SMB Server Replica for Scanning | Enable the toggle to add credentials for read-only Replica server in addition to primary server. You can use Replica server, such as a disaster recovery (DR) replica or a secondary site replica. You can also choose to read data from the replica server in discovery scans during business hours due to the load of scanning in primary server. File metadata in continues to represent the primary server. Policy actions such as quarantine and labeling still execute against the primary server. > [!NOTE] > Note > > - Both Replica server and Primary server must have the same Share Name to access the SMB resources successfully. > - To use this feature, you must upgrade your pod version to release 1.145 or higher. > - Data Inventory Sync support is not available for Replica Server. |
| Read Replica Host | If you have enabled **Use SMB Server Replica for Scanning** toggle, enter the server IP address of your replica server as a Host in *xxx.xxx.xxx.xxx* format. See the example below. `192.158.1.38` |
| Read Replica Domain | If you have enabled **Use SMB Server Replica for Scanning** toggle, Enter the domain name of Replica server as described in [Acquire authentication credentials in SMB](/latest/docs/acquire-authentication-credentials-in-smb). |
| Mounting Timeout | Specify the time interval for scanning operations. The interval reduces the default 24-hour mounting timeout in case of scan job failures. The maximum scan timeout is 24 hours. The mounting timeout is expressed in seconds. See an example below. *30* |
| (Optional) Allow Quarantine actions on this Data system | Enable the toggle for documents containing high-level personally identifiable information (PII). The provided quarantine path will undergo validation to ensure its existence and write access, guaranteeing a secure location for the quarantined documents. This toggle is a prerequisite to creating a File Insight Policy in Sensitive data Intelligence. For more information, see [Creating a File Insights policy to quarantine files](/latest/docs/creating-a-file-insights-policy). > [!NOTE] > Note > > You must grant read and write privileges to the scanning account for files to be quarantined and the relevant folder where you want to place quarantined files. |
| (Optional) Use separate Credentials for Quarantine | To use separate Credentials for quarantine policy, select **Yes** from the menu. Separate Credentials will be fetched from the vault in case **Use Keyring** is enabled. The below fields for privileged Credentials do not apply is Keyring is being used. > [!NOTE] > **Note** > > Separate Credentials is not supported for **Basic** and **CyberArk** Keyring types. |
| Privileged User *(separate Credentials for quarantine only)* | Enter username for quarantine Credentials. The privileged username uses a string value. See example below. *John-smb* |
| Privileged Password *(separate Credentials for quarantine only)* | Enter your password for quarantine Credentials. |
| (Optional) Quarantine Path *(for quarantine policy)* | > [!WARNING] > **Caution** > > The quarantine path and share name must be different for successful connector activation. Specify the path or share name where you want to move the quarantined files. The quarantine path must be a string that begins with a forward slash '/'. Depending on how you want to organize quarantined files, you can provide either a share name or a more specific file path within that share. Regardless of whether you specify a share name or a specific path, the original file path structure will be preserved in the quarantine location. This helps maintain context and traceability for quarantined files. > [!NOTE] > Note > > If you specify a share name as the quarantine path, Securiti treats it as a separate share on the same SMB host and mounts it using the credentials configured on the connector. This behavior applies to quarantining files within the same data system. For Central Quarantine, the mount path and quarantine path are configured as separate parameters on the destination. For more information, see [Using Central Quarantine Destination](/latest/docs/using-quarantine-destinations). See examples below. - To quarantine files in the root of a share (general quarantine location): - */quarantine* - To quarantine files in a specific sub-directory within a share: - */quarantine/Test2/Admin* |
| SMB Provider | In the **SMB Provider**, select from the following providers: - None - Dell Isilon - NetApp ONTAP > [!NOTE] > Note > > To fetch entitlements via the default LDAP method, select None from the available options above. |
| (Optional) Isilon API Port (For Dell Isilon Provider only) | Enter the Dell Isilion API Port number. It follows the following format: `8080` |
| ONTAP Management Hostname (For NetApp ONTAP Provider only) | The hostname or DNS name of the NetApp ONTAP management interface used to connect to the ONTAP REST API for collecting file system and permission metadata. See the example below: `ontap-mgmt.corp.local` > [!NOTE] > Note > > Enter the Hostname instead of the IP address. see the method below to get the hostname > > 1. For AWS FSx for NetApp ONTAP: Go to AWS Console → FSx → Your file system → Management endpoints → copy the Management DNS name > 2. For on-prem NetApp: Ask your NetApp admin for the cluster or SVM management hostname |
| ONTAP Management Username (For NetApp ONTAP Provider only) | The username used to authenticate with the NetApp ONTAP management API and access file system configuration and security information. See the example below: `fsxadmin`. |
| ONTAP Management Password (For NetApp ONTAP Provider only) | The password associated with the ONTAP management user account used for API authentication. See the example below: `MyOntapP@ssword123` |
| LDAP Server (For NetApp ONTAP Provider only) | The hostname or IP address of the Active Directory or LDAP server used to retrieve users, groups, and computer objects for entitlement discovery. See the example below: `dc01.corp.example.com` |
| LDAP Username (For NetApp ONTAP Provider only) | The service account username used to authenticate to Active Directory or LDAP and perform directory queries. See the example below: `admin@corp.example.com` |
| LDAP Password (For NetApp ONTAP Provider only) | The password for the LDAP service account used to authenticate to Active Directory. See the example below: `MYLDAP@ssword123` |
| (Optional) LDAP Base DN (For NetApp ONTAP Provider only) | The Distinguished Name (DN) that defines the starting location in the directory tree for LDAP searches. See the example below: `DC=corp,DC=example,DC=com` |
| Evaluate Data system size | Mark the checkbox to evaluate the Data system size during Authentication. The option computes the total size of all the files present under the given share name. Securiti calculates resource size on a weekly basis to keep the data size value up to date. |

**Kerberos Keytab**

Use the following table to add credentials using Kerberos authentication type:

| Setting | Description |
| --- | --- |
| Host | Enter your server IP address in *xxx.xxx.xxx.xxx* format. See the example below. **192.158.1.38** |
| Share name | Enter SMB share name beginning with a **forward slash (/)**. See the example below. */smb-share* > [!WARNING] > **Important** > > Securiti discovers all available network shares in the SMB server if you provide root path "/" here. These shares are listed when defining the scope of the Discovery scan. > [!NOTE] > **Note** > > This share name is different from the one you use in quarantine operations for your files. |
| (Optional) Use Keyring | You can Enable the **Use Keyring** toggle if you want to use a Keyring to manage Credentials for the Instance as described in [Using keyrings](/latest/docs/creating-keyrings). For Quarantine flow, separate Credentials can be used via Keyring for SMB. |
| Keyring Type *(Use Keyring enabled)* | Enable the toggle to select Keyring type like **CredStash** Credential vault that you've used previously to store Keyring(s). |
| Keyring | Select the Keyring you configured. Securiti supports the following vaults as keyrings, for SMB: - [CredStash credential vault](/latest/docs/configuring-credential-vaults-credstash-credential-vault) - [AWS Secrets Manager credential vault](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) - [CyberArk credential vault](/latest/docs/cyberark-credential-vault) - [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) - [Delinea Secret Manager credential vault](/latest/docs/configuring-credential-vaults-delinea-secret-manager-credential-vault) - [Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault) |
| Kerberos Configuration File | If you are not using Keyring, upload the Kerberos Configuration File received from the Kerberos server administrator. |
| Kerberos User Principal | Enter the kerberos principal for HTTP communication. See the example below. *HTTP or Instance@domain.com* |
| Kerberos Keytab | If you are not using Keyring, upload the keytab file that contains a pair of kerberos principal and encrypted keys. |
| Kerberos Password | If you are not using Keyring, enter your Kerberos server password. |
| Version | Specify the SMB version you acquired in [Acquire authentication credentials in SMB](/latest/docs/acquire-authentication-credentials-in-smb). The version uses a floating point number. See an example below. `2.0` for SMB version 2 or `2.1.1` > [!NOTE] > **Note** Starting with Securiti release 1.150, Securiti no longer lets you activate new SMB connectors using SMBv1. Securiti recommends using SMBv2 or SMBv3 for new connectors. > > Existing SMBv1 connector activations continue to work without interruption and don't require reconfiguration, though you can migrate them to SMBv2 or SMBv3 at any time. For more information, see [Upgrading version for SMB connector](/latest/docs/migrating-from-smbv1-to-smbv2-3). |
| Domain | (Optional) Enter the domain name. See [Acquire authentication credentials in SMB](/latest/docs/acquire-authentication-credentials-in-smb) for more information. |
| Domain Controller | Enter the Hostname or IP of the domain controller to use for SID resolution when the file server cannot resolve domain accounts. > [!NOTE] > Note > > To use the Domain Controller configuration, upgrade to Securiti pod version 1.148.0 or higher. |
| Use SMB Server Replica for Scanning | Enable the toggle to add credentials for read-only Replica server in addition to primary server. You can use Replica server, such as a disaster recovery (DR) replica or a secondary site replica. You can also choose to read data from the replica server in discovery scans during business hours due to the load of scanning in primary server. File metadata in continues to represent the primary server. Policy actions such as quarantine and labeling still execute against the primary server. > [!NOTE] > Note > > - Both Replica server and Primary server must have the same Share Name to access the SMBV resources successfully. > - To use this feature, you must upgrade your pod version to release 1.145 or higher. > - Data Inventory Sync support is not available for Replica Server. |
| Read Replica Host | If you have enabled **Read Replica Supported?** toggle, enter the server IP address of your replica server as a Host in *xxx.xxx.xxx.xxx* format. See the example below. *192.158.1.38* |
| Read Replica Kerberos Configuration File | If you have enabled **Read Replica Supported?** toggle, upload the Kerberos Configuration File received from the Replica Kerberos server administrator. |
| Read Replica Kerberos User Principal | If you have enabled **Read Replica Supported?** toggle, enter the kerberos principal for HTTP communication of the Relica server. See the example below. *HTTP or Instance@domain.com* |
| Read Replica Kerberos Keytab | If you have enabled **Read Replica Supported?** toggle, upload the keytab file that contains a pair of kerberos principal and encrypted keys from the replica server. |
| Read Replica Domain | If you have enabled **Read Replica Supported?** toggle, Enter the domain name of Replica server as described in [Acquire authentication credentials in SMB](/latest/docs/acquire-authentication-credentials-in-smb). |
| Mounting Timeout | Specify the time interval for scanning operations. The interval reduces the default 24-hour mounting timeout in case of scan job failures. The maximum scan timeout is 24 hours. The mounting timeout is expressed in seconds. See an example below. *30* |
| SMB Provider | In the **SMB Provider**, select from the following providers: - None - Dell Isilon - NetApp ONTAP > [!NOTE] > Note > > To fetch entitlements via the default LDAP method, select None from the available options above. |
| (Optional) Isilon API Port (For Dell Isilon Provider only) | Enter the Dell Isilion API Port number. It follows the following format: `8080` |
| ONTAP Management Hostname (For NetApp ONTAP Provider only) | The hostname or DNS name of the NetApp ONTAP management interface used to connect to the ONTAP REST API for collecting file system and permission metadata. See the example below: `ontap-mgmt.corp.local` > [!NOTE] > Note > > Enter the Hostname instead of the IP address. see the method below to get the hostname > > 1. For AWS FSx for NetApp ONTAP: Go to AWS Console → FSx → Your file system → Management endpoints → copy the Management DNS name > 2. For on-prem NetApp: Ask your NetApp admin for the cluster or SVM management hostname |
| ONTAP Management Username (For NetApp ONTAP Provider only) | The username used to authenticate with the NetApp ONTAP management API and access file system configuration and security information. See the example below: `fsxadmin`. |
| ONTAP Management Password (For NetApp ONTAP Provider only) | The password associated with the ONTAP management user account used for API authentication. See the example below: `MyOntapP@ssword123` |
| LDAP Server (For NetApp ONTAP Provider only) | The hostname or IP address of the Active Directory or LDAP server used to retrieve users, groups, and computer objects for entitlement discovery. See the example below: `dc01.corp.example.com` |
| LDAP Username (For NetApp ONTAP Provider only) | The service account username used to authenticate to Active Directory or LDAP and perform directory queries. See the example below: `admin@corp.example.com` |
| LDAP Password (For NetApp ONTAP Provider only) | The password for the LDAP service account used to authenticate to Active Directory. See the example below: `MYLDAP@ssword123` |
| (Optional) LDAP Base DN (For NetApp ONTAP Provider only) | The Distinguished Name (DN) that defines the starting location in the directory tree for LDAP searches. See the example below: `DC=corp,DC=example,DC=com` |
| Evaluate Data system size | Mark the checkbox to evaluate the Data system size during Authentication. The option computes the total size of all the files present under the given share name. Securiti calculates resource size on a weekly basis to keep the data size value up to date. |

**Kerberos Password**

Use the following table to add the credentials using Kerberos Password authentication type:

| Setting | Description |
| --- | --- |
| Host | Enter your server IP address in *xxx.xxx.xxx.xxx* format. See the example below. **192.158.1.38** |
| Share name | Enter SMB share name beginning with a **forward slash (/)**. See the example below. */smb-share* > [!WARNING] > **Important** > > Securiti discovers all available network shares in the SMB server if you provide root path "/" here. These shares are listed when defining the scope of the Discovery scan. > [!NOTE] > **Note** > > This share name is different from the one you use in quarantine operations for your files. |
| (Optional) Use Keyring | You can Enable the **Use Keyring** toggle if you want to use a Keyring to manage Credentials for the Instance as described in [Using keyrings](/latest/docs/creating-keyrings). For Quarantine flow, separate Credentials can be used via Keyring for SMB. |
| Keyring Type *(Use Keyring enabled)* | Enable the toggle to select Keyring type like **CredStash** Credential vault that you've used previously to store Keyring(s). |
| Keyring | Select the Keyring you configured. Securiti supports the following vaults as keyrings, for SMB: - [CredStash credential vault](/latest/docs/configuring-credential-vaults-credstash-credential-vault) - [AWS Secrets Manager credential vault](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) - [CyberArk credential vault](/latest/docs/cyberark-credential-vault) - [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) - [Delinea Secret Manager credential vault](/latest/docs/configuring-credential-vaults-delinea-secret-manager-credential-vault) - [Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault) |
| Kerberos Configuration File | If you are not using Keyring, upload the Kerberos Configuration File received from the Kerberos server administrator. |
| Kerberos User Principal | Enter the kerberos principal for HTTP communication. See the example below. *HTTP or Instance@domain.com* |
| Kerberos Keytab | If you are not using Keyring, upload the keytab file that contains a pair of kerberos principal and encrypted keys. |
| Kerberos Password | If you are not using Keyring, enter your Kerberos server password. |
| Version | Specify the SMB version you acquired in [Acquire authentication credentials in SMB](/latest/docs/acquire-authentication-credentials-in-smb). The version uses a floating point number. See an example below. `2.0` for SMB version 2 or `2.1.1` > [!NOTE] > **Note** Starting with Securiti release 1.150, Securiti no longer lets you activate new SMB connectors using SMBv1. Securiti recommends using SMBv2 or SMBv3 for new connectors. > > Existing SMBv1 connector activations continue to work without interruption and don't require reconfiguration, though you can migrate them to SMBv2 or SMBv3 at any time. For more information, see [Upgrading version for SMB connector](/latest/docs/migrating-from-smbv1-to-smbv2-3). |
| Domain | (Optional) Enter the domain name. See [Acquire authentication credentials in SMB](/latest/docs/acquire-authentication-credentials-in-smb) for more information. |
| Domain Controller | Enter the Hostname or IP of the domain controller to use for SID resolution when the file server cannot resolve domain accounts. > [!NOTE] > Note > > To use the Domain Controller configuration, upgrade to Securiti pod version 1.148.0 or higher. |
| Use SMB Server Replica for Scanning | Enable the toggle to add credentials for read-only Replica server in addition to primary server. You can use Replica server, such as a disaster recovery (DR) replica or a secondary site replica. > [!NOTE] > Note > > - Both Replica server and Primary server must have the same Share Name to access the SMBV resources successfully. > - To use this feature, you must upgrade your pod version to release 1.145 or higher. > - Data Inventory Sync support is not available for Replica Server. |
| Read Replica Host | If you have enabled **Read Replica Supported?** toggle, enter the server IP address of your replica server as a Host in *xxx.xxx.xxx.xxx* format. See the example below. *192.158.1.38* |
| Read Replica Kerberos Configuration File | If you have enabled **Read Replica Supported?** toggle, upload the Kerberos Configuration File received from the Replica Kerberos server administrator. |
| Read Replica Kerberos User Principal | If you have enabled **Read Replica Supported?** toggle, enter the kerberos principal for HTTP communication of the Relica server. See the example below. *HTTP or Instance@domain.com* |
| Read Replica Kerberos Keytab | If you have enabled **Read Replica Supported?** toggle, upload the keytab file that contains a pair of kerberos principal and encrypted keys from the replica server. |
| Read Replica Domain | If you have enabled **Read Replica Supported?** toggle, Enter the domain name of Replica server as described in [Acquire authentication credentials in SMB](/latest/docs/acquire-authentication-credentials-in-smb). |
| Mounting Timeout | Specify the time interval for scanning operations. The interval reduces the default 24-hour mounting timeout in case of scan job failures. The maximum scan timeout is 24 hours. The mounting timeout is expressed in seconds. See an example below. *30* |
| SMB Provider | In the **SMB Provider**, select from the following providers: - None - Dell Isilon - NetApp ONTAP > [!NOTE] > Note > > To fetch entitlements via the default LDAP method, select None from the available options above. |
| (Optional) Isilon API Port (For Dell Isilon Provider only) | Enter the Dell Isilion API Port number. It follows the following format: `8080` |
| ONTAP Management Hostname (For NetApp ONTAP Provider only) | The hostname or DNS name of the NetApp ONTAP management interface used to connect to the ONTAP REST API for collecting file system and permission metadata. See the example below: `ontap-mgmt.corp.local` > [!NOTE] > Note > > Enter the Hostname instead of the IP address. see the method below to get the hostname > > 1. For AWS FSx for NetApp ONTAP: Go to AWS Console → FSx → Your file system → Management endpoints → copy the Management DNS name > 2. For on-prem NetApp: Ask your NetApp admin for the cluster or SVM management hostname |
| ONTAP Management Username (For NetApp ONTAP Provider only) | The username used to authenticate with the NetApp ONTAP management API and access file system configuration and security information. See the example below: `fsxadmin`. |
| ONTAP Management Password (For NetApp ONTAP Provider only) | The password associated with the ONTAP management user account used for API authentication. See the example below: `MyOntapP@ssword123` |
| LDAP Server (For NetApp ONTAP Provider only) | The hostname or IP address of the Active Directory or LDAP server used to retrieve users, groups, and computer objects for entitlement discovery. See the example below: `dc01.corp.example.com` |
| LDAP Username (For NetApp ONTAP Provider only) | The service account username used to authenticate to Active Directory or LDAP and perform directory queries. See the example below: `admin@corp.example.com` |
| LDAP Password (For NetApp ONTAP Provider only) | The password for the LDAP service account used to authenticate to Active Directory. See the example below: `MYLDAP@ssword123` |
| (Optional) LDAP Base DN (For NetApp ONTAP Provider only) | The Distinguished Name (DN) that defines the starting location in the directory tree for LDAP searches. See the example below: `DC=corp,DC=example,DC=com` |
| Evaluate Data system size | Mark the checkbox to evaluate the Data system size during Authentication. The option computes the total size of all the files present under the given share name. Securiti calculates resource size on a weekly basis to keep the data size value up to date. |

1. Once you are done, click **Test Connection**.

Securiti activates the connector.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the SMB (self-hosted):

- [Configuring Data Inventory Sync for SMB](/latest/docs/configure-data-inventory-sync-for-smb).
- [Configure discovery scans in SMB](/latest/docs/configuring-discovery-scans-in-smb).
- [Fulfilling DSR requests for SMB](/latest/docs/fulfilling-dsr-requests-for-smb).

**Additional resources**

- [Troubleshooting for SMB connector](/latest/docs/troubleshooting-for-smb-connector).
