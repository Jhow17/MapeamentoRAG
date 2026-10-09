---
title: "Acquire authentication credentials in Tableau Server"
slug: "acquire-authentication-credentials-in-tableau-server"
updated: 2026-06-20T10:59:32Z
published: 2026-06-20T10:59:32Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-tableau-server"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Tableau Server

> [!WARNING]
> **Important**
> 
> You must log in as Server Administrator with access to all sites you want to scan or we assume, you are the Site Administrator of all the sites you want to scan.

To obtain Credentials in Tableau Server:

1. Log in to Tableau Server with your admin email and password.
2. To generate an Authentication Token, do one of the following:
  - Create a "Personal Access Token" by clicking on **My Account Settings**.
    1. Give the Token a name, and click "Create new Token".

![give_name_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4bd27d8f-e05e-6c14-968a-7c7128bc7b6f(1).png)
    2. Click **Copy to clipboard**, as shown below.

![personal_token_created_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-85329136-a744-370c-aa9f-93d6599d2849(1).png)

The **Token Name** and **Token Secret** are copied to the clipboard.

> [!WARNING]
> **Important**
> 
> The personal access Token contains all the information on activating the Connector.
    3. Record the Token Name and Token Secret to use later.
3. Acquiring REST API version.

Use the matching procedure below for obtaining the REST API version for Tableau Server.
  1. On the Tableau dashboard, near the upper right corner of the page, select **Help (question mark icon) > About Tableau**.

![click_help.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-17dd14a7-2ca4-9628-9b31-6320d7e70209(1).png)
  2. On the following popup, it shows you the version of your Tableau Server.

Record the **Tableau Server Version** for later use.

![tableau_server_version.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5dfecd90-d014-e92d-5ab8-5c171474da97(1).png)
  3. Now use the following link to Match your version with the REST API version under the "Tableau Server versions and REST API versions" heading.

<[*https://help.tableau.com/current/api/rest_api/en-us/REST/rest_api_concepts_versions.htm*](https://help.tableau.com/current/api/rest_api/en-us/REST/rest_api_concepts_versions.htm)>

> [!NOTE]
> **Note**
> 
> *2.3* is the minimum REST API version required.
4. Proceed to [Connecting Tableau Server with Securiti](/latest/docs/connecting-tableau-server-with-securiti).
