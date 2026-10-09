---
title: "Manually initiating request clarification from dashboard"
slug: "manually-initiating-request-clarification-from-dashboard"
updated: 2025-11-04T05:14:11Z
published: 2025-11-04T05:14:11Z
canonical: "helpcenter.securiti.ai/manually-initiating-request-clarification-from-dashboard"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Manually initiating request clarification from dashboard

Once you have configured the [supplemental form](/v1/docs/request-clarification-in-dsr), you can initiate the request clarification from the DSR dashboard. Creating and publishing supplemental forms

> [!NOTE]
> **Note**
> 
> You can raise a request clarification for a DSR only if it is an external DSR and not in the Completed state. For internal DSR requests, you can initiate a request clarification only if the Data Subject has an associated Privacy Central account.
> 
> ![Screenshot_2025-02-13_at_4_39_07_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-35ff9070-f474-4370-d6e9-4366b1b2509a.png)

1. On the DSR dashboard, locate the card for the DSR request. At the right end of the card, choose **Options (three dots) > Request Clarification**.
2. Select the supplemental form you want to send to the Data Subject for more details.

Optionally, click Edit Template, give descriptive name to the Subject and select bind variables to include in the message body. These variables act as dynamic placeholders, automatically replaced with specific values when the invite is sent. For more information, see [Configuring DSR email notification templates](/v1/docs/configuring-dsr-email-notification-templates).
3. Once done, click **Submit**

![Screenshot_2025-02-13_at_4_35_43_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-898e86db-31ae-0f7a-77e7-f14424cfde21.png)

This sends an email to the Data Subject asking for additional details needed to process their DSR request. The email includes a link to the DSR Request Center, where they can provide the required information. For more information, see [Submitting more details for request clarification.](/v1/docs/setting-up-privacy-central-account)

Once the data subjects submit additional details, Securiti automatically adds submitted form data to the DSR request and shows it in the DSR workbench under the Data Subject details panel. It links supplemental form fields to the original DSR form using unique keys.

> [!NOTE]
> **Note**
> 
> A unique key links a form field to a specific value in the database, ensuring updates apply to the correct field instead of creating duplicates.

Securiti updates DSR request details using one of two methods:

If the form includes new personal identifiers, Securiti re-scans data systems to fetch relevant data in the workbench. The DSR workbench also displays the status of the clarification request raised against the respective DSR request.

![request_clarification_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad26b910-cca0-eda5-ea16-525449c181d7.png)
  - **Updating existing fields:** If the unique keys match, Securiti updates the corresponding fields in the original DSR request within the DSR Workbench.
  - **Appending new details:** If the unique keys don’t match, Securiti adds the new details to the original request, ensuring all information stays together in the Data Subject details panel.

![request_clarification_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-53017f6a-fdae-d48e-d6cc-76bc10ea05c0.png)
