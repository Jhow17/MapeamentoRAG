---
title: "Keyrings"
slug: "managing-credentials-using-keyrings"
updated: 2026-09-22T03:45:17Z
published: 2026-09-22T03:45:17Z
canonical: "helpcenter.securiti.ai/managing-credentials-using-keyrings"
area: integrations
modulo: keyrings
tipo: guia
data_captura: 2026-10-08
---

# Keyrings

Keyrings in Securiti act as a secure pointer to a secret that is stored in an external credential vault, such as CyberArk or HashiCorp Vault. Instead of storing sensitive information like passwords, API keys, or client secrets directly in Securiti, a keyring stores the location, i.e, the path to that secret within your configured vault.

During a data system connector's authentication process in Securiti, you can choose to use keyrings to fetch credentials. Securiti uses the keyring to fetch the secret directly from your vault at runtime. The keyring itself does not contain the actual secret, ensuring your most sensitive credentials remain managed securely within your dedicated vault system.

## Roles and permissions

Securiti implements role-based access control on actions that can be performed for credential vaults and keyrings, such as keyring creation. For more information on roles and their permissions, see [Data Systems RBAC permissions](/v1/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-default-roles).

## Using the Keyrings dashboard

> [!WARNING]
> Important
> 
> If the new **Keyrings** UI is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

The **Keyrings** dashboard in **Integrations** lets you create, manage, and monitor credentials used by your data system connectors. You can view vault types, associated data systems, and the number of connectors attached to each keyring.

To access the **Keyrings** dashboard:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon, and choose **Integrations** from the left navigation bar.
2. From the left menu of the **Integrations** page, select **Keyrings**.

The dashboard displays a summary count and a table of all configured keyrings in your tenant. The page provides the following capabilities:

- A table view for all configured keyrings.
- Summary metric displayed at the top of the grid that show the total count for keyrings.
- A search bar to search keyrings by name.
- A top-level filter that lets you search keyrings by their name, ID, or vault type.
- A **Save View** button that lets you save the current filter and search combination as a named view.
- A **Saved Views** button that lets you apply a view you saved earlier.
- A **Column Selector** that lets you include or exclude specific columns, and rearrange their order for custom viewing. It also contains a **Restore Default** button that lets you reset the custom layout back to the original one.
- An **Add Keyrings** button at the upper right corner of the page to add new keyrings.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 10.51.56 AM.png)

### Understanding the table view

Each row in the table represents a single keyring instance. Key columns include:

| Column name | Description |
| --- | --- |
| Name | Displays the name assigned to the keyring. |
| Keyring ID | Displays the unique ID assigned to the keyring instance. |
| Vault Type | Displays the credential vault configured for the keyring, for example, HashiCorp. |
| Data System | Displays the data system associated with the keyring. |
| Connectors Attached | Displays the number of connectors currently using this keyring. |

> [!NOTE]
> Note
> 
> You can remove columns using the column selector. Securiti adds a horizontal scrollbar automatically as the number of columns increases.

### Filtering and searching keyrings

Use the search bar at the top of the grid to quickly locate keyrings by instance name or ID, as shown below.

![Integration settings showing CyberArk keyrings and search functionality for data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/keyringsnewUI_searchbar.png)

To narrow down the results, use the top-level filter to focus on keyrings associated with specific data systems or vaults, as shown below. You can select a single or multiple properties to filter the results.

![User interface displaying keyring integration options and vault types for data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/keyrings_newUI_filter.png)

The top-level filter supports filtering by the following properties:

| Property | Description |
| --- | --- |
| Name | Lets you filter by keyring names. |
| Keyring ID | Lets you filter by a specifying a keyring ID. |
| Vault Type | Lets you filter keyrings configured for a specific vault type, such as keyrings for HashiCorp vault only. |
| Connectors Attached | Lets you filter by the number of connectors attached to a keyring, such as keyrings with two connectors. |

#### Saving and reusing filter views

A saved view stores the filters and the search term you apply to the grid, under a name that you choose. Saving a view lets you return to a filter combination you use often, without building it again.

> [!NOTE]
> Note
> 
> The Save View option is disabled until you apply at least one filter or a search term.

**Saving a View**

1. To save a view, on the **Keyrings** page, apply the filters you want to reuse.
2. At the right end of the filter row, click **Save View**.
3. On the **Save View** popup, enter a **Group**, **Name**, and **Description** for the view and click Save, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 10.48.10 AM.png)

Securiti adds the view to the **Saved Views** list for the Keyrings page.

**Using a Saved View**

1. To apply a saved view, on the right end of the filter row for **Keyrings** page, click **Saved Views**.
2. On the **Saved Views**, click the view you want to apply.

Securiti loads the saved filters into the filter row, and the grid shows the matching connectors.
3. To view or delete a saved view, from the Saved Views list, click More Actions (three dots) for that view, then click Edit or Delete, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 10.55.58 AM.png)
