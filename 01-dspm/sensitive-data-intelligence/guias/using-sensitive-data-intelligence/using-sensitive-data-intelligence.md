---
title: "Using Sensitive Data Intelligence"
slug: "using-sensitive-data-intelligence"
status: "update"
updated: 2026-05-06T13:13:09Z
published: 2026-05-06T13:13:20Z
canonical: "helpcenter.securiti.ai/using-sensitive-data-intelligence"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using Sensitive Data Intelligence

Securiti platform includes a wide range of technologies for sensitive data detection that includes powerful Artificial intelligence (AI) and Machine learning (ML)detection techniques. Your requirements may vary as to whether you intend to detect sensitive data or classify data as sensitive. Sensitive Data Intelligence (SDI) helps you identify and document where data resides inside your organization and how it is processed internally or when shared with third-party companies.

Your organization may hold personal data attributes such as demographic, financial, health, and location information. There is also a tendency to hold onto data for longer periods of time to analyze historical patterns and identify trends to offer better and more targeted products. In some cases, it is simply too hard to identify and dispose of legacy data.

Securiti can discover hundreds of personal and sensitive data attributes in your data assets, such as:

- Names
- Phone numbers
- Email addresses
- Credit card numbers
- Social security numbers
- Medical IDs

Securiti automatically classifies structured data showing types and volume of personal data present in database tables and columns, and detects sensitive files (among unstructured data) such as financial statements, RFPs, invoices, source codes, etc.

### Why Sensitive Data Intelligence

Due to digital transformation and exponential growth in data, such as personally identifiable information (PII), financial records, intellectual property, and other sensitive information, safeguarding data becomes critical, as it is also due to the multiple risks associated with it. This requires critical thinking to mitigate the security risks and privacy breaches. You must have deep insights into the volume and type of sensitive and personal data stored across your multi-cloud environment. In addition, newer global regulations have been introduced to identify and regulate sensitive data. All of this puts a tremendous strain on traditional data discovery since it was not designed to work at scale.

Here comes the need for SDI, which refers to the systematic approach of gathering, analyzing, and managing sensitive information within an organization to ensure its confidentiality, integrity, and availability. SDI is purpose-built to operate at a petabyte scale and supports any self-hosted multi-cloud and SaaS environments. Major aspects of data that AI/ML-based SDI covers:

| Feature | Description |
| --- | --- |
| Multi-cloud Asset Discovery | Discover native, non-native, and dark data assets across environments such as Amazon Web Services (AWS), Microsoft Azure, Google Cloud Platform (GCP), or others. |
| Visibility into Sensitive Data | SDI provides organizations with full visibility into sensitive data, and you can gather and build a catalog of all managed and shadow assets as well as their owners, locations, security, and governance measures enabled on the data. |
| Data catalogs | SDI helps discover and build a central catalog of all data assets, including cloud-native and non-native, on-premises, and multi-cloud structured, unstructured, and streaming. Data catalog helps administrators find specific data attributes with their locations in columns, tables, databases, or specific folders (in case of unstructured data) within minutes. In this way, administrators can determine if a particular data attribute is appropriately protected or enforce required policies to enable protection. |
| Data discovery | Securiti platform leverages Artificial Intelligence / Machine Learning (AI/ML) tools and technologies to discover and maintain sensitive data across their networks, databases, and storage systems. With the help of discovery scans, you can run the scans across all different types of data systems based on multi-cloud SaaS, IaaS, or private cloud storage. |
| Identification and classification of sensitive data | SDI has the capability to classify structured and unstructured data which involves identifying and classifying sensitive data within the Securiti platform. Leverage Securiti’s built-in AL/ML based detection and content classification methods, such as data elements, document types, content profiles, etc. Fully customize the detection parameters as per your needs. |
| People data graph | Customizing your cookie banner and preference center |
| Data labeling policies | The data labeling policy lets you apply metadata tags to files in your unstructured data systems based on the data classification results. You can use these tags with network and endpoint protection solutions like firewalls, proxies, Data Loss Prevention (DLP), and similar, to enforce access control. You can seamlessly apply metadata tags to files within your unstructured data systems, from the outcomes of data classification. This will elevate your data protection strategy with precision and ease. |
| File insights policies to enforce quarantine and retention policies | With the file quarantine policy, you can quarantine files that might be suspicious or potentially dangerous, identified through various security mechanisms such as antivirus scans, intrusion detection systems, or other threat detection tools. Instead of allowing these files to execute or spread throughout the network, they are isolated and placed in a quarantine area. Additionally, you can identify files based on the relative data filters to see files older than a certain period or modified at a specific time. |
| Structured Data Insights policies | With the structured data insights policy, you can create policies to identify sensitive data in tables and columns from the structured data systems. |
| Data risk | Securiti platform conducts risk assessments to evaluate the potential threats and vulnerabilities associated with sensitive data. This helps in determining the level of protection required and allocating resources accordingly. |
| Reporting dashboards | Securiti platform has dashboards for reporting sensitive information, such as structured, unstructured, and streaming data dashboards. |

