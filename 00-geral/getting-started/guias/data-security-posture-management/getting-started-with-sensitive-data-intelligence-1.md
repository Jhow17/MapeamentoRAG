---
title: "Getting Started with Sensitive Data Intelligence"
slug: "getting-started-with-sensitive-data-intelligence-1"
updated: 2026-10-08T02:56:49Z
published: 2026-10-08T02:56:49Z
canonical: "helpcenter.securiti.ai/getting-started-with-sensitive-data-intelligence-1"
area: geral
modulo: getting-started
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Sensitive Data Intelligence

Sensitive Data Intelligence lets you run discovery scans across your multi-cloud environment and visualize the post-scan analytics. This can help you understand where sensitive data is located in your cloud across various regions and assess the associated risks. With this insight, you can perform necessary data privacy, security, compliance, and governance operations to ensure your data remains safe and secure.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/SDIDataDiscovery_gettingstarteddiagram.drawio.svg)

### Step 1 - Connect your Data System

Integrate your unstructured, structured and streaming data systems, such as MySQL, SharePoint, and Kafka, with Securiti by providing the necessary permissions. This integration makes your Data systems eligible for scans, ensuring full visibility into all types of data across your files, tables, and topics.

> [!NOTE]
> **Note**
> 
> Securiti offers out-of-the-box integration for over 300 SaaS and self-hosted platforms.

[Learn more about connecting your data system](/v1/docs/managing-data-system-connectors)

### Step 2 - Configure classifications to define scan criteria

Securiti offers various features to ensure that your scanning efforts are on point. Set up the relevant options as shared below.

Please note that Securiti offers default options for all these features. Adding more to it is optional.

