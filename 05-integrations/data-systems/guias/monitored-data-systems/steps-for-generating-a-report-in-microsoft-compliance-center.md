---
title: "Steps for generating a report in Microsoft Compliance Center"
slug: "steps-for-generating-a-report-in-microsoft-compliance-center"
updated: 2026-08-11T11:50:26Z
published: 2026-08-11T11:50:26Z
canonical: "helpcenter.securiti.ai/steps-for-generating-a-report-in-microsoft-compliance-center"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Steps for generating a report in Microsoft Compliance Center

Microsoft Compliance Center (MCC) serves DSR via scheduled DSR.

When you submit a request through the Securiti portal, Securiti prepares the request according to MCC's input requirements and generates a corresponding request in the MCC portal.

## Configuring steps for generating a report

To configure steps for generating a report in MCC:

1. On the Privacy management: Subject rights requests page, click **Actions (three vertical dots)** next to a request and select **Go to request details**, as shown below.

![Priva_Subject_Rights_Requests.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5dff9420-d5c6-2e7a-5375-8d575852603d.png)

![Click_Actions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-129547b8-b9eb-6a5a-9898-f2d80da2d1a5.png)
2. In the upper right corner of the page, click **Retrieve data**, as shown below.

![Click_Retrieve_data.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d3bf64e2-6839-5515-6e44-5a02c6b2a35e.png)

> [!NOTE]
> **Note**
> 
> By default, the Progress card displays status "Data estimate", and it may take an hour to fetch the searched data.

The progress then moves to the "Review data" stage.

![Review_data.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ec0b88af-28f4-4bc9-6906-9e18cc6d2f2b.png)
3. Click the **Data Collected** tab and mark the rounded checkbox next to the Item name on the left, as shown below

![Mark_the_rounded_checkbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08ec6ec1-dbb7-e51b-607d-3b0c3265d948.png)
4. Click the **Include** button (card icon with a checkmark). On the Include items flyout menu to the right, enter any notes and click **Submit**, as shown below.

![Click_Include.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3f0c4918-895e-6508-4b50-63580f09c253.png)

![Enter_notes_and_click_Submit.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52647f7e-a842-0770-dfb4-b744297e2650.png)

> [!NOTE]
> **Note**
> 
> Unmark the rounded checkbox for any items you don't want. The "Review status" Column shows Excluded for those documents.
5. Once done, click **Complete review** in the upper right corner of the page. Input note in the mandatory "Note" dialog, and click **Complete review** again to continue, as shown below.

![Complete_review.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a9db0b19-644d-6683-e74a-29d5a46d87be.png)

![Complete_review_and_Input_note.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8002da8c-fab2-3d6d-d232-94cd68773688.png)
6. Click **Generate reports** once the review's completed. To the right, click **Generate reports** again to complete the process on the flyout menu, as shown below.

![Generate_reports.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-866c62e5-2a34-aa4a-ea24-510cceabed06.png)

![Click_Generate_reports.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-395a2b3e-ee04-d844-348c-b88942837a2e.png)

> [!NOTE]
> **Note**
> 
> Report generation may take 30-45 minutes on average.
7. Click **Close the request** in the upper right corner of the page, then **Close the request** on the flyout menu to start pulling data, as shown below.

![Close_the_request.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be8c6b38-73e0-da1a-ff91-cdbe2fd8d034.png)

![Click_Close_the_request__flyout_menu_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f93d29af-c86b-877f-6dfe-fbb0cca4b6db.png)

Meanwhile, a scheduled task checks for data availability on the Securiti portal.

## Conditions

Observe the following caveats:

1. If the data isn't available in MCC, Securiti checks for it after another hour.
2. Once found, Securiti fetches the data, removes unwanted files, and retains only the relevant ones. Securiti then packages the results into a zip file and attaches it to the request.

The attachments are of two types:
  - **Text file attachments:** Text version of all file types.
  - **Native file attachment:** Specific version of each file such as .doc, .pdf, etc.
