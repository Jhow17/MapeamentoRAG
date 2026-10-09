---
title: "Viewing incipient DSR requests with the Privacy Central dashboard"
slug: "viewing-incipient-dsr-requests-with-the-privacy-central-dashboard"
updated: 2026-01-14T09:27:17Z
published: 2026-01-14T09:27:17Z
canonical: "helpcenter.securiti.ai/viewing-incipient-dsr-requests-with-the-privacy-central-dashboard"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Viewing incipient DSR requests with the Privacy Central dashboard

**Scenario**

As a Data Privacy Officer, you need to monitor pending DSR verifications to avoid delays in fulfilling data access requests. Tracking these manually is time-consuming and prone to missed follow-ups. With the Privacy Central dashboard, you can instantly see all requests awaiting email or ID verification and resend reminder emails when needed. This helps you keep verifications on track and ensures timely compliance.

The Privacy Central dashboard shows you the status of DSR requests that are waiting on external ID verification before they can be accepted and processed. In most cases the requests shown on this page are waiting for the completion of an external process that was triggered by the External Workflow Trigger configuration of a DSR request form. For more information, see [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms).

To open the Privacy Central dashboard, in **Data Subject Rights** choose **Data Subject Rights > Privacy Central Dashboard**.

The dashboard shows the stages and statuses for DSR request verification workflows.

| Stage | Status | Description |
| --- | --- | --- |
| Email Verification | In Progress | The request is waiting for email verification from the data subject. |
| Timeout | If the request times out due to no response from the data subject during email verification, Security automatically marks it as expired. You can configure the timeout duration when setting up the DSR form. For more information, see **Email Expiry** option in [Creating and publishing DSR request forms.](/v1/docs/creating-and-publishing-dsr-request-forms) |
| Failed | When a data subject enters the wrong 4-digit PIN three times, email verification fails after the third invalid attempt. |
| External Identity Verification | In Progress | The DSR request has been sent to an external identity provider and is waiting for a response from services such as ID.me, Jumio, or Unico. You can enable external ID verification when setting up the DSR form. For more details, see **external ID verification** in [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms). |
| Failed | The external verification service responded with an **Identity Failed** status. Securiti also notifies data subjects when their ID verification fails. |
| External Workflow Verification | In Progress | When the request is waiting for a response from an external workflow triggered after the id/email verification process. These workflows are added while setting up DSR forms. For more information, see **External Workflow Trigger** section in [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms). |
| Timeout | The request timed out due to one of the following reasons: - No response from the external workflow within the configured duration. - The DSR trigger node was deleted - The workflow was inactive when the DSR was received You can configure this timeout duration when setting up the DSR form. For more information, see **External Workflow Timeout** option in [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms). |

To view details for a specific request, click the down arrow at the right edge of the request.

To export the contents of the Privacy Central dashboard to a CSV file, near the upper right corner of the table of DSR requests, click **Export**. Securiti emails you a link to download a password-protected zip file containing the dashboard information in CSV format. The email also contains the password to open the zip file.

If encryption is disabled, you can freely download the exported CSV file without the need for a password. For more information on encryption standards, see [Configuring DSR encryption standards](/v1/docs/configuring-dsr-encryption-standards).

You can also skip sending email notifications to your data subjects upon DSR request completion directly from this dashboard.

1. Apply the **External Workflow Verification** filter from the filters panel in the Privacy Central Dashboard.

![Screenshot_2022-11-24_at_4_43_47_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dda1fdd5-7665-8626-0912-74e9febb4fb8.png)
2. Go to the record for which you want to skip sending an email notification to the data subject. Click the **Actions** (three dots) button and then select **Bypass** option.

![Screenshot_2022-11-24_at_4_45_02_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6b64040c-c8b3-aa28-1878-c0b86a7808f3.png)
3. On the **Bypass Request Parameters** popup, select **Skip DSR creation at Securiti and close the Privacy Central request** from the menu.
4. Enter a **Subject** and your custom **Message** that you want to send to your data subject.
5. Mark the **Skip notifying DSR completion to Data Subject** checkbox and click **Submit** as shown below.

![Screenshot_2022-11-24_at_4_46_12_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-007b4d4e-8d31-ea59-2327-4692bfbf10c3.png)

For more information, see [Setting up Privacy Central account](/v1/docs/setting-up-privacy-central-account).