| ![dePage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c6371271-1868-3685-a02c-212a52f35659.png) | **Data Elements** Securiti offers hundreds of default data elements, such as email, phone numbers, and date of birth, for classification. If a specific data element you need to classify is not available in the default list, you can create a custom data element so it can be included in the scan criteria and detected. [Learn more](/v1/docs/data-elements) |
| --- | --- |
| ![dcPage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a994f724-2e20-782a-935b-1ab7bebab1d0.png) | **Document Categories** Securiti offers several file categories to choose from, such as bank statements, credit card images, and birth certificates. You can also create a custom file category of your choice. [Learn more](/v1/docs/configuring-document-categories-and-types) |
| ![cpPage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e4e064c8-4b45-d186-bd0d-b20d2f8618c6.png) | **Content Profiles** Securiti offers content profiles such as PCI DSS, GDPR, etc., to help you create file-level content-matching policies. These profiles assist you in identifying and managing data according to the requirements of the selected regulation. [Learn more](https://helpcenter.securiti.ai/docs/configuring-content-profiles) |
| ![edpPage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c26516c1-d1fe-add6-3094-0e2b937bd540.png) | **Exact Data Profiles** An Exact Data Index helps detect sensitive data like bank account numbers and SSNs by matching actual values, reducing false positives, and improving accuracy. You define the exact data index to scan and create an Exact Data Profile using that index for use in discovery scans. This ensures that Securiti looks only for the exact matches you specified. [Learn more](/v1/docs/using-exact-data-indexes-and-profiles) |

To learn more about configuring classification types, refer to:

- [Data dictionaries](/v1/docs/configuring-dictionaries)
- [File formats](/v1/docs/configuring-file-formats)
- [Scan profiles](https://helpcenter.securiti.ai/docs/configuring-and-assigning-content-scan-profiles)
- [Scan categories](/v1/docs/configuring-custom-scan-categories)

### Step 3 - Run a Discovery Scan to discover sensitive data

Pick the scan mechanism to run the discovery scan:

| [Embedded content](https://player.vimeo.com/video/823707271) | **Discovery scan** Discover [duplicate documents](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data) and sensitive data across all sorts of self-hosted and SaaS platforms. It is available for structured, unstructured, and streaming data systems, ensuring comprehensive visibility. [Learn more](/v1/docs/discovery-scans) |
| --- | --- |

### Step 4 - Review Scan Results

In the SDI module, you can see dashboards for structured, unstructured, and streaming data explorers to review the respective discovery scan results. In Graph Explorer, you can also view classification and scan results according to data systems or any other criteria.

| ![gsCollectEvidence.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f30d89b9-435e-683c-30d1-3d681bc597c1.png) | **Discovery Scan Evidence** For your scan jobs, you can view the evidence on the discovery scan pages that take you to the cloud platforms to view the evidence. This evidence includes information about data elements and content profiles discovered. [Learn more](/v1/docs/discovery-scans) |
| --- | --- |
| [Embedded content](https://player.vimeo.com/video/846177351) | **Structured Data Discovery** **New Experience** View the discovery scan results associated with your structured data systems, such as MySQL, Snowflake, Oracle, and so on. You can perform bulk edits on classification. > [!NOTE] > **Note** > > If Structured Data Explorer New Experience feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. [Learn more](https://helpcenter.securiti.ai/docs/structured-data-discovery-new-experience) |
| [Embedded content](https://player.vimeo.com/video/1101564765) | **Validation Workbench** The Validation Workbench allows you to quickly review and validate a random sample of classified data, confirm or correct labels, and track classification accuracy using intuitive analytics dashboards. By using this tool, you can streamline your validation process and increase confidence in the accuracy of automated classifications. [Learn more](https://helpcenter.securiti.ai/docs/using-validation-workbench-to-review-and-validate-classifications) |
| [Embedded content](https://player.vimeo.com/video/847939614) | **Unstructured Data Discovery** View the discovery scan results associated with your unstructured data systems, such as Amazon S3, Alfresco, Microsoft 365 SharePoint, apply quick filters, and so on. [Learn more](https://helpcenter.securiti.ai/docs/using-the-unstructured-data-discovery) |
| [Embedded content](https://player.vimeo.com/video/846177351) | **Streaming Data Discovery** View the discovery scan results associated with your streaming data systems, such as Kafka, Confluent Kafka, and Amazon MSK. [Learn more](https://helpcenter.securiti.ai/docs/using-the-streaming-data-discovery-dashboard) |
| ![gePage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0e0ab916-596a-dc73-0297-1df7211ea1da.png) | **Graph Explorer** View relationships between different entities, such as discovery scans, data systems, content profiles, and so on,Securiti offers the Graph Explorer dashboard, where you can create widgets and view discovered assets. [Learn more](/v1/docs/using-graph-explorer) |

### Step 5 - Validate Classification Results / Fine-tuning Discovery Scan

This step is essential for ensuring that sensitive information, such as personally identifiable information (PII), financial data, or intellectual property, is in compliance with regulatory standards and organizational policies. You need to validate classification results for your structured, unstructured, and streaming data systems to see whether you have the expected sensitive data identified during the discovery scan jobs. In case of issues, you can go back to Step 2 to reconfigure classification types and make changes to discovery scans in Step 3.

For more information, see [Classification Validation and Fine-tuning Discovery Scans](/v1/docs/classification-validation-and-fine-tuning-discovery-scans).

### Step 6 - Apply Data Privacy and Security Policies to Remediate Risks (Structured and Unstructured Data)

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-05 at 3.14.28 PM.png) | **Data Labeling Policy** To apply sensitivity data labels to your files in your unstructured data systems based on the results of Securiti's data classification. Securiti integrates with Microsoft Purview Information Protection labeling and Google Drive labeling to apply the sensitivity labels to files and documents as per your requirements. **Example** Imagine a healthcare provider handling a large volume of patients' sensitive information, such as medical records. They have a significant responsibility to keep this data safe and comply with strict privacy rules under HIPAA. To manage this, they use a system to classify the data. For instance, they might label certain patient records as "Highly Confidential," helping them identify which data requires extra protection. [Learn more](https://helpcenter.securiti.ai/docs/configuring-data-labeling-policies) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-05 at 3.15.10 PM.png) | **File Insights Policy** You can create a file insights policy that leverages previously scanned data, allowing you to quickly identify files with specific data elements, skipping the need to perform scans repeatedly. You can also quarantine your files to move or quarantine files containing sensitive information or infected files to a new location of your choice. > [!NOTE] > **Note** > > If the File Insights policy feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. **Example** For example, consider students' grade report data placed in different files on SharePoint, and you want to identify sensitive information. For this purpose, you can create a file insights policy to see such details and apply quarantine and retention policies as well. [Learn more](https://helpcenter.securiti.ai/docs/using-file-insights-policies) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-05 at 3.16.03 PM.png) | **File Quarantine Policy** You can create a file quarantine policy to automatically identify and isolate files containing sensitive, non-compliant, or risky information. You can quarantine files by moving them to a secure location within the same data system or to a centralized quarantine destination, helping prevent unauthorized access and reduce exposure risks. > [!NOTE] > Note > > If the File Quarantine policy feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. **Example** For example, consider confidential financial reports stored across multiple folders in SharePoint that contain sensitive data such as account numbers or personally identifiable information (PII). You can create a file quarantine policy to automatically identify such files and move them to a secure quarantine location, ensuring that sensitive data is protected and access is restricted. [Learn more](https://helpcenter.securiti.ai/docs/using-file-quarantine-policies) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-05 at 3.16.36 PM.png) | **File ROT Policy** You can create a file ROT (Redundant, Obsolete, Trivial) policy to identify files that are no longer needed based on retention and lifecycle criteria. You can take actions such as quarantining or managing outdated files, enabling efficient data cleanup and reducing storage costs while minimizing risk associated with over-retained data. > [!NOTE] > Note > > If the File ROT policy feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. **Example** For example, consider outdated project files stored across multiple locations in SharePoint that have not been accessed or modified for several years. You can create a file ROT policy to identify such obsolete files based on last accessed or modified dates and take appropriate actions such as quarantining or removing them to maintain data hygiene. [Learn more](https://helpcenter.securiti.ai/docs/using-file-rot-policies) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-05 at 3.17.10 PM.png) | **Data Tagging Policy** You can create a data tagging policy to apply or remove tags on data assets based on defined conditions. You can use tags to categorize data based on sensitivity, business context, ownership, or other attributes, helping improve data visibility, governance, and policy enforcement across your environment. > [!NOTE] > Note > > If the Data Tagging policy feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. **Example** For example, consider datasets stored across multiple systems that contain sensitive information such as PII or financial data. You can create a data tagging policy to automatically tag these datasets as “Sensitive” or “Confidential,” making it easier to identify, manage, and apply further controls such as retention or quarantine policies. [Learn more](https://helpcenter.securiti.ai/docs/configuring-data-tagging-policy) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-05 at 3.17.51 PM.png) | **Structured Data Insights Policy** Structured Data Insights policy lets you identify sensitive data across structured data systems in tables and columns. > [!NOTE] > **Note** > > If the Structured Data Insights policy feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. **Example** A financial organization wants to make sure its customer data is properly categorized and structured. Using this policy, the organization scans its database metadata to identify anomalies, such as transaction records missing key attributes or being stored in incorrect tables. [Learn more](/v1/docs/policies-configuring-structured-data-insights-policies) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-05 at 3.18.18 PM.png) | **Automation Policy** The Automation policy lets you create tickets in ServiceNow and Jira to address issues found in posture, compliance tests, Gencore firewalls, and file findings. You can also send email notifications to relevant users in your team. > [!NOTE] > **Note** > > > > If the Automation policy feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. **Example** Set up an automation policy and create a ServiceNow or Jira ticket to turn on encryption for an AWS Redshift Cluster and assign it to the relevant team member. [Learn more](https://helpcenter.securiti.ai/docs/configuring-automation-policies) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-05 at 3.18.59 PM.png) | **Metadata Registration Policy** ​Metadata Registration Policies provide a policy-based approach to registering metadata from structured data systems into the Alation data system, eliminating the need for traditional discovery scans. Metadata registration occurs according to specified conditions and criteria. > [!NOTE] > **Note** > > > > If the Metadata Registration policy feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. **Example** ​If your organization wants to register metadata for all "Quarterly Sales" tables in a financial data warehouse without a full discovery scan, you configure the Alation connector, create a Metadata Registration Policy targeting tables with names or columns related to sales, use graph-powered queries to narrow the scope to the sales schema, and specify the data warehouse as the target; when run, the policy registers the matching metadata for immediate use in Alation. [Learn more](https://helpcenter.securiti.ai/docs/configuring-metadata-registration-policies) |

#### Other Policies

There are the following policies that you can also configure to get more benefits and view valuable insights:

- [Security Posture Policy](https://helpcenter.securiti.ai/docs/security-posture-policies-and-findings)
- [Structured Data Insights Policy](https://helpcenter.securiti.ai/docs/policies-configuring-structured-data-insights-policies)
- [Cross Border Transfer Policy](https://helpcenter.securiti.ai/docs/cross-border-transfer-policies)
- [Data Access Control Policy](https://helpcenter.securiti.ai/docs/data-access-control-policies)

### Step 7 - View all Policy Findings

You can view the relevant policy findings on their page.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-05 at 3.19.28 PM.png) | **Cross Border Transfer Findings** Quickly identify cross-border data access risks and potential compliance violations based on global regulations. > [!NOTE] > Note > > If the Cross Border Transfer policy feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. [Learn more](https://helpcenter.securiti.ai/docs/cross-border-transfer-policies) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-05 at 3.21.44 PM.png) | **Security Posture Findings** Quickly identify security misconfigurations, vulnerabilities, and compliance risks across your cloud and SaaS environments. > [!NOTE] > **Note** > > If the Security Posture Findings feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. [Learn more](https://helpcenter.securiti.ai/docs/security-posture-policies-and-findings) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-05 at 3.21.56 PM.png) | **Test Findings** Quickly identify compliance violations and control failures across your data environment. Monitor test results in real time to detect risks, prioritize remediation, and maintain compliance with regulatory frameworks. > [!NOTE] > Note > > If the Test Findings feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and meets eligibility requirements. [Learn more](https://helpcenter.securiti.ai/docs/test-findings) |

### Step 8 - View Results in the Data Remediation dashboards

You can view the results of your Data Labeling, File Insights, File Quarantine, and File ROT policies in their respective Data Remediation dashboards.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-18 at 2.56.25 PM.png) | **Data Labeling Remediation dashboard** The Data Labeling Remediation dashboard gives you a consolidated view of all files scoped by your Data Labeling policies and your overall labeling activity. You can view the total number of files in scope, how many you have labeled, how many Securiti labeled, how many carry externally applied labels, and how many your selected policy labeled, along with their respective volumes. You can also manually label files, remove labels, remediate files, and export your results directly from the dashboard. 2:35 AM ## [Learn more](https://helpcenter.securiti.ai/docs/using-data-remediation-dashboards) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-18 at 2.56.58 PM.png) | **File Insights Remediation dashboard** The File Insights Remediation dashboard gives you a consolidated view of all files scoped by your File Insights policies. You can view the total number of files in scope, how many you have quarantined, and how many you have reverted, along with their respective volumes. You can also search for files by name, apply filters, browse by folder, and take actions such as Remediate, Remove Remediation, and Export on your selected files. [Learn more](https://helpcenter.securiti.ai/docs/using-data-remediation-dashboards) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-18 at 2.57.35 PM.png) | **File Quarantine Remediation dashboard** The File Quarantine Remediation dashboard gives you a consolidated view of all files scoped by your File Quarantine policies. You can view the total number of files in scope, how many you have quarantined, how many you have reverted, how many your selected policy quarantined, and how many your selected policy reverted, along with their respective volumes. You can also take actions such as Quarantine, Revert, Remediate, Remove Remediation, and Export on your selected files. [Learn more](https://helpcenter.securiti.ai/docs/using-data-remediation-dashboards) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-18 at 2.58.05 PM.png) | **File ROT Remediation dashboard** The File ROT Remediation dashboard gives you a consolidated view of all files scoped by your File ROT policies. You can view the total number of files in scope, how many you have quarantined, how many you have reverted, how many your selected policy quarantined, and how many your selected policy reverted, along with their respective volumes. You can also apply filters based on conditions such as data system type, file format, and file modified time to identify and manage your redundant, obsolete, and trivial files. [Learn more](https://helpcenter.securiti.ai/docs/using-data-remediation-dashboards) |

#### Sensitive Data Intelligence Module API Documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without needing to set up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-intelligence/apidocs/index.html#section/Getting-Started) | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **Download the Postman collection** We also provide a Postman collection for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that let you quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-intelligence/apidocs/index.html#section/Getting-Started/Import-Postman-Collection) | ![SDIpostmanCollection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8adff8b8-52c9-0cc7-31f9-7b6c763c366f.png) |

## Related

- [Data classifications](/data-classifications.md)
- [Discovery scans](/discovery-scans.md)
- [Policies](/policies.md)
