---
title: "Obtain credentials in NetSuite (Securiti-Cloud) for OAuth 2.0 authentication"
slug: "obtain-credentials-in-netsuite-securiti-cloud-for-oauth-2-0-authentication"
updated: 2026-07-01T03:47:34Z
published: 2026-07-01T03:47:34Z
canonical: "helpcenter.securiti.ai/obtain-credentials-in-netsuite-securiti-cloud-for-oauth-2-0-authentication"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials in NetSuite (Securiti-Cloud) for OAuth 2.0 authentication

You can use the OAuth 2.0 Authentication method in NetSuite data system Securiti-Cloud connector for its activation. Securiti requires you to enter these parameters at the time of connector activation:

- **Consumer Key**
- **Private Key**
- **Certificate ID**

Use the matching procedure below.

> [!WARNING]
> **Important**
> 
> Before proceeding, ensure you are an administrator for your NetSuite account.

### Steps to record Consumer Key

1. On the Oracle NetSuite dashboard, click **Setup**.
2. In the left sidebar, under the Setup Tasks section, select **Company > Enable Features**.

![Step_1.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4bb94636-b857-6359-6d98-76b982616285.jpeg)
3. > [!NOTE]
> **Note**
> 
> You can add these Permissions to a specific user role.
  - On the following page, click the **SuiteCloud** tab. Near the bottom of the page, in SuiteTalk (Web service), mark the checkbox for **<*Rest Web Services*>** - used for SuiteQL Schema.

![Step_2.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-727def80-8f2e-4ce7-e981-4851f724046b.jpeg)

![Step_3.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-53fba065-a771-0e2f-63d0-5accfbd00e33.jpeg)
  - Similarly, in Manage Authentication, mark the checkbox for **<*OAuth 2.0*>**.

![Step_4A.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a1a0085a-0991-1b64-544d-c670ecab840d.jpeg)

![Step_4B.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be29bec1-4154-b478-132c-e3ff3ac81d5d.jpeg)
4. After enabling Permissions, select **User/Roles > Manage Roles**.

![Step_5.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7b41cf74-3544-eab5-8191-2d4652948428.jpeg)
5. On the Manage Roles page, click the user role (Buyer, CEO, Consultant, etc.) you want for connector activation and Data scan (we recommend the user with admin access).

![Step_6.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5cd3f75a-1397-6f2f-e016-67ea0e346b3f.jpeg)
6. Under Role, click **Edit**.

![Step_7.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-451538ca-8cdd-3746-3e3b-3e6e09f2300b.jpeg)

Near the bottom of the page, select **Permissions > Setup** tab. Click **Edit** and grant **<*Full*>** level OAuth 2.0 Permissions to these user roles, as shown below.
  - **Log in using OAuth 2.0 Access Tokens**
  - **Rest Web Services**
  - **OAuth 2.0 Authorized Applications Management**
  - **Integration Application**

![Step_9.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-82985246-1c4f-a72e-4b9c-898a613d9228.jpeg)
7. After granting Permissions, NetSuite requires you to create Integration Record.

On the dashboard, click **Setup**, and under Setup Tasks, select **Integration > Manage Integrations**.
8. Click **New** to create new Integration, AKA "OAuth application."

![Step_10.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a44207bd-8fda-00a4-9615-283172523286.jpeg)
9. Under the **Integration** section, enter a **Name** and select **State** for your application.
10. Under the **OAuth 2.0** section, enable the following to support OAuth 2.0 Authentication:

Click **Save**
  - **Authorization Code Grant**
  - **Client Credentials**
  - **Rest Web Services**
  - **Redirect URI**: Add your Securiti URI according to your tenant’s region. See the example below:

`https://app.securiti.ai/static/activateConnector.html`

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-24 at 11.34.56 AM.png)
11. On the following page, under the Client Credentials section, record the **Consumer Key/****Client ID**, and **Consumer Secret/Client Secret.**

![Step_12.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08f6cd0b-1bf9-796b-28e0-459d276ccb80.jpeg)

### Generate the Public Certificate and Private Key

- Next, to configure the OAuth 2.0 setup, generate the Public Certificate and Private Key as follows:
  1. Open your machine's terminal (console) and enter the following command.

> Note
> 
> We recommend using OpenSSL to generate the Certificate and key.

```plaintext
openssl req -x509 -newkey rsa:4096 -sha256 -keyout private-auth-key.pem -out public-auth-cert.pem -nodes -days 730
```
  2. The command, upon execution, asks you to enter information about these parameters:

> Important
> 
> You must enter a value for each parameter and not leave it empty. These values must be unique for generating the Certificate and key on every OAuth 2.0 Client Credentials setup. The generated Certificate and key won’t be unique if the parameters are not unique.
    1. **Country Name** (e.g., *2-letter code = US*)
    2. **State or Province Name** (e.g., *full name = New York*)
    3. **Locality Name** (e.g., *city = New York*)
    4. **Organization Name** (e.g., *company = ABC*)
    5. **Organizational Unit Name** (e.g., *section = XYZ*)
    6. **Common Name** (e.g., *fully qualified hostname = www.NetSuite.com*)
    7. **Email Address** (e.g., *abc.xyz@NetSuite.com*)

![command_parameters.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e6c466c7-608f-1ea1-2fd0-b41c65238b49.png)
  3. Public Certificate and Private Key are generated at the same path you have opened in the terminal once you supply the information to the above parameters. For example:

```plaintext
/users/john.doe/certificate/

public-auth-cert.pem
private-auth-key.pem
```

Record the **Private Key** for later use.

> [!NOTE]
> Note
> 
> Both Certificate and key have a validity of two years.

### Steps to record Certificate ID

1. > [!WARNING]
> **Important**
> 
> After you have generated the Public Certificate and Private key, ensure you log into the NetSuite account with the user that has the role already assigned, as outlined in the steps above.

Return to Setup Manager, and select **Integration > OAuth 2.0 Client Credentials (M2M) setup**.

![Step_17.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ce947ded-1d99-3bc0-c027-3e77c15e836e.jpeg)
2. > [!WARNING]
> **Important**
> 
> Entity (User account) and Role (Role associated with the user account) are linked with the company data you want to access.

Click **Create New** and enter the following information in the dialog box.

![Step_18.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-240e956c-87a1-33d0-7b8d-64ee1f1048b3.jpeg)
  - **Entity (User account)**
  - **Role (Role associated with the user account)**
  - **Application (Integration Record)**
  - **Certificate (Public Certificate)**

> [!WARNING]
> **Warning**
> 
> You can only use one Certificate for one combination of Integration records, roles, and entities. If you want to use the same Integration record for multiple entities or roles, you must use a different Certificate for each combination.

![Step_19.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a53e65ff-cc93-e370-682e-4a1156cc3f39.jpeg)
3. Click **Save**, and NetSuite creates the mapping needed to activate the connector in Securiti. Record the **Certificate ID**, which is displayed afterward for later use.

![Step_20.jpeg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eebb9e84-d48f-b124-e753-6b0779302851.jpeg)
4. Activate the [Connecting NetSuite (Securiti-Cloud) with Securiti](/latest/docs/connecting-netsuite-securiti-cloud-with-securiti).
