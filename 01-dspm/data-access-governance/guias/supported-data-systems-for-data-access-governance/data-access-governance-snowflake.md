---
title: "Snowflake"
slug: "data-access-governance-snowflake"
updated: 2026-09-23T05:33:01Z
published: 2026-09-23T05:33:01Z
canonical: "helpcenter.securiti.ai/data-access-governance-snowflake"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Snowflake

This section describes the Data Access Governance features supported for Snowflake and the steps to configure these functionalities.

#### Supported Data Access Governance Feature Sets

Following is the list of the features supported for Snowflake:

### Access Intelligence

- Privilege Analysis - Privilege Analysis is supported for Securiti Cloud and Self-Hosted Securiti Connectors.
  - Database, Schema, and Table permissions granularity
  - Supported Authentication Type : Oauth2 and Key Pair Auth
- Activity Analysis - Not Supported
- Supported Credential Vault for Sharepoint Access Scan : HashiCorp

#### Access Control

- Column Masking Properties
- Row Filtering Properties
- Permissions Management Properties

#### Cross Border Transfer Policies

- Alerts and recommendations based on the Data Location

> [!NOTE]
> Note
> 
> If Data Access Governance features for Snowflake are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

#### Example Supported Use Cases

The supported example use cases include:

### Access Intelligence

- Identify and report on which Snowflake users have access to Databases and what their permissions are on those databases are
- Identify and report on which Snowflake users have access to Tables and what their permissions are on those tables
- Identify and report on which Snowflake Users can access Tables containing sensitive data
- Identify and report on users who have Account Admin or System Admin privileges on your Snowflake Account
- Identify and report on which Roles assignments grant User access to sensitive data

#### Configuring Snowflake Data Access Governance

To see the Snowflake access intelligence data there are some prerequisite steps.

### Configuring Access Intelligence Privilege Analysis using IAM Metadata Sources

#### Prerequisites

To configure access intelligence for Snowflake you must

**1. Create a custom role in your Snowflake account and assign permissions**

To scan the Snowflake account for Access Intelligence , Securiti requires certain permissions and privileges to access the account and obtain metadata from there. Mainly, the metadata is obtained from the SNOWFLAKE.ACCOUNT_USAGE schema. This document describes the steps by which the privileges can be granted, by using a custom role. This role is named as SECURITI_IAM_MONITOR in the rest of the document, although in your account you may create a differently named role. This role is then assigned to the user that is configured in the Snowflake Connector on Securiti, to make the connection and to perform the Access Intelligence scan. We will use 'securitiuser' as the user-id in the rest of the document. Further we will assume, for illustration, that the user has a default role of 'SECURITI_CONNECTOR'. Note that in your account the user in question and the default role granted to that user may be differently named — we are using securitiuser and SECURITI_CONNECTOR for illustration.

