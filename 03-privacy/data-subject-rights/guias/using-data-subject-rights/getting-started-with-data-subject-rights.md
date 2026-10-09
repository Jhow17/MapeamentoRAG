---
title: "Getting Started with Data Subject Rights"
slug: "getting-started-with-data-subject-rights"
updated: 2026-05-04T10:28:34Z
published: 2026-05-04T10:28:34Z
canonical: "helpcenter.securiti.ai/getting-started-with-data-subject-rights"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Data Subject Rights

Data Subject Rights is an automated system that simplifies the process of fully complying with Data Subject rights requests. It lets you securely collect and manage DSR requests, verify identities and fulfill requests efficiently. You can also share encrypted responses in the form of DSR reports with data subjects using a secure portal.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS_DSR-Design2.drawio(1).svg)

### Step 1 - Configure DSR Settings

Configure DSR settings, including [retention policies](/v1/docs/configuring-dsr-retention-policy), [request types](/v1/docs/configuring-dsr-request-types), [task templates](/v1/docs/understanding-task-templates-and-rule-based-task-creation), and [email notification templates](/v1/docs/configuring-dsr-email-notification-templates). You can also enable or disable [Privacy Central account](/v1/docs/setting-up-privacy-central-account) options for data subjects, allowing them to create an account to view and download DSR reports.

### Step 2 - Configure DSR Forms

Use the form builder to create or customize forms to collect DSR requests.

