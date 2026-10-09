---
title: "Microsoft 365 Calendar"
slug: "microsoft-365-calendar-connectors"
status: "update"
updated: 2026-06-23T06:47:41Z
published: 2026-06-23T06:47:54Z
canonical: "helpcenter.securiti.ai/microsoft-365-calendar-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft 365 Calendar

> [!WARNING]
> Important
> 
> Securiti scans M356 Calendar data as far back as four years, but if you schedule a rescan, it assigns the events between the current date and the date you performed the last scan. However, if no last scan date exists, Securiti reverts to the default, i.e., four years.
> 
> Furthermore, Securiti scans new events based on the above scenario and does not support delta scan in M365 Calendar.

Microsoft 365 Calendar is a cloud-based scheduling tool that lets you manage appointments, meetings, and events across your organization. It is part of the Microsoft 365 suite, offering integration with other Microsoft services such as Outlook, Teams, and OneDrive. You can create, edit, and share calendars, schedule appointments, set reminders, and collaborate on events. Microsoft 365 Calendar falls under the category of monitored, unstructured data systems. For more information, see [data systems classification](/v1/docs/managing-data-system-connectors).

Prerequisites:

- You must hold the Admin role in Securiti.
- You must be an admin for your Microsoft 365 account.

### Configuring the application secret

1. In the Manage area of the navigation pane for the connector page, click **Certificates and Secrets** as shown below.

![secret1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cac12a5a-df19-152e-cace-4e198e0a1880.png)
2. In the Client Secrets area, click **+ New client secret**.

![secret2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f1cc5995-94d6-8aad-838a-9e17aad0cc28.png)
3. Enter a description for the secret, for example “Securiti Connector for OneDrive”, and choose an expiration term. We recommend one year.

![secret3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5311845c-256e-24f8-5873-537d0ae0eeee.png)
4. Click **Add** to add the secret to the list.
5. Next to the new client secret, click **Copy to Clipboard** as shown below.

![secret4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-77b5eb61-6f91-2506-360e-2be3a7a1537f.png)
6. Record the client secret so that you can use it when you create an Microsoft 365 Instance in Securiti.
7. Proceed to [Configuring Graph API permissions](/v1/docs/configuring-an-application-in-azure)

### Configuring Graph API permissions

1. In the Manage area of the navigation pane for the connector page, click **API permissions** as shown below.

![graph_api_permissions1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f1af5b5d-1b1a-de0b-b8ec-ca6997f3a203.png)
2. On the API permissions page, click **Add a permission**.

![graph_api_permissions2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba425a80-9b45-943d-3f39-b616407b175d.png)
3. On the Request API permissions page, click **Microsoft Graph**.

![graph_API_permissions3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b085b423-b306-b40d-3f98-b9a0c5c0ee45.png)
4. Click **Application Permissions**.

![graph_API_permissions4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3bdf84c3-5246-5a7d-a96d-61ca78cf080f.png)
5. On the Select Permissions page for Microsoft Graph, expand the various areas and mark the checkboxes for the following permissions for the Microsoft 365 Outlook connector:

![graph_api_permissions5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-56411554-2610-e08b-384d-c625d248926f.png)
  - Directory.Read.All
  - Calendars.Read
  - User.Read.All
6. Near the bottom of the Request API permissions box, click **Add permissions**.

### Granting consent for the application

1. Near the bottom of the API permissions page for the Securiti connector, click **Grant admin consent for *<organization>***.

![grant_consent1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff546e2e-c050-5cfa-6c84-886d5c21ceee.png)
2. Click **Yes** to confirm as shown below.

![grant_consent2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-75515a42-5e93-c6e8-eb30-914144473e08.png)

The API permissions page appears similar to that shown below.

![outlook-permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f97bbf32-4131-f953-b82a-cc43eb5907fe.png)
3. Click **Overview** to review the application registration. It should look similar to the example below.

![grant_consent4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-09ea4909-6cb5-354a-0524-e3003e32c36d.png)

Perform the following procedures for Microsoft 365 Calendar (Securiti-Cloud) connector:

1. [Configuring an application in Azure](/v1/docs/configuring-an-application-in-azure):
  1. [Registering an application in Azure](/latest/docs/registering-an-application-in-azure).
  2. [Configuring the application secret](/v1/docs/configuring-an-application-in-azure).
  3. [Configuring Graph API permissions](/v1/docs/configuring-an-application-in-azure).
  4. [Granting consent for the application](/v1/docs/configuring-an-application-in-azure).
2. [Connecting Microsoft 365 Calendar with Securiti](/latest/docs/new-ui-connecting-microsoft-365-calendar-securiti-hosted-with-securiti)
3. [Configuring General permissions for Microsoft 365 Calendar](/latest/docs/configuring-general-permissions-for-microsoft-365-calendar)

**Additional resources**

- [Troubleshooting for Microsoft 365 Calendar](/latest/docs/troubleshooting).