1. Create a custom role in your Snowflake account. As an example, we have used **SECURITI_IAM_MONITOR** as the name in the rest of the topic. See [Snowflake documentation](https://docs.snowflake.com/en/sql-reference/sql/create-role#access-control-requirements) for requirements to create a custom role.
2. Assign the role **securitiuser**.

```plaintext
GRANT ROLE SECURITI_IAM_MONITOR TO USER securitiuser;
```
3. Set the role as the default for the user.

```plaintext
ALTER USER securitiuser SET DEFAULT_ROLE = 'SECURITI_IAM_MONITOR';
```

Alternatively, assign the role to the **DEFAULT_ROLE** of the user, e.g., assuming securitiuser has *SECURITI_CONNECTOR* as the DEFAULT_ROLE in your account, then' then:
  - If the DEFAULT_ROLE for **securitiuser** is **SECURITI_CONNECTOR** then:
    - ```plaintext
GRANT ROLE SECURITI_IAM_MONITOR TO ROLE SECURITI_CONNECTOR;
```
  - This will ensure that the **securitiuser** has the privileges to not only perform the activities associated with the connector to fetch data resources but also the privileges to fetch the IAM-related metadata for the Access Intelligence scan.
4. Use the SNOWFLAKE database role to provide metadata access to the custom role.
  - Grant the**OBJECT_VIEWER** role to the custom role e.g., to **SECURITI_IAM_MONITOR** using the following SQL statement:

```plaintext
use database snowflake;
use schema SNOWFLAKE.ACCOUNT_USAGE;
GRANT DATABASE ROLE OBJECT_VIEWER TO ROLE SECURITI_IAM_MONITOR;
```

The **OBJECT_VIEWER** role provides visibility into object metadata. Note that the **OBJECT_VIEWER** role has the **SELECT** privileges on the following **VIEWS**:

For more details, see Snowflake [documentation](https://docs.snowflake.com/en/sql-reference/snowflake-db-roles#account-usage-views-by-database-role).
    - COLUMNS
    - COMPLETE_TASK_GRAPHS
    - DATABASES
    - ELEMENT_TYPES
    - FIELDS
    - FILE_FORMATS
    - FUNCTIONS
    - HYBRID_TABLES
    - INDEXES
    - INDEX_COLUMNS
    - OBJECT_DEPENDENCIES
    - PIPES
    - REFERENTIAL_CONSTRAINTS
    - SCHEMATA
    - SEQUENCES
    - STAGES
    - TABLE_CONSTRAINTS
    - TABLES
    - TAGS
    - VIEWS
    - SERVICES
5. Create an oAuth security integration to enable oAuth-based access to Snowflake from the Securiti connector.
  - Note that the **ACCOUNTADMIN** role is necessary to create security integrations within Snowflake.
  - In the following command, the validity of the oAuth Refresh Token is set to the maximum allowed by Snowflake. The oauth_redirect_uri will change depending on where your Securiti tenant has hosted. Various endpoints have been listed below:

| Cloud Instance | URl |
| --- | --- |
| U.S. Cloud | app.securiti.ai |
| EU Cloud | app.eu.securiti.ai |
| U.S. GCP Cloud | app1.securiti.ai |
| Indonesia Cloud | app2.securiti.ai |
| Canada Cloud | app3.securiti.ai |
| Australia Cloud | app4.securiti.ai |
| UAE Cloud | app5.securiti.ai |
| Mumbai Cloud | app6.securiti.ai |
  - Use this SQL Command to create the integration:

```plaintext
create or replace security integration <INTEGRATION-NAME>
type = oauth
enabled = true
oauth_client = custom
oauth_client_type = 'CONFIDENTIAL'
oauth_redirect_uri = 'https://app.securiti.ai/static/activateMetadataSource.html, https://app.securiti.ai/static/activateMetadataSource.html'
oauth_issue_refresh_tokens = true
oauth_refresh_token_validity=7776000;
```
6. Grant ownership of the oAuth integration to the custom role. Note that a user with **SYSADMIN** or **ACCOUNTADMIN** role must execute these SQL statements:

```plaintext
GRANT OWNERSHIP on integration <INTEGRATION-NAME> to role SECURITI_IAM_MONITOR REVOKE CURRENT GRANTS;
```

This grants ownership of the specified integration (<INTEGRATION-NAME>) to the **SECURITI_IAM_MONITOR** role. The **REVOKE CURRENT GRANTS** clause ensures any existing grants on the integration are revoked before assigning ownership.
7. View the integration details. Use the following SQL commands to view the secrets and details of the integration. This lets the custom role view details and secrets associated with the integration.

```plaintext
DESCRIBE INTEGRATION <INTEGRATION-NAME>;
select system$show_oauth_client_secrets('<INTEGRATION-NAME>');
```
8. [Setup the pod or elastic pod](/latest/docs/securiti-pods-and-elastic-pods).
9. Configure (or re-configure) and activate the connector using **securitiuser**. Select OAuth 2.0 or Key Pair Auth as the authentication type.
  - For Snowflake Self-hosted connectors, you must perform Connector Scope Sync.
10. Perform discovery scan for your Snowflake Self-hosted instance or Data Scan for the Snowflake Securiti Cloud instance

**2 . Authenticate Credentials in Snowflake**

1. Log in to your Snowflake account for example, <***https://cla43452.snowflakecomputing.com/console/login#/?returnUrl=internal%2Fworksheet***>.

The part before *snowflakecomputing.com* is your account name or ID. In the above example, *cla43452* is your Snowflake account name or ID. Record it to use later.
2. For **Basic** Authentication method, record the username and password for your Snowflake account.
3. For **Key pair** Authentication, follow the procedure below:

For more information, see Snowflake's official documentation on [Key Pair Authentication & Key Pair Rotation](https://docs.snowflake.com/en/user-guide/key-pair-auth).
  1. Open Snowflake terminal (or any open-ssl terminal) and generate a private key.

You can generate either an encrypted version of the private key or an unencrypted one.

> [!NOTE]
> **Note**
> 
> The commands below assume *rsa_key* as your custom file name. You can choose a file name of your choice for private key file.

To generate an unencrypted version, use the following command.

```plaintext
$ openssl genrsa 2048 | openssl pkcs8 -topk8 -inform PEM -out rsa_key.p8 -nocrypt
```

To generate an encrypted version, use the following command (which omits “-nocrypt”):

```plaintext
$ openssl genrsa 2048 | openssl pkcs8 -topk8 -v2 des3 -inform PEM -out rsa_key.p8
```

> [!NOTE]
> **Note**
> 
> The command for encrypted key, prompts for a passphrase to regulate access to the key. It is recommended to use a passphrase that complies with PCI DSS standards to protect the locally generated private key.

The commands generate a private key in PEM format as shown below.

```plaintext
-----BEGIN ENCRYPTED PRIVATE KEY-----
MIIE6TAbBgkqhkiG9w0BBQMwDgQILYPyCppzOwECAggABIIEyLiGSpeeGSe3xHP1
wHLjfCYycUPennlX2bd8yX8xOxGSGfvB+99+PmSlex0FmY9ov1J8H1H9Y3lMWXbL
...
-----END ENCRYPTED PRIVATE KEY-----
```

Record the private key for later.
  2. Generate a public key, referencing the private key generated in the previous step.

In the command line, use the following command to generate the public key. The following command assumes the private key is encrypted and contained in the file named *rsa_key.p8.*

```plaintext
$ openssl rsa -in rsa_key.p8 -pubout -out rsa_key.pub
```

The command generates the public key in PEM format as shown below.

```plaintext
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAy+Fw2qv4Roud3l6tjPH4
zxybHjmZ5rhtCz9jppCV8UTWvEXxa88IGRIHbJ/PwKW/mR8LXdfI7l/9vCMXX4mk
...
-----END PUBLIC KEY-----
```
  3. (Optional) Use the following command to view the key in terminal.

```plaintext
cat rsa_key.pem
```
  4. Save the public and private keys securely.

Copy the public and private key files to a local directory for storage. Record the path to the files.

> [!NOTE]
> **Note**
> 
> The private key is stored using the PKCS#8 (Public Key Cryptography Standards) format and is encrypted using the passphrase.
  5. Assign the Public Key to a Snowflake user.

Use the following [ALTER USER](https://docs.snowflake.com/en/sql-reference/sql/alter-user) command to assign the public key to a Snowflake user.

```plaintext
ALTER USER jsmith SET RSA_PUBLIC_KEY='MIIBIjANBgkqh...';
```

> [!NOTE]
> **Note**
> 
> Only security administrators (i.e. users with the SECURITYADMIN role) or higher can alter a user.
  6. Passphrase is optional to use for key pair Authentication. As you provide the encrypted key, the passphrase is needed to decrypt the key and authenticate the Connector. A passphrase is not needed when the key is in plaintext.

**3. Configure an IAM Metadata source for Snowflake**

1. In Securiti, open Data Access Governance.
2. From the left navigation menu, click Settings.
3. Click IAM Metadata Sources.
4. Click + New IAM Metadata Source.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1781168774903.png)

1. On the New IAM Metadata Source popup:
  - Enter the Connection Name.
  - Select Snowflake Onprem in Source Type.
  - Enter:
    - Account
    - Warehouse
    - Pod Name
2. In the Authentication Details section you have two options:
  - If you select Key Pair Authentication from Authentication Type dropdown.
    - Enter the Snowflake Username.
    - Upload the Private Key file (.p8 or .pem).
    - Enter Passphrase (if encrypted).
    - (Optional) Enter SHA256 Fingerprint.
  - If you Select OAuth 2.0 in Authentication Type then enter the following:
    - Client ID
    - Client Secret
3. Click Authenticate and Create New IAM Metadata Source. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1781168774908.png)

> [!NOTE]
> Note
> 
> Key Pair Authentication is supported for Snowflake (Onprem and Cloud) connectors and is recommended for service accounts where OAuth-based browser authentication is not desired.

**4. Configure an Access Scan Definition for Snowflake**

1. In Securiti, open **Data Access Governance**, then from the left menu bar choose **Settings>Access Scan Definitions**.
2. Near the upper right corner of the page, click **+ New Access Scan Definition**.
3. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select the **Snowflake** in the **Data System**.
  3. Specify the Account ID in the **Account**.
  4. In the **IAM Metadata Sources**, select the metadata sources that you have created for a particular data system. If you have not configured a metadata source, then you must click **+ Add New** to add a metadata source.
  5. In the **Associated Connectors** area, select the associated systems in the **Data Systems** for which access metadata is being scanned.
  6. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information daily.
  7. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  8. Click **Add Definition**.

**5. Enable the Access Intelligence Scan**

If you have not selected the associated Connectors while configuring the Access Scan Definition, then you must:

- Enable the Access Intelligence Scan toggle on the Data System Connector Page. Navigate to the **Permissions** tab of the Connector. Enable the Access Intelligence Scan button to the ASD with the data system connector.

**6. Initiate Access Intelligence Scan**

On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.

Click the three dots option, and select the **Scan Now** option.

### Configuring Access Intelligence Privilege Analysis without using IAM Metadata Sources

#### Prerequisites

To configure access intelligence for Snowflake you must

**1. Create a custom role in your Snowflake account and assign permissions**

To scan the Snowflake account for Access Intelligence , Securiti requires certain permissions and privileges to access the account and obtain metadata from there. Mainly, the metadata is obtained from the SNOWFLAKE.ACCOUNT_USAGE schema. This document describes the steps by which the privileges can be granted, by using a custom role. This role is named as SECURITI_IAM_MONITOR in the rest of the document, although in your account you may create a differently named role. This role is then assigned to the user that is configured in the Snowflake Connector on Securiti, to make the connection and to perform the Access Intelligence scan. We will use 'securitiuser' as the user-id in the rest of the document. Further we will assume, for illustration, that the user has a default role of 'SECURITI_CONNECTOR'. Note that in your account the user in question and the default role granted to that user may be differently named — we are using securitiuser and SECURITI_CONNECTOR for illustration.

> [!NOTE]
> Note
> 
> When using Snowflake Connectors as Data System Connectors in Access Scan Definitions, please be aware that only HashiCorp Vault is supported for keyring-based credentials. Snowflake Connectors support additional vault providers for discovery scans, but Access Scan Definitions only support HashiCorp Vault. Therefore, if your Snowflake Connector is configured with a keyring, it must use HashiCorp Vault.
> 
> If you want to use vault-stored credentials for your Access Scan Definition, you must configure the Snowflake Connector as the source of credentials ("Connectors as Metadata Source") with a HashiCorp Vault keyring. As a workaround, you may configure either a new Snowflake Connector that uses HashiCorp Vault, or configure an IAM Metadata Source with credentials entered directly, and then use it in the Access Scan Definition.

1. Create a custom role in your Snowflake account. As an example, we have used **SECURITI_IAM_MONITOR** as the name in the rest of the topic. See [Snowflake documentation](https://docs.snowflake.com/en/sql-reference/sql/create-role#access-control-requirements) for requirements to create a custom role.
2. Assign the role **securitiuser**.

```plaintext
GRANT ROLE SECURITI_IAM_MONITOR TO USER securitiuser;
```
3. Set the role as the default for the user.

```plaintext
ALTER USER securitiuser SET DEFAULT_ROLE = 'SECURITI_IAM_MONITOR';
```

Alternatively, assign the role to the **DEFAULT_ROLE** of the user, e.g., assuming securitiuser has *SECURITI_CONNECTOR* as the DEFAULT_ROLE in your account, then' then:
  - If the DEFAULT_ROLE for **securitiuser** is **SECURITI_CONNECTOR** then:
    - ```plaintext
GRANT ROLE SECURITI_IAM_MONITOR TO ROLE SECURITI_CONNECTOR;
```
  - This will ensure that the **securitiuser** has the privileges to not only perform the activities associated with the connector to fetch data resources but also the privileges to fetch the IAM-related metadata for the Access Intelligence scan.
4. Use the SNOWFLAKE database role to provide metadata access to the custom role.
  - Grant the**OBJECT_VIEWER** role to the custom role e.g., to **SECURITI_IAM_MONITOR** using the following SQL statement:

```plaintext
use database snowflake;
use schema SNOWFLAKE.ACCOUNT_USAGE;
GRANT DATABASE ROLE OBJECT_VIEWER TO ROLE SECURITI_IAM_MONITOR;
```

The **OBJECT_VIEWER** role provides visibility into object metadata. Note that the **OBJECT_VIEWER** role has the **SELECT** privileges on the following **VIEWS**:

For more details, see Snowflake [documentation](https://docs.snowflake.com/en/sql-reference/snowflake-db-roles#account-usage-views-by-database-role).
    - COLUMNS
    - COMPLETE_TASK_GRAPHS
    - DATABASES
    - ELEMENT_TYPES
    - FIELDS
    - FILE_FORMATS
    - FUNCTIONS
    - HYBRID_TABLES
    - INDEXES
    - INDEX_COLUMNS
    - OBJECT_DEPENDENCIES
    - PIPES
    - REFERENTIAL_CONSTRAINTS
    - SCHEMATA
    - SEQUENCES
    - STAGES
    - TABLE_CONSTRAINTS
    - TABLES
    - TAGS
    - VIEWS
    - SERVICES
5. Create an oAuth security integration to enable oAuth-based access to Snowflake from the Securiti connector.
  - Note that the **ACCOUNTADMIN** role is necessary to create security integrations within Snowflake.
  - In the following command, the validity of the oAuth Refresh Token is set to the maximum allowed by Snowflake. The oauth_redirect_uri will change depending on where your Securiti tenant has hosted. Various endpoints have been listed below:

| Cloud Instance | URl |
| --- | --- |
| U.S. Cloud | app.securiti.ai |
| EU Cloud | app.eu.securiti.ai |
| U.S. GCP Cloud | app1.securiti.ai |
| Indonesia Cloud | app2.securiti.ai |
| Canada Cloud | app3.securiti.ai |
| Australia Cloud | app4.securiti.ai |
| UAE Cloud | app5.securiti.ai |
| Mumbai Cloud | app6.securiti.ai |
  - Use this SQL Command to create the integration:

```plaintext
create or replace security integration <INTEGRATION-NAME>
type = oauth
enabled = true
oauth_client = custom
oauth_client_type = 'CONFIDENTIAL'
oauth_redirect_uri = 'https://app.securiti.ai/static/activateConnector.html'
oauth_issue_refresh_tokens = true
oauth_refresh_token_validity=7776000;
```
6. Grant ownership of the oAuth integration to the custom role. Note that a user with **SYSADMIN** or **ACCOUNTADMIN** role must execute these SQL statements:

```plaintext
GRANT OWNERSHIP on integration <INTEGRATION-NAME> to role SECURITI_IAM_MONITOR REVOKE CURRENT GRANTS;
```

This grants ownership of the specified integration (<INTEGRATION-NAME>) to the **SECURITI_IAM_MONITOR** role. The **REVOKE CURRENT GRANTS** clause ensures any existing grants on the integration are revoked before assigning ownership.
7. View the integration details. Use the following SQL commands to view the secrets and details of the integration. This lets the custom role view details and secrets associated with the integration.

```plaintext
DESCRIBE INTEGRATION <INTEGRATION-NAME>;
select system$show_oauth_client_secrets('<INTEGRATION-NAME>');
```
8. [Setup the pod or elastic pod](/latest/docs/securiti-pods-and-elastic-pods)
9. [Configure (or re-configure) and activate the connector](/latest/docs/snowflake-connectors) using **securitiuser**. Select OAuth 2.0 as the authentication type.
  - For Snowflake Self-hosted connectors, you must perform Connector Scope Sync
10. Enable the Access Intelligence Scan toggle on the Data System Connector Page. Navigate to the **Permissions** tab of the Connector. Enable the Access Intelligence Scan button to the ASD with the data system connector.
11. Perform discovery scan for your Snowflake Self-hosted instance or Data Scan for the Snowflake Securiti Cloud instance.
12. Configure Access Intelligence Scans:
  1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.
  2. Click **Access Scan Definitions**. This opens the Access Scan Definitions (ASDs) page.
  3. Near the upper right corner of the page, click **+ New Access Scan Definition**.
  4. On the New Access Scan Definition popup:
    1. Enter the **Name** for the Access Scan Definition.
    2. Select **Snowflake** in the **Data System** menu. For more information about supported systems, see [Configuring Access Intelligence Scans without using IAM Metadata Sources](/latest/docs/access-intelligence-scans-without-using-iam-metadata-sources).
    3. Enter the account name for the Snowflake cloud account in the **Account**.

Securiti will provide the list of all the relevant instances of the selected data systems configured using the provided Account ID in the **Data System Connector** menu.
    4. In the **Source of Credentials and Connectivity for Access Intelligence Scans** area, you must select the **Data System Connector** tile.

![DAG_Connctor_as_MDS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dd07143d-58e1-344e-9b0c-3b61a2b47149(1).png)
    5. In the **Data System Connector** menu, select the data system instance for which you must perform Access Scan.
    6. In the **Data Systems** menu, the instance you selected earlier in **Data System Connector** is selected by default. You can also select other instances related to provided Account ID if required.
    7. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information weekly.
    8. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
    9. Click **Add Definition**.
  5. On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.
  6. Click the three dots option, and select the **Scan Now** option.

#### Using Access Intelligence with Snowflake

Below are example use cases to familiarize you with how to leverage our Data Command Graph to identify access and risk in your Snowflake tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

#### Identifying Users with Access to a specific Database(s) using the Data Command Graph

To identify the users that have access to a specific database:

1. In Securiti, open **Data Access Governance** and choose **Data Access Governance Overview** to access the Command Graph.
2. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, set **Entity** to **Database**. Set the **Attribute** to the **Database Name**. Set the operator to the **Equals**.

![DAG_Snowflake_DBName.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e01e73cd-c368-82eb-368c-a8a2da54dd70.png)
3. Select the **Database** for which you want to identify the users that have access to the Site.
4. Click **Apply**.
5. Click on the **User Principal** node to see the users in the data grid.

#### Identifying Users with Access to a Table(s) containing sensitive data using the Access Graph Explorer

1. In Securiti, open **Data Access Governance** and choose **Access Graph Explorer** from the left menubar.
2. Click on the **Saved Views** button on the upper left side of the page.
3. On the **Popular Views** tab, navigate to the **Snowflake Queries** area. You can see the queries that help you perform privilege analysis for your Snowflake instances.
4. Click on the query **Users with Any access to Tables containing Sensitive Data**. Click on the User Principal node to see the users in the data grid.

![DAG_Snowflake_identity_explorer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4fcfe122-3c6e-b972-69e6-c8676da369e8.png)

#### Identifying Users with Control Access Access to Database using the Access Graph Explorer

1. In Securiti, open **Data Access Governance** and choose **Access Graph Explorer** from the left menubar.
2. Click on the **Saved Views** button on the upper left side of the page.
3. On the **Popular Views** tab, navigate to the **Snowflake Queries** area. You can see the queries that help you perform privilege analysis for your Snowflake instances.

![Identity_Graph.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a8fa932a-9311-fccc-c617-66fd83c383b2.png)
4. Click on the query **Users with Control Access to Databases**. Click on the User Principal node to see the users in the data grid.

#### Identifying Users with Any access to Tables containing Column Classification using the Access Graph Explorer

1. In Securiti, open **Data Access Governance** and choose **Access Graph Explorer** from the left menubar.
2. Click on the **Saved Views** button on the upper left side of the page.
3. On the **Popular Views** tab, navigate to the **Snowflake Queries** area. You can see the queries that help you perform privilege analysis for your Snowflake instances.
4. Click on the query **Users with Any access to Tables containing Column Classification**. Click on the **User Principal** node to see the users in the data grid.

#### Identifying Inherited Roles and Privileges using the Role Collection Node

Securiti adds a **Role Collection** node for every **Role** node in the Data Command Graph. This node holds precomputed relationships to every Role that the associated Role can, in turn, assume, so you get the complete Role hierarchy without Securiti recomputing it on each query. The **Role** and **User Principal** nodes connect directly to their **Role Collection** node, letting you query inherited Roles, and the grants and privileges that come with them, faster from either node. Use the **Role Collection** node only in queries where inherited Roles are necessary to get the complete access picture.

> [!NOTE]
> Note
> 
> The Role Collection node requires a new access scan to run before it appears in the graph. Run a new Snowflake access scan to populate Role Collection nodes for your account.
> 
> Role recursion is disabled only when the query contains a **Role Collection** node. In such queries, traversing into or out of a **Role** node fetches only the Roles directly connected to that Role node, and the **Role Collection** node provides the complete Role hierarchy. Queries that do not contain a **Role Collection** node continue to recurse through the Role hierarchy, so existing queries return the same results as before.

**Identifying users with direct access to tables containing sensitive business data**

To identify users that have direct access to tables containing sensitive business data:

1. In Securiti, open **Graph Explorer**.
2. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **Data Element** entity. Click three dots with the **Data Element** entity, and select **+ Add Property**. Choose **Non-Personal Sensitive Data**. Select the **Equals** operator. Select **True**.
3. Click three dots with the **Data Element** entity, select **Add Relationship**, and select **Table**. Repeat this to build out the chain: **Table** to **Resource Scope**, **Resource Scope** to **Policy Element**, and **Policy Element** to **Role**.
4. Click three dots with the **Role** entity, select **Add Relationship**, and select **User Principal**. Click three dots with the **User Principal** entity, and select **+ Add Property**. Choose **Provider Type**. Select the **Is one of** operator. Select **Snowflake**, as shown below.
5. Click **Apply**, then click **Run Query**.
6. Click on the **Data Element** node to see the data elements in the data grid.
7. Click on the **Role** node to see the roles in the data grid.
8. Click on the **User Principal** node to see the users in the data grid. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 4(21).png)

**Identifying users with any access to tables containing sensitive business data (via Role Collection)**

To identify users that have access to tables containing sensitive business data, including access gained through an inherited Role:

1. In Securiti, open **Graph Explorer**.
2. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **Data Element** entity. Click three dots with the **Data Element** entity, and select **+ Add Property**. Choose **Non-Personal Sensitive Data**. Select the **Equals** operator. Select **True**.
3. Click three dots with the **Data Element** entity, select **Add Relationship**, and select **Table**. Repeat this to build out the chain: **Table** to **Resource Scope**, **Resource Scope** to **Policy Element**, and **Policy Element** to **Role**.
4. Click three dots with the **Role** entity, select **Add Relationship**, and select **Role Collection**. This adds the node that holds every Role the associated Role can, in turn, assume.
5. Click three dots with the **Role Collection** entity, select **Add Relationship**, and select **User Principal**. Click three dots with the **User Principal** entity, and select **+ Add Property**. Choose **Provider Type**. Select the **Is one of** operator. Select **Snowflake**, as shown below.
6. Click **Apply**, then click **Run Query**.
7. Click on the **User Principal** node to see the users in the data grid.
8. Click on the **Role Collection** node to see every inherited Role, including Roles the user only holds indirectly through Role inheritance. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 5(15).png)

#### 

#### Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards).

### Configuring data access control policies for Snowflake

This policy type lets you configure granular access permissions across your Snowflake database.

#### Prerequisites

To create a data access control policy for Snowflake (self-hosted) you must:

- [Set up a pod or elastic pod](/latest/docs/securiti-pods-and-elastic-pods).
- [Configure and activate the connector](/latest/docs/snowflake-connectors). The user account you use to configure and activate the connector must have a role assigned that has ownership permissions on the data sources (tables, columns, schemas) for which you want to configure policies.
- Mark the checkbox for **Enable Data Access Control** in the data system’s **Access Permissions** tab, so that this data system is available for selection when you create the policy.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(51).png)

