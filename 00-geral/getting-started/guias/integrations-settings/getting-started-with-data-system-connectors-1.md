---
title: "Getting Started with Data System Connectors"
slug: "getting-started-with-data-system-connectors-1"
updated: 2026-08-20T11:23:59Z
published: 2026-08-20T11:23:59Z
canonical: "helpcenter.securiti.ai/getting-started-with-data-system-connectors-1"
stale: true
area: geral
modulo: getting-started
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Data System Connectors

Securiti offers more than 250 connectors, letting you connect your data systems to the platform for your privacy, data security, and AI governance needs. Configuring connectors for your data systems is a prerequisite to retrieving the data and metadata required by Securiti modules such as Sensitive Data Intelligence, Data Access Governance, Data Mapping Automation, Data Subject Rights, etc.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Data%20Systems%20&amp;%20Connectors.drawio(2).svg)

### Step 1 - Access connector configuration

To access data system connectors configuration:

1. On the Securiti **Dashboard** in the left side navigation, click **Main Menu** icon.
2. On the **New Navigation** sidebar, choose **Settings** > **Data Systems**.

![acces-DS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9e9c2915-f6be-066a-147c-315e8067bb1c(1).png)

### Step 2 - Choose your type of data system connector

You can select the following types of connector categories on the **Integrations** page.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Monitored DS(1).png) | **Monitored** The **Data Systems** page is where you configure connectors that integrate with the source data system to retrieve metadata, perform data scanning and classification, perform data subject requests, and take remediation action in your source data systems. [Learn more.](/v1/docs/configuring-connectors-for-monitored-data-systems) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Unmonitored DS(1).png) | **Unmonitored** The Unmonitored page lets you add data systems that Securiti does not connect to for metadata and data extraction. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. You configure unmonitored data systems in Securitis Data Mapping Automation module. [Learn more.](/latest/docs/managing-data-system-connectors) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/CMDB Systems.png) | **CMDB systems** CMDB data systems store information on the configuration of items like hardware, software, systems, facilities, and even personnel.. Securiti connects to CMDB systems and identify data mapping assets from the CMDB systems. You can synchronize Securiti with a ServiceNow instance to import assets from ServiceNow into the Catalog in the Data Mapping Automation module. [Learn more.](/v1/docs/using-data-mapping-automation) |

For **Monitored** and **User-Defined** data systems, move to step 3, and choose the data system type.

### Step 3 - Choose data system type

#### Monitored data system connector

To access the **Monitored** data system connector, choose **Integrations** > **Monitored**. Monitored data system connectors are classified depending on the Pod type. These connectors are classified into:

- Self-hosted connector
- Securiti Cloud connector

**Data system classification**

Monitored data system connectors (Self-hosted and Cloud) are classified into categories depending on the data structure of the underlying system and the type of connectors that we support for those data systems. For Self-hosted and Cloud connectors, you can see the following types of data systems.

| **Structured** Data systems organize and store data in a predefined manner based on a schema, typically using tables with rows and columns. Examples include AWS S3, Azure Blobs, Box, etc. [Learn more](/latest/docs/managing-data-system-connectors). | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Structured Data Discovery .png) |
| --- | --- |
| **Unstructured** Unstructured data systems store file and object data that does not follow a structured schema. Examples include SharePoint Online and SMB File Servers. [Learn more](/latest/docs/managing-data-system-connectors). | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Unstructured Data Discovery.png) |
| **Hybrid** Connect your hybrid data system to Securiti to perform Sensitive Data Intelligence, DSR, and other modules tasks. Hybrid data systems contain both structured and unstructured data. Some examples include JIRA, Zendesk, and Workday. [Learn more](/latest/docs/managing-data-system-connectors). | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Hybrid Data Discovery(1).png) |
| **Streaming** Connect your data systems that transmit data continuously or in real-time. Data systems that transmit data continuously or in real-time. An example of a streaming data system is Apache Kafka. [Learn more](/latest/docs/managing-data-system-connectors). | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Streaming Data Discovery.png) |
| **Scanless DSR support** Connect your Scanless data system to Securiti. For DSR use cases, some of our connectors support data systems that do not undergo data scanning, as Securiti can query them in real-time via API. Examples of scanless DSR connectors include Twilio, Alation, and Okta. [Learn more](/latest/docs/managing-data-system-connectors). | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Scanless.png) |

