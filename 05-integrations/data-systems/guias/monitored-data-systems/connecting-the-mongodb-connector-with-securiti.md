---
title: "Connecting the MongoDB connector with Securiti"
slug: "connecting-the-mongodb-connector-with-securiti"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/connecting-the-mongodb-connector-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting the MongoDB connector with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

    

## Creating a data system instance

        
        
            

Perform the following steps to create a Data system instance for self**-**hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Self-Hosted** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | Select your preferred **Hosting Location** and configure the Service provider settings where applicable. Securiti supports **SaaS**, or **Private Cloud**, as Hosting options for specific Data system Instances. | SaaS, Private Cloud |
| Country | Select the **country** from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the **city** where the data source or resource is located. | Calgary |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

        
    

## Authenticating the data system instance

After creating a MongoDB connector instance, in the **Authentication** tab, authenticate your connector:

1. In the **Select Pod**, choose the pod you configured earlier.
2. > [!WARNING]
> Important
> 
> - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as:

  - Table Training Sample files
  - Sensitive Data Intelligence protection evidence files
  - Scan Summary

> [!NOTE]
> Note
> 
> DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support.

You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another:

  1. On the activated data system instance, click on the **Reconfigure** link.
  2. From the **PCS Destination** menu, select the PCS where you want to migrate the data.
  3. Click **Reconfigure connector**.

Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete.
3. Under the **Credentials** section, in the **Authentication** tab, apply the following settings that you recorded earlier.

> [!NOTE]
> **Note**
> 
> 
>     
> 
> We assume you have MongoDB version 2.6 or higher running for Connector authentication.

Use the following topics to add activation credentials:

- [Create a MongoDB connection without srv](/latest/docs/obtain-credentials-for-mongodb-without-srv-connection)
- [Create a MongoDB+srv connection](/latest/docs/granting-db-permissions)
- [Configuring mTLS authentication](/latest/docs/configuring-mtls-authentication)
- [Obtain credentials for various MongoDB connection methods](/latest/docs/prerequisites-for-mongodb-connector)

    
        Password Authentication
        X.509 Certificate Authentication
        Kerberos Authentication
    
    
        
            
                