- Mark the checkbox for **Create AD Users Mapping Table** in the data system’s Permissions tab. When enabled and saved, user mapping tables are created in the data system that allow users to create custom row filters and conditional masking.
- Mark the checkbox for **Enable Database Row Filter Policy** in the data system’s Permissions tab. When enabled, the **Sync Row Filter Policy** option will appear which syncs row filter policies from Snowflake to Securiti. Note that to create row Level policies, the user account you used to configure the connector must have a role assigned that has **CREATE ROW ACCESS POLICY** privilege.
- Mark the checkbox for the **Enable Database Column Masking Policy**. When enabled and saved, the **Sync Masking Policy** option appears, which syncs masking policies from Snowflake to Securiti. Note that to create masking policies, the user account you used to configure the connector must have a role assigned that has **CREATE MASKING POLICY** privilege.
- Mark the checkbox for **Enable Sync Role**. When enabled and saved, the Sync Roles Option appears, which syncs roles from Snowflake to Securiti.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(35).png)

- To use the user defined masking function, you must create **_secmask** schema in Snowflake, and define your custom user-defined masking functions within it.
- To use the user defined row filtering functions, you must create **_secfilter** schema in Snowflake, and define your custom user-defined masking functions within it. To create a masking policy for masking functions, you can refer to the [Snowflake’s Create Masking Policy](https://docs.snowflake.com/en/sql-reference/sql/create-masking-policy) documentation.
- To define the conditional row filtering and masking conditions based on the user attributes, you must synchronize the Active Directory with Securiti. For more information see, [Configuring Active Directory Server](/latest/docs/identity-providers-idp-providers-for-identity-sync).
- Perform a discovery scan for the Snowflake instance.

> [!NOTE]
> Note
> 
> **_secgen** tables are objects created by the Securiti to manage policies. Securiti does not push any policies to these tables since they are used internally.

#### Creating data access control policies

1. In Securiti, open **Data Access Governance**, then click three dots icon to expand the navigation bar. Choose **Policies>Data Access Policies**.

![DAG_navbar.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d2d78989-9dd6-f337-918a-5f64aa9633c1(2).png)
2. Near the upper right corner of the page, click **Create Policy**.
3. On the Create a New Policy popup:
  1. Choose policy type **Data Access Control**.
  2. From the **Select Data System** menu, choose **Snowflake**.
  3. (Optional) Choose a template for the policy.
  4. Click **Get Started**.
4. Enter a name for the policy.
5. (Optional) Add a description for the policy.
6. Expand the **Data Scope** area and use the tools there to configure the scope. Scope defines the boundaries and context within which the access policy's rules and privileges are enforced.

> [!NOTE]
> **Note**
> 
> If you delete a data system instance for which you have defined an access control policy and selected associated data objects such as databases, schemas, etc. in scope, Securiti changes its state to "Not in Use" on the Policies page. The policy is automatically deactivated. Note that the privileges enforced by the policy on the data system will not be removed, as Securiti will no longer have an active connection with the data system.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (6)(1).png)
  1. From the Actions column, click on the graph icon to add the scope. Once you click the graph icon, the Graph Explorer window opens. You are presented with a blank canvas where you can begin defining your graph search criteria in the following ways:
    - By clicking the **+** sign in the upper left corner of the upper row of the dashboard.
    - By clicking the **Begin Your Search** button at the center.
    - By loading an existing filter from **Saved Views** from the upper right corner of the page
  2. Click + or the Begin Your Search button at the center of the page. The filter menu has three panels as described below:

