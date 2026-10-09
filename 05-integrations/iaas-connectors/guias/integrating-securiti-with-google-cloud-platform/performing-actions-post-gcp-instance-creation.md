---
title: "Performing Actions Post GCP Instance Creation"
slug: "performing-actions-post-gcp-instance-creation"
updated: 2026-05-20T15:52:11Z
published: 2026-05-20T15:52:11Z
canonical: "helpcenter.securiti.ai/performing-actions-post-gcp-instance-creation"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Performing Actions Post GCP Instance Creation

Once a GCP IaaS instance is created on the Securiti platform, users gain access to a variety of post-instance creation actions designed to help manage and secure their cloud environment. These actions let users edit configurations, delete instances, and reinitiate asset discovery and posture scan.

For detailed guidance on creating a GCP IaaS instance, refer to the [Creating a GCP IaaS Instance](/v1/docs/creating-a-gcp-iaas-instance-version-1124-and-later) section, which outlines the step-by-step process for setting up your instance on the Securiti platform.

To perform these post activation actions:

1. In Securiti, select the jewel icon and choose **Integrations** from the left navigation bar.
2. On the **Integrations** page, navigate to **IaaS Connectors**.
3. On the **IaaS Connectors** page, you will see a list of existing instances. Click the **More actions** icon next to an instance, or click the instance directly. A menu appears, letting you perform the following actions.

### Editing a GCP Instance

**Scenario**

As a Data Governance Officer, you must align project ownership and scanning scope in your GCP instance after organizational shifts. Manually updating co-owners and project lists in separate tools risks overlooking new resources. With Securiti’s post-instance actions, you add co-owners and new projects to your instance and reinitiate discovery and posture scans in seconds. You secure comprehensive visibility without delays.

In the **Basic Information** tab, under the **Owners** section you can add co-owners by clicking the **+Add co-owner** button.

> [!NOTE]
> **Note**
> 
> Asset discovery email notifications are also sent to co-owners, providing insights into discovered assets. For more information, see [Asset Discovery](/latest/docs/data-security-posture-management#asset-discovery).

To add a project to the existing instance, go to the **Instance Setup** tab, under the **Scope** section click **Add Projects**.

> [!NOTE]
> **Note**
> 
> This option is available if the GCP instance scope is set to Project at creation and the instance activation.

You can selectively reinitiate Asset Discovery and Posture Scan on specific projects. After an instance is created and the initial scan is complete, select your desired projects and click the **Initiate Scan** button under **Scope** section. This action triggers asset discovery and posture scanning for all selected entities.

![gcp-initiate-scan.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9169a76b-f89e-4941-8fd4-36d5012b492b.png)

> [!NOTE]
> **Note**
> 
> - This feature is supported:
>   - Only for Asset Discovery and Posture Scan.
>   - Only for on-demand reinitiation. Scheduled Asset Discovery and Posture Scan will continue to run automatically for all projects.
>   - Only for projects where both the Asset Discovery and Posture Scan are in a **Completed** or **Failed** state. If either scan is in **In Progress** or **Scheduled** state, the option will be disabled.
> - To support this feature, checkboxes are now designated for selecting projects when reinitiating scans. Account linking is now managed through toggle buttons—disabling an account prevents it from being included in future checks and scans.

Under the **Scan Location** section, you can edit the region for data scan.

Under the **Advanced Settings** section, you can choose to run the following scans;

- Detect Security Posture Misconfigurations
- Activate Security Posture Auto-remediation
- Send Classification Information to Dataplex

After selecting your desired scans, make sure to save the configuration to update your instance settings.

If you selected Download Template as the deployment type during onboarding, you also need to execute the Terraform template to apply your changes. This step triggers the creation of service accounts required for the enabled scans.

After saving the configuration, asset discovery does not run automatically. You must manually reinitiate it. For more information, see [Reinitiating DSPM](/latest/docs/performing-actions-post-gcp-instance-creation#reinitiating-dspm).

> [!NOTE]
> **Note**
> 
> - Advanced Settings cannot be modified while new projects are being added. You need to complete the addition of new projects before making changes to these settings.
> - New projects cannot be added while advanced settings have been modified but not yet applied. Save and execute the Terraform template for your advanced settings changes before adding new projects.
> - Once scan settings are enabled, you cannot disable them. Currently, the platform only lets you enable scan settings.
> - This option is available for both deployment types: **Click Through** and **Download Template**. However, you cannot switch the deployment type when editing the instance
> - You can enable both Discover Packages on VM snapshots and Detect for Sensitive Data settings and save the configuration to deploy the necessary roles and policies. However, reinitiating these scans during instance edits is not currently supported. Currently, the scans run only once—during the initial asset discovery process.

You can modify the period to discover cloud assets, detect security posture misconfigurations, and enable/disable email notifications.

You can choose to deactivate your instance by selecting **More options** in the upper-right corner of the **Instance Setup** tab.

### Deleting a GCP Instance

**Scenario**

As a Data Security Officer, you must decommission inactive GCP instances to reduce risk and control costs. Relying on spreadsheets and manual sign-offs delays removal and leaves stale assets exposed. With Securiti’s post-instance actions, you delete inactive instances and erase their discovered assets in seconds. You eliminate outdated resources promptly and keep your environment lean and secure.

### 

- Select **Delete** to remove the instance. A warning message confirms whether you are sure about the deletion.

> [!NOTE]
> **Note**
> 
> Only inactive instances can be deleted.

- You can choose to deactivate your instance by selecting **More options** in the upper-right corner of the Instance Setup tab.

### Reinitiating DSPM

**Scenario**

As a Data Compliance Officer, you need to verify security posture immediately after policy updates in GCP. Relying on periodic scans leaves compliance gaps unaddressed. With Securiti’s DSPM feature, you trigger combined asset discovery and posture assessment on demand. You identify misconfigurations and link findings to assets within minutes, closing gaps fast and sustaining regulatory adherence.

Select **Reinitiate DSPM** to reinitiate both asset discovery and the detection of data security posture misconfigurations.

> [!NOTE]
> **Note**
> 
> - If the **Data Security Posture Misconfigurations** checkbox was not selected when configuring your GCP instance, only asset discovery runs on your activated instance.
> - Securiti combines asset discovery and data security posture misconfiguration detection because security posture findings rely on posture scan results linked to assets from asset discovery. Therefore, all assets must be pre-populated before the asset discovery findings and scan results are generated and linked.

## Related

- [Creating a GCP IaaS Instance (version 1.124 and later)](/creating-a-gcp-iaas-instance-version-1124-and-later.md)
- [Creating a GCP IaaS Instance (version 1.123 and earlier)](/creating-a-gcp-iaas-instance-version-1123-and-earlier.md)
