---
title: "Register an application in Hubspot"
slug: "register-an-application-in-hubspot"
updated: 2026-07-09T06:01:11Z
published: 2026-07-09T06:01:11Z
canonical: "helpcenter.securiti.ai/register-an-application-in-hubspot"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Register an application in Hubspot

1. Browse to the [Hubspot developer portal](https://app.hubspot.com/login) and log in with your Hubspot enterprise account Credentials.
2. On the Hubspot accounts page, choose the account on which you are registering the Securiti application.

![C00106.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2135da8d-0697-134f-bf61-39fb6959a24b.png)

Hubspot redirects you to the Developer Home page for that account.

> [!NOTE]
> **Note**
> 
> Based on your region, you can use these URLs in the redirect URL field.
> 
> - US Cloud: <[https://app.securiti.ai/static/activateConnector.html](https://app.securiti.ai/static/activateConnector.html)>
> - US1 Cloud: <[https://app1.securiti.ai/static/activateConnector.html](https://app1.securiti.ai/static/activateConnector.html)>
> - EU Cloud: <[https://app.eu.securiti.ai/static/activateConnector.html](https://app.eu.securiti.ai/static/activateConnector.html)>
> - Indonesia Cloud: <[https://app2.securiti.ai/static/activateConnector.html](https://app2.securiti.ai/static/activateConnector.html)>
3. On the menu bar near the top of the page, click **Apps**, then click **Create app** as shown below.

![C00107.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c17b395a-31ed-91a6-df62-fbdc7c372838.png)
4. On the Create app box apply the following settings, as shown below.

| Setting | Description |
| --- | --- |
| App name | Enter any convenient name for the app. We recommend you use the word "Securiti" in the app name to remind you that it is for the Securiti solution. |
| Application visibility | Mark the radio button for **Public**. |

![C00108.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-23dc5505-b1d7-6477-ffcb-995ae026b763.png)
5. Click **Create**.

Hubspot opens the Details page.
6. Enter the application details to suit, as shown below.

![C00109.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f15f7205-6cdd-16bd-0e00-250ece76ef9d.png)
7. Record the Client ID and Client Secret to use later.
8. Select scopes:
  1. On the developer portal, choose your app.

![choose_app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-39667bcd-1e2a-423d-d19b-441f30fd817f.png)
  2. Click the auth tab and mark the checkboxes for the following scopes.
    - automation
    - business-intelligence
    - content
    - crm.lists.read
    - crm.objects.companies.read
    - crm.objects.contacts.read
    - crm.objects.deals.read
    - crm.objects.owners.read
    - crm.schemas.companies.read
    - crm.schemas.contacts.read
    - crm.schemas.deals.read
    - files
    - forms
    - Integration-sync
    - social
9. Near the bottom of the page, click **Save**.
10. Proceed to [Connecting Hubspot with Securiti](/latest/docs/connecting-hubspot-with-securiti).
