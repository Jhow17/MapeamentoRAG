---
title: "Customize DSR request summary page"
slug: "customize-dsr-request-summary-page"
updated: 2026-01-14T08:17:21Z
published: 2026-01-14T08:17:21Z
canonical: "helpcenter.securiti.ai/customize-dsr-request-summary-page"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Customize DSR request summary page

You can customize the DSR request summary page that data subjects see after they verify their identity. Preview and tailor content for different identity verification states, including third-party verification, passwordless login, and exception cases. You can edit the header text, body content, and top-band color, and customize translations. You can also control which fields appear on the summary page and which fields are hidden.

This update lets organizations manage the content of the DSR request summary page so data subjects see only the most relevant details.

> [!NOTE]
> **Note**
> 
> Securiti does not show the DSR Summary page for requests submitted through internal forms or through an embedded form link for physical (non-digital) requests.

To customize request summary page:

1. Open the form in the DSR form builder, configure all relevant components and click **Customize Summary Page** tab.

Use the preview area on the right half of the page to see what the summary page looks like on computer, tablet, and phone screens. This lets you preview the request summary page as it appears to data subjects. You can use the menu to select a verification scenario and view the configured summary page settings.

![Screenshot_2025-08-25_at_12_52_23_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-57be7a9f-08f7-1012-9241-a280005edddf.png)

Use the table below to define the message shown to the data subject on the summary page under different identity verification outcomes. You can also reset to the default wording that Securiti provides.

| Header background color | Click **Edit Color** (pencil icon) to choose a color from the color picker. You can also enter hex code in the **Background Color** field. |
| --- | --- |
| Page Title (Heading) | Edit the title shown at the top of the request summary page. You can always reset it to the default wording that we offer. |
| Description (3rd Party Verification Enabled) | Lets you edit the description below the title that the summary page shows when third-party verification is enabled for a DSR form. |
| Description (3rd Party Verification Disabled) | Lets you edit the description below the title that the summary page shows when third-party verification is disabled for a DSR form. |
| **Form Content** |
| Heading | Lets you edit the heading that appears above the request information on the summary page. |
| Form Fields to display | Lets you choose which fields from the published DSR form appear on the summary page. Data subjects can submit these fields on the form, but you can enable or disable them to show or hide in the request summary. > [!NOTE] > **Note** > > The summary page hides any form fields configured as hidden in the form settings, even if data subjects provide that information. It also hides fields with no values, even if they are configured as visible. |
| **Conditional User Messages** |
| When passwordless login is disabled | Message for a new user (third-party verification disabled) | Lets you define the message shown to new data subjects when passwordless login is disabled and third-party verification is not required. |
| Message for an Existing User(3rd Party Verification Disabled) | Lets you define the message shown to an existing data subject when passwordless login is disabled and third-party verification is not required > [!NOTE] > **Note** > > The login link is required in the message and is included by default. If it is removed during editing, re-add it by selecting any text and clicking **Add Link** from the top right of the input editor. You can click **Reset to default** at any time to restore it to default wording. |
| Message for a New User(3rd Party Verification Enabled) | Lets you define the message shown to new data subjects when passwordless login is disabled and third-party verification is required. |
| Message for an Existing User(3rd Party Verification Enabled) | Lets you define the message shown to an existing data subject when passwordless login is disabled and third-party verification is required. > [!NOTE] > **Note** > > The login link and identity verification link are required in the message and are included by default. If either link is removed during editing, re-add it by selecting any text and clicking **Add Link** from the top right of the input editor. You can click **Reset to default** at any time to restore the default wording. |
| When Password-less Login is Enabled | Message for a User(3rd Party Verification Enabled | Lets you define the message shown to a Data Subject when passwordless login is enabled and third-party verification is required. > [!NOTE] > **Note** > > The identity verification link is required in the message and is included by default. If the link is removed during editing, re-add it by selecting any text and clicking **Add Link** from the top right of the input editor. You can click **Reset to default** at any time to restore the default wording. |
| Message for a User(3rd Party Verification Disabled ) | Lets you define the message shown to a data subject when passwordless login is enabled and third-party verification is not required. |
| Exceeded DSR Submission Limit Message | Lets you define the page heading and notification text shown to a data subject when they attempt to submit more DSR requests than allowed for that form. For more information on setting the limit, see **Restrictions** section in [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms). |
2. Once done, click **Edit Translations** to edit system-generated translations for the DSR summary page.
