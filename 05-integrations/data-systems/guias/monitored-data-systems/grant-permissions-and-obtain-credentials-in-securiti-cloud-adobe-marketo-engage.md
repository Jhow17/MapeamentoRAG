---
title: "Grant permissions and obtain credentials in Adobe Marketo Engage (Securiti-Cloud)"
slug: "grant-permissions-and-obtain-credentials-in-securiti-cloud-adobe-marketo-engage"
updated: 2026-07-17T04:38:43Z
published: 2026-07-17T04:38:43Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-securiti-cloud-adobe-marketo-engage"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Adobe Marketo Engage (Securiti-Cloud)

The API token is linked to the company data you seek access to. It authorizes data retrieval. Follow these steps to acquire an API access token:

1. Log in to your instance and go to the **Admin** menu on the top left.

![marketo_admin.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-27237563-49aa-a6d0-2608-f1491247b77a.jpg)
2. Click **User and Roles** as shown below.
3. Click **Roles > New Role**.

![marketo_newrole.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-84665e2e-7efa-1548-3f98-281707b02f95.jpg)
4. Enter a Role name.
5. Select **Access API** and mark the checkboxes for the following minimum permissions:

![marketo_accessapi.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-59decd0a-be82-6006-f585-3efec5e6a6bb.png)
  - Read-Only Activity
  - Read-Write Activity
  - Read-Only Opportunity
  - Read-Write Opportunity
  - Read-Only Sales Person
  - Read-Write Sales Person
  - Read-Only Company
  - Read-Only Person
  - Read-Write Person
6. Click **Create**.
7. On your homepage, click the **Users** tab.
8. Click **Invite New User**.

![marketo_invitenewuser.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b040bc28-a0e9-9dd3-e90c-71a377141438.jpg)
9. Enter a descriptive user name for **API user** and an **Email Address**. Click **Next**.
10. Mark the **API Only** checkbox to award the user API role, then click **Next**.

![marketo_APIpermission.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6779b5a2-c59a-89f0-84df-59ca22b890ba.jpg)
11. Click **Send**
12. From the left **Admin** menu, under the **Integrations** section, select **LaunchPoint**.
13. From the upper left corner, select **New > New Service** and give it a descriptive name.

![marketo_newservice.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1fbbff66-e050-c1ec-e3d2-dedf7220f9d5.jpg)
14. In the **Service** field, select **Custom** from the menu and enter a description for it.
15. In the **API Only User** field, select your new user from the menu.

![marketo_selectnewuser.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-108c3cf5-387a-cc5c-793d-de652dd17960.jpg)
16. Click **Create**.
17. Click **View Details** to access the Client ID and Secret, then click the **Get Token** to generate an API access token.

![marketo_creds.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86fdc4fc-2b43-c51e-2e19-1767b481d4a2.jpg)
18. Record the token for later use.
19. To fetch the **Account (Domain)**:
  - In the **Admin** menu > **Web Services**.
  - Find the **Endpoint** in the **REST API** box.
  - Record the domain part of the **Endpoint** URL as shown below.

![marketo_domain.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1301a558-ca6e-37eb-0334-1d729f54164a.png)
20. Proceed to [Connecting the Adobe Marketo Engage connector with Securiti](/latest/docs/connecting-the-adobe-marketo-engage-securiti-cloud-connector-with-securiti).

## Related

- [Connecting the Adobe Marketo Engage (Securiti-Cloud) connector with Securiti](/connecting-the-adobe-marketo-engage-securiti-cloud-connector-with-securiti.md)
