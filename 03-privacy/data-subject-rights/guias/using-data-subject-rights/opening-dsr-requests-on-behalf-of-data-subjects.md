---
title: "Opening DSR requests on behalf of data subjects"
slug: "opening-dsr-requests-on-behalf-of-data-subjects"
updated: 2026-06-18T11:40:23Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/opening-dsr-requests-on-behalf-of-data-subjects"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Opening DSR requests on behalf of data subjects

**Scenario**

As a Data Privacy Officer, you often receive DSR requests through email or phone. Asking data subjects to resubmit through a public form may not be possible. With internal DSR forms, your support team can directly log requests on behalf of Data Subjects and route them to your existing process. This lets you respond promptly and ensures all requests, regardless of source, are recorded in one system and follow the same review and fulfillment workflow in Securiti

### Overview

Under normal circumstances, data subjects open DSR requests by submitting them through the Securiti DSR form you publish as described in [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms). However, You can initiate DSR requests on behalf of data subjects based on requests received via email or other communication channels from those individuals. This functionality is useful when you receive DSR requests through channels not directly integrated with the module, such as phone calls, physical mail, or emails. In such cases, there may be a delay between when you receive and log the request.

> [!NOTE]
> **Note**
> 
> Securiti lets the following roles in your Securiti tenant open DSR requests on Data Subject’s behalf:
> 
> - Super Admins
> - DPO
> - Org Admins
> - Module Owners
> - Operator

1. In Securiti, choose **Data Subject Rights > Dashboard** to open the [DSR Dashboard](/v1/docs/using-the-data-subject-rights-dashboard) page.
2. Near the upper right corner of the DSR Dashboard, click **+Create**. Securiti opens the Create DSR page.
3. On the Create DSR page, fill in the following fields:

| Field | Description |
| --- | --- |
| Select a Form | Choose the internal DSR request form to use. For more information about creating and customizing internal DSR request forms, see [Creating and publishing DSR request forms](/latest/docs/creating-and-publishing-dsr-request-forms). |
| Creation Date | For any creation date you set for an internal request submission, the time log will be 12:00 AM (start of the day). If the creation date and deadline have both passed, and you have enabled auto-extension on the form, Securiti automatically extends the DSR request on your behalf. In this case, Securiti does not send notifications to the Data Subject regarding this extension. However, you may still have a regulatory obligation to inform them, so be sure to review applicable transparency requirements. |
| Timestamp | Enter the timestamp before submitting the request. - If you select the current date, Securiti does not let you choose a future time. - If you select a past date, Securiti lets you select a future time. - If you do not set the timestamp, Securiti defaults it to the start of the day (12:00 AM). |
| Timezone | By default, Securiti sets the current system timezone when you open the internal form. You can adjust it before submitting the request. > [!NOTE] > Note > > Securiti captures this time zone to display submitted date, created date, and deadline values in DSR email notification templates. For API-based requests, if the system does not receive a time zone, Securiti uses UTC as the fallback time zone. |
| Work on this request upon creation | Mark this checkbox if you want to start working on the DSR request immediately after it is created. |
| Create or associate with data subject account in Privacy Central portal | Optional) Mark this checkbox to invite the Data Subject to create a Securiti account. While DSR requests submitted with the internal DSR request form are not subject to ID validation, you can use this checkbox to have send an email to the Data Subject when it creates the DSR request. The email invites them to create an account so that they can later log in to the portal to access their report. |
| Scope for Search in Data Systems | (Optional) Mark this checkbox to narrow the Outlook search for this DSR to specific mailboxes and keywords. This option is only available when Microsoft 365 Outlook (Self-Hosted) with Smart Search enabled is part of the applicable data systems. For more information, see Focused search scope for Microsoft 365 Outlook (Self-Hosted) in internal DSRs. > [!NOTE] > Note > > This feature is available only for internal DSRs. If this is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. |
| Data Subject Information | Fill in the relevant details for the data subject, such as name, email address, and other identifiers. The fields available depend on the configuration of your internal DSR request form. |
| Request Type | Select one or more request types (for example, Access, Erasure, Rectification). For more information, see [Configuring DSR request types.](/latest/docs/configuring-dsr-request-types) |

What fields are available, and which ones are required, is determined by the configuration of your internal DSR request form. For more information, see [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms).
4. Once done, Click **Submit Request**.
