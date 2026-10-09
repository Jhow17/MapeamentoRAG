---
title: "Acquire authentication credentials in Tableau Cloud"
slug: "acquire-authentication-credentials-in-tableau-cloud"
updated: 2026-06-20T10:54:56Z
published: 2026-06-20T10:54:56Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-tableau-cloud"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Tableau Cloud

1. Log in to Tableau with your email and password.
2. To generate an Authentication Token, do one of the following:
  - Make a post request with your login Credentials as basic auth to:

**/api/api-version/auth/signin**.

Tableau generates a Token in response. Record it to use later.
  - Create a "Personal Access Token" by clicking on **My Account Settings**.
    1. Give the Token a name, and click "Create new Token".

![give_name_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4bd27d8f-e05e-6c14-968a-7c7128bc7b6f.png)
    2. Click **Copy to clipboard**, as shown below.

![personal_token_created_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-85329136-a744-370c-aa9f-93d6599d2849.png)

The **Token Name** and **Token Secret** are copied to the clipboard.

> [!WARNING]
> **Important**
> 
> The personal access Token contains all the information on activating the Connector.
    3. Record the Token Name and Token Secret to use later.
    4. **Site Name** is entered at the time of sign up and is the part of your base URL, present right after "/site/<site_name>".

Record the site name to use later. See the example below.

*https://prod-apnortheast-a.online.tableau.com/#/site/****securiti_site****/home*.
    5. In response, a Token is returned. Record the Token to use later. ![request_body_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eaa8cf05-d02e-cb9e-cb07-da17b8e81500.png)
    6. **Pod Name** is required and is part of your base URL (present right before online.tableau.com) as shown.

*https://****prod-apnortheast-a****.online.tableau.com/#/site/securiti_site/home*

Record it to use later.
3. Proceed to [Connecting Tableau Cloud with Securiti](/latest/docs/connecting-tableau-cloud-with-securiti).
