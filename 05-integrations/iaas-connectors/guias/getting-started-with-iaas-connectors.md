---
title: "Getting Started with IaaS Connectors"
slug: "getting-started-with-iaas-connectors"
updated: 2026-09-28T06:15:29Z
published: 2026-09-28T06:15:29Z
canonical: "helpcenter.securiti.ai/getting-started-with-iaas-connectors"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Getting Started with IaaS Connectors

Using Securiti, you can integrate your IaaS connectors such as AWS, GCP, Azure, and OCI with the Securiti platform. As a result of this integration, you can utilize a wide variety of security posture management features such as asset discovery and dark asset discovery to detect cloud and SaaS posture misconfigurations and AI services deployed in your cloud environment, auto-remediation of posture risks, sensitive data detection and discovering access entitlements.

> [!NOTE]
> Note
> 
> To learn about how to use the IaaS Connectors dashboard, see [Using IaaS Connectors dashboard](/latest/docs/using-iaas-connectors-page).

In this section, we will explore the various important steps involved in the IaaS connector onboarding. We will also explain various available options, important for your decision-making that will help you prepare ahead of the cloud integration. The diagram shared below helps you visualize the steps.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[GS] Cloud Systems.drawio.svg)

> [!NOTE]
> **Note**
> 
> This is a high level overview of the onboarding process. For the detailed step-by-step procedure for a specific IaaS connector and its prerequisites, see:
> 
> - [Integrating AWS with Securiti](/latest/docs/integrating-securiti-with-aws)
> - [Integrating GCP with Securiti](/latest/docs/integrating-securiti-with-google-cloud-platform)
> - [Integrating Azure with Securiti](/latest/docs/integrating-securiti-with-microsoft-azure)
> - [Integrating OCI with Securiti](/latest/docs/integrating-securiti-with-oracle-cloud-infrastructure)

> [!WARNING]
> Important
> 
> This module is available in Securiti SaaS deployments but is not currently available in Securiti Sovereign deployments. Contact your Customer Success Manager or Account Representative for updates on its availability in your tenant.

### Step 1: Create your IaaS connector instance

Create a new instance for the IaaS connector you want to onboard. Doing so will make your cloud instance eligible for a variety of scans covered in step 3, ensuring full visibility into all types of assets, AI models, and data residing in your cloud.

### Step 2: Specify the Scan Location

Choose the location where the scanning must be performed. You need to provide the following information:

- Scan Location
- Region

#### Scan Location

The following scan location options are offered by Securiti:

| Scan Locations | Description | When to use? |
| --- | --- | --- |
| Securiti Cloud | Securiti Cloud refers to Securiti provided cloud ecosystem that will be used for running all scans as specified in step 3. This means the data from IaaS connector instance you just configured will be scanned on Securiti cloud. | Securiti Cloud is recommended if you prefer a quick, fully managed setup with no need for pod launch in your environment for scanning purposes. It’s ideal for fast deployment, reducing resource utilization on your infrastructure, and leveraging Securiti's built-in security controls. > [!NOTE] > **Note** > > Security Cloud is recommended for Proof of Concepts (PoCs) only. |
| My Cloud | My Cloud refers to customer provided cloud ecosystem will be used for running all scans as specified in step 3. This means the data from IaaS connector instance you just configured will be scanned on your cloud environment, as mentioned in configuration settings. | My Cloud is recommended when you need full control over the scanning process, have strict data residency requirements, or prefer to manage everything within your own cloud environment. > [!NOTE] > **Note** > > My Cloud is recommended for use in production environments. |
| Use Existing Pods | Use Existing Pods refers to leveraging already deployed Securiti pods within your environment to run all scans as specified in step 3. With this option, you map your existing pods to discover regions and configure trust relationships to enable cross-account discovery across multiple AWS accounts. This means the data from the IaaS connector instance you just configured will be scanned using your existing pods, based on your selected configuration settings. > [!NOTE] > Note > > This deployment method is supported only for AWS cloud. | Use Existing Pods is recommended when you already have Securiti pods deployed and want to reuse them for scanning, avoiding the need to launch new pods. It’s ideal for optimizing existing resources, enabling cross-account discovery by mapping pods to regions, and configuring trust relationships across multiple AWS accounts while maintaining control within your environment. > [!NOTE] > Note > > This deployment method is supported only for AWS cloud. |