| Panel | Description |
| --- | --- |
| Left panel (Groups) | The left panel shows the entity groups. Clicking on a group name moves the second panel to that group. |
| Center panel (Entities) | The second panel lists all available entities. |
| Right panel (Description) | Hovering over one of the entities in the center panel brings up the description for the entity in the right panel. |
  3. From the center panel, click on the **Database** entity. Click **Add Property** to add a property. Select the **Data System Type** from the list of properties associated with the selected node.
  4. After selecting the property, you can choose the operator to select what criteria to match on from the menu. Select the **contains** operator, and type the value as **Snowflake**. You can also search **Snowflake** in the search bar to filter the databases.
  5. Select the database from the data grid on which you must apply the policy.
  6. Apply the **increment (+ icon)** operator to add the entity and attribute as an include rule to the page filter. The added filter appears in the top row of the dashboard with the rest of the filters.
  7. Click options (three dots) on the right side of the **Database** node and click **+ Add Relationship**.
  8. Select the **Database Schema** node. Click on the Database Schema entity from the left panel. Select the Database Schema for which you want to implement the privileges. Apply the **increment (+ icon)** operator. You can also add the Tables to the scope of the policy as shown above. Note that if you have selected Tables in the data scope, then you can select the table-level privileges in the Access Rules.
  9. ![Scope section defining data system properties and instance count for access policies.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (5)(1).png) You can also see the policies that has same data objects in the data scope of the current policy. If multiple access control policies grant different permissions (such as READ and WRITE) on the same data object, Securiti combines those permissions. This means users (principals) will receive the full set of access rights granted across all applicable policies. For masking policies applied to the same data object (for example, the same column), Securiti enforces a defined precedence order. The following masking functions take priority in enforcement:
    - Unmasked
    - Masking Function
    - ConditionalMasking
    - Hash SHA 256
    - Email Masking
    - Last Four
    - First Four
    - Custom Value
    - Default Masking
    - Nullify