### How you can use the SDI module

The following table lists the actions you can perform.

| Purpose | Description |
| --- | --- |
| Set up Pods or Elastic Pods to let Securiti perform scans. | [Set up Pods or Elastic Pods](/v1/docs/securiti-pods-and-elastic-pods) for self-hosted data systems. |
| Connect structured, unstructured, or streaming data systems in your environment for monitoring. | [Activate the connectors](/v1/docs/managing-data-system-connectors) |
| Create discovery scans to identify personal or sensitive information. | Perform data discovery on data assets and SaaS applications. See ([Structured](/v1/docs/discovery-scans), [Unstructured](/v1/docs/discovery-scans), [Streaming](/v1/docs/discovery-scans))/[Table training](/v1/docs/table-training-for-structured-and-hybrid-data-systems) |
| Review, edit, and validate structured data classifications. | [Using the validation workbench for structured data](https://helpcenter.securiti.ai/docs/using-the-validation-workbench-to-review-and-validate-classifications) |
| Detect data elements using discovery scans | [Configuring system](/v1/docs/customizable-system-data-element-types) and [custom data elements](/v1/docs/configuring-custom-data-element-types) |
| Content profiles to detect documents containing any specific data elements. | [Configure content profiles](https://helpcenter.securiti.ai/docs/configuring-content-profiles) |
| Configure document categories supported by Securiti platform | [Configuring document categories](/v1/docs/configuring-document-categories-and-types) |
| Configure file formats | [Configuring file formats](/v1/docs/configuring-file-formats) |
| Configure cluster analysis to detect duplicate and near-duplicate documents | [Detect and reduce duplicate and near-duplicate documents](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data) |
| Configure scan profiles to improve scanning performance by excluding files that are unlikely to contain personal data. | [Configure scan profiles](https://helpcenter.securiti.ai/docs/configuring-and-assigning-content-scan-profiles) |
| Identify sensitive data by using exact data indexes and profiles. In exact data indexes, you can identify the columns to include in the index and whether they are primary identifiers. You can then include the index in an exact data profile. | [Using Exact Data Indexes and Profiles](/v1/docs/using-exact-data-indexes-and-profiles) |
| Data labeling policies let you apply metadata tags or labels to files in your unstructured data systems based on the results of Securiti data classification. You can use these tags or labels to enforce access control and categorize your files or documents. You can apply Microsoft Purview labels to files in Amazon S3, Azure Files, Microsoft 365 OneDrive, Microsoft 365 SharePoint Online, and SMB. Additionally, you can apply Google Drive labels to files in Google Drive using our Data Command Graph search capability. | [Configuring Data Labeling Policies](/v1/docs/configuring-data-labeling-policies) |
| The File Insights policy lets you see the important information related to files available in your data system storage, and what kind of sensitive data they contain. In the File Insights policy, you can configure auto-quarantine and on-demand action to quarantine files. You can also define the retention time of sensitive documents or infected files. | [Configuring File Insights Policies](/v1/docs/configuring-file-insights-policies) |
| The Automation policy lets you create tickets in ServiceNow and Jira to address issues found in posture, compliance tests, Gencore firewalls, and file findings. You can also send email notifications to relevant users in your team. Additionally, you can generate posture and compliance test findings in the Google Cloud Security Command Center (SCC). | [Configuring Automation Policies](https://helpcenter.securiti.ai/docs/configuring-automation-policies) |
| Structured Data Insights policy lets you identify and manage findings for your structured data using Graph Explorer to generate queries and get findings based on the tables and columns of your structured data. | [Configuring Structured Data Insights policies](/v1/docs/policies-configuring-structured-data-insights-policies) |
| View statistics on reporting dashboards. | View statistics related to the sensitive data in [structured](https://helpcenter.securiti.ai/v1/docs/discovery-scans), [unstructured](https://helpcenter.securiti.ai/v1/docs/discovery-scans), and [streaming](https://helpcenter.securiti.ai/v1/docs/discovery-scans) data discovery. |
| Validation Workbench to review and validate classifications for structured data | [Using the Validation Workbench to review and validate classifications](https://helpcenter.securiti.ai/docs/using-the-validation-workbench-to-review-and-validate-classifications) |

## Related

- [Getting Started with Sensitive Data Intelligence](/getting-started-with-sensitive-data-intelligence.md)
- [Policies](/policies.md)
- [Discovery scans](/discovery-scans.md)
