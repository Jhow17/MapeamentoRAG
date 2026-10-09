---
title: "Getting Started with Data Breach Management"
slug: "getting-started-with-data-breach-management-1"
updated: 2026-09-22T08:59:22Z
published: 2026-09-22T08:59:22Z
canonical: "helpcenter.securiti.ai/getting-started-with-data-breach-management-1"
area: geral
modulo: getting-started
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Data Breach Management

Data Breach Management is an automated data breach incident response management tool that helps you comply with applicable breach regulations, reduces cost and time to remediation. With Securiti's Data Breach Management tool, you can align privacy and security by securely storing the audit trails required for compliance.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Data%20Breach%20Management-Design.drawio(2).svg)

### Step 1 - Configuring Self-Service Portal (SSP) and data systems

Securiti offers two ways for you to report an incident. Admin users can report an incident directly from the Data Breach dashboard and members of your organization without Securiti accounts can use the self-service portal to report an incident.

| **Configuring SSP** Configure the SSP and publish the link on your website or share it via email with users who want to report a breach incident. Securiti offers a variety of customization options to tailor the appearance of your portal according to your business requirements. [Learn more](/v1/docs/configuring-the-securiti-self-service-portal) | ![Screenshot_2024-10-07_at_12_17_30_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e4475e36-1fbc-69ac-49d9-e8228c327735.png) |
| --- | --- |
| **Configuring monitored data systems** Configure both structured and unstructured data systems for breach analysis. For self-hosted unstructured data systems, you must create at least one discovery scan job to run enhanced breach flow. [Learn more](/v1/docs/setting-up-data-systems-for-breach-analysis) | ![Screenshot_2024-10-04_at_6_09_31_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-26ed1852-5f2e-4ce7-2b6e-5d70f5f9cd9a.png) |
| **Configuring unmonitored data systems** Configure unmonitored data systems in the Securiti Data Mapping Automation module to represent systems that have been breached. Breach owners can further select that data system in the Data Breach workbench and process breach incident. [Learn more](/v1/docs/setting-up-data-systems-for-breach-analysis) | ![Screenshot_2024-10-04_at_6_23_18_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cf6328df-c9c9-2aa8-d4e3-c0c368f4d7a5.png) |

### Step 2 - Reporting a data breach

| ![Screenshot_2024-10-03_at_10_26_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e98dfbfd-893a-98dd-eeaf-f6d629f57880.png) | **Guest users** Guest users are internal users who can login to the self-service portal to report a breach incident. [Learn more](/v1/docs/reporting-a-data-breach) |
| --- | --- |
| ![Screenshot_2024-10-03_at_10_30_41_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-190113b1-aa2d-1b44-d1da-161677130c62.png) | **Admin users** Admins users can login to the Data Breach Management module and report the incident directly from the Data Breach Dashboard. [Learn more](/v1/docs/reporting-a-data-breach) |
| ![Screenshot_2024-10-03_at_10_42_10_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-652cdaa6-d6bf-0893-8e13-4671fe65495e.png) | **Breach Management node** Breach Management node manages the key breach operations, such as creating a breach incident, retrieving incident details, and fetching a list of all incidents. Moreover, you can: - Generate breach reports from incidents in other management tools for better tracking. - Email a summary report of open and closed incidents to leadership for transparency. - Retrieve breach details and integrate them into incident management tools for centralized access. [Learn more](/v1/docs/trigger-nodes-breach-management) |

### Step 3 - Securiti assigns reported breaches to DPOs and sends out invites

| **Assignment of reported breaches** When a data breach incident is submitted, Securiti assigns all DPO role users as incident owners. If there are no DPOs in the tenant, it assigns the incident to all admins. An admin submitting the breach report also becomes a co-owner. [Learn more](/v1/docs/managing-data-breach-incident-ownership) | ![Screenshot_2024-10-10_at_12_41_35_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ecafc178-01a6-ffee-5490-13b225414328.png) |
| --- | --- |

### Step 4 - Processing a breach incident and generating a report

Once a breach is report, breach owners can process it in the Data Breach Workbench.

| ![Screenshot_2024-10-10_at_12_41_35_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ecafc178-01a6-ffee-5490-13b225414328.png) | **Reassign reported breaches to admin users** Breach owners can review and change the ownership of data breaches as needed. Securiti lets you reassign data breach incidents to other admins within the tenant. [Learn more](/v1/docs/managing-data-breach-incident-ownership) |
| --- | --- |
| [Embedded content](https://player.vimeo.com/video/874509279) | **Manually processing a breach incident** In the Data Breach Workbench, breach owners can manually process reported incidents through its various stages. Manual breach handling accommodates both monitored and unmonitored data systems. [Learn more](/v1/docs/processing-a-data-breach-report) |
| [Embedded content](https://player.vimeo.com/video/874510074) | **Enhanced Breach Analysis** Breach impact analysis refers to advanced analysis of the reported incident through the integration of real-time data intelligence and People Data Graph(PDG) technology. Before using Enhanced Breach Analysis, make sure to enable Breach Analysis for your tenant. Otherwise, [contact support@securiti.ai](http://support@securiti.ai) to enable it for your tenant. > [!NOTE] > **Note** > > Enhanced Breach Analysis currently does not support unmonitored data systems or hashed data. In such cases, select“No” to process the incident manually. [Learn more](/v1/docs/using-the-enhanced-breach-impact-analysis-dashboard) |
| ![Screenshot_2024-10-03_at_11_35_32_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-245c5575-41e9-8dbb-7200-3738f52079cf.png) | **Communicate with incident reports** Breach owners can use the message panel to communicate with breach reporters. [Learn more](/v1/docs/using-data-breach-management-messaging) |
| ![Screenshot_2024-10-03_at_11_38_49_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7bb6a24c-b2d5-df99-c8b2-6a8563d7a464.png) | **Initiate an assessment** Securiti offers a series of assessment templates by jurisdiction in the template library. These templates help data breach managers determine whether an incident constitutes a data breach and evaluate the need for notification by assessing potential risks. [Learn more](/v1/docs/using-data-breach-assessments) |
| [Embedded content](https://player.vimeo.com/video/874509279) | **Notify Impacted identities and relevant authorities** For each impacted jurisdiction, breach owners get information about the relevant notifications to be sent to impacted data subjects and relevant regulatory authorities. For certain jurisdictions, Securiti also provides notification template details that they can use for sending notifications. [Learn more](/v1/docs/processing-a-data-breach-report) |
| [Embedded content](https://player.vimeo.com/video/874509279) | **Complete the incident and generate report** Specify the details regarding how to prevent similar incidents in the future. Further, verify the incident summary details and mark the incident as complete. You can export the incident details in CSV and PDF formats for manually processed incidents. [Learn more](/v1/docs/processing-a-data-breach-report) |

### Step 5 - Data Breach Management API Documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The Data Breach Management API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without needing to set up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-breach-management/apidocs/index.html) | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **Download the postman collection** We also provide Postman collections for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that lets you quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-breach-management/apidocs/index.html) | ![Screenshot_2024-10-10_at_1_09_33_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-de143a99-3df6-5d53-13eb-77c1375fd3d8.png) |