7. In the **Access Rules** area, click **+ Add a Privilege Rule** to add a rule. **In the Add a Privilege Rule window**:
  1. Provide the Rule Name.
  2. (Optional) Add description.
  3. In the **Principals** area, click **+ Add a Principal**. Principals are the entities on which the access rule is applied. You can select Roles as Principals.
  4. In the **Privileges** area, you must select the privileges that you want to grant to the **Principals**. Note that the privileges displayed are the native Snowflake privileges. The privileges displayed are dependent on the data resources you select in the **Data Scope**. If you have selected **Database Schema** in the **Data Scope**, then the Schema level privileges are displayed.
  5. Click the **Create Rule** button to add an access rule.
  6. If you have selected the **Tables** in the **Data Scope**, you can define filtering rules to configure row-level filtering conditions for the Principals (users and groups). To add a filtering rule:
    - In the **Access Rules** area, click on the **Filtering tab**.
    - Click on the **+ Add a filtering Rule** button to add the rule.
    - In the **Add a Filtering Rule** window, provide the **Rule Name**.
    - (Optional) Add the description.
    - In the **Principals** area, click **+ Add a Principal** to add the Principals as shown above.
    - In the **Row Filtering Condition**, select the filtering condition. You can select the **General Filtering** conditions such as **Include all rows** and **filter out all rows** or **Advanced Filtering** condition such as **Conditional filtering**. The **Include all rows** condition provides access to all the rows to the selected principals. The **Filter out all rows** condition restricts access to all the rows. Note that if you use Filter out all rows condition to restrict access for a particular user, the function also prevents other users from accessing all the rows. To provide access to other users, you must define the Include all rows condition. You can also select the User-defined Function. Note that if you have selected the **User-Defined Function (UDF)** as a **Row Filtering Condition**, you must select the UDF from the **Row Filtering Condition**. User-defined functions (UDFs) are the custom row filtering conditions that you define in the Snowflake.