#### Choose User-Defined data system connector

If you want to connect a connector based on your defined APIs and configuration, you can choose the data system type. To access the User-Defined systems, click **User-Defined** in the left sidebar.

**User-Defined** data systems are classified on Pod types. Choose the preferred Pod type on the **User-Defined Data Systems** page.

- Self-hosted Webhooks
- Securiti Cloud Webhooks

![user-defined.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b71fa75b-7256-2532-ce24-c00acc320eaf.png)

### Step 4 - Create a connector to a data system instance

To create a connector to a data system instance, on the **Integrations** page, click **Add Integration**, and choose your data system.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Instance Creation..png) | **Create an instance in Monitored data system connectors** When creating an instance for your data system, you can select where the data system is hosted and the location where the data system is deployed for use in data mapping. You can select the owner and co-owners while creating a data system connector. [Learn more](/v1/docs/configuring-data-system-ownership). |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 11.02.31 AM.png) | **Create an instance in User-Defined connectors** User-Defined systems connect to Securiti through APIs. You need to select the hosting country and region in order to leverage location based features in the Securiti platform. You can select the owner and co-owners while creating a data system instance. [Learn more.](/v1/docs/user-defined-webhooks-connectors) |

After configuring the hosting location and co-owners in the **Basic Information** tab, click **Create Instance & Continue**.

### Step 5 - Authenticate and activate the connector

When you create a data system instance, it redirects you to the **Connector** tab of the connector configuration UI. Securiti asks you to enter the authentication credentials with the appropriate permissions required for your specific module use cases. The types of supported authentication methods and the permissions required of the credentials are different for each data system. See the data system-specific documentation for those details.

#### Prerequisites for connector activation

| **Authentication types** Different data system connectors require different types of authentication methods such as Basic, IAM Role, Account Key, etc. You can view the list of supported data system connectors and their authentication types. [Learn more](/v1/docs/supported-data-system-connectors-in-securiti) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Authentication Types.png) |
| --- | --- |
| **Obtain authentication credentials and assign permissions** Create an application or server for the data system and assign permissions to the application or server to access the various Securiti modules. Obtaining credentials method varies depending on the application type, such as SQL, SAAS, IAAS, and Streaming. See the example for obtaining authentication credentials in the SharePoint Online application. [Learn more.](/v1/docs/microsoft-365-sharepoint-online-connectors) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Authentication Credentials.png) |
| **Activate the connector** Provide the credentials used to authenticate the connector with the appropriate level of permissions required of your module use case as defined in the individual connector documentation. For example, GitHub's Self-hosted data system requires you to add the Client ID and Client Secret generated in the GitHub account. [Learn more.](/v1/docs/create-an-application-and-obtain-authentication-credentials-in-github) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Authentication Credentials(1).png) |

### Step 6 - Configure Module Settings in the connector Permissions tab

After activating the connector, click the **Permissions** tab to configure module-related settings. Securiti shows only those module settings in the **Permissions** tab that are supported for a specific data system.