| Setting | Description |
| --- | --- |
| Connection String Scheme | Choose the MongoDB **Connection String Scheme** from the menu: - **mongodb**: Choose this option for the standard connection format for direct connections to MongoDB deployments, including standalone servers, replica sets, and shared clusters. - **mongodb+srv:** Choose this option for the DNS Seed List connection format that supports automatic discovery of cluster members using DNS SRV records. See the example below. `mongodb+srv://localhost/` |
| Host | Enter the MongoDB host that follows the **mongodb.net** format. See the examples below: - For MongoDB connection (Primary Host): `ac-k3tabab-shard-00-01.4ababab.mongodb.net` - For MongoDB+srv connection: `cluster0.mongodb.net` |
| Port | Enter the port number on which MongoDB is running. The default port number for MongoDB is 27017. See the example below. `27017` |
| Authentication | Select the **Password (Basic)** authentication type from the menu |
| (Optional) Use Keyring | Enable the toggle to use Keyring to manage Credentials for your Instance. See topics below for more information on supported Keyring types. - [Using keyrings](/latest/docs/creating-keyrings) - [Azure key vault](/latest/docs/configuring-credential-vaults-azure-key-vault) - [CredStash](/latest/docs/configuring-credential-vaults-credstash-credential-vault) - [CyberArk](/latest/docs/cyberark-credential-vault) - [HashiCorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) Select your Keyring type and the respective vault Instance from the menu. |
| User | If you are not using Keyring, specify your DB username with the required Permissions that you recorded n earlier. See an example below. `john_securiti` |
| Password | If you are not using Keyring, enter your DB user's password. |
| Database Name | Enter the name of the Database you want to connect with. The Database name uses a string value. See the example below. `automation db` > [!NOTE] > **Note** > > > > > The Database name is case-sensitive. Enter it exactly as it appears in the Data system. |
| Auth Database Name | Enter the Database name used for Authentication that you recorded earlier. See examples below. **For Password authentication:** Use *admin* **For LDAP Authentication**: Use *$external* as a value. |
| Row scan depth | Specify the number of rows (documents) to scan within a collection in MongoDB. The Row scan depth value is a number, and by default, you can use 1. See the example below. *1* |
| Use SSL (optional) | Enable the toggle if your MongoDB server supports SSL/TLS encryption. |
| Additional Connection String Options (optional) | > [!WARNING] > Important > > > > > > If you encounter the following error, read the [troubleshooting for MongoDB](/v1/docs/troubleshooting-for-mongodb) to resolve the issue. > > > > > ```plaintext > Failed to get tables from database : > error : For MDBP-FERPROMO-2.DC.NOVA > Failed to get accessible databases. > Failed to fetch any databases from the connection. > ``` Configure to suit as described below. **AuthScheme**: Use the AuthScheme parameter to specify the authentication mechanism for connecting to MongoDB: - `MONGODB-CR`: Use this value for MongoDB 2. - `SCRAM-SHA-1`: Use this value for MongoDB 3.x or 4.x. MongoDB 4 uses this value by default. - `SCRAM-SHA-256`: MongoDB 5.x or 6.x uses this value by default. - `GSSAPI` - `PLAIN`: Use this value when using LDAP Authentication - `NONE` **ReadPreference**: Use the ReadPreference parameter to define the strategy for reading data from a MongoDB replica set. Supported values include: - `primary` - `primaryPreferred` - `secondary` - `secondaryPreferred` - `nearest` Parameter formatting examples: - **Multiple parameters** Separate multiple parameters using a semicolon (;). ```plaintext “AuthScheme=SCRAM-SHA-25;readPreference=primary" ``` - **Replica set parameters** When specifying replica set values, separate the host and port using a colon (:), as shown below. Format: `ReplicaSet=&lt;Host&gt;:&lt;Port&gt;;SlaveOK=true;ReadPreference=PrimaryPreferred` Example: ```plaintext ReplicaSet=ab-k3aaabb-shard-00-01.4ababab.mongodb.net:27017;SlaveOK=true;ReadPreference=Primary Preferred ``` |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
| Timeout | Enter a custom timeout if you want the Activation session greater than Securiti default. The timeout value is in milliseconds or seconds. See an example below. *0* |

            
        
        
            
                