| **Create and customize DSR forms** Identify form requirements and use the DSR form builder to customize forms based on Data Subject types, request types, and jurisdictional compliance. Configure third-party verification methods like [ID.me](/v1/docs/configuring-identity-verification-with-idme), [Jumio](/v1/docs/configuring-identity-verification-with-jumio), and [Unico](/v1/docs/configuring-identity-verification-with-unico) for added security. > [!NOTE] > **Note** > > By default, Securiti verifies Data Subject identity with a 4-digit code sent to their email. [Learn more](/v1/docs/creating-and-publishing-dsr-request-forms) | [Embedded content](https://player.vimeo.com/video/835312415) |
| --- | --- |
| **Configure data identifiers on DSR Form** Securiti lets you add additional identifiers, such as a phone number, address, or government ID, when configuring the DSR form. Mark these fields as identifiers to ensure accurate data subject identification. > [!NOTE] > **Note** > > By default, Securiti uses the email address as the primary identifier to identify the Data Subject when querying your systems. [Learn more](/v1/docs/configuring-dsr-request-forms-for-multiple-identifiers) | ![Screenshot_2024-08-30_at_9_55_13_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-61388cd2-df49-8692-6a8b-424e5793827c.png) |
| **Edit DSR form translations** Securiti auto-translates DSR form content using an integrated service when multiple languages are enabled. You can review and edit these translations if the default wording isn't accurate. [Learn more](/v1/docs/customizing-translations-for-dsr-forms) | ![Edit_DSR_form_translations.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-18ab46a1-5d5f-3279-259a-f5c1b3608451.png) |
| **Configure supplemental forms** You can configure supplemental forms to collect more information from data subjects after they submit a DSR. This helps when the initial request doesn’t provide enough detail to understand its scope. [Learn more](/v1/docs/request-clarification-in-dsr) | ![Configure_supplemental_forms.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2852239c-402c-0d49-a3b6-6e1a6dd9fdc8.png) |
| **Configure rules in DSR form** You can configure rules to determine which task templates and workflows apply to incoming DSR requests. Rules evaluate request details like type, jurisdiction, or form fields. When conditions match, the assigned templates or workflows are triggered. [Learn more](/v1/docs/configuring-rules-in-the-dsr-form) | ![Screenshot_2025-07-30_at_12_23_36_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a0987628-2590-08e1-ac85-06e79cf781a5.png) |

### Step 3 - Connect your data system and setup DSR automation

Identify all the data systems storing data of data subjects. Integrate your structured, unstructured, and streaming data systems, such as MySQL, SharePoint, and Kafka, with Securiti by providing the necessary permissions.

Setting up DSR Automation depends on the type of data systems you are using such as structured, unstructured, user-defined etc.

[Learn more](/v1/docs/setting-up-data-systems-for-dsr-automation)

| ![Screenshot_2024-08-30_at_9_58_44_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-60d64dba-4e0e-623b-03ad-ba455fdbf464.png) | **Unstructured Data System** In unstructured data systems, DSR Automation is supported either using "Full Scan'' or "API". For unstructured data systems supporting Full Scan for DSR Automation, you must create at least one Discovery Scan Job in the **Sensitive Data Intelligence** module. To see the DSR Automation methods for each unstructured Data System, refer to supported Data System connectors. [Learn more](/v1/docs/setting-up-data-systems-for-dsr-automation) |
| --- | --- |
| ![Screenshot_2024-08-30_at_10_00_10_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9d4f9b80-8417-314a-913d-66126171593a.png) | **Structured Data System** Securiti searches data within structured data systems using either SQL queries or search APIs, depending on whether the system supports query-based or API-based DSR Automation. [Learn more](/v1/docs/setting-up-data-systems-for-dsr-automation) |
| ![Screenshot_2024-08-30_at_10_01_20_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bd688565-0dab-c40a-ee3d-e2048d17b3ac.png) | **Scanless Data System** For scanless data systems, Securiti responds to queries on specific elements of personal data in real-time as DSR requests come in. This eliminates the need for pre-scanning or maintaining an internal data inventory, ensuring efficient and timely data handling. [Learn more](/v1/docs/setting-up-data-systems-for-dsr-automation) |
| ![Screenshot_2024-08-30_at_10_03_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b8af21cd-50da-0302-3f44-b70e950217cf.png) | **User-defined Data System** You configure User-Defined data system connectors to connect your proprietary data systems to Securiti so you can process DSR requests for personal data they contain. [Learn more](/v1/docs/setting-up-data-systems-for-dsr-automation#dsr-automation-for-userdefined-data-systems) |
| ![Screenshot_2024-08-30_at_10_02_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c328f364-53fd-aedb-d664-cb2c6cdae0b2.png) | **Unmonitored data systems** You can configure Unmonitored data systems in the Securiti Data Mapping Automation module to represent systems that may contain relevant personal data for a DSR request. Securiti creates subtasks based on these systems, but since they aren't monitored, you must manually access and process the data. [Learn more](/v1/docs/setting-up-data-systems-for-dsr-automation#dsr-automation-for-unmonitored-data-systems) |

### Step 4 - Add relevant data systems to the DSR Form and publish it

| **Inclusion of data systems** Securiti lets you include selective data systems on the DSR form for which you have purchased a license to use DSR Automation.When handling DSR requests, Securiti will only search these specific data systems to locate the Data Subject's information. [Learn more](/v1/docs/creating-and-publishing-dsr-request-forms) | ![Screenshot_2024-08-30_at_10_05_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-34d4e042-58d0-2345-31ea-28a754cd68df.png) |
| --- | --- |
| **Publishing DSR Form** You can work with your website team to either publish the link to the DSR form, embed it in a page on your website or publish it on [privacy center](/v1/docs/customizing-your-privacy-center). Once the DSR form is successfully published, you are ready to receive Data Subject requests. > [!NOTE] > **Note** > > You can only embed or publish external DSR forms. [Learn more](/v1/docs/approving-and-publishing-reports) | [Embedded content](https://player.vimeo.com/video/841822502) |

### Step 5 - Submit DSR request via form

Data subjects can submit forms published on your internal website or privacy center.

[Learn more](/v1/docs/how-dsr-requests-originate)

### Step 6 - Identity verification of the Data Subject as configured in the DSR form

Securiti offers various methods to verify the Data Subject identity. These processes ensure that the request comes from a real Data Subject, and that they are who they assert they are.

To learn more about Data Subject identity verification, refer to:

- Default identity verification
- Passwordless identity verification
- Identity verification with Unico
- Identity verification with ID.me
- Identity verification with Jumio

### Step 7 - Securiti auto-creates and assigns tasks and subtasks

Securiti creates a task for each Data System containing the Data Subject’s information and names it accordingly. Creations of subtasks depend upon the type of Data System.

| ![Screenshot_2025-08-09_at_5_57_10_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-14e64d85-4c31-8980-21d4-29f9f18d629f.png) | **Structured data systems** For structured data Systems, Securiti creates one Subtask for each task in the DSR workbench and attaches zip files that contain CSV files with the Data Subject’s information. You can verify all attachments and include them in the final DSR report. You can also inspect these CSV attachments and delete rows or columns containing any extraneous sensitive data. [Learn more](/v1/docs/dsr-workbench-overview) |
| --- | --- |
| ![Screenshot_2025-08-09_at_5_57_30_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ab5cf793-0381-dc2f-fa86-a7809e0eee6d.png) | **Unstructured data Systems** For unstructured Data Systems, Securiti creates a Subtask for each file found in an unstructured Data System containing the Data Subject’s data. For certain files in unstructured data systems, Securiti provides a "Preview PD found in file" button. Click this button to preview the file with Personal Data (PD) highlighted. [Learn more](/v1/docs/dsr-workbench-overview) |
| ![GS_user-defined.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f44c28e8-08b2-17dd-8cd9-3b78d9e2e5bc.png) | **User defined Data System** For user-defined systems, Securiti creates one Task and Subtask for each data system instance in the DSR workbench. Securiti attaches data found using the specified API operation to respective subtasks. The Securiti user-defined connectors use the OpenGDPR APIs. [Learn more](/v1/docs/dsr-workbench-overview) |
| ![Screenshot_2025-08-09_at_6_14_28_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cc5edf0e-cad8-d0eb-b418-cad6bfd93fd2.png) | **Unmonitored data systems** For unmonitored systems, Securiti creates one task with one Subtask for each system. No data is searched or attached since Securiti does not connect with and has no visibility into these data systems. As soon as, tasks and subtasks are created, Securiti alerts relevant subtasks owners to manually attach files containing Data Subject's information. [Learn more](/v1/docs/dsr-workbench-overview) |
| ![Screenshot_2025-08-09_at_6_14_41_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7179ffad-f6f2-0c70-a431-ef95688d6173.png) | **Subtask Statuses** When searching for a Data Subject's information: - **Error:** Securiti logs any errors and sets Subtask status to “Error” for DSR and Subtask owners to review and export. - **No Data:** Securiti deletes task or Subtask if no data is found. - **Data Found:** Securiti packages the data, uploads it to the Subtask, and sets the Subtask status to "Review." [Learn more](/v1/docs/dsr-workbench-overview) |

### Step 8 - Review and reassign ownership and initiate request clarification

Add or remove DSR request and Subtask owners.

| **Invite DSR co-owners** You can review and change the ownership of DSR request as needed. By default, the owner of the DSR form automatically becomes the owner of all requests submitted through that form. DSR request owners can add co-owners and also reassign ownership of their DSR requests. [Learn more](/v1/docs/adding-and-changing-dsr-request-and-dsr-form-owners) | [Embedded content](https://player.vimeo.com/video/835313607) |
| --- | --- |
| **Invite Subtask co-owners** Securiti lets you reassign subtasks to others inside and outside your organization. By default, Securiti assigns subtasks to the co-owners of each Data System for which it created the tasks. You can also invite a collaborator from inside or outside your organization to have ownership of a Subtask without adding them as a Securiti user. [Learn more](/v1/docs/manually-assigning-dsr-request-subtasks) | [Embedded content](https://player.vimeo.com/video/835313607) |
| **Initiate request clarification** You can configure request clarification to collect more details from data subjects when a submitted DSR lacks enough information. Clarification can be triggered [manually](/v1/docs/manually-initiating-request-clarification-from-dashboard) from the dashboard or [automatically](/v1/docs/creating-and-publishing-dsr-request-forms) after form submission and email verification. [Learn more](/v1/docs/request-clarification-in-dsr) | ![Initiate_request_clarification.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a2d4b3c4-ec9d-ffc2-2a94-de541a2f08ba.png) |

### Step 9 - Full or partial rescanning of DSR requests

You can initiate rescanning of tasks or subtasks in case if new data is added to the data systems.

| ![Screenshot_2025-08-09_at_6_15_25_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-87ef5419-760b-ec3e-3d9a-4c2b5da7a556.png) | **Fully or partially rescan DSR requests** You rescan DSR requests to update personal data findings. A [full scan](/v1/docs/re-scanning-dsr-requests) refreshes all subtasks, while a [partial scan](/v1/docs/partial-re-scanning-in-dsr) targets specific tasks and data systems to save time and resources. You can run full scans manually or on a schedule. [Learn more](/v1/docs/re-scanning-dsr-requests) |
| --- | --- |

### Step 10 - Redact or mask data for requests of type access and port

Securiti provides redaction and masking features for both unstructured and structured data reports in DSR workbench, specifically for access or port types.This ensures that only the requester's personal information is visible in the final DSR report, while the personal details of others are redacted.

| **Redacting unstructured data reports** Securiti lets you automatically or manually redact unstructured data reports containing personal data of the Data Subject. Automated redaction is only available for unstructured monitored data systems. > [!NOTE] > **Note** > > To enable auto-redaction, you must subscribe to Securiti’s Sensitive Data Intelligence module with the Content Classification feature. [Learn more](/v1/docs/processing-access-request-subtasks) | ![Screenshot_2024-08-30_at_10_29_16_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1ec428a3-8853-170d-1312-c2520374b247.png) |
| --- | --- |
| **Masking structured data reports** You can mask personal data in structured data reports, such as CSV files, containing the Data Subject's information. You can also delete rows in the CSV containing extraneous or duplicate information such as - Your organization’s confidential information - Anyone else’s personal data [Learn more](/v1/docs/processing-access-request-subtasks) | ![Screenshot_2024-08-30_at_10_24_07_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-abdc1434-e9dd-5c9f-7357-165acd87b370.png) |

### Step 11 - Complete all subtasks in the DSR workbench

In the DSR Workbench, Subtask owners can complete all assigned subtasks as per the guideline.

| [Embedded content](https://player.vimeo.com/video/835313607) | **Processing DSR Requests** Subtask owners inspect the contents of the search results and then approve or decline the Subtask. Each request is handled uniquely based on its type. > [!NOTE] > **Note** > > If you decline subtasks, no data is shared with the Data Subject in the DSR report. [Learn more](/v1/docs/processing-dsr-subtasks) |
| --- | --- |

### Step 12 - Generate and review DSR report

When all the subtasks are approved or declined, the DSR Owner can generate a consolidated report.

| **Reviewing and Finalizing the DSR Report** Once all subtasks are completed, you as a DSR owner can generate preview of a consolidated DSR report for DSR request types of access and port. Review this report carefully before sending it to the Data Subject. If you find any issues, you have the option to regenerate the report by replacing the one by before finalizing it. [Learn more](/v1/docs/approving-and-publishing-reports) | ![Screenshot_2025-08-09_at_6_18_36_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1742c204-1dbb-bce8-2965-e14553e36b79.png) |
| --- | --- |

### Step 13- Publish DSR report and send to the data subject

Once all subtasks are completed, you can publish the DSR report

| [Embedded content](https://player.vimeo.com/video/841748607) | **Approve and publish DSR report** You can publish the DSR report, send it to the Data Subject, and keep a compliance record in the audit logs of DSR request. [Learn more](/v1/docs/approving-and-publishing-reports) |
| --- | --- |
| ![Screenshot_2025-08-09_at_6_19_11_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3109631e-f226-c356-1a1f-0e33c4ad994e.png) | **Reject DSR request** Securiti lets you reject a DSR request if it seems repetitive or fulfilling it would violate other legal obligations. Once all subtasks are created, you review and reject the request accordingly. > [!NOTE] > **Note** > > Rejecting a DSR sets all the subtasks to declined status and overwrites the reason for declining for each Subtask with a reject reason. [Learn more](/v1/docs/rejecting-dsr-requests) |

### Step 14 - View and download the DSR report from privacy central

When the DSR owner publishes a DSR report, Securiti sends an email to the Data Subject with instructions to access the report from Privacy Central.

| **View and download the DSR report** Data subjects can log in to their Privacy Central account to access the published report. The report is encrypted, so they can download both the report and the key needed to unlock it. [Learn more](/v1/docs/setting-up-privacy-central-account) | ![view_and_download_report.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9131777d-daf5-b404-7c41-b7d3545850ad.png) |
| --- | --- |
| **Initiate an appeal** If a Data Subject is dissatisfied with a DSR report, they can initiate an appeal request once the DSR request has been processed. [Learn more](/v1/docs/setting-up-privacy-central-account) | ![initate_appeal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-93b17618-1d91-42b1-b03f-00b78afd9e19.png) |

### Step 15 - Data Subject Rights API Documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The Data Subject Rights API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without needing to set up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-subject-rights/apidocs/index.html) | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **Download the postman collection** We also provide Postman collections for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that lets you quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-subject-rights/apidocs/index.html) | ![Screenshot_2024-09-24_at_1_50_36_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf54d08d-7781-bf2a-3f59-047a24a5a9bd.png) |

A rule defines the conditions under which one or more task templates or workflows are triggered for incoming DSR requests. Each rule evaluates request metadata, such as request type, data subject type, jurisdiction, location, or specific form fields, and applies the assigned task templates or workflows when all conditions are met.

Proprietary data systems that Securiti interacts with using webhooks (reverse APIs) that your IT teams develop.

Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert incident owners to actively check them for unauthorized data access when a data breach incident is reported.

Privacy Central also known as **Data Subject Portal (DSP)** or **Data Request Center** is a unified portal that provides data subjects with a seamless way of raising, tracking Data Subject requests, and downloading DSR reports. Data subjects can also use the messaging feature in Privacy Central to communicate with DSR owners.