![dac_v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-57ddc4b0-3df2-b7eb-aff4-20b6a87f8777(2).png)
  7. If you have selected **Conditional filtering,** you must specify the condition based on the **User Attribute**, **Column by Name**, or **Column by Element**.

Click **Add a Filtering Rule** button to add multiple filtering rules.
    - From the **Return rows where** area, click on the + Icon. Select the **User Attribute** from the left panel if you want to apply a condition based on the **Active Directory** user attributes. Select the attribute and Operator such as **Equal**, **Not Equal**, **Less than** etc. Provide the value in the field below **Constants**. Note that SQL syntax is not supported. You must provide the value in JSON String format. For example, “New York”. Note that if you have selected the **City** as the User Attribute, and provided “New York” as a Constant value, the policy upon execution evaluates if the selected user attribute i.e, City in this case has the same value as that of the provided Constant (“New York”) in the Active Directory mapping table. If this condition is true, then the selected Principal can access the table rows.
    - To add a condition based on the column name, select the Column By Name option. Type the column name such as City in the middle panel. Select the operator value from the right panel. You can select the **Constant** or **Attribute** options. If you have selected the Constant, you must provide the value of the Constant. For Example, for the column name ‘City’ you have selected, you provide ‘’Los Angeles’’ as the **Value** of the Constant. Upon successful execution of the policy, the Principal will have access to all the rows in the table for which the value of the column name ‘City’ is ‘’Los Angeles’’.
    - To add a condition based on the data elements, select the **Column By Element** option. Select the data element such as the Email address in the middle panel. Note that the data elements must be discovered in the discovery scan. Select the operator value from the right panel. You can select the **Constant** or **Attribute** options. If you have selected the Constant, you must provide the value of the Constant. For Example, for the data element ‘Email Address’’ you have selected, you provide ’'jane@example.com', and 'michael@example.com’’ as the **Value** of the Constant. Upon successful execution of the policy, the Principals will have access to all the rows in the table for which the values of the column ‘Email Address’ are ‘’jane@example.com'’ or 'michael@example.com’’. If you have selected the **Attribute** option, you must select the attribute that the policy will compare with the selected column name. For example, for the data element ‘Email Address’’ previously selected, you select the Email Address as the **Attribute**, and in the mapping table, for the selected Principal, the value of the Email Address attribute is “michael@example.com’. Upon successful execution of the policy, the Principal will have access to all the rows of the selected table for which the value of the Email Address is michael@example.com.
    - Click the **Create Rule** button. You can add multiple conditions separated by ‘**AND**’ and ‘**OR**’ operators.
  8. If you have selected the Column in Datascope, you must configure the masking rule to create an access control policy. To configure a masking rule:
    - Click on the **+ Add a Masking Rule** button to add the rule.
    - Enter the **Rule Name**.
    - (Optional) Add description.
    - In the **Principals** area, click **+ Add a Principal**.
    - Select **Users** or **Groups**. You must select Users or Groups as a Principal to create an access rule. If you have selected the **Users** as a Principal, then you must specify the **Users**. In the **Users** area, select the users from the menu. You can also add the users using the or use **Graph Query button**. Note that you can add the Active Directory users and Securiti Tenant users. A Tenant User is the User that can access the Securiti’s Data Command Center.
    - You can also add Active Directory **Groups** as a Principal.
    - In the Masking Behaviour area, you must configure the type of masking to mask the selected columns to only the specified principals.
      - If you have selected the **Custom Value** option, you must provide the value by which data will be masked. For example, if you have entered “**##**” as the **Custom Value**, and selected the email column in the **Data Scope**, the values of the email column will be masked for the specified Principal. You can also view the masking function under the **_secgen** schema.
      - Note that if you have selected a user as a Principal and applied a masking behavior such as Custom Value, the null masking will be applied for all other users. They will not be able to see any data in the specified column. To provide access to all other users, you must select them as Principals, and select Unmasked from the Masking Behaviour area.
      - You can also use built-in masking functions such as Hash (SHA-256), Default Masking etc. To use the built-in masking functions, select the Built-In Masking Function option from the menu. And select the type of masking you want to apply from the Built-In Masking Function option. You can select the following masking functions:

