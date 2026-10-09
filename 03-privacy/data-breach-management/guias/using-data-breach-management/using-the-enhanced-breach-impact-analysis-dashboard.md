---
title: "Using the enhanced breach impact analysis dashboard"
slug: "using-the-enhanced-breach-impact-analysis-dashboard"
status: "update"
updated: 2025-11-04T18:24:21Z
published: 2025-11-04T18:24:21Z
canonical: "helpcenter.securiti.ai/using-the-enhanced-breach-impact-analysis-dashboard"
area: privacy
modulo: data-breach-management
tipo: guia
data_captura: 2026-10-08
---

# Using the enhanced breach impact analysis dashboard

**Scenario**

As a Data Security Officer, you need to assess the scope of a reported incident quickly. The challenge is that manual reviews take too long and increase the risk of missing critical jurisdictions or penalties. With the Breach Impact Analysis dashboard, you initiate advanced breach analysis and automatically see which data elements, identities, and jurisdictions are impacted. This allows you to act fast, prioritize high-risk regions, and meet regulatory deadlines with confidence.

## Overview

With our Breach impact analysis dashboard, you can now selectively initiate enhanced analysis against any reported incident and get an automated report for remediation. Breach impact analysis refers to advanced analysis of the reported incident through the integration of real-time data intelligence and People Data Graph(PDG) technology. This helps you automate the breach management process. Admin users can enable this functionality by enabling this feature while setting up the necessary discovery scan jobs for monitored data systems, ensuring comprehensive and proactive breach analysis.

> [!NOTE]
> **Note**
> 
> The advanced breach analysis is available only for Security Sovereign deployments within your AWS-managed services environment.

Before initiating the enhanced breach analysis, ensure that you have the following prerequisites in place:

- Breach Analysis must be enabled for your tenant. Otherwise, contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your tenant.
- You must enable the “Breach Impact Analysis” option while setting up discovery scan jobs for self-hosted structured or unstructured monitored data systems. For more information, see [Discovery scan for unstructured data systems](/v1/docs/discovery-scans).
- Similarly, make sure to activate the "Unique Identity Analysis for Breach" option when setting up cloud-monitored unstructured data systems.

![Screenshot_2024-06-06_at_10_02_16_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5413d469-b79f-dc05-2d5f-ece810b5721a.png)

> [!NOTE]
> **Note**
> 
> Securiti does not support breach analysis for cloud-structured data systems, unmonitored data systems, or hashed data.

It is recommended that you configure and scan data systems beforehand which are prone to breaches and incidents.

In Securiti open **Data Breach Management >** **Incidents** and report a new incident by clicking **+ Report New Incident.**

![report_advanced_incident.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c5507cdf-a661-87de-31ef-8327102ce174.png)

After reporting the incident, click on it from the list of **Reported Incidents**. Securiti shows you a pop up asking to enable the advanced breach impact analysis feature. Click **Yes**.

![enhanced_incident.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-679b5acd-d74d-887c-ce82-d3de160a4c2a.png)

Securiti redirects you to the **Information** tab where you can use the details provided on the intake form to do a preliminary investigation. On that basis, determine whether or not an actual breach has occurred:

- If so, use the Basic Information, Timeline, and Contacts area to capture additional details about the breach. Further, select the **Data System** and in the Review Task Status area click **Approve**.

![advanced_breach_stages.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b3b0fecc-0737-45df-1966-e7da5cb39b33.png)

> [!NOTE]
> **Note**
> 
> The **Data systems** menu lists data systems that have breach analysis enabled. After completing the discovery scan job, it typically takes some time for all assets (data systems) to be linked and become visible in the list, depending on the amount of data. Securiti audit logs show linking completion status. To open the audit logs:
> 
> - In Securiti, from the menu at the bottom of the dashboard, click **Settings > Security > Audit Logs**.
- If not, in the Review Task Status area click **Decline.**

