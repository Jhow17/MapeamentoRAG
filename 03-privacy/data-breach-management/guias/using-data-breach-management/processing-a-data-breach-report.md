---
title: "Processing a data breach report"
slug: "processing-a-data-breach-report"
status: "update"
updated: 2025-11-02T06:10:36Z
published: 2025-11-02T06:10:36Z
canonical: "helpcenter.securiti.ai/processing-a-data-breach-report"
area: privacy
modulo: data-breach-management
tipo: guia
data_captura: 2026-10-08
---

# Processing a data breach report

**Scenario**

As a Data Privacy Officer, you receive a reported breach that requires manual handling. The challenge is ensuring each stage is reviewed carefully to stay compliant and avoid delays. In the Data Breach Management module, you process the incident step by step: verify details, analyze risks, record remedial actions, and send notifications. This structured approach helps you comply with regulations and reduce overall remediation costs.

## Overview

When a member of your organization submits a data breach report, Securiti assigns as incident owners all Securiti users with DPO role. If the breach report is submitted by a Securiti admin, that admin is also a co-owner of the incident. If you are an incident owner, you can work on the incident report in the Data Breach Workbench. Use the tabs in the workspace to process the breach through its various phases. Manual breach handling accommodates both monitored and unmonitored data systems.

1. On the Verify tab, use the information provided on the intake form to do a preliminary investigation. On that basis, determine whether or not an actual breach has occurred:

![RN_data_breach_management_verify_tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c439055b-2717-e34e-d4f3-5123dd463360.png)
  - If so, use the Basic Information, Timeline, Contacts, and Asset Details area to capture additional details about the breach. Then in the Review Task Status area click **Approve**.
  - If not, in the Review Task Status area click **Decline**.
2. On the **Detect** tab, click **View Asset Details** link to open the asset details in case there is a data system catalog entry for the affected asset.

![view_asset.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e554a760-10a5-db3d-1045-93d32ef28d11.png)

On the **Detect** tab, use the tools to describe the scope of the incident, areas impacted by the incident, and actual level of service impact. Further, add the impacted jurisdictions by clicking **Add Jurisdiction**.

Against each impacted jurisdiction add the following details:

Click **Approve** to move to the next stage.
  - Expand **Data Element** and add data element types and counts impacted by the jurisdiction

![Add_data_elements_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-19732f37-1b0d-160b-4414-4c5f0c84ff60.png)
  - Expand **Data Subject Types** to add Data subject types and counts

![Add_data_subject_type.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-640499c5-959c-707f-e7a6-0ebc853795c7.png)
  - Expand **Contact Information** and upload the contact information of data subjects in the form of a CSV file.

![Add_data_subject_contact_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-895629ab-03bc-77f6-3ca6-b96c3c3410b9.png)
3. On the **Analyze** tab, for each jurisdiction, you assess the risks and potential penalties associated with the breach and determine what notifications are appropriate. This is the most critical phase of processing a data breach report.

| **Regulatory Summary** | Click **View Regulation** to view the applicable privacy regulation summary. ![View_Regulation_summary.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d1ce215a-ae23-07e8-4b0f-0227a7d58c10.png) |
| --- | --- |
| **Analysis** | The Analysis area lets you collect information about the current status of the incident and its investigation, and what remedial action you have taken. |
| **Risk** | The Risk area lets you set risk scores based on assessments you initiate to evaluate the risk associated. |
| **Further Compliance** | The Further Compliance area lets you analyze the impact and reduction of harm caused by the data breach. |
| **Penalties** | The Penalties area summarizes potential penalties that might be incurred as a result of the breach. |
| **Notify** | The Notify area lets you choose who to notify about the breach, and how. You can add new resources to be notified by clicking **Add Notification**. ![Add_notification.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0d7f6ead-a264-29a4-1d26-dc3b971530c3.png) You can also view notification content details: 1. Click **Option** (3 dots) **> View** as shown below: ![View_notification_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d2e8e3fb-2147-766f-fb3e-10ca46e02892.png) 2. Expand **Notification Methods** to view content and contact details related to the notification. ![notification_content_contact_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-42177f1f-980c-5044-e882-78ab6fa4ebca.png) |
4. Use the Remediate tab to document what remedial action you have taken in response to the incident.

![DBA_new_remediate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-554a4ce8-702e-eeb2-2f59-5c05d0807b61.png)
5. On the Notify tab, for each jurisdiction in the Tasks panel, confirm that you have notified the appropriate parties of the breach.

![RN_data_breach_management_notify_tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c627dfc3-f5de-60c9-2967-707912f24b9c.png)

> [!NOTE]
> **Note**
> 
> The Tasks panel also contains an optional task for Organizational Notifications. You can use this task to capture information about who in your organization you have notified of a data breach incident.
6. On the **Complete** tab, use the **Lessons Learned** tab to capture information that helps you to prevent similar incidents in the future.

![Lesson_learned_tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-350905d0-b3c8-ca4a-dfa1-bf4b1d8e6968.png)

Use the **Summary** tab to review a summary of the incident and click **Complete** to confirm that that incident has been fully addressed.

![Summary_tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-40fb1a81-9e6e-8093-d27d-4eba85da4e42.png)

---

### FAQ

#### 1. Why is an asset type required?

Choosing a data asset is mandatory for processing a breach incident because the Data Breach Management tool specifically addresses and manages data breaches. Its core functionality revolves around efficiently responding to incidents related to unauthorized access or compromise of sensitive information.

#### 2. Can I fill out contact info in the first stage without populating a phone number and email?

You can complete the contact information without filling in the phone number and email address since these are not mandatory fields.

#### 3. Is there a way to open all stages from the start or do I need to work through each stage sequentially?

You must approve the incident in the Verify stage to move to the Detect stage. Similarly, you must select a jurisdiction in the Detect stage to see tasks in the Analyze stage and further notification requirements associated with each jurisdiction in the Notify stage.On the other hand, after approving the incident in the Verify stage, you have the option to proceed directly to the Remediate stage, bypassing the Detect and Analyze stages.

#### 4. Can I add more manual tasks in the detect and remediate stage? They only populate from the assets selected?

No, as per the current implementation of the Data Breach Management tool you cannot add the tasks manually in the detect and remediate stage.

Asset Details provide a list of data systems, and you can choose the ones that are affected by a breach. For manual breach processing, the list contains both monitored and unmonitored data systems. For enhanced breach processing, the list shows only monitored data systems that are linked after the completion of the discovery scan job. Once the discovery scan job is completed, it typically takes approximately 2-3 hours for all assets to be linked and visible in the list.

Data subject types refer to the different categories or groups of individuals whose personal information may be compromised or exposed due to a data breach. Data subjects are the individuals to whom the data pertains. The types of data subjects affected by a breach can vary depending on the nature of the data system. For instance, your data subject types could be customers, students, patients, stakeholders from within your organization, etc.
