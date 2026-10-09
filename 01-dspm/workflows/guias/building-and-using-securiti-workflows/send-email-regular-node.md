---
title: "Send Email"
slug: "send-email-regular-node"
updated: 2026-02-12T15:17:27Z
published: 2026-02-12T15:17:27Z
canonical: "helpcenter.securiti.ai/send-email-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Send Email

The Send Email node sends an email to the specified email accounts provided. This node is typically connected in a Workflow such that on any event completed on the previous node, an email can be sent to a specific set of users. You can also use this node to send emails after specific intervals of time.

> [!NOTE]
> **Note**
> 
> Securiti currently only supports 3 legged **OAuth 2.0** or **Microsoft OAuth 2.0** for sending emails via SMTP protocol. You must select the credentials type from the menu first to select the authentication type to pass the credentials.

### Example use case

As an example use case, let’s create a Workflow where every time any [data map process](/document/preview/33279#UUID-a7c85e18-591b-04ea-9715-ff0de8af57ae) is modified in the data catalog, you can send an email to the administrator and alert them to the recent changes. This use case requires the following two nodes:Creating and editing processes

1. Data Maps trigger node
2. Send email node

#### Prerequisites

You must have valid SMTP credentials for your required authentication type i.e. OAuth 2.0 or basic authentication.

#### Sending email to the data process owner on every process update

1. Add the details in the Data Maps node as per your requirement. Refer to [Data Maps node reference](/v1/docs/data-maps) for details.
2. Fill in the fields in the **Send Email** node as per your requirement as shown below:

![Send-Email-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6be20acc-68ee-ecec-d778-3187d7dbb913.png)
3. Connect the nodes to execute the Workflow:

![Data-Maps-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e1a4e685-5912-67f5-29dd-47c023f71a80.png)
4. Execute the Workflow and on any event trigger, the Workflow node provides a successful response. Once the Workflow is successfully executed, you can view both table view and JSON response. This is how the success response looks like.

![Send-Email-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-357cdfba-4c9b-d439-876a-b1dbe62e8cc3.png)

### Node Configuration

#### Parameters

| Parameters |
| --- |
| SMTP/ SMTP OAuth 2.0 | Select the credentials from the drop down list. If you do not have a list, select the Create New option to create a set of credentials. See the [Setting up Credentials](/v1/docs/send-email) section to see the steps. |
| Credentials Type | Basic Authentication | Select this authentication type if you have user name and password to log into the email server. |
| OAuth2.0 | Select this authentication type if you have OAuth token (client secret, key) to log into the email server. |
| Custom SMTP (toggle) | Turn this toggle on if you want to send the email through your own email provider. Turn this toggle off to send email using Securiti Mail service. |
| From Email | Specify the email address using which you want to send the email. *This option will not be visible if custom SMTP toggle is off* |
| To Email | Specify the email address to which you want to send the email. |
| CC Email | Specify the email address of cc recipient. |
| BCC Email | Specify the email address of bcc recipient. |
| Subject | Specify the subject line of the email. |
| Send HTML (toggle) | Text | Turn the toggle on if you want to add email body in the form of HTML. |
| HTML | Turn the toggle off if you want to add email body in the form of text. |
| Attachments | Specify the name of the binary properties which contain data which should be added to the email as attachment. Add multiple values by comma separating their names. The maximum file size limit for an attachment is 10 MB. |
| Options | Ignore SSL Issues (toggle) | Enable this to connect even if SSL certificate validation is not possible. |

#### Set up credentials

Refer to this section to understand the authentication types and setting up credentials for all the authentication types.

#### Basic Authentication

Fill the following fields to set up the credentials for basic authentication type:

| Parameter | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself |
| User | Specify the email address of data subject's account, for example, johndoe@azure.com. |
| Password | Specify the password for the user account |
| Host | Specify the host name, for example, “smtp.office365.com”. |
| Port | Specify the active port number, for example, 587. > [!WARNING] > **Caution** > > If you are using port 587 or port 25, you must disable the SSL/TLS toggle. |
| SSL/TLS | Turn the toggle on if SSL/TLS is enabled on the account. |
| Nodes with access | Add the nodes who can access using the credentials and mark the checkbox to select them |

#### Auth2.0

Fill the following fields to set up the credentials for OAuth 2.0 authentication type:

| Parameter | Description |
| --- | --- |
| URL | Copy this callback URL to redirect your domain visitor to this URL. |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself |
| Scope | Specify the scope of the connection. For example: - https://outlook.office.com/Mail.Send - https://outlook.office.com/SMTP.Send - https://outlook.office.com/IMAP.AccessAsUser.All offline_access |
| User | Specify the email address of data subject's account, for example, johndoe@azure.com. |
| Host | Specify the host name, for example, “smtp.office365.com”. |
| Port | Specify the active port number, for example, 587 |
| Grant type | Specify the grant type from: - Authorization Code - Client Credentials |
| Authorization URL | Specify the URL to authorize the user, for example, https://login.microsoftonline.com/common/oauth2/v2.0/authorize |
| Access Token URL | Specify the access token URL to access the API, for example, https://login.microsoftonline.com/common/oauth2/v2.0/token |
| ClientID | Specify the client ID associated with the account. |
| ClientSecret | Specify the client secret associated with the account. |
| Auth URI Query Parameters | Specify any additional parameters that need to be set (if any) |
| Authentication | Body | Specify the credentials in body if selected |
| Header | Specify the credentials in header if selected |
| Nodes with access | Add the nodes who can access using the credentials and mark the checkbox to select them |

> [!NOTE]
> **Note**
> 
> Callback URL is updated for multiple-tenancy in Workflow. Now the host is specified as *wf-mt.ENV.xyz* in the callback URL.

### Setting up Microsoft account

To set up your Microsoft account to use SMTP:

1. Log in to your Microsoft account and navigate to the **Azure Active Directory**.
2. Navigate to the **App Registrations** and create a new registration.
3. Enter the app name and callback redirect URL. Copy this URL from **Create new credentials** section from the Securiti platform. The application is successfully created.
4. From the overview tab, collect the Client ID to use in the **ClientID** section in credentials.
5. Navigate to the certificates and secrets section and create a new client secret by adding a description and expiry. Copy this value to use in the **ClientSecret** section in credentials.
6. Navigate to the API permissions section and select Microsoft Graph. From the permissions, choose delegated permissions. Search for IMAP and mark the **Imap.AccessAsUser.All** checkbox. Similarly, search and add permissions for **SMTP.send** and **offline_access**.