| Masking Function | Description |
| --- | --- |
| Default Masking | The uppercase alphabets are replaced with ‘N’. Lowercase alphabets are replaced with the ‘n’. Integers are replaced with 0. Special characters are replaced with X. |
| Email Masking | The data system selected while creating the policy. |
| First Four | The first four characters will be displayed, and the remaining part of the string will be masked by *. If the length of the value is equal to or less than four characters, then the value will be masked by SHA-256 hash function. You can only use this masking function for String data type value. |
| Last Four | The last four characters will be displayed, and the remaining part of the string will be masked by *. If the length of the value is equal to or less than four characters, then the value will be masked by SHA-256 hash function. You can only use this masking function for String data type value. |
| Hash (SHA-256) | This replaces the characters with the random 256 bits string (16 characters). |
| Nullify | Nullifies the value. |
      - You can also apply **Conditional Masking** based on the **User Attribute**, **Column By Name**, and **Column By Element**, and use the Expression Builder to define conditions. You can define masking behaviour **if** the expression returns a **True** value and which type of masking must be applied if the expression returns a false value.
      - Click the **Create Rule** button.
8. Activate the **Enable policy after saving** toggle. When activated, the policy will be enforced as soon as the policy information is saved.
9. Click the **Create Policy** button to create the policy.

