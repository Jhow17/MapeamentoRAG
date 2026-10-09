---
title: "Performing Actions Post Azure Instance Creation"
slug: "performing-actions-post-azure-instance-creation"
updated: 2026-05-22T06:11:54Z
published: 2026-05-22T06:11:54Z
canonical: "helpcenter.securiti.ai/performing-actions-post-azure-instance-creation"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Performing Actions Post Azure Instance Creation

Once an Azure IaaS instance is created on the Securiti platform, users gain access to a variety of post-instance creation actions designed to help manage and secure their cloud environment. These actions enable users to edit configurations, discover accounts, reinitiate asset discovery and posture scan, and delete instances.

For detailed guidance on creating an Azure IaaS instance, refer to the [Creating a Microsoft Azure Instance](/v1/docs/creating-a-microsoft-azure-instance) section, which outlines the step-by-step process for setting up your instance on the Securiti platform.

To perform these post-activation actions:

1. In Securiti, select the jewel icon and choose **Integrations** from the left navigation bar.
2. On the **Integrations** page, navigate to **IaaS Connectors**.
3. On the **IaaS Connectors** page, you will see a list of existing instances. Click the **More actions** icon next to an instance, or click the instance directly. A menu appears, letting you perform the following actions.

### Editing an Azure Instance

**Scenario**

As a Data Governance Officer, you need to assign co-owners and refresh scan coverage when responsibilities shift across your Azure accounts. Manually tracking owner changes and kicking off separate scans risks missing new stakeholders and hidden misconfigurations. With Securiti’s post-instance actions, you add co-owners and reinitiate asset discovery and posture scans in seconds, maintaining continuous visibility and control.

In Securiti, the instance view includes three tabs. Each tab serves a different purpose:

- Basic Information
- Instance Setup
- Audit Trial

#### Basic Information

On the **Basic Information** tab, click **+ Add Co-owner** in the **Owners** section, under the **Primary Owner** field, to add a co-owner.

