---
title: "Prerequisites for Airtable connectors"
slug: "prerequisites-for-airtable-connectors"
updated: 2026-07-04T22:11:06Z
published: 2026-07-04T22:11:06Z
canonical: "helpcenter.securiti.ai/prerequisites-for-airtable-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Airtable connectors

> [!NOTE]
> **Note**
> 
> Airtable no longer supports authentication via API keys. Personal Access Token (PAT) method is used for authenticating the data system.

### Using PAT authentication

Follow the matching procedure below to generate Personal Access Token (PAT) in Airtable.

1. Log in to [Airtable](https://airtable.com/login) and click on your user profile. Select **Developer hub** from the menu.

![airtable_console.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b3a74556-e0c4-24d6-388d-202eaa5eb418.png)
2. From the left navigation bar, under the **Developers** tab, click **Personal access tokens**.
3. Near the upper right corner of the page, click **Create new token**.

![airtable_PAT.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-785cc857-30f2-41c8-b9b9-60e799dbcbae.png)
4. In the create token modal, enter your token name and in the **Scopes** section, select the following scopes based on your connector type:
  - For Securiti Cloud connector, select the `data.records:write` scope, as shown below.

![airtable_createPAT.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cd5406af-b591-e67c-8ba6-31ffc3b5bacf.png)
  - For a self-hosted schema-driven connector, select the following scopes:
    - `data.records:read`
    - `data.recordComments:read`
    - `schema.bases:read`
5. In the **Access** section, the bases or workspaces that the token can access. You can choose from the following options:
  - A specific base or multiple bases across different workspaces.
  - All current and future bases in your workspace.
6. Click **Create token**.
7. On the popup, copy and save the token to use later.

#### Acquiring Base ID and name

Follow the procedure below to obtain **Base ID** and **Base name**:

1. On the Account overview page, click **Airtable API**.

![airtable_api_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52ad6835-d625-2542-266d-822c50e0d63e.png)
2. Under **Standard API**, select a base for its Base ID. In this example, it is "Product Launch".

![standard_api_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1b3447f4-7d0a-68a4-ab24-3eb0410468c9.png)

It can be found in the introduction text of the selected base as shown.

![base_id_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7c6f8932-0b0c-6549-987d-0407f2be5ce4.png)

It is also the value between / / and looks like apphXmBxHuxynZ2Kf in the URL.

#### Acquiring Tables

> [!NOTE]
> **Note**
> 
> This procedure is not applicable for the self-hosted connector. **Tables** are required for authenticating Airtable (Securiti Cloud) connector only.

Follow the procedure below to obtain the **Tables**:

1. On the Bases page, select the base which you did for acquiring Base ID. In this example, it is "Product Launch".

![workspace_1_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-677e662d-6ce4-351d-6d90-a943302353cd.png)
2. Record the "Table tabs" for the selected base. You must enter them in the Tables field when you activate Airtable.

![table_names_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ef1dc43a-738c-299e-76c5-4d563b49a91e.png)