Once the information is verified, on **Breach Impact Analysis** tab, initiate advanced breach analysis against the data systems impacted by the breach. Securiti detects, classifies, and links sensitive information to individuals and their residencies to automatically populate the breach impact analysis dashboard. Once this analysis is complete, the dashboard displays detailed insights into the data breach and its impact. It shows you the following information:

- **Data Element Types**--The number of data element types that were involved.
- **Residencies**--The residencies that were involved, which translates directly into jurisdictions that must be handled.
- **Identities**--The number of unique identities that were impacted.
- **Monitored Data Systems**--The number of monitored data systems that were involved.
- **Potential Penalties**--The potential penalties that the organization could face if appropriate actions are not taken within the prescribed timelines.

![enhanced_breach_impact.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8bdd2d32-eb8e-a727-8cfb-fa07d8567a10.png)

On the dashboard, the **Residency Distribution** widget groups Impacted identities by residency while highlighting the severity of the data breach. This lets you focus on high-priority jurisdictions while analyzing the impact of storing and processing non-sensitive data from other jurisdictions. Securiti determines if a jurisdiction falls into the high impact or low impact bucket by assessing severity of the incident based on two factors:

- Securiti categorizes the incident impact as High if any impacted data elements within a jurisdiction contain sensitive personal data. Sensitive personal data includes First Name/First Initial and Last Name or National Identification Number (SSN) in conjunction with one of the following:
  - Financial information
  - Medical information
  - Insurance-related details
  - Minor’s information
  - Data related to criminal records
  - Biometric information
  - Genetic information.
- If the data breach involves records of more than 500 individuals, Securiti considers the severity of the incident to be High.

Only one of the above two factors must be met within a jurisdiction for the incident to be considered a high-severity incident for that jurisdiction. In all other scenarios, Securiti considers the incident impact to be low for the particular jurisdiction.

![graph_breach.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b6f246a-c752-02d9-1425-b3458dbeaea2.png)

The global map view shows you the severity by region, and also breaks down the impact within each region. This feature is particularly helpful in countries such as the US, where you must consider multiple state and federal breach notification requirements.

![Map_Updated.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-41774aea-917c-4994-a2ff-a57817030483.png)

The **Jurisdiction** tab highlights the key requirements within each jurisdiction. At a high level, for every jurisdiction you can easily see the deadlines and notification requirements as it relates to the associated regulation, and the potential penalties for non-compliance.

![Jurisdictions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bcc75388-5627-5f61-5735-0716ded49dbb.png)

You can expand each jurisdiction to dive deeper into it to review detailed regulatory requirements. You can review the exposed data element types and counts for that jurisdiction, and you can review a breakdown of the penalties involved.

![JurisdictionsExpand.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fc3df9f-4fad-5065-843f-ad2062ed26bb.png)

Securiti automatically identifies notification requirements and methods, and makes details such as notification content and contact information readily available without the need for an external research database or solution.

The **Impacted Identities** tab lets you analyze exposure based on data subjects' primary identifier to understand the key data elements that were exposed.

![Impacted_identities.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6e38bbc8-060f-1530-9c27-2b3665edcc2d.png)

As with all Securiti dashboards, here you can also use the Filter panel to help you focus on the information or jurisdiction that is relevant.

You can also export jurisdiction or identity-related data in clear-text format to:

- Perform analytics in third-party tools such as Tableau or Power BI
- Contact the impacted individuals
- Generate custom reports
- Initiate any other followup tasks or activities

All other aspects of the data breach workbench such as remediation tracking, notification status, and reports remain the same as the standard incident handling process.

> [!NOTE]
> **Important**
> 
> The feature to export incident details in PDF or JSON format is not available for enhanced breach impact analysis.

### List of data systems supporting breach analysis

### On-prem data systems

