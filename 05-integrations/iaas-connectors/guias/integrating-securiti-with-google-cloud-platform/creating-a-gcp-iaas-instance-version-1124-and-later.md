---
title: "Creating a GCP IaaS Instance (version 1.124 and later)"
slug: "creating-a-gcp-iaas-instance-version-1124-and-later"
updated: 2026-07-20T11:20:55Z
published: 2026-07-20T11:20:55Z
canonical: "helpcenter.securiti.ai/creating-a-gcp-iaas-instance-version-1124-and-later"
stale: true
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Creating a GCP IaaS Instance (version 1.124 and later)

> [!NOTE]
> **Important**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

Creating a GCP IaaS instance is essential for enabling automated discovery, classification, and protection of data across your cloud environment. By setting up and activating the instance, you ensure that Securiti has the necessary permissions to monitor, manage the security posture, and apply privacy controls to the data within your GCP infrastructure.

### Prerequisites

- You must have Terraform 1.6.6 or later. We strongly recommend using 1.7.0 or later, because it addresses several vulnerabilities.
- Install the Google Cloud (gcloud) CLI along with Terraform before you begin. Without the gcloud CLI, the Terraform template may not discover the required GCP projects, which can block the onboarding process.
- You must have the following GCP roles:
  - Organization Administrator - When the scope selected is **organization**.
  - Owner/s - When the scope selected is **project** (single project). For multiple projects, multiple project owners' access is needed.