> [!NOTE]
> **Note**
> 
> - You cannot edit the **Instance Name** or **Primary Owner** after the instance has been created.
> - Asset discovery email notifications are also sent to co-owners, providing insights into discovered assets. For more information, see [Asset Discovery](/latest/docs/data-security-posture-management#asset-discovery).

#### Instance Setup

On the **Instance Setup** tab, you can perform the following actions:

- In the **View Accounts** section, you can selectively reinitiate asset discovery and posture scan for specific accounts. After the instance is created and the initial scan is complete, select the desired accounts and click **Initiate**. This action triggers asset discovery and posture scan for all selected accounts.

> [!NOTE]
> **Note**
> 
> - This feature is supported:
>   - Only for Asset Discovery and Posture Scan.
>   - Only for on-demand reinitiation. Scheduled Asset Discovery and Posture Scan will continue to run automatically for all accounts.
>   - Only for accounts where both the Asset Discovery and Posture Scan are in a **Completed** or **Failed** state. If either scan is in **In Progress** or **Scheduled** state, the option will be disabled.
> - To support this feature, checkboxes are now designated for selecting accounts when reinitiating scans. Account linking is now managed through toggle buttons; disabling an account prevents it from being included in future checks and scans.

- You can add a new subscription to the connector and assign the required roles to the service principal.

> [!NOTE]
> Note
> 
> - For existing connectors, only the **Service Principal ID** is displayed. To find the corresponding **Service Principal Name**, follow these steps:
>   - Copy your **Service Principal ID** and paste it into the global search bar in your Azure portal. If the subscription associated with the ID does not appear in the dropdown list, click **Continue searching in Microsoft Entra ID**.
>   - Azure redirects you to the **Overview** tab of your **Default Directory**. In the dropdown menu, locate the **Enterprise applications** section, where you can view your **Service Principal Name**.

#### Add new Subscription

  1. In your Azure portal, navigate to the **Subscriptions** tab and copy the **Subscription ID** you want to add.
  2. In the Securiti platform, open the **Instance Setup** page for your connector.
  3. Click **+ Add New Subscription**, paste the **Subscription ID**, and click **Save**.
  4. Refresh the page. The new subscription appears in the **View Subscriptions** table.

> [!NOTE]
> Note
> 
> The initial asset discovery scan will fail because the service principal does not yet have the required Reader or custom roles on the newly added subscription.

**Assign Required Reader Roles to the Service Principal**

  1. In your Azure portal, open the newly added subscription and navigate to **Access Control (IAM)**.
  2. Click **+ Add** and select **Add role assignment**.
  3. Under the **Job function roles** tab, search for Reader, select it, and click Next.
  4. Click + Select members, paste your Service Principal Name into the search bar, and select it.
  5. Click Next, then Review + assign.
  6. Repeat the same process to assign the following roles:

**Storage Blob Data Reader**

**Storage Table Data Reader**

**Storage File Data Privileged Reader**

**Storage File Data SMB Share Reader**

**Create and Assign a Custom Role**

**Create and Assign a Custom Role**

  1. In the subscription’s **Access Control (IAM)** page, click **+ Add** and select **Add custom role**.
  2. On the **Create a custom role** page, enter your custom role name.
  3. For **Baseline permissions**, select **Start from scratch**, then click **Next**.
  4. On the **Permissions** tab, click **Add permissions**, and add the following permissions:

```plaintext
"Microsoft.CognitiveServices/accounts/listKeys/action",
```

```plaintext
"Microsoft.Web/sites/config/list/action",
```

```plaintext
"Microsoft.Web/sites/host/listkeys/action",
```

```plaintext
"Microsoft.Web/sites/functions/*/action"
```

```plaintext
“Microsoft.CognitiveServices/accounts/listKeys/action",
```
  5. Complete the remaining steps to create the custom role.

**Assign the Custom Role**

  1. Return to the **Add role assignment** page.
  2. Search for the custom role you created under the **Job function roles** tab and select it.
  3. Click **Next**.
  4. Click **+ Select members**, then paste and select your **Service Principal Name**.
  5. Click **Next**, then **Review + assign**.

**Run Asset Discovery**

After the required Reader and custom roles have been assigned, run the Asset Discovery scan again. It should now complete successfully.
- To discover data system assets in monitored IaaS accounts, mark the **Initiate asset discovery** checkbox.
- To monitor and remediate misconfigurations across your IaaS data systems, mark the **Initiate security posture scan** checkbox.
- To send findings to external systems, mark the Integrate with **Azure Purview data catalog** checkbox.

> [!NOTE]
> Note
> 
> - Use the Prepare Template option to execute the terraform template to integrate with Azure Purview if you did not opted for this integration while onboarding the connector.
> - This is applicable only if you chose the **Download Template** option while onboarding the connector.
- To schedule automatic scans to discover data systems and security posture, mark the checkbox. Moreover, to define time periods when scans should be paused, click **+ Add Exclusion**.
- Mark the **Notify all owners by email when asset discovery is complete** to enable email notifications.
- To deactivate the instance select **Deactivate** from **More options** in the upper-right corner.
- To renew Azure cloud credentials select **Renew Credentials** from **More options**, which downloads a terraform template. Update the **Client ID**, **Tenant ID**, and **Client Secret Value**, then execute the terraform template to update the credentials.

> [!NOTE]
> Note
> 
> Ensure you have an existing service principal whose credentials are used to execute the renew credentials Terraform template.

#### Audit Trail

The Audit Trail tab displays comprehensive logs. It records the status of the asset discovery and posture scans at every stage. This includes whether the process is scheduled, initiated, in progress, successfully completed, or has failed.

These logs help identify issues and bottlenecks in the discovery process and ensure that all assets in your Azure environment are accounted for. You can also view role validation logs under this tab.

### Deleting an Azure Instance

**Scenario**

As a Data Security Officer, you must decommission inactive Azure instances to reduce risk and control costs. Coordinating deletions via email and spreadsheets is slow and error-prone. With Securiti’s post-instance actions, you remove inactive instances and purge their discovered assets in seconds, keeping your environment lean and minimizing vulnerability exposure.

Select **Delete** to remove the instance. A warning message will confirm whether you're sure about the deletion.

> [!NOTE]
> **Note**
> 
> Only inactive instances can be deleted.

### Reinitiating DSPM

**Scenario**

As a Data Compliance Officer, you must validate Azure security posture immediately after policy updates. Waiting for scheduled scans leaves compliance gaps unaddressed. With Securiti’s DSPM on-demand action, you rerun asset discovery and posture assessments together, linking findings to resources instantly. You close compliance gaps in minutes and maintain uninterrupted regulatory adherence.

Select **Reinitiate DSPM** to reinitiate both asset discovery and the detection of data security posture misconfigurations for all the subscriptions available in an instance.

> [!NOTE]
> **Note**
> 
> If the **Initiate Security Posture Scan** checkbox wasn't selected when configuring your Azure instance, only asset discovery runs on your activated instance.

## Related

- [Creating a Microsoft Azure Instance](/creating-a-microsoft-azure-instance.md)