- Alfresco
- Alibaba Cloud OSS
- Amazon S3
- Azure Blob Storage
- Azure Data Lake Gen2
- Azure Files
- Azure SQL Server
- Azure Synapse
- Box
- Citrix Sharefile
- Confluence Cloud
- Confluence Data Center
- Databricks
- Dropbox
- G Suite Google Drive
- G Suite Google Mail Attachments
- G Suite Google Mail Content
- GitHub
- Go File Room
- Google Cloud Storage
- HDFS OnPrem
- Jira Software
- Jira Software Data Center
- Microsoft 365 OneDrive
- Microsoft 365 Outlook
- Microsoft 365 Sharepoint Online
- Microsoft Teams
- MySQL
- NFS
- Office 365 Microsoft Lists
- Office 365 Outlook Mail Content
- OpenText Content Server (OTCS)
- Oracle
- Oracle HCM
- Oracle Object Storage
- Oracle Service Cloud
- PostgreSQL
- ServiceNow Files
- SFTP
- Slack Enterprise
- SlackPro
- SMB
- SQL Server
- Tableau Server
- Workday
- Zendesk Support
- Zoho Recruit

### Cloud data systems

- Box
- Cloud Firestore
- DocuSign
- Dropbox
- Facebook Workplace
- Files.com
- Firebase Storage
- G Suite Gmail
- G Suite Google Calendar
- G Suite Google Drive
- Jira
- Office 365 Calendar
- Office 365 OneDrive
- Office 365 Outlook
- Office 365 Sharepoint Online
- Salesforce Chatter
- Slack
- Zuora

---

### FAQ

#### 1. What are the differences between breach analysis type?

Securiti’s Data Breach Management module offers two methods for processing incidents. One is a manual incident resolution process and the other is enhanced breach analysis.

**Manual breach processing**

- In the manual breach processing approach, you manually add jurisdictions affected by the breach. You also have to specify data elements and data subject types impacted by the incident for each jurisdiction and update contact information associated with users affected by the incident.
- For each jurisdiction, you assess risks and potential penalties associated with the breach and determine what notifications are appropriate.

For more information, see [Manually processing the incident](/v1/docs/processing-a-data-breach-report).

**Enhanced Breach Analysis**

- The enhanced breach analysis refers to advanced analysis of the reported incident through the integration of real-time data intelligence and People Data Graph(PDG) technology. In this approach, Securiti automatically identifies the jurisdiction associated with data systems, impacted as a result of breach.
- Securiti detects, classifies, and links sensitive information to individuals and their residencies while highlighting the severity of the data breach which further determines if a jurisdiction falls into the high impact or low impact bucket

For more information, see Using the [enhanced breach impact analysis dashboard](/v1/docs/using-the-enhanced-breach-impact-analysis-dashboard).

#### 2. Is there benefit to using one over the other?

We recommend using the enhanced breach analysis approach to process the breach incident as automatically identifies the affected residents’ details and related jurisdiction without you manually adding these details. The automated incident processing method not only streamlines the process but also saves valuable time.

Additionally, it enhances accuracy by minimizing the risk of human error in manually inputting impacted jurisdictional and resident details.

Breach impact analysis refers to advanced analysis of the reported incident through the integration of real-time data intelligence and People Data Graph(PDG) technology. This helps you automate the breach management process. Admin users can enable this functionality by enabling this feature while setting up the necessary discovery scan jobs for monitored data systems, ensuring comprehensive and proactive breach analysis.

Impacted identities refer to the Personal Identifiers of data subjects such as Email, SSN, and MRN impacted as a result of a data breach. The details of impacted identities also encompass severity levels based on exposure to Sensitive Personal Data (PD). For instance, the severity is deemed high if personal identifiers like Name or SSN are compromised. The information also includes a count of data elements categorized by PD classifications, as well as the total number of files containing records associated with the compromised identity.

## Related

- [Exporting jurisdiction data in CSV format](/exporting-jurisdiction-data-in-csv-format.md)
- [Exporting impacted identities in CSV format](/exporting-impacted-identities-in-csv-format.md)