| Setting | Description |
| --- | --- |
| Connection String Scheme | Choose the MongoDB **Connection String Scheme** from the menu: - **mongodb**: Choose this option for the standard connection format for direct connections to MongoDB deployments, including standalone servers, replica sets, and shared clusters. - **mongodb+srv:** > [!NOTE] > Note > > > > > > mongodb+srv support is not available forKerberos authentication |
| Host | Enter the host that you recorded ea[r](/v1/docs/prerequisites-for-mongodb-connector)lier. The MongoDB host ends in **mongodb.net**. See an example below. `cluster0.mongodb.net` |
| Port | Enter the port number on which MongoDB is running that you recorded earlier. The default port for MongoDB is `27017`. |
| Authentication | Select the **Kerberos Authentication** type from the menu. This opens another option to choose between Kerberos Password and Keytab strategies. - > [!NOTE] > **Note** > > > > > For Kerberos Keytab Authentication, a Kerberos server must be installed and properly configured, and your MongoDB Instance must be integrated with Kerberos for Authentication. |
| Authentication Strategy | Select the Kerberos Authentication Strategy from the menu: - Use Password - Keytab |
| (Optional) Use Keyring | Enable the toggle to use Keyring to manage Credentials for your Instance. For more information on supported Keyring types, see the topics below. - [Using keyrings](/latest/docs/managing-credentials-using-keyrings) - [CyberArk](/latest/docs/cyberark-credential-vault) (For both Kerberos (Password) and Kerberos (Keytab) - [HashiCorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) (For Kerberos (Password) only) Select your Keyring type and the respective vault Instance from the menu. > [!WARNING] > **Important** > > > > > The Kerberos (Keytab) `creds_file` should be Base64-encoded. |
| User (For Use password strategy) | If you are not using Keyring, specify your DB username with the required Permissions that you recorded earlier. See an example below. `john_securiti` |
| Password (For Use password strategy) | If you are not using Keyring, enter your DB user's password. |
| Service Principal | Specify the Service Principal registered against your for mongodb service. See the example below. `mongodb/user@KERBEROSREALM` |
| User Principal (For Keytab strategy) | Specify the Kerberos principal you created in MongoDB $external Database. See the example below. `user@KERBEROSREALM` |
| Kerberos KDC | Specify the public IP address for your KDC server. See the example below. `34.133.185.7` |
| Kerberos Realm | Specify the realm name corresponding to the MongoDB service. `KERBEROSREALM` |
| Keytab (For Keytab strategy only) | Upload the keytab file containing the principal. The keytab file uses .keytab file extension. |
| Database Name | Enter the name of the Database, you want to connect with. The Database name uses a string value. See the example below. *automation db* > [!NOTE] > **Note** > > > > > The Database name is case-sensitive. Enter it exactly as it appears in the Data system. |
| Auth Database Name | Enter the Database name used for Authentication that you recorded earlier. See an example below. *admin* **For LDAP Authentication**: Use *$external* as a value. |
| Row scan depth | Specify the number of rows (documents) to scan within a collection in MongoDB. The Row scan depth value is a number, and by default, you can use 1. See the example below. `1` |
| Use SSL (optional) | Enable the toggle if your MongoDB server supports SSL/TLS encryption. |
| Additional Connection String Options (optional) | > [!WARNING] > Important > > > > > > If you encounter the following error, read the [troubleshooting for MongoDB](/v1/docs/troubleshooting-for-mongodb) to resolve the issue. > > > > > ```plaintext > Failed to get tables from database : > error : For MDBP-FERPROMO-2.DC.NOVA > Failed to get accessible databases. > Failed to fetch any databases from the connection. > ``` Configure to suit as described below. **AuthScheme**: For AuthScheme parameter, you can enter one of these values: `MONGODB-CR`: Use this value for MongoDB 2. `SCRAM-SHA-1`: Use this value for MongoDB 3.x or 4.x. MongoDB 4 uses this value by default. `SCRAM-SHA-256`: MongoDB 5.x or 6.x uses this value by default. `GSSAPI` `PLAIN`: Use this value when using LDAP Authentication `NONE` **ReadPreference**: Set this parameter to a strategy for reading from a replica set. You can enter one of these values: `primary` `primaryPreferred` `secondary` `secondaryPreferred` `nearest` For multiple parameters, separate values using a semicolon (;), as shown in the example below: “AuthScheme=SCRAM-SHA-25;readPreference=primary" |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
| Timeout | Enter a custom timeout if you want the Activation session greater than Securiti default. The timeout value is in milliseconds or seconds. See an example below. `0` |

            
        
        
            
                

| Setting | Description |
| --- | --- |
| Connection String Scheme | Choose the MongoDB **Connection String Scheme** from the menu: - **mongodb**: Choose this option for the standard connection format for direct connections to MongoDB deployments, including standalone servers, replica sets, and shared clusters. - **mongodb+srv:** Choose this option for the DNS Seed List connection format that supports automatic discovery of cluster members using DNS SRV records. See the example below. `mongodb+srv://localhost/` |
| Host | Enter the MongoDB host that follows the **mongodb.net** format. See the examples below: - For MongoDB connection (Primary Host): `ac-k3tabab-shard-00-01.4ababab.mongodb.net` - For MongoDB+srv connection: `cluster0.mongodb.net` |
| Port | Enter the port number on which MongoDB is running that you recorded earlier. The default port number for MongoDB is 27017. See the example below. `27017` |
| Authentication | Select the **X.509 Certificate Authentication** (mTLS) authentication type from the menu. |
| Database Name | Enter the name of the Database you want to connect with. The Database name uses a string value. See the example below. `automation db` > [!NOTE] > **Note** > > > > > The Database name is case-sensitive. Enter it exactly as it appears in the Data system. |
| Auth Database Name | Enter the Database name used for Authentication that you recorded earlier. See an example below. **For LDAP and X.509 Certificate Authentication**: Use *$external* as a value. |
| Row scan depth | Specify the number of rows (documents) to scan within a collection in MongoDB. The Row scan depth value is a number, and by default, you can use 1. See the example below. `1` |
| Keystore File | Upload the Keystore file containing the client certificate and private key. Securiti dynamically validates the keystore file based on its extension type, as described below: - Files with *.p12* or *.pfx* extensions are recognized as *PKCS12* keystores. - Files with a *.jks* extension are recognized as *JKS* keystores. > [!WARNING] > Important > > > > > > - If the Keystore is signed by a custom CA, you must upload the root certificate of that custom CA to the Trust Store; otherwise, authentication fails. > - To use this feature, you must upgrade your pods with the release version 1.138 or higher. For more information, see [MongoDB documentation](https://www.mongodb.com/docs/manual/tutorial/configure-x509-client-authentication/). |
| (Optional) Use Keyring | Enable the toggle to use Keyring to manage Credentials for your Instance. For more information on supported Keyring types, see the topics below. - [Using keyrings](/latest/docs/managing-credentials-using-keyrings) - [CyberArk](/latest/docs/cyberark-credential-vault) Select your Keyring type and the respective vault Instance from the menu. |
| Keystore password | Enter the Keystore password that matches the Keystore file you uploaded. For more information, see [MongoDB documentation](https://www.mongodb.com/docs/manual/tutorial/configure-x509-client-authentication/). > [!WARNING] > **Important** > > > > > The X.509 Keystore `keystore_file` should be Base64-encoded. |
| Additional Connection String Options (optional) | > [!WARNING] > Important > > > > > > If you encounter the following error, read the [troubleshooting for MongoDB](/latest/docs/troubleshooting-for-mongodb) to resolve the issue. > > > > > ```plaintext > Failed to get tables from database : > error : For MDBP-FERPROMO-2.DC.NOVA > Failed to get accessible databases. > Failed to fetch any databases from the connection. > ``` Configure to suit as described below. **AuthScheme**: For AuthScheme parameter, you can enter one of these values: `MONGODB-CR`: Use this value for MongoDB 2. `SCRAM-SHA-1`: Use this value for MongoDB 3.x or 4.x. MongoDB 4 uses this value by default. `SCRAM-SHA-256`: MongoDB 5.x or 6.x uses this value by default. `GSSAPI` `PLAIN`: Use this value when using LDAP Authentication `NONE` **ReadPreference**: Set this parameter to a strategy for reading from a replica set. You can enter one of these values: `primary` `primaryPreferred` `secondary` `secondaryPreferred` `nearest` For multiple parameters, separate values using a semicolon (;), as shown in the example below: “AuthScheme=SCRAM-SHA-25;readPreference=primary" |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
| Timeout | Enter a custom timeout if you want the Activation session greater than Securiti default. The timeout value is in milliseconds or seconds. See an example below. *0* |

            
        
    

- Click **Test Connection**.

        

Securiti activates the connector.

### Monitoring the overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Verify the statuses for supported capabilities.

    

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

    

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scan settings

Proceed to the following topics to configure the post-authentication scans settings for the MongoDB (Self-hosted):

- [Configure discovery scans in MongoDB](/latest/docs/configure-discovery-scans-in-mongodb).

**Additional resources**

- [Fulfilling DSR requests for MongoDB](/latest/docs/fulfilling-dsr-requests-for-azure-cosmos-for-mongodb).
- [Troubleshooting for MongoDB](/latest/docs/troubleshooting-for-mongodb).
