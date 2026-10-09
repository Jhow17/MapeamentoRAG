---
title: "Obtain authentication credentials using OAuth JWT authentication in ServiceNow Tables"
slug: "obtain-authentication-credentials-using-oauth-jwt-authentication-servicenow"
updated: 2026-09-21T10:20:00Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/obtain-authentication-credentials-using-oauth-jwt-authentication-servicenow"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain authentication credentials using OAuth JWT authentication in ServiceNow Tables

The ServiceNow Tables connector supports JWT authentication. With JWT, Securiti signs each token request with a private key instead of storing a password for the integration user. To set this up, you create a dedicated user in ServiceNow, upload the signing certificate, and register an OAuth application.

This topic covers the ServiceNow side of the configuration. When you finish, you have the values that the Securiti connector asks for.

> [!WARNING]
> Important
> 
> Before you proceed, make sure you must have the **admin** role in ServiceNow, so you can create users, certificates, and OAuth applications.

### Step 1 - Create a user and assign roles

Securiti authenticates as a single ServiceNow user. Create a dedicated user for the integration, rather than reusing a person's account.

1. Log in to your ServiceNow instance with an administrator account, and record the **Instance ID** in the URL. For example:

If the URL is `https://dev123456.service-now.com/now/...`, then the Instance ID will be `dev123456`.
2. Go to the **All** menu in the top-left corner of the interface, and type **User** in the search filter bar.
3. Expand the **User Administration** module, and click on **Users** to open the list of all user records, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-16 at 12.30.45 PM.png)
4. On the **Users** screen, near the upper right corner, click **New**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-16 at 12.37.02 PM.png)
5. On the **User New record** screen, complete the required parameters to create a user. For more information, see ServiceNow’s documentation on [Create a user](https://www.servicenow.com/docs/r/platform-administration/user-administration/t_CreateAUser.html).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-16 at 12.55.23 PM.png)
6. While completing the required parameters, record the **User ID** to be used later in the connector authentication.
7. After creating a user, open the relevant user. On the bottom of the screen, under **Roles** section, click **Edit** to assign the roles to the user.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-16 at 12.57.44 PM.png)
8. On the **User Role - Edit Members** screen, select the following from the collection and click Save, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-16 at 1.06.58 PM.png)
  - `itil`
  - `snc_platform_rest_api_access`

### Step 2 - Create the signing certificate

ServiceNow verifies the signature on each token request against a certificate that you upload. Generate a key pair first, then upload the public certificate and keep the private key for Securiti.

1. On your local machine, generate the key pair by running the following command:

```plaintext
openssl req -x509 -newkey rsa:2048 -keyout jwt_private_key.pem -out jwt_public_key.pem -nodes -days 365
```

> [!NOTE]
> Note
> 
> Keep the placeholders generic, for example a file name of servicenow_jwt rather than JWT_Public_Key.

After running the command, **Private key** and **Public key** will be created.
2. Record the Private Key as **.pem** file created to the be used later during Securiti connector authentication.
3. Once you have created the private key, Go to the **All** menu in the top-left corner of the interface.
4. In the **All** menu, search and select **System Definition >** **Certificates**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 9.13.14 AM.png)
5. On the **X.509 Certificates** screen, Click the **New** button, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 9.15.48 AM.png)
6. On the **X.509 Certificates - New Record** screen, fill in the basic record details, paste the **Public Key** certificate you created earlier in the **PEM Certificate** field, and click **Submit**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 9.21.30 AM.png)

For more information, see ServiceNow’s documentation on [Uploading a certificate to an instance](https://www.servicenow.com/docs/r/platform-security/t_UploadACertificateToAnInstance.html).

### Step 3 - Register the OAuth application

The OAuth application ties the certificate to the integration user, and produces the client credentials that Securiti uses.

1. In the ServiceNow admin portal, go to the **All** menu in the top-left corner of the interface.
2. In the **All** menu, search and select **System OAuth >** **Application Registry**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 9.33.35 AM.png)
3. On the **Application Registries** screen, on the top right corner click the **New** button, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 9.35.46 AM.png)

> [!NOTE]
> Note
> 
> Securiti recommends you to use the **New Inbound Integration Experience** to create the OAuth application.
4. After selecting **New Inbound Integration Experience**, you will be redirected to the **Machine Identity Console** screen.
5. On the top right corner on **Machine Identity Console** screen, click **New Integration**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 9.38.21 AM.png)
6. After clicking **New Integration**, you will prompted a **Select your application connection type** menu.
7. In the **Select your application connection type**, select OAuth - JWT bearer grant, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 9.41.15 AM.png)
8. On the **New Record** screen, enter the details for the JWT OAuth application, and select the OAuth scope as **useraccount**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EO2TECBD.png)![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 9.58.26 AM.png)
9. Record the **Client ID** and **Client Secret** to be used later during connector authentication.
10. After creating a JWT OAuth application, open the created app and click JWT verifier map, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 10.02.42 AM.png)
11. In the **JWT Verifier map** screen, enter the details and select the public X.509 Certificate in the **Sys certificate** dropdown, that you uploaded earlier.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-17 at 10.08.55 AM.png)

For more information, see ServiceNow’s documentation on [Create an OAuth JWT API endpoint for external clients (machine to machine integration)](https://www.servicenow.com/docs/r/platform-security/authentication/create-jwt-endpoint.html).

Proceed to [Connecting ServiceNow Tables with Securiti](/latest/docs/connecting-servicenow-tables-with-securiti).
