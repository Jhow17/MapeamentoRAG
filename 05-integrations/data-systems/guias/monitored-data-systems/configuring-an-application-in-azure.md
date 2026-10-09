---
title: "Configuring an application in Azure"
slug: "configuring-an-application-in-azure"
updated: 2026-10-01T10:35:26Z
published: 2026-10-01T10:35:26Z
canonical: "helpcenter.securiti.ai/configuring-an-application-in-azure"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring an application in Azure

Perform all the procedures in the subsections below to configure an Azure application for the Securiti Connector.

### Configuring the application secret

1. In the Manage area of the navigation pane for the connector page, click **Certificates and Secrets** as shown below.

![secret1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cac12a5a-df19-152e-cace-4e198e0a1880(1).png)
2. In the Client Secrets area, click **+ New client secret**.

![secret2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f1cc5995-94d6-8aad-838a-9e17aad0cc28(1).png)
3. Enter a description for the secret, for example “Securiti Connector for Calendar”, and choose an expiration term. We recommend one year.

![secret3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5311845c-256e-24f8-5873-537d0ae0eeee(1).png)
4. Click **Add** to add the secret to the list.
5. Next to the new client secret, click **Copy to Clipboard** as shown below.

![secret4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-77b5eb61-6f91-2506-360e-2be3a7a1537f(1).png)
6. Record the client secret so that you can use it when you create an Microsoft 365 Instance in Securiti.
7. Proceed to [Configuring Graph API permissions](/v1/docs/configuring-an-application-in-azure)

### Configuring Graph API permissions

1. In the Manage area of the navigation pane for the connector page, click **API Permissions** as shown below.

![graph_api_permissions1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f1af5b5d-1b1a-de0b-b8ec-ca6997f3a203(1).png)
2. On the API Permissions page, click **Add a permission**.

![graph_api_permissions2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba425a80-9b45-943d-3f39-b616407b175d(1).png)
3. On the Request API Permissions page, click **Microsoft Graph**.

![graph_API_permissions3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b085b423-b306-b40d-3f98-b9a0c5c0ee45(1).png)
4. Click **Application Permissions**.

![graph_API_permissions4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3bdf84c3-5246-5a7d-a96d-61ca78cf080f(1).png)
5. On the Select Permissions page for Microsoft Graph, expand the various areas and mark the checkboxes for the following Permissions for the Microsoft Calendar connector:

![graph_api_permissions5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-56411554-2610-e08b-384d-c625d248926f(1).png)
  - Directory.Read.All
  - Calendars.Read
  - User.Read.All
6. Near the bottom of the Request API Permissions box, click **Add Permissions**.

### Granting consent for the application

1. Near the bottom of the API Permissions page for the Securiti Connector, click **Grant admin consent for *<organization>***.

![grant_consent1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff546e2e-c050-5cfa-6c84-886d5c21ceee(1).png)
2. Click **Yes** to confirm as shown below.

![grant_consent2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-75515a42-5e93-c6e8-eb30-914144473e08(1).png)

The API Permissions page appears similar to that shown below.

![outlook-permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f97bbf32-4131-f953-b82a-cc43eb5907fe(1).png)
3. Click **Overview** to review the application registration. It should look similar to the example below.

![grant_consent4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-09ea4909-6cb5-354a-0524-e3003e32c36d(1).png)
4. Proceed to [Connecting Microsoft 365 Calendar with Securiti](/latest/docs/new-ui-connecting-microsoft-365-calendar-securiti-hosted-with-securiti).