#### Access Policy Preview and Backup

You can Preview the changes the policy will make to the access configurations of your data systems prior to the enforcement of the policy. For each of the policy, that you create, update, or delete, Securiti creates backups automatically, and you can restore to any backup to roll back to that specific state. These controls let you enforce the data access control policies on your data systems in a secure manner, ensuring that you realize the impact of the policies before enforcement.

#### Policy Preview

When you click **Create Policy** button, the **Policy Preview** will be generated. Policy Preview presents you with the entities such as Databases, Tables, Columns, etc. and privileges, row filters, and masking functions that that will be implemented upon successful enforcement of the policy. Note that the policy execution will start only if you **Accept** the Policy Preview.

![Policy_preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-150e7650-4b63-9de0-b869-607808bbd18e(2).png)

> [!NOTE]
> **Note**
> 
> No backup will be created in the case of preview being rejected in policy creation.

If you accept the **Policy Preview**, the backup of the policy will be automatically generated and you can access it via **Backups** page. Securiti also generates Policy Preview and Backup when you update or delete the access control policies.

![Backup_policy_Snowflake.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b6c156cf-acce-d8dc-4b3e-f8559ea49936(1).png)

#### Backups

This section describes the configurations steps for creating a policy Backup manually and restoring a Backup.

#### Creating a Policy Backup manually

To create a Policy Backup:

1. In Securiti, open **Data Access Governance**, then choose **Policies**>**Data Access Policies**.
2. Near the upper right corner of the page, click **Backups**.

![Backup_policy_button.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bef6fa34-90f6-0db1-77e6-3abcdaf18956(2).png)
3. Near the right corner of the page, click **Manual Backup**.
4. On the **Manual Backup** popup, enter the following information
  1. Add **Backup Name** to suit.

![Manual_Backup_Policy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-39ea62b0-b5f4-9f31-e320-b1d003dde0a2.png)
  2. Select the data system from the **Data System Type** menu.
  3. From the **Data System** menu, select the Data System instance.
  4. Click, **Create Backup** button.

#### Restoring a Policy Backup

To restore a Policy Backup:

1. In Securiti, open **Data Access Governance**, then choose **Policies**>**Data Access Policies**.
2. Near the upper right corner of the page, click **Backups**.

![Backup_policy_button.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bef6fa34-90f6-0db1-77e6-3abcdaf18956(2).png)
3. Near the right corner of the user row, click Options (three dots) > **View Backup**.

![Restore_Backup_Snowflake.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-da81fbf9-7bb1-94bf-9b03-799b018007ba(1).png)
4. The Backup Policy page will show you the privileges, row filters, and masking functions and entities, included in the backup, when this backup was taken.
5. Near the upper right corner of the page, click the **Restore Backup** button If you want to revert the current state of the data system and restore the data system to the state when this backup was created.

![Restore_backup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-45fb49e9-de41-3f4b-8ef4-9479afa25bd5(2).png)
6. Click the **Restore Backup** button on the confirmation popup to restore the backup. The policies for that particular data system that were not included in the backup that you want to restore to, will be deactivated from the Policies page.

#### Policy Backup upon policy deletion

If you delete an active policy, the Policy Preview will be generated. Securiti will not delete the policy instantly, the policy will only delete the policy once you Accept the Preview for deletion.

![Delete_Policy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ccb4fc06-6f52-0d86-0158-170d241ce2a1(2).png)![Policy_preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-150e7650-4b63-9de0-b869-607808bbd18e(2).png)

Once you **Accept** the **Policy Preview**, the execution will start, and the policy will be deleted from the **Policies** page. Securiti automatically takes the backup for the policy. In the Backup Preview, you will not see any privilege rules, row filters, and masking applied on entities affected by the deleted policy, as there are no active privileges, filters, and masking conditions defined on these entities currently.
