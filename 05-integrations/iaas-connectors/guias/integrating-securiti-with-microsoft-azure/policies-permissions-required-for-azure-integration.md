---
title: "Policies & Permissions Required for Azure Integration"
slug: "policies-permissions-required-for-azure-integration"
updated: 2026-04-07T07:05:24Z
published: 2026-04-07T07:05:24Z
canonical: "helpcenter.securiti.ai/policies-permissions-required-for-azure-integration"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Policies & Permissions Required for Azure Integration

#### Azure Service Accounts

For integrating Azure, Securiti creates some service accounts outlined in the table below:

| App registration | Feature | Built-in roles granted |
| --- | --- | --- |
| SECURITI_APP_*<8-HEX-CHARS>* | - Asset Discovery - Posture Scan | Reader [https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#reader](https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#reader) |
| Azure Purview Data Catalog Integration | Azure Purview role assignments: - Data Curator - Data Source Admin - Collection Admin (required if creating new collections via workflow) |

#### Azure Subscription Managed Roles

These roles are attached to the subscription against the configured App Registration. These roles are used by Resource Manager API.

- Reader
- Storage Blob Data Reader
- Storage Table Data Reader
- Storage File Data Privileged Reader
- Storage File Share SMB Data Reader

#### Azure Managed Roles

| Policy/Role | Access Level | Purpose | Required for |
| --- | --- | --- | --- |
| [Reader](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles/general#reader) (Mandatory) | List, Read | Provides permission to list and read resources and their configuration. | - Asset Discovery - Posture Scan |
| [Key Vault Reader](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles/security#key-vault-reader) | List, Read | Read metadata of key vaults and it's certificates, keys, and secrets. Cannot read sensitive values such as secret contents or key material. Only works for key vaults that use the 'Azure role-based access control' permission model. | Asset Discovery |
| Microsoft.PolicyInsights/policyStates/queryResults/action | List, Read | Provides insights into the compliance status of Azure resources. | Asset Discovery |
| Microsoft.Web/sites/config/list/Action) | List, Read | Provides insights into configuration settings of web apps. | Asset Discovery |
| Microsoft.CognitiveServices/accounts/listKeys/action > [!NOTE] > **Note** > > This permission exists within the custom role configured on Azure Cloud. | List, Read | Accesses the API keys of Cognitive Services accounts | Asset Discovery |
| Microsoft.CognitiveServices/accounts/projects/*/read | Read | Read project configurations and metadata | Asset Discovery |
| Microsoft.CognitiveServices/*/read | Read | Read data from Cognitive Services resources (including OpenAI completions, deployments, etc.) | Asset Discovery |
| **Custom Role - Azure Functions** 1. Microsoft.Web/sites/config/list/Action 2. Microsoft.Web/sites/host/listkeys/action 3. Microsoft.Web/sites/functions/*/action | List , Read | 1. Grants permission to list the configuration settings of a Function App. 2. Grants permission to list the host keys for a Function App. 3. Grants wildcard access to actions on all functions in a Function App. | Asset Discovery |
| **Custom Role - Azure AI Search** Microsoft.Search/searchServices/listAdminKeys/action | List , Read | Grants permission to retrieve the admin API keys (primary and secondary) for Azure AI Search, providing full read access to all AI Search indexes, indexers, data sources, knowledge sources, and knowledge bases. | Asset Discovery |

## Permission required for Terraform Activation

The authentication for Azure IaaS connector through terraform activation requires the following permissions.

1. **Azure Active Directory Permissions**

These permissions are required to create the app registration, service principal, and grant admin consent.

Required Microsoft Graph API Permissions

| Permission | Type | Description | Purpose |
| --- | --- | --- | --- |
| `Application.ReadWrite.Al` | Application | Create and manage applications and service principals | Required to create `azuread_application`, `azuread_service_principal`, and `azuread_application_password` resources |

1. **Azure Subscription Permissions (RBAC)**

These permissions are required on each subscription listed in `var.target_subscriptions`.

**Option A: Built-in Role (Simpler)**

| Role | Scope | Description |
| --- | --- | --- |
| User Access Administrator | Subscription | This role can manage user access to Azure resources, create custom roles, and assign roles |

**Option B: Custom Role (Least Privilege)**

Create a custom role with these specific actions:

```json
{
    "Name": "Securiti Terraform Executor",
    "IsCustom": true,
    "Description": "Minimum permissions to execute Securiti onboarding Terraform",
    "Actions": [
        "Microsoft.Resources/subscriptions/read",
        "Microsoft.Authorization/roleDefinitions/read",
        "Microsoft.Authorization/roleDefinitions/write",
        "Microsoft.Authorization/roleDefinitions/delete",
        "Microsoft.Authorization/roleAssignments/read",
        "Microsoft.Authorization/roleAssignments/write",
        "Microsoft.Authorization/roleAssignments/delete",
        "Microsoft.Purview/accounts/read"
    ],
    "NotActions": [],
    "DataActions": [],
    "NotDataActions": [],
    "AssignableScopes": [
        "/subscriptions/{subscription-id-1}",
        "/subscriptions/{subscription-id-2}"
    ]
}
```

**Detailed Action Breakdown**

| Action | Resource Type | Description | Purpose |
| --- | --- | --- | --- |
| `Microsoft.Resources/subscriptions/read` | Subscription | Read subscription details | Required by `data.azurerm_subscriptions` and permission check script |
| `Microsoft.Authorization/roleDefinitions/read` | RBAC | Read role definitions | Required to check if a custom role already exists before creation |
| `Microsoft.Authorization/roleDefinitions/write` | RBAC | Create or update role definitions | Required to create the `Securiti_Role_*` custom role in `azurerm_role_definition.securiti_custom_openai` |
| `Microsoft.Authorization/roleDefinitions/delete` | RBAC | Delete role definitions | Required for Terraform destroy operations |
| `Microsoft.Authorization/roleAssignments/read` | RBAC | Read role assignments | Required to check existing assignments and prevent duplicates |
| `Microsoft.Authorization/roleAssignments/write` | RBAC | Create or update role assignments | Required to assign custom role and built-in Reader roles to the Service Principal via `azurerm_role_assignment` resources |
| `Microsoft.Authorization/roleAssignments/delete` | RBAC | Delete role assignments | Required for Terraform destroy operations |
| `Microsoft.Purview/accounts/read` | Purview | List Purview accounts | Required by `data.azurerm_resources.purview_accounts` to discover Purview accounts |

1. **Azure Purview Permissions**

These permissions are not Azure RBAC permissions. They are internal to Purview's own access control system.

| Action | Resource Type | Description | Purpose |
| --- | --- | --- | --- |
| Collection Administrator | Purview Root Collection | Full access to manage collections and permissions | Required by `scripts/configure_purview.sh` to call the Purview Policy Store API (PUT `/policystore/metadataPolicies/{policyId}`) to add the new Service Principal to Purview roles |

For more information on how to grant these permissions, see [Terraform Activation](/latest/docs/creating-a-microsoft-azure-instance#terraform-activation) section.

## Related

- [Creating a Microsoft Azure Instance](/creating-a-microsoft-azure-instance.md)