> [!NOTE]
> **Note**
> 
> - To learn more about the required My Cloud configurations, see [My Cloud requirements for AWS](https://helpcenter.securiti.ai/docs/creating-an-aws-iaas-instance-version-1111-and-later#prerequisites-for-my-cloud).
> - These scan location options are currently available for selected IaaS connectors only. For more information, select the appropriate IaaS connectors documentation from the navigation sidebar.

#### Region

Region refers to the geographical hosting location selected by your organization to access and utilize cloud service provider (CSP) resources. For example, us-east-2 (AWS), europe-west1 (GCP). The only regions specified in this step will be considered for the scans.

### Step 3: Select the Scans to Perform

> [!NOTE]
> **Note**
> 
> 1. The checkboxes for all the below-mentioned scans are enabled by default except for posture scan auto-remediations. To enable it, mark the **Activate security posture auto-remediation checkbox**.
> 2. For sensitive data scans, the following scan settings are enabled by default.
>   - For unstructured data systems
> 
> 
> 
> ![unstructured_data_system-GS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7705a6c5-1ba2-6981-5d98-f6411e6bc4b0.png)
>   - For structured data systems
> 
> 
> 
> ![structured_data_systems-GS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5729abae-c02c-df45-d886-a8455ba90c2f.png)
>   - To collect sensitive data scan evidence, ensure your private cloud storage is enabled. For more information, see Configuring private cloud storage.
> 3. While these settings are configurable initially, they cannot be changed once the instance is activated.

### Supported IaaS Connectors for DSPM Scans

| Features | Description | AWS | GCP | Azure | OCI | View Results Location |
| --- | --- | --- | --- | --- | --- | --- |
| Asset Discovery (Mandatory) | Run Asset Discovery scans to scan for instances of services and map relationships between them. This helps build an inventory of assets and AI services to have a contextual understanding of your cloud. This does not require a pod deployment. [Learn more.](/latest/docs/data-security-posture-management-solution#asset-discovery) | ✓ | ✓ | ✓ | X | [Data Command Graph](/latest/docs/using-data-command-graph) |
| Sensitive Data Scan | Run Sensitive Data scans to identify and classify sensitive information such as PII, financial records, and intellectual property across structured, unstructured, and streaming data systems. These scans help mitigate risks associated with data breaches and privacy violations, providing insights into data types, volumes, and locations across your cloud. This requires a pod deployment. > [!NOTE] > **Important** > > To scan Azure and OCI assets, you must manually configure connections through the **Sensitive Data Intelligence > Data Systems Overview** dashboard. > [!NOTE] > **Note** > > Sensitive Data Scan can be performed on an existing pod. [Learn more.](/latest/docs/data-security-posture-management-solution#sensitive-data-discovery) | ✓ | ✓ | ✓ | ✓ | [Data Command Graph](/latest/docs/using-data-command-graph) |
| Dark Asset Discovery (Including AI services) | Scans disk snapshot of VMs. It builds an inventory of software packages that helps users understand specific software packages and versions available in their cloud environment. This requires a pod deployment. > [!NOTE] > **Note** > > Dark Asset Discovery cannot be performed on an existing pod. [Learn more.](/latest/docs/data-security-posture-management-solution#dark-assets-discovery) | ✓ | ✓ | ✓ | ✓ | [Data Command Graph](/latest/docs/using-data-command-graph) |
| Posture Scan and Auto Remediation | Posture scans goes through the configuration settings of your cloud services and run it against a rule-set to detect misconfigurations, incorporating data classification to help identify and prioritize misconfigurations. Auto-remediation, if enabled, assists with automatically resolving the open posture scan findings. [Learn more](/latest/docs/data-security-posture-management-solution#security-posture-management) | ✓ | ✓ | ✓ | ✓ | [Findings](/latest/docs/configuring-security-posture-policies) |
| Discovery Scan | Run scan on data in the data systems to classify and identify sensitive data. This information is used to provide context / understanding of risk to asset inventory, posture scan, and access scan. This requires a pod deployment. [Learn more](/latest/docs/discovery-scans). | ✓ | ✓ | ✓ | X | [Sensitive Data Intelligence](/latest/docs/using-sensitive-data-intelligence) |
| Access Entitlements scan | This scans entitlements to data systems and incorporates data classification to provide visibility to user entitlements and identify risky entitlements. > [!NOTE] > **Note** > > Subscription to [Data Access Governance](/latest/docs/getting-started-with-data-access-governance) module is mandatory for this scan. [Learn more.](/latest/docs/data-security-posture-management-solution#discover-access-entitlements) | ✓ | X | X | X | [Data Access Governance](/latest/docs/getting-started-with-data-access-governance) |

### Step 4: Set the Scan Frequency

Securiti offers the following scan frequency options:

#### Default scan frequency

By default, Securiti creates an inventory of cloud assets and runs posture scans on a fixed schedule unless modified later. This means any new assets, including both cloud and dark assets, added to your IaaS connector instance configured with the Securiti platform will be automatically discovered after a set period. This is the current default configuration.

> [!NOTE]
> **Tip**
> 
> Default scans are recommended for scenarios where a small, static set of cloud assets is being tested, and no additional assets are expected to be added anytime soon. This is particularly useful for initial trials where the focus is on validating specific configurations.

#### Automatic Scan

Automatic scan refer to the periodic, recurring scans that continuously assess and monitor cloud assets. Unlike a one-time scan, periodic scans ensure that any newly added or modified cloud assets—including dark assets—are regularly discovered and assessed by the Securiti platform. This ongoing process helps maintain an up-to-date inventory of cloud assets and ensures proactive identification of risks or misconfigurations in your IaaS connector environment.

> [!NOTE]
> **Tip**
> 
> Automatic scans are recommended for environments with dynamic or growing cloud assets, where ongoing visibility and continuous monitoring are critical. They are ideal for production environments or situations where new assets are frequently added.

### Step 5 & 6: Select the Stack Deployment Method

Before we dive into the details, refer to the table below to see which IaaS connector platforms support specific deployment methods:

| Supported Cloud | Click Through | Download Template | Other |
| --- | --- | --- | --- |
| [AWS](/latest/docs/integrating-securiti-with-aws) | ✓ | ✓ |  |
| [GCP](/latest/docs/integrating-securiti-with-google-cloud-platform) |  | ✓ |  |
| [Azure](/latest/docs/integrating-securiti-with-microsoft-azure) |  | ✓ |  |
| [OCI](/latest/docs/integrating-securiti-with-oracle-cloud-infrastructure) |  | ✓ | Directly via Console |

You can choose the following cloud deployment methods:

| ![3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dd343a03-e28f-7e5f-cd69-3dc542616957.png) | **Click Through** In the **click-through deployment method**, you will be redirected to the CSP Management Console, where all the stack creation fields are automatically populated based on a pre-configured template (such as a CloudFormation template). This simplifies the process, requiring no manual input or configuration adjustments. All you have to do is review the settings and click the **Create** button to initiate the deployment. > [!NOTE] > **Tip** > > The click-through method is most effective when you need to quickly onboard your stack while maintaining consistency across all production clouds and are comfortable with the default options provided. |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(314).png) | **Download Template** In the **Download Template** method, users can select specific configuration options directly within the Securiti platform. Once these options are set, the platform automatically generates a deployment template that includes a list of all the permissions required. This template is designed for infrastructure provisioning, ensuring that the necessary access roles, permissions and policies are properly configured. After generating the template, you can download it and upload it to your CSP Console to initiate the deployment. > [!NOTE] > **Tip** > > The download template approach is particularly useful for organizations that want to review their deployment configurations at a granular level before execution. |

### Steps 7, 8, 9: Asset discovery and pod launch

When you deploy a stack on your AWS cloud console, Securiti performs the following steps:

- **Creates IAM roles** to grant and manage permissions.
- **Initiates asset discovery** in the specified regions. If assets are found, it launches a pod for scanning purposes.

If Securiti **Cloud** is selected, all operations are conducted within the Securiti environment. If **My Cloud** is chosen, CloudFormation templates grant the necessary permissions to Securiti for pod deployment in your cloud infrastructure to scan your data.

> [!NOTE]
> **Note**
> 
> - The pod is deployed only in the regions where data assets are discovered, as specified in step 2.
> - To learn more about the permissions granted, see [Integrating Securiti with AWS](/latest/docs/integrating-securiti-with-aws).

Once the pod is deployed, the following scans are run on the discovered assets:

- Sensitive data scan
- Disk scan

In parallel with asset discovery, access entitlement scans, and cloud security posture scans are also triggered.

[Learn more about the permissions granted](/latest/docs/policies-and-permissions-required-for-aws-integration)

### Step 10: Create and activate data system connectors

Securiti automatically identifies and onboards discovered data systems by creating their instances on the platform. This removes the need for manually activating each data system. This automation is particularly useful for large enterprises with numerous data systems, as it streamlines the process and drastically reduces the time required for setup and integration.

> [!NOTE]
> **Note**
> 
> Instances are provisioned for selected self-hosted cloud services only. To view the complete list of supported services, see [List of supported cloud and SaaS services](/latest/docs/supported-cloud-native-services-for-posture-policy-rules).

![Overview of monitored data systems with active and inactive connectors listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-03 at 12.48.47 PM.png)

### Step 11: Run scans on each asset

Once Securiti creates instances of your data systems, it automatically initiates discovery scans to classify sensitive data across files, folders, tables, and views. This classification is crucial for identifying the type and location of data within the platform. With these insights, you can apply privacy and security controls tailored to the type of data discovered to mitigate the risk associated with it.

> [!NOTE]
> **Note**
> 
> Discovery scans are auto-initiated for selected cloud services only.

### Step 12: Visualize the asset and data scan results

| **SDI Dashboard** Securiti's platform offers dashboards that visualize discovery scan results, delivering insights into data elements, content profiles, and system associations for efficient data management. - Universal Data Explorer - Structured Data Discovery - Unstructured Data Scans - Streaming Data Discovery - Data Risk | ![Overview of data systems with hosting details and cloud service counts displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-03 at 12.54.44 PM(1).png) |
| --- | --- |
| **Reporting Dashboard** To view and create system and custom widgets for your specific requirements such as: - Data systems, Discovery scans, Classification | ![Overview of data security findings, highlighting risk severity and posture scores.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-03 at 3.34.29 PM.png) |
| **Data Command Graph** To view stats for your discovered data such as: - Discovered assets such as MySQL, SQL Server - Entities such as regions, accounts, sensitive data elements - Document types - Entities such as Data, Controls, and so on | ![Overview of data systems with asset types and scanned document statistics displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-03 at 3.36.51 PM.png) |
| **Graph Explorer** View relationships between different entities, such as discovery scans, data systems, content profiles, and so on, Security offers the Graph Explorer dashboard where you can create widgets and view discovered assets. | ![Graph Explorer interface displaying accounts and data systems with Oracle Cloud hosting.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-03 at 12.58.38 PM.png) |
| **Findings** View the results of the posture scan to understand the misconfigurations associated with your IaaS and SaaS configurations and auto-remediate them using the Securiti platform. | ![Dashboard displaying security posture findings and statistics for open and resolved issues.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-03 at 3.27.37 PM.png) |

### Step 13: IaaS Connectors API Documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The IaaS Connectors API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without needing to set up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/cloud-systems/apidocs/index.html) | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **Download the postman collection** We also provide Postman collections for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that lets you quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/cloud-systems/apidocs/index.html) | ![iaas-cloud-postman-collection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b51cbfda-c5d7-d187-2ea4-f27bb96f3135.png) |

## Related

- [Integrating Securiti with AWS](/integrating-securiti-with-aws.md)
- [Integrating Securiti with Google Cloud Platform](/integrating-securiti-with-google-cloud-platform.md)
- [Integrating Securiti with Microsoft Azure](/integrating-securiti-with-microsoft-azure.md)
- [Integrating Securiti with Oracle Cloud Infrastructure](/integrating-securiti-with-oracle-cloud-infrastructure.md)
