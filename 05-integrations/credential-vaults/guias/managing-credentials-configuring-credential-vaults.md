---
title: "Credential vaults"
slug: "managing-credentials-configuring-credential-vaults"
updated: 2026-09-22T03:45:28Z
published: 2026-09-22T03:45:28Z
canonical: "helpcenter.securiti.ai/managing-credentials-configuring-credential-vaults"
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# Credential vaults

Securiti supports credential vaults that you can use to manage privileged account access and SSH keys for data systems that you integrate with Securiti.

> [!WARNING]
> **Important**
> 
> - If the Credential Vaults feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.
> - Securiti does not let you view sensitive information in the credential vaults with the User role account.

## Roles and permissions

Securiti implements role-based access control on actions that can be performed for credential vaults and keyrings, such as keyring creation. For more information on roles and their permissions, see [Data Systems RBAC permissions](/v1/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-default-roles).

## Using the Credential Vaults dashboard

The **Credential Vaults** dashboard in **Integrations** lets you view, manage, and monitor all configured credential vault integrations in your tenant. You can add new vaults, track their status, and review ownership details from a single interface.

Credential vaults store and manage secrets that Securiti uses to authenticate connectors and integrations securely.

To access the **Credential Vaults** dashboard:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon, and choose **Integrations** from the left navigation bar.
2. From the left menu of the **Integrations** page, select **Credential Vaults**.

The dashboard displays a summary count and a table of all configured credential vaults in your tenant. The page provides the following capabilities:

- A table view for all configured vaults.
- Summary metrics displayed at the top of the grid that show the total count for **Configured Connectors** and **Active Connectors**
- A search bar to search credential vaults by name or vault type.
- A top-level filter that lets you search vaults by their status or vault type.
- A **Save View** button that lets you save the current filter and search combination as a named view.
- A **Saved Views** button that lets you apply a view you saved earlier.
- A **Column Selector** that lets you include or exclude specific columns, and rearrange their order for custom viewing. It also contains a **Restore Default** button that lets you reset the custom layout back to the original one.
- An **Add Integration** button at the upper right corner of the page to add new vault instances.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 11.03.04 AM.png)

### Understanding the table view

Each row in the table represents a single vault instance. Key columns include:

| Column name | Description |
| --- | --- |
| Instance Name | Displays the name assigned to the vault instance or connector. |
| Status | Displays the connector status for the vault instance. |
| Vault Type | Displays the type of credential vault configured, for example, HashiCorp. |
| Owner | Displays the owner associated with the vault instance creation. |

> [!NOTE]
> Note
> 
> You can remove columns using the column selector. Securiti adds a horizontal scrollbar automatically as the number of columns increases.

### Filtering and searching vaults

Use the search bar at the top of the grid to quickly locate vaults by instance name or vault type, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 11.03.39 AM.png)

To narrow down the results, use the top-level filter to focus on specific vault type or filter them by status.

![Integration settings showing filter options and vault types for credential management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/vaults_newUI_toplevelfilter.png)

The top-level filter supports filtering by the following properties:

| Property | Description |
| --- | --- |
| Status | Lets you filter by active or inactive states of a connector. |
| Vault Type | Lets you filter vault instances configured for a specific vault type, such as HashiCorp vault instances only. |

#### Saving and reusing filter views

A saved view stores the filters and the search term you apply to the grid, under a name that you choose. Saving a view lets you return to a filter combination you use often, without building it again.

> [!NOTE]
> Note
> 
> The Save View option is disabled until you apply at least one filter or a search term.

**Saving a View**

1. To save a view, on the **Credentials Vaults** page, apply the filters you want to reuse.
2. At the right end of the filter row, click **Save View**.
3. On the **Save View** popup, enter a **Group**, **Name**, and **Description** for the view and click Save, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 11.15.25 AM.png)

Securiti adds the view to the **Saved Views** list for the Credentials Vaults page.

**Using a Saved View**

1. To apply a saved view, on the right end of the filter row for **Credentials Vaults** page, click **Saved Views**.
2. On the **Saved Views**, click the view you want to apply.

Securiti loads the saved filters into the filter row, and the grid shows the matching connectors.
3. To view or delete a saved view, from the Saved Views list, click More Actions (three dots) for that view, then click Edit or Delete, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 10.55.58 AM.png)

## Adding a credential vault instance

To add a credential vault instance in Securiti:

1. From the upper right corner of the page, click **Add Integration.**
2. Select your credential vault from the catalog of available credential vaults, as shown below. You can browse through the catalog or search for a specific credential vault.

![Integration options for various credential vaults displayed in a grid layout.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/vaults_catalog.png)
3. In the **Basic Information** tab, provide the instance name, description, and hosting location details, as shown below.

![AWS Secret Manager settings page showing instance name and location details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/vaults_basicinfotab.png)
4. In the **Authentication** tab, configure the following:
  1. In the **Pod Configuration** section, select a pod from the menu. You can select the pod(s) where a vault authenticates, as shown below.

> [!NOTE]
> Note
> 
> - Securiti authenticates the vault only on the pods you select. You can choose all pods, a single pod, or multiple pods for a vault instance. If you select **ALL**, Securiti runs vault authentication across all pods.
> - You can update pod selection after creation without recreating the vault configuration.
> - Only vaults associated with the same pod as the data system connector appear as available keyrings during connector configuration.
  2. Select the authentication type and provide authentication credentials.
5. Click **Test and Save.**

![Configuration settings for AWS Secret Manager, focusing on authentication options and pod selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/vaults_authentication.png)
6. Once the connection is successful, you can review the connector details in the **Overview** tab, as shown below.

![Overview section of AWS Secret Manager showing active status and configuration options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/vaults_overviewtab.png)
7. Click **Activity Log** tab to view and monitor all activities related to an instance.

![AWS Secret Manager interface showing activity log and filter options for credential management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/activitylog_vaults.png)

## Supported credential vaults in Securiti

Securiti supports integration with the following credential vaults:

- [AWS Secrets Manager](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault)
- [Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault)
- [GCP Secret Manager](/latest/docs/configuring-credential-vaults-gcp-secret-manager-credential-vault)
- [Credstash](/latest/docs/configuring-credential-vaults-credstash-credential-vault)
- [CyberArk](/latest/docs/configuring-credential-vaults-cyberark-conjur-credential-vault)
- [Delinea Secret Manager](/latest/docs/configuring-credential-vaults-delinea-secret-manager-credential-vault)
- [Hashicorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault)

## Related

- [AWS Secrets Manager credential vault](/configuring-credential-vaults-aws-secrets-manager-credential-vault.md)
- [Azure Key Vault](/configuring-credential-vaults-azure-key-vault.md)
- [Delinea Secret Manager credential vault](/configuring-credential-vaults-delinea-secret-manager-credential-vault.md)
