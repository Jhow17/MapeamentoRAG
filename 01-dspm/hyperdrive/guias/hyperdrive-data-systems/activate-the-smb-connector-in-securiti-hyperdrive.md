---
title: "Connecting the SMB with Securiti (Hyperdrive)"
slug: "activate-the-smb-connector-in-securiti-hyperdrive"
updated: 2026-08-31T11:10:46Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/activate-the-smb-connector-in-securiti-hyperdrive"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Connecting the SMB with Securiti (Hyperdrive)

This topic covers authenticating and connecting SMB data system connector using Hyperdrive mode.

Before proceeding with the SMB connector activation, apply these permissions:

> [!NOTE]
> **Note**
> 
> We assume you are the admin of your SMB Instance or have access to the user with admin privileges.
> 
> To include the `created_date` in your files, see the [Troubleshooting for SMB connector](/v1/docs/securiti-pods-and-elastic-pods).

- **Read**: Read permission is required for all shares provided in the SMB Configuration. Ensure the user account used for Authentication has read access to the specified SMB shares.
- **Write** (For Quarantine Policy): To apply the quarantine policy, write permission is also required on both the source and destination paths. This ensures that Securiti can securely quarantine documents containing high-level personally identifiable information (PII) in the specified location.

****Create a data system instance****

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
| Instance Location | Select one of your preferred Hosting locations from the menu. | - IaaS - SaaS - Private Cloud Storage > [!NOTE] > Note > > IaaS location opens a new menu to select Service Providers. For more information on IaaS locations, see [this section](/v1/docs/activate-the-smb-connector-in-securiti#hosting-location-for-data-system-instance). |
| Country | Select the country of hosting location from the menu. | Country: United States |
| State/Region | Select the State or region inside the hosting country. | State: California |
| City | Enter the city name where the hosting server is located. | City: San Jose |
| Owners | Choose additional co-owners for the Instance if you want. By default, you are the Instance owner. | John.doe@securiti.ai |
8. Click **Create Instance & Continue**.

## Authenticating the connector

Before proceeding with the SMB connector authentication, apply these Permissions:

> [!NOTE]
> **Note**
> 
> We assume you are the admin of your SMB Instance or have access to the user with admin privileges.
> 
> To include the `created_date` in your files, see the [Troubleshooting for SMB connector](/v1/docs/securiti-pods-and-elastic-pods).

- **Read**: Read permission is required for all shares provided in the SMB Configuration. Ensure the user account used for Authentication has read access to the specified SMB shares.
- **Write** (For Quarantine Policy): To apply the quarantine policy, write permission is also required on both the source and destination paths. This ensures that Securiti can securely quarantine documents containing high-level personally identifiable information (PII) in the specified location.

After creating a Microsoft 365 OneDrive connector instance, in the **Authentication** tab, authenticate your connector:

1. On the **Authentication** page, select the **Outpost** you configured earlier in [Securiti outpost deployment](/latest/docs/securiti-outpost-deployment).
2. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data. For more information, see [Configuring PCS Destination](https://helpcenter.securiti.ai/latest/docs/system-settings-configuring-private-cloud-storage).

> [!NOTE]
> Note
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
3. In the **Credentials** section, choose the **Authentication Type** from the menu.
  - NTLM (User/ Password)
  - Kerberos - Keytab
  - Kerberos - Password
4. After choosing the authentication type choose the configure the following settings based on the authentication method you choose:

**NTLM (User/Password)**

Use the following table to add credentials for NTLM (User/Password) authentication type:

| Setting | Description |
| --- | --- |
| Host | Enter your server IP address in *xxx.xxx.xxx.xxx* format. See the example below. **192.158.1.38** |
| Share name | Enter SMB share name beginning with a **forward slash (/)**. See the example below. */smb-share* > [!WARNING] > **Important** > > Securiti discovers all available network shares in the SMB server if you provide root path “/” here. These shares are listed when defining the scope of the Discovery scan. > [!NOTE] > **Note** > > This share name is different from the one you use in quarantine operations for your files. For more information, see the [quarantine path option below](/v1/docs/activate-the-smb-connector-in-securiti). |
| User | Enter your SMB server username. The username uses a string value. See example below. *John Doe* |
| Password | Enter your SMB server password. See the example below. *testpassword@123* |
| Version | Specify the SMB version you acquired in [Acquire authentication credentials in SMB (Hyperdrive)](/latest/docs/acquire-authentication-credentials-in-smb-hyperdrive). The version uses a floating point number. See an example below. `1.0` for SMB version 1 or `3.1.1` > [!NOTE] > **Note** > > Starting with Securiti release 1.150, Securiti no longer lets you activate new SMB connectors using SMBv1. Securiti recommends using SMBv2 or SMBv3 for new connectors. > > Existing SMBv1 connector activations continue to work without interruption and don't require reconfiguration. You can still reconfigure an existing connector using SMBv1, and you can migrate it to SMBv2 or SMBv3 at any time. > > For more information, see [Upgrading version for SMB connector](/latest/docs/migrating-from-smbv1-to-smbv2-3). |
| (Optional) Domain | Enter the domain name. For more information, see [Acquire authentication credentials in SMB (Hyperdrive)](/latest/docs/acquire-authentication-credentials-in-smb-hyperdrive). |
| (Optional) Domain Controller | Enter the Hostname or IP of the domain controller to use for SID resolution when the file server cannot resolve domain accounts. > [!NOTE] > Note > > To use the Domain Controller configuration, upgrade to Outpost version 1.148.0 or higher. |
| Is Read Replica Supported? | Enable the toggle to add credentials for read-only Replica server in addition to primary server. You can use Replica server, such as a disaster recovery (DR) replica or a secondary site replica. You can also choose to read data from the replica server in discovery scans during business hours due to the load of scanning in primary server. File metadata in continues to represent the primary server. Policy actions such as quarantine and labeling still execute against the primary server. > [!NOTE] > Note > > - Both Replica server and Primary server must have the same Share Name to access the SMB resources successfully. > - Data Inventory Sync support is not available for Replica Server. |
| Read Replica Host | If you have enabled **Read Replica Supported?** toggle, enter the server IP address of your replica server as a Host in *xxx.xxx.xxx.xxx* format. See the example below. *192.158.1.38* |
| Read Replica Domain | If you have enabled **Read Replica Supported?** toggle, Enter the domain name of Replica server as described in [Acquire authentication credentials in SMB (Hyperdrive)](/latest/docs/acquire-authentication-credentials-in-smb-hyperdrive). |
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
| (Optional) Allow Quarantine actions on this Data system | Enable the toggle for documents containing high-level personally identifiable information (PII). The provided quarantine path will undergo validation to ensure its existence and write access, guaranteeing a secure location for the quarantined documents. This toggle is a prerequisite to creating a File Insight Policy in Sensitive data Intelligence. For more information, see [Using File Quarantine policies with Hyperdrive mode](/latest/docs/using-quarantine-policies-with-hyperdrive-mode). > [!NOTE] > Note > > You must grant read and write privileges to the scanning account for files to be quarantined and the relevant folder where you want to place quarantined files. |
| (Optional) Use separate Credentials for Quarantine | To use separate Credentials for quarantine policy, select **Yes** from the menu. |
| Privileged User *(separate Credentials for quarantine only)* | Enter username for quarantine Credentials. The privileged username uses a string value. See example below. *John-smb* |
| Privileged Password *(separate Credentials for quarantine only)* | Enter your password for quarantine Credentials. |
| (Optional) Quarantine Path *(for quarantine policy)* | > [!WARNING] > **Caution** > > The quarantine path and share name must be different for successful Connector Activation. Specify the path or share name where you want to move the quarantined files. The quarantine path must be a string that begins with a forward slash '/'. Depending on how you want to organize quarantined files, you can provide either a share name or a more specific file path within that share. Regardless of whether you specify a share name or a specific path, the original file path structure will be preserved in the quarantine location. This helps maintain context and traceability for quarantined files. See examples below. - To quarantine files in the root of a share (general quarantine location): - */quarantine* - To quarantine files in a specific sub-directory within a share: - */quarantine/Test2/Admin* |
| Evaluate Data system size | Mark the checkbox to evaluate the Data system size during Authentication. The option computes the total size of all the files present under the given share name. Securiti calculates resource size on a weekly basis to keep the data size value up to date. |

**Kerberos Keytab**

Use the following table to add credentials using Kerberos Kyey tab authentication type:

| Setting | Description |
| --- | --- |
| Host | Enter your server IP address in *xxx.xxx.xxx.xxx* format. See the example below. **192.158.1.38** |
| Share name | Enter SMB share name beginning with a **forward slash (/)**. See the example below. */smb-share* > [!WARNING] > **Important** > > Securiti discovers all available network shares in the SMB server if you provide root path "/" here. These shares are listed when defining the scope of the Discovery scan. > [!NOTE] > **Note** > > This share name is different from the one you use in quarantine operations for your files. For more information, see the [quarantine path option below](/v1/docs/activate-the-smb-connector-in-securiti). |
| Kerberos Configuration File | If you are not using Keyring, upload the Kerberos Configuration File received from the Kerberos server administrator. |
| Kerberos User Principal | Enter the kerberos principal for HTTP communication. See the example below. *HTTP or Instance@domain.com* |
| Kerberos Keytab | If you are not using Keyring, upload the keytab file that contains a pair of kerberos principal and encrypted keys. |
| Kerberos Password | If you are not using Keyring, enter your Kerberos server password. |
| Version | Specify the SMB version you acquired in [Acquire authentication credentials in SMB (Hyperdrive)](/latest/docs/acquire-authentication-credentials-in-smb-hyperdrive). The version uses a floating point number. See an example below. `1.0` for SMB version 1 or `3.1.1` > [!NOTE] > **Note** > > Starting with Securiti release 1.150, Securiti no longer lets you activate new SMB connectors using SMBv1. Securiti recommends using SMBv2 or SMBv3 for new connectors. > > Existing SMBv1 connector activations continue to work without interruption and don't require reconfiguration. You can still reconfigure an existing connector using SMBv1, and you can migrate it to SMBv2 or SMBv3 at any time. > > For more information, see [Upgrading version for SMB connector](/latest/docs/migrating-from-smbv1-to-smbv2-3). |
| (Optional) Domain | Enter the domain name. See [Acquire authentication credentials in SMB](/v1/docs/acquire-authentication-credentials-in-smb) for more information. |
| (Optional) Domain Controller | Enter the Hostname or IP of the domain controller to use for SID resolution when the file server cannot resolve domain accounts. > [!NOTE] > Note > > To use the Domain Controller configuration, upgrade to Outpost version 1.148.0 or higher. |
| Is Read Replica Supported? | Enable the toggle to add credentials for read-only Replica server in addition to primary server. You can use Replica server, such as a disaster recovery (DR) replica or a secondary site replica. You can also choose to read data from the replica server in discovery scans during business hours due to the load of scanning in primary server. File metadata in continues to represent the primary server. Policy actions such as quarantine and labeling still execute against the primary server. > [!NOTE] > Note > > - Both Replica server and Primary server must have the same Share Name to access the SMBV resources successfully. > - To use this feature, you must upgrade your Outpost version to release 1.145 or higher. > - Data Inventory Sync support is not available for Replica Server. |
| Read Replica Host | If you have enabled **Read Replica Supported?** toggle, enter the server IP address of your replica server as a Host in *xxx.xxx.xxx.xxx* format. See the example below. *192.158.1.38* |
| Read Replica Kerberos Configuration File | If you have enabled **Read Replica Supported?** toggle, upload the Kerberos Configuration File received from the Replica Kerberos server administrator. |
| Read Replica Kerberos User Principal | If you have enabled **Read Replica Supported?** toggle, enter the kerberos principal for HTTP communication of the Relica server. See the example below. *HTTP or Instance@domain.com* |
| Read Replica Kerberos Keytab | If you have enabled **Read Replica Supported?** toggle, upload the keytab file that contains a pair of kerberos principal and encrypted keys from the replica server. |
| Read Replica Domain | If you have enabled **Read Replica Supported?** toggle, Enter the domain name of Replica server as described in [Acquire authentication credentials in SMB](/v1/docs/acquire-authentication-credentials-in-smb). |
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
| Share name | Enter SMB share name beginning with a **forward slash (/)**. See the example below. */smb-share* > [!WARNING] > **Important** > > Securiti discovers all available network shares in the SMB server if you provide root path "/" here. These shares are listed when defining the scope of the Discovery scan. > [!NOTE] > **Note** > > This share name is different from the one you use in quarantine operations for your files. For more information, see the [quarantine path option below](/v1/docs/activate-the-smb-connector-in-securiti). |
| Kerberos Configuration File | If you are not using Keyring, upload the Kerberos Configuration File received from the Kerberos server administrator. |
| Kerberos User Principal | Enter the kerberos principal for HTTP communication. See the example below. *HTTP or Instance@domain.com* |
| Kerberos Keytab | If you are not using Keyring, upload the keytab file that contains a pair of kerberos principal and encrypted keys. |
| Kerberos Password | If you are not using Keyring, enter your Kerberos server password. |
| Version | Specify the SMB version you acquired in [Acquire authentication credentials in SMB](/v1/docs/acquire-authentication-credentials-in-smb). The version uses a floating point number. See an example below. `1.0` for SMB version 1 or `3.1.1` > [!NOTE] > **Note** > > Starting with Securiti release 1.150, Securiti no longer lets you activate new SMB connectors using SMBv1. Securiti recommends using SMBv2 or SMBv3 for new connectors. > > Existing SMBv1 connector activations continue to work without interruption and don't require reconfiguration. You can still reconfigure an existing connector using SMBv1, and you can migrate it to SMBv2 or SMBv3 at any time. > > For more information, see [Upgrading version for SMB connector](/latest/docs/migrating-from-smbv1-to-smbv2-3). |
| (Optional) Domain | Enter the domain name. See [Acquire authentication credentials in SMB](/v1/docs/acquire-authentication-credentials-in-smb) for more information. |
| (Optional) Domain Controller | Enter the Hostname or IP of the domain controller to use for SID resolution when the file server cannot resolve domain accounts. > [!NOTE] > Note > > To use the Domain Controller configuration, upgrade to Outpost version 1.148.0 or higher. |
| Is Read Replica Supported? | Enable the toggle to add credentials for read-only Replica server in addition to primary server. You can use Replica server, such as a disaster recovery (DR) replica or a secondary site replica. > [!NOTE] > Note > > - Both Replica server and Primary server must have the same Share Name to access the SMBV resources successfully. > - To use this feature, you must upgrade your Outpost version to release 1.145 or higher. > - Data Inventory Sync support is not available for Replica Server. |
| Read Replica Host | If you have enabled **Read Replica Supported?** toggle, enter the server IP address of your replica server as a Host in *xxx.xxx.xxx.xxx* format. See the example below. *192.158.1.38* |
| Read Replica Kerberos Configuration File | If you have enabled **Read Replica Supported?** toggle, upload the Kerberos Configuration File received from the Replica Kerberos server administrator. |
| Read Replica Kerberos User Principal | If you have enabled **Read Replica Supported?** toggle, enter the kerberos principal for HTTP communication of the Relica server. See the example below. *HTTP or Instance@domain.com* |
| Read Replica Kerberos Keytab | If you have enabled **Read Replica Supported?** toggle, upload the keytab file that contains a pair of kerberos principal and encrypted keys from the replica server. |
| Read Replica Domain | If you have enabled **Read Replica Supported?** toggle, Enter the domain name of Replica server as described in [Acquire authentication credentials in SMB](/v1/docs/acquire-authentication-credentials-in-smb). |
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

1. Click **Authenticate & Activate Connector**.

Securiti activates the connector.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-authentication-statuses-hyperdrive).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Amazon S3 (self-hosted):

- [Configure Data Inventory Sync for SMB (Hyperdrive)](/latest/docs/configure-data-inventory-sync-for-smb-hyperdrive)
- [Configuring discovery scans in SMB (Hyperdrive)](/latest/docs/configuring-discovery-scans-in-smb-hyperdrive)
- ####