- All projects that you want to be discovered and scanned must have the compute.googleapis.com APIs and billing enabled on them as a minimum requirement. Otherwise, those projects and associated assets may not be discovered. You may have to enable additional APIs depending on the types of assets in the projects.
- The following GCP [API](https://cloud.google.com/resource-manager/docs/reference/orgpolicy/rest) must be enabled to identify whether a bucket is public or not as scanning is applicable only on public buckets.
- In case of [My Cloud](/v1/docs/getting-started-with-iaas-cloud), ensure you have pod roles deployed before onboarding the connector.
- You must have the subscription to the following modules to integrate Securiti with Google Cloud Platform:

| Purpose | Module Required |
| --- | --- |
| Pod Activation | [System Settings](/v1/docs/getting-started-with-system-settings) |
| Sensitive Data Scan | [Sensitive Data Intelligence](/v1/docs/using-sensitive-data-intelligence) |
| Posture Scan and Auto-remediation | [Security Posture Management](/v1/docs/using-security-posture-management) |
| Dark Asset Discovery for VM Snapshots | [Data Mapping Automation](/v1/docs/using-data-mapping-automation) |
| Content Classification | [Sensitive Data Intelligence](/v1/docs/using-sensitive-data-intelligence) |
| Visualize Scan Results | 1. [Graph Explorer](/v1/docs/using-graph-explorer) 2. [Data Command Graph](/v1/docs/using-data-command-graph) 3. [Inventory](/latest/docs/using-inventory) 4. [Reporting](/v1/docs/using-graph-reporting-dashboards) |

> [!NOTE]
> **Note**
> 
> If these modules are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether these are included in your plan and whether your tenant meets the eligibility requirements for their activation.

### Step-by-step Instructions

1. In Securiti, select the jewel icon and choose **Integrations** from the left navigation bar.
2. On the **Integrations** page, navigate to **IaaS Connectors**.
3. To create a new instance, click **Add IaaS Connectors** in the top-right corner of the page, and then select **Google Cloud Platform**.
4. On the **Google Cloud Platform** configurations page provide the following information:

| Section | Parameter | Description |
| --- | --- | --- |
| General Information | Instance Name | Enter a convenient name for the instance. Example: GCP-Data |
| Primary Owner | Select the primary owner of the instance responsible for managing the instance. By default the instance creator is set as the primary owner. You can also select the primary owner from the menu. |
| Scope | Organization | To perform scans at the root level, enter the **Organization ID**. To include or exclude specific organization units, click **Add Labels**. > [!NOTE] > Note > > When onboarding at the organization level, projects with names starting with `sys-` are not discovered. These prefixes are typically used by system-generated projects, which are not included in discovery. Since it is not possible to distinguish between system-generated projects and user-created projects with the same prefix, all `sys-` projects are excluded. |
| Project | To perform scans on a Project, enter your **Project ID**. > [!NOTE] > **Note** > > - To find your project ID, open the Cloud project. At the top-right, click **More > Project Settings** and view the **Project ID**. The Project ID is alphanumeric. > > Example: gcpapp-1144215 > - To add more than one project click **Add project**. |
| Scan Location | Securiti Cloud | Scanning of data in assets is done in the Securiti cloud. For more information on when to choose this option, see [Securiti Cloud](/v1/docs/getting-started-with-iaas-cloud). |
| My Cloud | Automatic deployment of pod on customer’s infrastructure. Scanning of data in assets is done in the customer's cloud infrastructure. For detailed information on when to choose this option, see [My Cloud](/v1/docs/getting-started-with-iaas-cloud). |
| Deploy Pod | Pod deployment is a prerequisite to enable Securiti for sensitive data scan and to discover packages on VM. However, to provide you control over pod deployment and scanning, Securiti lets you connect your data systems to existing pods without deploying new ones. You can select the data systems to scan and initiate scans whenever needed. - You can select the **Detect for Sensitive Data** and **Discover Packages on VM Snapshots** options even if the Deploy Pod option is not selected. - The TF template will include connection details for the data systems but will not initiate scans. - To initiate scans, you must manually connect your data systems to pods using the **Data Systems Overview** dashboard. For more information, visit [Deploying Pod](/latest/docs/deploying-pod-gcp). > [!NOTE] > **Note** > > When you select **Securiti Cloud** for pod deployment, the pod is deployed on Securiti’s account. It is not a permanent deployment and there are no additional charges for it. If you require a permanent pod, select **My Cloud**, and charges are incurred, according to the provider. |
| Project to Deploy Pod | Enter your **Project ID** and **Project Number** to let Securiti deploys pod on your cloud infrastructure. |
| Download Template | Click **Prepare Template** and then click **Download Template**. > [!NOTE] > **Note** > > This Terraform template streamlines onboarding one or more GCP projects to Securiti SaaS by provisioning essential resources, configuring IAM roles, VPC networks, secrets management, and enabling required GCP services. |
| Region for Data Scan | Choose the region(s) to deploy the pod in for scanning purposes. For example, us-west-2. > [!NOTE] > **Note** > > The regions specified here are for data scanning purposes only. Asset discovery operates independently of the regions selected. |
| Advanced Settings | Scan Settings | In the Scan Settings area, choose the specific sensitive data type(s) to scan for. Click a category to open and select the relevant **Data Elements**, **Document Categories**, **Content Profiles** or **Exact Data Profiles** to perform the scan on. > [!NOTE] > **Note** > > Some Data Element Categories and Document Categories are pre-selected by default. The values configured at this stage will be used for running automated discovery scans on discovered assets. |
| Collect Evidence | If you have enabled private cloud storage, use this toggle to configure results of **Detect for Sensitive Data** to be saved to an evidence file. Doing so lets you view matched highlights for specific documents. > [!NOTE] > **Note** > > The scanning limit is 1000 files per storage. |
| Discover Cloud Assets (default) | Find, identify, and catalog all assets such as virtual machines and databases. > [!NOTE] > **Note** > > In case of **Advanced Settings**, the **Discover Cloud Assets** option is pre-selected. |
| Detect Security Posture Misconfigurations | Mark this checkbox to have Securiti scan your GCP account for security vulnerabilities and identify misconfigurations (access controls, network settings, encryption protocols) in cloud infrastructure or resources. > [!NOTE] > Note > > Selecting this checkbox is mandatory when creating a GCP instance. If not selected, you may encounter issues later when manually connecting GCP data systems to pod. For more information, see [Deploying Pod](/latest/docs/deploying-pod-gcp). |
| Detect for Sensitive Data | Mark this checkbox to have Securiti look for specific data elements distributed across different locations, and different data systems, on specific schedules and owners. **Optional:** Select **Add Tags** to perform scanning of selective assets of your data systems. You can include or exclude assets for scanning by entering **Key** and its **Value**. Example: Key: Owner Value: john.doe@securiti.ai Scans only those buckets whose owner is john.doe@securiti.ai > [!NOTE] > **Note** > > Public GCS buckets are scanned regardless of inclusion or exclusion tags, and scans by default process up to 1,000 files. |
| Send Security Alerts to Security Command Center | Sends all security alerts to Google Security Command Center to centralize your cloud security findings and remediation. |
| Discover packages on VM snapshots | Mark this checkbox to automatically discover dark assets in your GCP cloud account. Scan disks of compute instances, and find installed packages and associated vulnerabilities. To learn more about discovering packages on VM snapshots refer to Dark Asset Discovery and Vulnerability Detection. **Optional:** Select **Add Tags** to perform scanning of selective EC2 Instances. You can include or exclude instances for scanning by entering the **Key** and its **Value**. Example: Key: Owner Value: john.doe@securiti.ai Scans the root volumes of only those compute instances whose owner is john.doe@securiti.ai. |
| Activate Security Posture auto-remediation | Mark this checkbox to have Securiti automatically remediate applicable GCP security vulnerabilities it finds. |
| Execution Id | It is the role suffix added to the roles and policies provisioned by Securiti cloud in Customer GCP account. The value for this field is auto-generated by Securiti. |
| Define the period to discover cloud assets and detect security posture misconfigurations | Mark this checkbox to include or exclude specific time periods for asset discovery. From the menu, select the period. Example: Hourly, Daily, Weekly, Monthly |
| Notify all owners by email when asset discovery is complete | Enabled by default to send emails to owners and co-owners after an asset discovery scan completes. The notification includes key insights and a direct link to the Graph for deeper analysis. > [!NOTE] > **Note** > > - Email notifications are sent only when asset discovery identifies new assets. > - To trigger the email notifications, it is necessary to reschedule and run asset discovery again. > - To enable this feature for existing instances, navigate to the **Instance Setup tab > Advanced Settings > Notify all owners by email when asset discovery is complete**. > - If the feature was enabled during the connector onboarding, you can disable it from the same tab if you no longer wish to receive email notifications. |
| Deployment | Click Through | Select this option to have Securiti redirect you to your GCP console, where GCP prompts you to log in if you are not already authenticated. Click **Sign in with Google**. Choose your registered Google account. To see what permissions are required from you to perform the automated advanced settings, click **View Roles and Permissions Requested**. |
| Download Template | Select this option to download the Terraform template in Shell format before deployment. Review the resources and permissions needed, which vary based on selected Securiti features. This template onboards GCP projects to Securiti’s SaaS, enabling asset discovery, security posture analysis, and data scanning. Click **Prepare Template** and then click **Download Template**. |
5. On Securiti Platform, click **Save Configuration**. After the stack deploys, Securiti automatically starts asset discovery and populates the overview dashboard with the scanned results.

Securiti sends automated email notifications upon completing an asset discovery scan. These notifications highlight changes detected in the latest scan, identify newly discovered assets, and include a link to the Graph for detailed analysis.

To view the logs, you can click the created instance and click the **Audit Trail** tab.

### List of supported GCP assets enabled for data and disk scans

Securiti scans a wide range of GCP assets, but currently supports automated data scans for Google Cloud Storage

For automated disk scans, Securiti scans the boot (root) disks of Cloud VMs with user-specified tags, as long as the disks use the Ubuntu drive image.

## Related

- [Performing Actions Post GCP Instance Creation](/performing-actions-post-gcp-instance-creation.md)
- [Visualizing Results of Asset Discovery](/visualizing-results-of-gcp-asset-discovery.md)
- [Deploying Pod](/deploying-pod-gcp.md)
- [How it Works?](/how-it-works-gcp.md)
