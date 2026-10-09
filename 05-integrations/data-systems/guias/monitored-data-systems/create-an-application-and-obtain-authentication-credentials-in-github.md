---
title: "Create an application and obtain authentication credentials in GitHub"
slug: "create-an-application-and-obtain-authentication-credentials-in-github"
updated: 2026-07-20T21:00:00Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/create-an-application-and-obtain-authentication-credentials-in-github"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create an application and obtain authentication credentials in GitHub

GitHub uses the following parameters for connector activation.

| Parameter | Authentication Method |
| --- | --- |
| Client ID/App ID | - GitHub App - OAuth App |
| Client Secret | OAuth App |
| Private Key | GitHub App |
| Installation ID | GitHub App |

**GitHub App (recommended)**

Follow the steps mentioned below to acquire authentication credentials for GitHub app authentication method.

1. Log in to your [GitHub](https://github.com/join?plan=free&amp;ref_cta=Join%20for%20free&amp;ref_loc=cards&amp;ref_page=%2Ffeatures%2Fintegrations&amp;source=pricing-card-free) account.
2. On the top of the page, click **Settings,** as shown below:
  1. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-15 at 12.13.37 PM.png)
  2. On the left sidebar, click **Developer settings > GitHub Apps.**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-15 at 12.16.58 PM.png)
  3. On the **GitHub Apps** page, click **New GitHub App.**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-15 at 12.18.54 PM.png)
3. On your new **Create GitHub App** page, add the following parameters:
  - Enter a name for your GitHub app.
  - Enter the Homepage URL for your GitHub App.

For more information on creating an app, see [Registering a GitHub App](https://docs.github.com/en/apps/creating-github-apps/registering-a-github-app/registering-a-github-app).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-LE1XV1A1.png)
  - Under the **Permissions > Repository permissions**, give **Read-only** access to the following permissions.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-C0MBTQYA.png)
    - `Contents`
    - `Issues`
    - `Metadata`
    - `Pull requests`
4. Under the **Where can this GitHub App be installed**, select **Only on this account**.

> [!NOTE]
> Note
> 
> If you want to use this GitHub app for other accounts/organizations, select **Any account.**
5. Click **Create GitHub App.**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Y9P70KKL.png)
6. On top of the page, click on the **Generate a private key** link to record the private key.
7. On the **General** tab, under the **About** section, copy the **Client ID**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-20 at 12.38.50 PM.png)
8. To install and configure the App for organization, open the **Install App** tab, and click **Install** ahead of your GitHub App that you configured earlier**.**

It opens Install <GitHub App> page.
  1. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-15 at 3.30.15 PM.png)
9. On the **Install <GitHub App>** page, mark the radio button for **All Repositories** in case you want to access all repositories. Or mark the radio button for **Only select repositories**, and select available repositories.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5SDG3FL9.png)
10. In the URI, Record the **Installation ID** for connector activation. See the example below:

For instance in the URI`Github.com/organizations/securiti-io/settings/installations/112233444`, the Installation ID will be **112233444**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-20 at 12.42.16 PM.png)

**OAuth App**

Follow the steps mentioned below to acquire authentication credentials for OAuth app authentication method.

1. Log in to your [GitHub](https://github.com/join?plan=free&amp;ref_cta=Join%20for%20free&amp;ref_loc=cards&amp;ref_page=%2Ffeatures%2Fintegrations&amp;source=pricing-card-free) account.
2. Create a "GitHub App Token" using the below procedure:
  1. On the top right of the page, click on your **profile menu >** **Settings**.

![step-2a-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7ab488e9-82fc-4bd1-28a5-85bbabb77885.png)
  2. On the left sidebar, click **Developer settings**.

![step-2b-gihub.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-967e4181-7f2b-6026-bcf0-f7e6cc01dd78.png)
  3. On the left sidebar, click **GitHub Apps**. Click **New GitHub App.**

![step-2c-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-58b65849-be1a-611c-0950-cc9364a75659.png)
3. On your new GitHub App page, enter the following values in the relevant fields:

![step-3a-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07bf041a-c0b0-2c4e-37f0-b1bddf4fcd81.png)

![step-3b-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bbdfea5d-51a2-e288-1991-1c688b0c2134.png)
  1. (Optional) Enter your GitHub App description.
  2. Add a Callback URL based on your Securitienvironment.
    - US Cloud: `https://app.securiti.ai/static/activateConnector.html`
    - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html`
    - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html`
    - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html`
    - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html`
    - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html`
    - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html`
    - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html`
    - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html`
    - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html`
    - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html`
  3. Under the **Where Can this GitHub App be installed**, mark the radio button for **Any account**.
  4. Click **Create GitHub App.**
4. On the **General** page, generate and record the following for later use:
  1. Click **Generate a new client secret**, and copy the "Client ID" and "Secret".

![step-4a-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a7d65c8a-6a5c-5e33-0fbb-863581a224b2.png)
  2. Scroll down to the bottom of the page, and click **Generate a private key**.

![step-4b-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-88255e13-3645-1b60-19c5-08ea1c729950.png)
5. On the left sidebar, click **Permissions & events**.
6. On the **Permissions & events** page, select Permissions for "Repository Permissions" and "Organization Permissions".
  1. From the **Repository Permissions** menu, select **Read-only** access for "Contents", "Issues", Metadata", and "Pull requests."

![step-6a-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9f9ae75d-51a1-5dba-4fd9-cc218238b3bc.png)

![step-6a1-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8f0b4707-9b58-36e8-d363-5447efe60906.png)![step-6a2-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c165da1a-da05-f58a-1b6d-df2e6042a2a1.png)
  2. From the **Organization Permissions** menu, select **Read-only** access for "Members."

![step-6b-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-071ea675-2014-b801-e4ab-bbff20eec480.png)
  3. Click **Save changes**.
7. Install and configure the App for an organization:
  1. On the left sidebar, click **Install App**.

![Step-7a-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2c01b280-76b7-52ff-351b-fad57e922b92.png)
  2. From the organization's list, click **Install**.
  3. Mark the radio button for **All Repositories** in case you want to access all repositories. Or mark the radio button for **Only select repositories**, and select available repositories.

![Step-7b-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-64cca5a3-16be-1412-18f9-ea16d5757b58.png)
  4. Under the Organization setting on the left sidebar, click **GitHub Apps**.
  5. Click **Configure** and accept the required Permissions.

![step-7c-github.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1761ba02-fdf5-4619-d776-0c61c84f7f1d.png)

Proceed to [Connecting GitHub with Securiti](/latest/docs/connecting-github-with-securiti).
