---
title: "Create an application and obtain authentication credentials in GitLab"
slug: "create-an-application-and-obtain-authentication-credentials-in-gitlab"
updated: 2025-10-31T07:40:40Z
published: 2025-11-03T06:14:44Z
canonical: "helpcenter.securiti.ai/create-an-application-and-obtain-authentication-credentials-in-gitlab"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create an application and obtain authentication credentials in GitLab

The minimum permission required for GitLab is **read_api (Read API)** to run discovery, inventory, and entitlement scans.

> [!NOTE]
> **Note**
> 
> For Genstack Entitlement Scan, the user email must be publicly accessible. If the email visibility is set to 'Do not show on profile,' entitlement resolution does not function as expected.

Use the matching procedure below to acquire the Credentials.

1. Log in to your [GitLab](https://gitlab.com/users/sign_in) account.
2. On the top right corner of the left sidebar, click on your **User Profile** icon and select **Preferences** from the menu.

![step-2-lab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3e622c11-fb35-3110-fbd3-d6e5a1ec0133.png)
3. On the left sidebar under **User settings**, click **Applications**.

![step-3-lab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-189f3bf8-54c2-2266-0ec6-2ab6359461f8.png)
4. On the **Applications** page, click **Add new application**.

![step-4-lab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-38db0034-b9fa-7daf-ffd2-4bda574757cc.png)
5. On the **Add new application** page, configure the following information.

| Parameters | Description |
| --- | --- |
| Name | Enter a convenient name for the GitLab application. See the example below. *GitLab Connector* |
| Redirect URL | Add a Redirect URL based on your Securitienvironment. - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
| Scopes | Select **read_api** permission under the Scopes section. |

![step-5-lab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c51bb719-6a6c-27c4-4f6f-bd0e3b0b2507.png)
6. Scroll down and click **Save application**.

It redirects you to the newly created application screen.
7. Save the following information to use for Connector Activation:
  - **Application ID**
  - **Secret**.

![step-7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-222a6a46-16ee-78f9-9c36-26037e147649.png)

> [!NOTE]
> **Note**
> 
> You must copy the **Secret** instantly. It appears only once. You need to reconfigure the **Secret** if you move to another page.
8. Click **Continue** to close the page.
9. Proceed to [Activate the GitHub connector in Securiti](/v1/docs/activate-the-github-connector-in-securiti).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
