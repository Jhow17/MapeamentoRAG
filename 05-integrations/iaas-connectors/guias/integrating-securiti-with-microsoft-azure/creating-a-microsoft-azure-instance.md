---
title: "Creating a Microsoft Azure Instance"
slug: "creating-a-microsoft-azure-instance"
updated: 2026-05-21T08:13:48Z
published: 2026-05-21T08:13:48Z
canonical: "helpcenter.securiti.ai/creating-a-microsoft-azure-instance"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Creating a Microsoft Azure Instance

Creating an Azure instance is essential for automated asset discovery; including shadow assets, discovery scans and protection of your data across your cloud environment. By setting up and activating the instance, you ensure that Securiti has the necessary permissions to monitor, and manage the security posture, and apply privacy controls to the data within your Azure infrastructure.

### Prerequisites

- **Azure Prerequisites**
  - You must have a **Global Administrator** role in Microsoft Entra ID (formerly known as Azure AD). This role is required to register the Securiti platform under Enterprise Applications and create an App Registration (Service Principal) in Microsoft Entra ID.

For more information, visit the [Azure Global Administrator Role Guide](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference#global-administrator).

> [!NOTE]
> **Note**
> 
> The Application Administrator can create service principals but cannot create graph APIs, which is why a Global Administrator role is required.
  - In Azure, you must have the **Owner** role in all subscriptions you want to connect to. Securiti uses this role to grant the App Registration the **Reader** role in each subscription.

For more information, visit [Azure Built-in Roles Guide](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).
- **Securiti Prerequisites**
  - In Securiti, you must have the subscription to the following modules to integrate Securiti with Azure:

| Purpose | Module(s) Required |
| --- | --- |
| Pod Activation | [System Settings](/v1/docs/getting-started-with-system-settings) |
| Sensitive Data Scan | [Sensitive Data Intelligence](/v1/docs/using-sensitive-data-intelligence) |
| Posture Scan & Auto-remediation | [Security Posture Management](/v1/docs/using-security-posture-management) |
| Visualize Scan Results | 1. [Graph Explorer](/v1/docs/using-graph-explorer) 2. [Data Command Graph](/v1/docs/using-data-command-graph) 3. [Inventory](/latest/docs/using-inventory) 4. [Reporting](/v1/docs/using-graph-reporting-dashboards) |

> [!NOTE]
> Note
> 
> If these modules are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether these are included in your plan and whether your tenant meets the eligibility requirements for their activation.

Securiti offers the following two deployment methods to onboard Microsoft Azure cloud:

- Click Through
- Download Template

### One-click Activation

This section outlines the step by step procedure to onboard your Azure environment using the **Click Through** deployment method.

#### Step-by-step Instructions

1. In Securiti, select the jewel icon and choose **Integrations** from the left navigation bar.
2. On the **Integrations** page, navigate to **IaaS Connectors**.
3. To create a new instance, click **Add IaaS Connectors** in the top-right corner of the page, and then select **Azure**.
4. On the **Add Azure Cloud Account** page provide the following information:

![Form to add an Azure Cloud account with various configuration options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-21 at 12.57.51 PM.png)

| Parameter | Description |
| --- | --- |
| Connector Name | Enter a convenient name for the instance. Example: Azure-Data |
| Subscription IDs | Enter subscription IDs. Multiple values can be entered by separating them with a comma. |
| Initiate asset discovery (default) | Find, identify, and catalog all assets such as virtual machines and databases. This option is pre-selected. |
| Notify all owners by email when asset discovery is complete | Enabled by default to send emails to owners and co-owners after an asset discovery scan completes. The notification includes key insights and a direct link to the Graph for deeper analysis. > [!NOTE] > **Note** > > - Email notifications are sent only when asset discovery identifies new assets. > - To trigger the email notifications, it is necessary to reschedule and run asset discovery again. > - To enable this feature for existing instances, navigate to the **Instance Setup tab > Advanced Settings > Notify all owners by email when asset discovery is complete**. > - If the feature was enabled during the connector onboarding, you can disable it from the same tab if you no longer wish to receive email notifications. |
| Initiate security posture scan | Mark this checkbox to let Securiti scan your Azure account for security vulnerabilities and identify misconfigurations (access controls, network settings, encryption protocols) in cloud infrastructure or resources. |
| Auto-remediate security posture violations | Mark this checkbox to let Securiti automatically remediate applicable Azure security vulnerabilities it finds. |
| Integrate with Azure Purview data catalog | Mark this checkbox to let Securiti to write metadata to Azure Purview data catalog collections. Rules may be defined via the workflow module. |
| Deployment Method | Choose **Click Through**. |
5. Click **Authorize User Profile**. Securiti redirects you to your Azure console, where Azure prompts you to log in with your Org Admin level credentials if you are not already authenticated.

Azure prompts you to allow Securiti to read the authenticated user’s profile to determine if it has rights to perform activation.
6. On the Permissions Requested popup, click **Accept**.
7. On the Securiti prompt, click **Create service account**.
8. Azure prompts you to allow Securiti rights to create a service principal (app registration), click **Accept**.
9. On the Securiti prompt, click **Authorize Service Account**.
10. Azure prompts you to allow Securiti rights to add the service principal created in the previous step. Click **Accept** to grant permission.

> [!NOTE]
> **Note**
> 
> - These permissions are granted to Securiti for activation and discover assets. These permissions are also required for subsequent rediscovery to detect any changes i.e. addition or removal of assets.
> - After activation, you can delete the Securiti Application listed under the Enterprise Applications in your Azure tenant. All subsequent operations are performed using the service principal(s) (app registration) created during the activation process.

### Terraform Activation

This section outlines the step by step procedure to onboard your Azure environment using the **Download Template** deployment method.

#### Step-by-step Instructions

1. In the **Azure portal**, go to **Microsoft Entra ID > App registrations**, then select **New registration** to create an app registration.
2. In your app registration, select **Manage > Certificates & secrets**. Under **Client secrets**, select **New client secret**, enter a **Description**, choose an **Expires** value, then select **Add**.

> [!NOTE]
> Note
> 
> Copy the client secret value immediately and store it securely. Azure displays this value only once; after you leave the page, you can’t view it again.

![Overview of Azure App Registration with essential details and instructions for users.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/azure-step-2(1).png)
3. From the app registration **Overview** page, copy and store the following values (you use them later during Terraform onboarding):

> [!NOTE]
> Note
> 
> Make sure you copy the **client secret value**, not the **secret ID**.

![Azure app registration page displaying client secrets and their expiration details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/azure-step-3.png)
  1. Application (client) ID
  2. Directory (tenant) ID
  3. Client secret value
4. In the app registration, go to **Manage > API permissions**. Select **Add a permission**, add the required permissions listed below, then select **Grant admin consent for default directory**.

| Permission | Type | Description | Purpose |
| --- | --- | --- | --- |
| `Application.ReadWrite.AI` | Application | Create and manage applications and service principals | Required to create, `azuread_application` , `azuread_service_principal` , and `azuread_application_password` resources. |
| `AppRoleAssignment.ReadWrite.All` | Application | Manage application role assignments | Required to assign Microsoft Graph permissions to the new application. |

![Azure API permissions page showing configured permissions and admin consent requirements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/azure-step-4.png)
5. Create a custom role with the required permissions listed below. While creating the role, add the subscription ID(s) you want to onboard to the **Assignable scopes**.

**Required permissions (Actions):**

Microsoft.Resources/subscriptions/read

Microsoft.Authorization/roleDefinitions/read

Microsoft.Authorization/roleDefinitions/write

Microsoft.Authorization/roleDefinitions/delete

Microsoft.Authorization/roleAssignments/read

Microsoft.Authorization/roleAssignments/write

Microsoft.Authorization/roleAssignments/delete

Microsoft.Purview/accounts/read

> [!NOTE]
> Note
> 
> If you plan to onboard multiple subscriptions using the same connector, include all relevant subscription IDs in the Assignable scopes while creating the custom role. You can’t assign the role to subscriptions that aren’t listed here.

![Creating a custom role in Azure with JSON format permissions and scopes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/azure-step-5.png)
6. **Optional (Azure Purview integration only):** Assign your app’s service principal to the Purview account collection.

> [!NOTE]
> Note
> 
> Complete this step only if you want to integrate with Azure Purview.
  1. Open the **Microsoft Purview** portal.
  2. Go to **Data map > Role assignments**.
  3. Select **Edit role assignments**.
  4. Under **Collection** admins, select **Add**, search for your service principal (the app registration from Step 1), then select **Save**.
7. Assign the custom role to the subscription you want to onboard:

> [!NOTE]
> Note
> 
> - Make sure you assign the role at the subscription scope. Assigning it at a different scope (for example, resource group) can prevent successful onboarding.
> - If you’re onboarding multiple subscriptions, repeat this step for each subscription.
  1. In the Azure portal, open the required **Subscription**.
  2. Go to **Access control (IAM)**.
  3. Select **Add > Add role assignment**.
  4. On the **Role** tab, select **Privileged administrator roles**, then choose the custom role you created.
  5. Assign the role to the service principal created in Step 1, then complete the role assignment.
8. While creating the role assignment, add the service principal as the member:

> [!NOTE]
> Note
> 
> If you don’t see the app registration in the list, make sure you’re searching for the service principal name (not the application name) and that the app registration exists in the same tenant as the subscription.

![Azure portal showing role assignment options for user, group, or service principal.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/azure-step-8.png)
  1. On the **Members** tab, select **Add members**.
  2. Search for and select the app registration (service principal) created in Step 1.
  3. Select **Review + assign** to complete the role assignment.
9. On the **Add role assignment** page, go to the **Conditions** tab. Under **Exclude roles**, select **Owner**, then continue to complete the role assignment.

> [!NOTE]
> Note
> 
> This exclusion prevents the role assignment from granting Owner-level permissions and follows the principle of least privilege.

![Azure role assignment interface showing role, members, and conditions for access control.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/azure-step-9.png)
10. In Securiti, create a new Azure connector to onboard the required subscription(s). For the complete workflow, see [One-click Activation](/latest/docs/creating-a-microsoft-azure-instance#oneclick-activation) section.

At a high level, you:
  1. Create a new Azure connector and enter the **Subscription ID(s)** you want to onboard.
  2. Select **Download Template** and create the instance to download the Azure Terraform template.
  3. Unzip the downloaded template and update the values you copied in Step 3:
    1. Application (client) ID
    2. Directory (tenant) ID
    3. Client secret value
  4. Run the Terraform commands.

```plaintext
terraform init
terraform apply
```

> [!NOTE]
> Note
> 
> If you’re onboarding multiple subscriptions, ensure the connector and Terraform configuration include all required **Subscription ID(s)**, and that your custom role’s **Assignable scopes** (Step 5) and role assignments (Steps 7–8) cover those subscriptions.

After activation, Securiti automatically starts asset discovery and the scanned results can be viewed using the **Universal Data Explorer** or **Inventory**.

> [!NOTE]
> Note
> 
> If Universal Data Explorer and Inventory are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether these are included in your plan and whether your tenant meets the eligibility requirements for their activation.

To view comprehensive logs, you can click the created instance and click the **Audit Trail** tab. It records the status of the asset discovery and posture scans at every stage. This includes whether the process is scheduled, initiated, in progress, successfully completed, or has failed.

These logs help identify issues and bottlenecks in the discovery process and ensure that all assets in your Azure environment are accounted for. You can also view role validation logs under this tab.

## Related

- [Performing Actions Post Azure Instance Creation](/performing-actions-post-azure-instance-creation.md)
- [Visualizing Results of Asset Discovery](/visualizing-results-of-azure-asset-discovery.md)
- [Deploying Pod](/deploying-pod-azure.md)
- [Policies & Permissions Required for Azure Integration](/policies-permissions-required-for-azure-integration.md)
