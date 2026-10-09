---
title: "Request Clarification in DSR"
slug: "request-clarification-in-dsr"
updated: 2026-09-21T10:53:22Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/request-clarification-in-dsr"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Request Clarification in DSR

**Scenario**

As a Data Privacy Officer, you often receive DSRs with vague or incomplete information. Manually following up delays response times. With Securiti’s request clarification feature, you can collect extra details needed from the Data Subject either manually or automatically. This helps you understand the request scope faster and reduces back-and-forth, ensuring timely and accurate processing.

### Overview

Securiti enables DSR owners to collect additional details from data subjects using supplemental forms after data subjects submit a request. This feature is useful when the initial DSR lacks sufficient details for the DSR owner to understand the scope of the request. Request clarification can be done in two ways:

- **Manually:** On a case-by-case basis for each DSR request, the DSR owner can initiate request clarification from the DSR dashboard. For more information, see [Initiating request clarification from dashboard.](/v1/docs/manually-initiating-request-clarification-from-dashboard)
- **Automatically:** While configuring the DSR form, you can enable request clarification. Once the request is submitted and email verification is completed, the data subject receives an email prompting them to provide additional details relevant to the DSR request. For more information, see **Automatic Request Clarification** section in [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms).

Before initiating request clarification, you must configure supplemental forms to gather specific details from data subjects. The supplemental form builder allows you to define the required fields and publish the forms. If these forms include new personal identifiers, Securiti re-scans data systems to fetch relevant data in the workbench. This re-scan initiation is also recorded in the audit logs of the particular request. For more information on configuring these forms, see [Creating and publishing supplemental forms](/v1/docs/request-clarification-in-dsr).

When clarification is requested, data subjects receive an email prompting them to provide additional details. They can log in to their Privacy Central account (Data Subject portal) to respond to the request. For more information, see [Submitting more details for request clarification.](/v1/docs/setting-up-privacy-central-account)

The DSR dashboard provides visibility into the status of request clarifications, allowing you to track whether they have been initiated, responded to, or are awaiting a response. For more information, see [Using the Data Subject Rights Dashboard](/v1/docs/using-the-data-subject-rights-dashboard).

### Creating and publishing supplemental forms

Securiti enables DSR owners to collect additional details from data subjects using supplemental forms after they submit a request. This feature is useful when the initial DSR lacks sufficient details for the DSR owner to understand the scope of the request. With Securiti's simple form builder tools, you can quickly create and publish supplemental forms to gather the specific details needed to process the request.

> [!NOTE]
> **Note**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

1. In Securiti open Data Subject Rights, then choose **Settings > DSR Supplemental Forms**.

On this page, you can use the search bar to search for a particular form by entering its title. You can select various filter options to specify the criteria for filtering the supplemental form list. There are two filters available: **Published** and **Organizations**.

Once the filter is applied, the list updates to display only the forms that meet the specified criteria. The **DSR Supplemental Forms** dashboard also shows the total number of created and published forms.
  - **Published**: This filter allows you to refine the list based on when the form was published, such as in the last 7 days, last week etc.
  - **Organizations**: This filter appears only if you have selected multiple organizations within a tenant. It helps you filter forms created within those selected organizations.
2. Do one of the following:
  - To create a new form, near the upper right corner of the list of forms, click **+ Create Form**. Enter the form name and click **Create Supplemental Form**.
  - To open an existing form for editing, click its card.
  - To create a new form based on an existing one, on the card for the existing form choose **Options (three dots) > Clone Form**.

You can clone a DSR form within the same organization that you are currently managing or working in or across all your active organizations within the tenant. This eliminates the need to recreate or manually copy forms from one organization to another within your tenant.

> [!NOTE]
> **Note**
> 
> To migrate DSR forms across organizations, you must have the Manage Org Units premium feature enabled for your Securiti tenant. Also, Securiti does not support the deletion of supplemental forms.
3. Near the upper left corner of the page, click the pencil icon and give the form a convenient name. Then click the checkmark to save the name.

> [!NOTE]
> **Note**
> 
> The title of the supplemental form should be unique. Two forms cannot have the same titles within the same organization.
4. On the Supplemental Form Builder page, add elements as per your requirements:

| Label | Description |
| --- | --- |
| **Attachments** |
| Enable Attachment upload | Mark the checkbox to configure the supplemental form to include options that let data subjects attach and upload files. The form allows a maximum attachment size of 10 MB and up to 3 attachments. > [!NOTE] > **Note** > > Securiti performs anti-virus checks on any attachments submitted by data subjects, as well as attachments added by internal teams through the DSR Workbench. Additionally, If a data subject attaches a file larger than 10 MB, the request submits, but the attachment does not appear in the **Data Subject Details** section of the DSR Workbench. This is happening due to an issue in the third-party library being used. We are actively investigating the matter. |
| Mandatory | Mark the checkbox to make it mandatory for the data subject to attach files in the supplemental form while submitting additional details. |
| Caption for Attachment field | Enter the caption that identifies the Attachment field on the DSR form. |
| **Template Content** |
| Heading | Enter the main heading of the supplemental form. |
| Body | Enter the body text that you want to display on the form. |
| **Define Form Fields and Requirements** |
| Custom Fields | You can click and drag custom fields to add them to the form. For more information about editing the form components, see [Form Builder](/v1/docs/form-builder-tabs) Tabs. > [!NOTE] > **Note** > > Fields with the keys “email” and “request_type” cannot be created in the supplemental form, as they are already configured on DSR forms by default. However, you can create these fields using different keys. |
5. Use the preview area on the right half of the page to see what the form looks like on computer, tablet, and phone screens, as shown below.

![Screenshot_2025-02-10_at_2_11_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-962d595e-06ce-2968-ff5e-efa027464f57.png)
6. When you are done, click **Save** and **Publish**. After publishing the form, wait a couple of minutes for the changes to take effect.

> [!NOTE]
> **Note**
> 
> Unlike DSR forms which you can embed on an external website or make publicly accessible, supplemental forms do not have this capability.

Once done, you can initiate request clarification for submitted DSR requests.

On a sequential DSR request, request clarification always resets to level 1. If the qualifying rule changes after the data subject submits additional details, Securiti deletes all tasks from the original rule and creates level 1 tasks from the newly qualifying rule instead. On a non-sequential DSR request, Securiti keeps tasks from both the original and the newly qualifying rule. For more information, see [Configuring sequential task processing in the DSR form](/latest/docs/configuring-sequential-task-processing-in-dsr-forms).

## Related

- [Manually initiating request clarification from dashboard](/manually-initiating-request-clarification-from-dashboard.md)
