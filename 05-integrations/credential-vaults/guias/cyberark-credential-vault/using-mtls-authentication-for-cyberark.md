---
title: "Using mTLS authentication for CyberArk"
slug: "using-mtls-authentication-for-cyberark"
updated: 2025-11-28T12:11:08Z
published: 2025-11-28T12:11:08Z
canonical: "helpcenter.securiti.ai/using-mtls-authentication-for-cyberark"
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# Using mTLS authentication for CyberArk

Mutual TLS (mTLS) authentication strengthens security for CyberArk Central Credential Provider (CCP) by requiring both the server and client to authenticate using certificates.

This ensures only trusted clients can connect, while protecting against credential theft and man-in-the-middle attacks.

> [!WARNING]
> Important
> 
> You must have a valid certificate installed on the Windows machine hosting CyberArk. The certificate must be trusted by Internet Information Services (IIS).

To enable mTLS authentication with CyberArk, you must follow the procedures below as prerequisites.

## 1. Configuring certificates in Internet Information Services (IIS)

To configure IIS to accept and map client certificates:

1. Open the Run dialog and type mmc. Click OK, as shown below to open the IIS window. ![Windows Run dialog box with 'mmc' typed in the input field.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberark_mmcrun.png)

1. In Microsoft Management Console (MMC), from the upper left corner of the window, select File and click Add or Remove Snap-ins.
2. On the Add or Remove Snap-ins popup, from the left menu, select Certificates, as shown below.

![The image shows the 'Add or Remove Snap-ins' window with highlighted 'Certificates' option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberark_certificatesnapin.png)
3. Click OK.
4. In Certificates snap-in popup, select Computer account radio button and click Next, as shown below.

![Options for managing certificates in the Certificates snap-in interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberark_computeraccountsnapin.png)
5. Next, select **Local Computer** and click **Finish**.
6. In the IIM console, click **OK** to add the certificates node to the IIM console.
7. From the left menu, expand and right-click the **Certificates (Local Computer)**. Select **All Tasks > Import**, as shown below. Follow the wizard to select and import the client certificate.

![Menu options for managing certificates in the Local Computer console interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberark_importcert.png)

This step ensures that the certificate is authorized to access the VM using the IIS.

## 2. Enabling IIS certificate authentication for CyberArk

You must install some features and roles in the CyberArk server manager, to use certificate-based authentication. Follow the steps below to enable IIS certificate authentication in CyberArk server manager.

  

1. In CyberArk, open the server manager.
2. From the server manager dashboard, select Add roles and features, as shown below.

![Server Manager dashboard showing options to configure the local server and add features.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberark_servermanager_addroles.png)
3. In the wizard, select Role-based or Feature-based installation and click Next. Select the server where the certificate-based authentication needs to be enabled.
4. In Web Server (IIS)> Web Server, from the left menu, select Server Roles.
5. In the right pane, under the Security section, ensure IIS Client Certificate Mapping Authentication is installed, as shown below.

![Selecting IIS Client Certificate Mapping Authentication in the server roles installation wizard.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberark_iisroleinstalled.png)

In case it is not installed, follow the steps on screen to install it.

This setting enables IIS to request and validate client certificates and map them for access control.
6. In Server Manager dashboard, from the upper right corner of the page, select Tools and click Internet Information Services (IIS) Manager from the menu to open the IIS Manager, as shown below.

![Server Manager dashboard displaying tools and configuration options for local server management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberakr_issmanager.png)
7. In IIS Manager select COMPONENTS > Sites > Default Web Site > AIMWebService. Then select Authentication and ensure that Anonymous Authentication is enabled.

> [!NOTE]
> Note
> 
> This step ensures the CCP site stays accessible while you configure and test client certificate authentication.

1. In the **AIMWebService Home** window select SSL Settings and select one of the following options:
  - Accept: Selecting this option causes CyberArk to enable non certificate-based authentication, and let both mTLS and non-mTLS callers. However, certificates are accepted if presented.
  - Require: Selecting this option causes CyberArk to require a certificate for SSL or TLS authentication. Require enforces mTLS for all requests.

![IIS Manager interface showing AIMWebService and SSL Settings options highlighted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberark_sslsettingsbutton.png)
2. In the **AIMWebService Home** window select Configuration Editor. In the new window, select system.webServer > security > authentication > iisClientCertificateMappingAuthentication from the folders, as shown below.

![IIS Manager configuration editor showing authentication settings for Default Web Site.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberark_issmappingfeature.png)

iisClientCertificateMappingAuthentication is an IIS feature that maps client certificates to authenticated identities based on defined certificate rules.
3. In the settings, set enabled to true.

This setting enables IIS to evaluate and apply mapping rules to the presented certificate.
4. Click manyToOneMappings, and in the right panel, click Add to add a new mapping rule and in the new window, in right panel, set fields, as shown below:
  - `certificateField` = Issuer
  - `certificateSubField` = CN
  - `matchCriteria`= <Your-CA-Issuer-Name>
  - `compareCaseSensitive` = True or False
  - `permissionMode` = Allow
  - Leave `userName/password` blank as you are authorizing by certificate instead of basic authentication.

The changes are auto-saved, and both preceding screens can be closed.

> [!NOTE]
> Note
> 
> This step ensures that CyberArk only passes IIS-approved or trusted certificates to the next authentication phase when they meet the matching criteria. If a certificate does not match, the request fails with an error.

![IIS Manager configuration showing manyToOneMappings settings for AIMWebService.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberark_manytoonemappings.png)

![Collection Editor interface displaying user authentication properties and settings for configuration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberark_rulemappings.png)

![Collection Editor interface displaying certificate field properties and entry path settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberark_matchcriteria.png)

## 3. Configuring CCP for certificate authentication

To configure CCP for certificate authentication:

1. Execute the below command to generate the certificate serial number.

`openssl x509 -in certificate.crt -serial -noout`

Record the serial number (SN) to use later.

1. Log in to the CyberArk CCP administration and select the application for which certificate authentication is required.
2. For the selected application, in the right window, in the Authentication tab click Add and select Certificate Serial Number.
3. In the dialog box, enter the serial number (SN) that you recorded from the above command and click Add.

![Application details for security certificate with fields for authentication and serial number.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cyberark_SNnumber.png)

## 4. Placing certificate file and key in Securiti pod

To place your certificate and private key file in pod:

1. In Securiti, from the left menu, click Settings. From the left menu, select go to Integrations > Credentials > Credential Vaults.

![Dashboard displaying security findings, data posture score, and settings options for management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/settings_nav(1).png)

![List of credential vaults with instance counts for various integrations displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/credentialvaults_nav.png)
2. From the list of available credential vaults, locate the card for CyberArk and near the upper right corner, click + to create instance. Or open an existing instance if created already.

![List of credential vaults with instance counts and options to view instances.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/settings_createcyberarkinst.png)
3. Record the CyberArk instance ID from the URL.

In the example URL below, the vault instance ID is "12201"

`https://test.securiti.com/#/settings/credential-vaults?inst=12201&amp;tab=BASIC_INFORMATION`
4. In the `securitictl` utility, on your `appliance-config-controlle`r pod, run the following command in CLI:

`securitictl configure-vault-secret`

Select CyberArk from the vault types, and enter the vault instance ID you recorded earlier.
5. In the text editor, enter private key and certificate details as PEM format and save it.

> [!NOTE]
> Note
> 
> Use the keyboard commands to save the credential file information and exit from the editor. Commands can vary depending on the operating system you are using.
6. Proceed to [configuring CyberArk vault instance in Securiti](/v1/docs/cyberark-credential-vault-1)