After activating the connector, on the side panel under **Configurations** section, Securiti shows only those module settings that are supported for a specific data system.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/DSR Scan(2).png) | **Data Subject Rights Settings** Include the respective data system in processing the Data Subject Rights (DSR) request by enabling the toggle for **DSR Scan**. You can include the specific data in DSR workflow, DSR automation, and assign guest users for DSR subtasks. [Learn more](/v1/docs/setting-up-data-systems-for-dsr-automation). |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/DSPM(2).png) | **Security Posture Scan Setting** Configure a Security Posture scan for your data system if it is supported. Running posture scans on the data system checks for any policy violations and performs automated remediation of misconfigurations. You have an option of auto and manual scan. [Learn more](/latest/docs/using-security-posture-management). |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/DSPM(2).png) | **Data Scan Policy Setting** For Securiti connectors, you configure the scanning of the data system directly in the General permissions tab. You can configure scan intervals, auto or manual scans, and the scope of data objects you want to scan. [Learn more.](/latest/docs/configuring-and-assigning-content-scan-profiles) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Data Access Control.png) | **Data Access Governance setting** Enable Data Access Control and Data Access Intelligence features from the Permissions tab for the specific data system. See the Data Access Governance documentation for additional prerequisites required for Access Intelligence and Access Control. [Learn more.](/v1/docs/data-access-governance-dag-overview) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Breach Analysis(1).png) | **Breach setting** Enable the **Breach** to allow Securiti to run a breach analysis for your data system. This option appears if it is supported for the specific data system. [Learn more.](/v1/docs/using-the-data-breach-management-dashboard) |

### Step 7 - Perform scans for your data system connector

After activating the connector, Securiti lets you scan your data systems to discover sensitive information like PII, PHI, PCI, and data subject to regulations like GDPR. Different scan types are supported for Securiti Cloud-hosted connectors and self-hosted data system connectors.

| **Initiate Discovery scan** Initiate a Discovery scan for your data systems connected via self-hosted connectors from the **Overview** tab. You use discovery scans to target specific data systems, looking for specific data elements, on specific schedules, by specific data owners, etc.. [Learn more.](/v1/docs/using-the-data-systems-overview-dashboard) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Discovery Scan.png) |
| --- | --- |
| **Run Inventory sync** Run the Inventory sync for your data systems connected via self-hosted connectors on the **Inventory** tab. Securiti performs an Inventory metadata scan after the connector activation process to build an inventory of the data resources in the data system. [Learn more.](/v1/docs/data-inventory-sync-for-self-hosted-connectors) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Inventory Scan.png) |
| **Initiate Data scan** Initiate a Data scan for your Cloud-hosted data system under the **General** tab. The scan is performed in two phases: - Initial scan - Ongoing Delta scans [Learn more.](/v1/docs/initiate-data-scanning-for-front) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Data Scan Policy(2).png) |
| **View DSR module for DSR requests** After including your structured or unstructured data system in the DSR workflow. You can visit the DSR module to initiate a DSR request for scanless connectors and other DSR-supported connectors. [Learn more.](/v1/docs/dsr-workbench-overview) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/DSR Scan(4).png) |

After performing the scans, you can view the results on the following dashboards.

- [Sensitive Data Intelligence Dashboard](/v1/docs/using-sensitive-data-intelligence)
- [Graph Explorer](/v1/docs/using-graph-explorer)
- [Data Command Graph](/v1/docs/using-data-command-graph)
- [Inventory](/v1/docs/using-inventory)
- [Reporting](/v1/docs/using-graph-reporting-dashboards)

### Step 8 - View error logs and reports

Securiti lets you view the Permission Statuses and error logs under the **Acitivity Log** tab for your selected data system connector.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Diagnostic Report(1).png) | **View Diagnostic Report** After activating the connector, you can view the **Diagnostic Report** under the **Overview** tab. The auto-diagnostic report helps you identify problematic areas in the connector configuration. [Learn more](/v1/docs/auto-diagnostic-reports-in-data-system-connectors). |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Activity Log(4).png) | **View Activity Log** Use the **Activity Log** page filter to select the connector’s activity for your data system connector. You can view detailed messages on processes, configuration changes, and errors [Learn more](/v1/docs/using-connector-audit-logs). |

### Data System Connectors API Documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The Data System Connector API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This allows you to quickly test endpoints and view API responses without needing to set up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/connectors/apidocs/index.html) | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **Download the Postman collection** We also provide a Postman collection for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that let you quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/connectors/apidocs/index.html). | ![API-SC.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e296ed45-2317-f5b4-9ecd-6f72c1a203b6.png) |
