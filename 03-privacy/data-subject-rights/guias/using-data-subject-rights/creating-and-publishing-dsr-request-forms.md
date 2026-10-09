---
title: "Creating and publishing DSR forms"
slug: "creating-and-publishing-dsr-request-forms"
status: "update"
updated: 2026-10-03T14:57:36Z
published: 2026-10-03T14:57:36Z
canonical: "helpcenter.securiti.ai/creating-and-publishing-dsr-request-forms"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Creating and publishing DSR forms

You can use simple form builder tools in Securiti to quickly create and publish one or more of the forms that data subjects use to submit DSR requests. Customizing how requests are received is a primary focus for managing data subject requests. Privacy professionals need to evaluate their organization's intake needs and capabilities using these criteria when handling data subject access requests:

- Ensure data subjects can access your organization's web forms.
- Identify and support the types of data subjects that align with your organization's business needs.
- Determine the types of requests your organization is liable for or likely to receive based on your data processing activities.
- Identify the jurisdictions where you process personal data and comply with their privacy laws and regulations.

Securiti offers two types of DSR request form:

- **External forms** are the forms that let any data subject submit a DSR request to your organization. You can have multiple external forms. When you create an external form, Securiti publishes it at a URL that you can link to from your website, or embed in a page on your website. When a data subject follows a link and fills out and submits the form, Securiti validates the form as described in [How Securiti verifies data subject identity](/v1/docs/how-securiti-verifies-data-subject-identity). Once the data subject verifies their email address, Securiti assigns the DSR request an ID number and shows it on the DSR dashboard.

> [!NOTE]
> **Note**
> 
> Securiti comes with one or two sample external DSR request forms, typically for CCPA and LGPD. You can use these forms as-is or modify them to suit.
- **Internal forms** are similar to external forms, but are only available to Securiti users within your organization. These are the forms that you use to open a DSR request on behalf of a data subject. Since internal forms are only for your internal use, the choices and options are more aligned with identity profile flexibility, and remove the need for additional features such as file attachments and ID verification:
  - Internal DSR request forms do not allow file attachments.
  - DSR requests submitted through internal forms are not subject to ID verification.
  - Internal forms use a default style template, and you cannot change it.
  - You cannot configure restrictions, attachments, or language settings. The internal template uses the default language settings configured for your Securiti account.

1. In Securiti open **Data Subject Rights**, then choose **Settings > Form Builder**.

Top row on DSR Form Dashboard shows the following stats:
  - Total number of DSR forms created and published.
  - Total number of URLs generated for DSR forms.
  - Total number of unique DSR owners.
  - Total number of organizations added as business units in DSR form configuration.
2. Do one of the following:
  - To create a new form, near the upper right corner of the page, click **+Add New**.
  - To open an existing form for editing, click its card.
  - To create a new form based on an existing one, on the card for the existing form choose **Options** (three dots) **> Clone**.
3. Near the upper left corner of the page, click the pencil icon and give the form a convenient name. Then click the checkmark to save the name.
4. (Optional) Near the upper right corner of the page, click **Manage Form Owners** (pencil icon) as shown below and add co-owners.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-10-03 at 7.39.35 PM.png)

To add a member of your organization as a new Securiti user and make them DSR form owner:
  1. Click Add New Users and use the Add New Users popup to specify the new user by name, email and role.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-10-03 at 6.56.47 PM.png)

The logged-in user can assign the following roles when adding a new user as a DSR Form Owner:

| Logged-in User Role | Roles They Can Assign |
| --- | --- |
| Super Admin | - Super Admin - Organization Admin - DPO - Module Owner - Operator - Module Owner DSR User Profile Role - Module Owner Self Service Portal User Profile Role |
| Org Admin | - Organization Admin |

The **Roles** dropdown menu also includes custom roles where custom access profiles with DSR module permissions were assigned to module owners or users [before migration](/v1/docs/new-role-based-access-control-rbac-en).

> [!NOTE]
> **Note**
> 
> Logged-in users with roles such as , module owner or operator cannot add a new user to the DSR form.

Form owners become the owners of all DSR requests submitted with the form. For more information, see [Understanding the DSR request process](/v1/docs/understanding-the-dsr-request-process).
5. On the Select Form Template page, choose from among the available form templates. Then scroll to the bottom of the page and click **Form Settings**.

For an Internal form, just choose any form template. Your choice is overridden when you designate the form as internal on the Form Settings tab.

The Form Settings page shows you a series of collapsible sections, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-10-03 at 7.39.46 PM.png)
6. On the Form Settings page, apply the following settings in the various sections:

| **Logo & Branding** |
| --- |
| Logo tools | Click **Upload**, then navigate to a file containing your company logo. Then click **Upload** again. |
| Background Color | (Where available) Enter the hex code. |
| Text Color | (Where available) Enter the hex code. |
| **General** |
| Organization/Unit | Enter the name of your organization or unit. We show this information on the list of forms to make it easier to arrange the forms for your different departments or groups. |
| Embeddable Domains | Use the tools to build an allow-list of domains where you can embed the form on a web page with an HTML <iframe> element. If you embed the form in a web page that is not on the list, Securiti does not serve the page. |
| This is an internal form | Mark this checkbox to create an internal form. |
| **Identity Verification** (External forms only) |
| Email ID Verification | Enable or disable standard email verification to verify data subject identity. The option is selected by default. For more information on data subject's identity verification, see [How Securiti verifies data subject identity](/v1/docs/how-securiti-verifies-data-subject-identity). > [!WARNING] > **Important** > > Disabling email verification for certain request types, such as Access or Port, could potentially result in compliance risks and liabilities. Securiti disclaims any liability or responsibility for any risks that may arise from deactivating email verification. |
| Email Expiry | Enter the number of days after which the four-digit code expires, and the DSR request is discarded. |
| External ID verification | To enable verification of the data subject's identity by an external service, mark the checkbox and choose the service from the menu. - **Associate with selective DSR request types**: Mark this checkbox to perform External ID verification on selective DSR types. The menu displays labels for request types configured on the respective DSR form. These labels may differ from those listed on the Request Types page in DSR settings. > [!NOTE] > Note > > If Enable Dynamic Rendering of Request Types is marked, this menu shows every request type configured across your tenant, not just the types configured on this form. For more information, see **Enable Dynamic Rendering of Request Types** in this article's **Response** section. |
| **External Workflow Trigger** (External forms only) |
| Enable External Workflow | Mark this checkbox to configure the form so that it triggers an external workflow, and waits for its completion, before accepting a DSR request submitted with it. You can use this feature to perform such actions as validating the data subject’s identity with a third-party service before accepting the request. Once the workflow completes, it must call a Securiti webhook to resume the DSR request process. For more information, see [Workflow automation in DSR](/v1/docs/workflow-automation-in-dsr). > [!NOTE] > **Note** > > If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. |
| Select Workflow | Choose the workflow to be executed. The workflow must: - Start with a trigger node of type **DSP Trigger** - Have its trigger node Action set to **External Workflow Verification Initiated** - Have **Active** status. |
| External Workflow Timeout | Choose the timeout duration in days. |
| Webhook Endpoint | Copy the URL to the clipboard so you can use it in the external system that the workflow calls. Click **Webhook Details** for more information. |
| **Automatic Request Clarification** |
| Automatic Request Clarification | Enable this to automate the request clarification process. After verifying the data subject's identity, they receive an email requesting additional details relevant to the DSR request. > [!NOTE] > **Note** > > If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. When you set up a DSR form, automatic request clarification is off by default. You can still initiate it [manually from the DSR dashboard](/v1/docs/manually-initiating-request-clarification-from-dashboard) for submitted requests. If you turn it on later in the DSR form, it only applies to new requests, not ones submitted while it was off. For appeals, you can only [request clarifications manually](/v1/docs/manually-initiating-request-clarification-from-dashboard) from the DSR dashboard. |
| Select Supplemental Form | Select the supplemental form you want to use for request clarification. The menu shows all published supplemental forms within the org. For more information, see [Creating and publishing supplemental forms.](/v1/docs/request-clarification-in-dsr) |
| Associate with selective DSR request types | Mark this checkbox to initiate request clarification for selective DSR types. The menu displays labels for request types configured on the respective DSR form. These labels may differ from those listed on the [Request Types](/v1/docs/configuring-dsr-request-types) page in DSR settings > [!NOTE] > Note > > If **Enable Dynamic Rendering of Request Types** checkbox is marked, this menu shows every request type configured across your tenant, not just the types configured on this form. For more information, see Enable Dynamic Rendering of Request Types in this article's **Response** section. |
| **Response** |
| Response Deadline for | Do one of the following: - Choose a regulation type (for example, CPRA) or country to set the duration to the maximum response time it allows. When you choose a regulation type or country, it automatically configures the form to accommodate only the DSR request types required under those regulations or in that country. - Choose one of the auto detect options to automatically choose the regulation type based on the data subject's IP address or on the state and country they entered on the form. - Choose Custom and enter custom values for duration and reminder. > [!NOTE] > **Note** > > Securiti has deprecated the CCPA in DSR forms due to CPRA amendments on January 1, 2023. You must update CCPA DSR forms to CPRA by December 31, 2024. Securiti does not let you publish the form if you select CCPA from the **Response Deadline** menu in the DSR form configuration as the CCPA regulation is no longer available for deployment. > > ![new_image_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0147f26c-8ee0-46ae-75e6-2947eb87b25f.png) |
| Enable Dynamic Rendering of Request Types | Mark this checkbox to render request types dynamically based on the data subject's detected residency, instead of always showing every request type configured on the form. This checkbox appears only when Response Deadline is set to Auto Detect Source Country based on IP Address (external forms only) or Auto Detect DS Residency using Country and State (external and internal forms). With IP-based detection: - Securiti determines the applicable regulation as soon as the form is rendered. - Securiti shows the request types associated with that regulation from the [Regulations Support](/latest/docs/using-the-regulations-support-dashboard) dashboard. - If no regulation applies to the detected location, Securiti falls back to the request types configured on the form. With Country and State-based detection: - Securiti shows the form's configured request types first, then re-renders them once the data subject enters or changes Country and State. - If the data subject reaches the form through a Universal form, Securiti determines the regulation from the Country and State already selected there. Securiti does not wait for the data subject to enter these fields again. - If no regulation applies to the entered location, falls back to the request types configured on the form. > [!NOTE] > Note > > If a data subject already selected a request type before Country and State changes the rendered list, Securiti keeps that selection only if it also appears among the newly rendered request types. Otherwise, the data subject must choose a new request type before submitting the form. Where you place the Country and State fields on the form affects the data subject's experience. > [!WARNING] > Important > > We recommend moving the Country and State fields to the top of the form for an optimal experience. Securiti still updates request types correctly even if these fields remain lower on the form. |
| Duration | Accept the default duration for the regulation type, or edit it to suit. To comply with the regulations, we recommend that you do not increase the duration. |
| Reminder | Set the number of days prior to the end of the duration at which Securiti sends the task owner a reminder that the duration expires soon. |
| Enable Extension | Mark this checkbox to enable DSR request deadline extension for the respective regulation. - **Both Automation & Manual Extension:** Mark this radio button to let Securiti apply both automatic and manual extensions to the DSR request deadline. > [!NOTE] > **Note** > > If a DSR request is extended automatically within the allowed period, you cannot extend it manually. A DSR request can only be extended once either manually or automatically. - **Only Automation**: Mark this radio button to let Securiti automatically extend the request deadline and notify the DSR owners and the data subject. - **Only Manual**: Mark this radio button to manually extend the DSR request deadline from the dashboard. Securiti notifies the DSR owners and the data subject about extension. If the Response deadline is set to auto-detect (by IP or by country/state), Securiti applies the extension only if the detected regulation supports it. > [!NOTE] > **Note** > > If the regulation does not allow extensions, no extension is applied, even if an extension option is selected in the form configuration. |
| Duration | Sets the duration of the deadline extension. > [!NOTE] > **Note** > > The duration must be between 1 and 365 days. |
| Select Extension Notification Template | Choose the template for the deadline extension notification that Securiti sends to the data subject. For more information, see [Configuring email notification templates](/latest/docs/configuring-dsr-email-notification-templates). |
| Days Remaining | Set the number of days prior to the end of the duration at which Securiti sends the DSR owners and the data subject notification that Securiti is extending the deadline. > [!NOTE] > **Note** > > This option is not applicable when only manual DSR extension is enabled. |
| Customize response deadline by request type | > [!NOTE] > **Note** > > Securiti sets CPRA as a default regulation for all newly created DSR forms. Mark the checkbox to customize the DSR form response deadlines based on different DSR request types. Securiti automatically populates custom request type deadlines for CPRA. The feature is available only for future DSR forms, meanwhile old ones still require manual entry of custom deadlines. > [!NOTE] > **Note** > > If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. |
| Add Rule | Click to add a new rule for the custom DSR form response deadline. |
| DSR Types | Select the type of DSR request from the menu. The menu displays labels for request types configured on the respective DSR form. These labels may differ from those listed on the [Request Types page](/v1/docs/configuring-dsr-request-types) in DSR settings. |
| Duration | Accept the default duration for the response deadline of DSR type, or edit it to suit. To comply with the regulations, we recommend that you do not increase the duration. |
| Reminder | Set the number of days prior to the end of the duration at which Securiti sends the task owner a reminder that the duration expires soon. > [!NOTE] > **Note** > > The number of days for the reminder should always be less than the set duration. |
| Enable Extension | Mark this checkbox to enable DSR request deadline extension for selected request types. - **Both Automation & Manual Extension**: Mark this radio button to let Securiti apply both automatic and manual extensions to the response deadline of the selected DSR request type. > [!NOTE] > **Note** > > If the request is extended automatically within the allowed period, you cannot extend it manually. - **Only Automation**: Mark this radio button to let Securiti automatically extend the response deadline of the selected DSR request type. Securiti notifies the DSR owners and the data subject. - **Only Manual**: Mark this radio button to manually extend the response deadline of the selected DSR request type. Securiti notifies the DSR owners and the data subject. > [!NOTE] > **Note** > > If multiple DSR request types are extended by different methods (automatic or manual), the request type with the shorter duration takes priority. If both request types have the same duration, the system cannot guarantee the outcome. |
| Duration | Accept the default duration for the auto extend selected response deadline of DSR type, or edit it to suit. To comply with the regulations, we recommend that you do not increase the duration. > [!NOTE] > **Note** > > You must add only positive numbers between the range of **1** and **365**. Decimals are not allowed. |
| Select Extension Notification Template | Choose the template for the deadline extension notification that Securiti sends to the data subject. For more information, see [Configuring DSR email notification templates.](/latest/docs/configuring-dsr-email-notification-templates) |
| Days Remaining | Set the number of days prior to the end of the duration at which Securiti sends the DSR owners and the data subject notification that Securiti is extending the deadline > [!NOTE] > **Note** > > Days Remaining should be less than the number of days set for the **Reminder** field. Also, this option is not applicable when only manual DSR extension is enabled. |
| Delete Rule | Click to delete the current or existing custom rule for the custom DSR form response deadline. |
| Enable Appeals | Mark the checkbox to let data subjects submit an appeal to challenge decisions made in response to their requests. If a data subject feels dissatisfied with a DSR report shared in response to a submitted DSR request, they can initiate an appeal to pursue reconsideration or resolution. For Connecticut, Colorado and Virginia regulations, Securiti enables the appeal flow by default. > [!NOTE] > **Note** > > If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. |
| Duration | Accept the default duration for the regulation type, or edit it to suit. To comply with the regulations, we recommend that you do not increase the duration. |
| Reminder | Set the number of days prior to the end of the duration at which Securiti sends the task owner a reminder that the duration of the appeal request expires soon. |
| Enable Extension | Mark this checkbox to enable extension for DSR appeal deadline. - **Both Automation & Manual Extension**: Mark this radio button to let Securiti apply both automatic and manual extensions to the response deadline of the DSR appeal. > [!NOTE] > **Note** > > If the appeal is extended automatically within the allowed period, you cannot extend it manually. - **Only Automation**: Mark this radio button to let Securiti automatically extend the response deadline of DSR appeal. Securiti notifies the DSR owners and the . - **Only Manual**: Mark this radio button to manually extend the response deadline of appeal. |
| Duration | Sets the duration of the appeal deadline extension. > [!NOTE] > **Note** > > Duration must be between 1 and 365. |
| Select Appeal Notification Template | Choose the template for the appeal deadline extension notification that Securiti sends to the data subject. See [Configuring DSR email notification templates](/v1/docs/configuring-dsr-email-notification-templates) for more information about appeal notification templates |
| Days Remaining | Set the number of days prior to the end of the duration at which Securiti sends the DSR owners and the data subject notification that you are extending the appeal deadline. |
| Time limitation to file an appeal | Set the time limit for data subjects to submit an appeal after the completion of a DSR request. The countdown begins once the DSR report is published. > [!NOTE] > **Note** > > The maximum allowable time limit for data subjects to submit an appeal request is 10 years (3650 days). |
| Maximum characters for appeal reason | Specify the character limit for data subjects when articulating appeal reasons while submitting an appeal request. > [!NOTE] > **Note** > > The minimum character count for providing appeal reasons is 100, while the maximum limit is 5000 characters. |
| Maximum number of file attachments | Specify the number of files data subjects can upload during the appeal filing process. > [!NOTE] > **Note** > > A data subject can attach a maximum of 10 files with their appeal request. Additionally, each file size cannot exceed 10 MBs. To disable data subjects from uploading attachments, set max attachments limit to zero. |
| **Restrictions** (External forms only) |
| Allowed Requests | Set the maximum number of DSR requests allowed from each data subject per request cycle. If a data subject submits more requests than the maximum, Securiti sends them a notification consisting of the text in the Restrictions Text box. |
| Request Cycle | Set the duration for which the allowed requests value applies. |
| Allow parallel requests | Mark the checkbox to allow Securiti to process multiple DSR requests from the same data subject at the same time. Clear the checkbox to make Securiti process only a single DSR request at a time for each data subject. |
| Allow same type requests | Mark the checkbox to allow parallel requests of the same type. |
| Minimum duration between requests | Enter the request interval in days. |
| **Attachments** (External forms only) |
| Enable Attachment upload | Mark the checkbox to configure the DSR form to include options that let data subjects attach and upload files. The form allows a maximum attachment size of 10 MB and up to 3 attachments. > [!NOTE] > **Note** > > Securiti performs anti-virus checks on any attachments submitted by data subjects, as well as attachments added by internal teams through the DSR Workbench. Additionally, If a data subject attaches a file larger than 10 MB, the request submits, but the attachment does not appear in the **Data Subject Details** section of the **DSR Workbench**. This is happening due to an issue in the third-party library being used. We are actively investigating the matter. |
| Mandatory | Mark the checkbox to require an attachment for each DSR request. |
| Caption for Attachment field | Enter the caption that identifies the Attachment field on the DSR form. |
| **Automation** |
| Automate Sub Task Completion | Mark the checkbox to automate completion of sub tasks created in response to the DSR. Subtasks are automatically transitioned to Success state if Securiti encounters no errors. > [!NOTE] > **Note** > > All DSR request types except for **Access**, **Port**, **Confirmation**, and **Disclosure of Subprocessors** requests are supported only for scanless and user-defined (webhook) data system connectors. Hybrid/Scanned connectors are not supported under automated sub-task completion. |
| Auto Generate report & close DSR request | Mark the checkbox to make Securiti automatically generate the DSR report, publish it to the DSR request center, and close the DSR request. |
| Associate with Workflows | Mark the checkbox and build a list of workflows to make Securiti associate the form with those workflows. The workflows must have DSR trigger nodes. Submitting the form triggers the workflows, as long as they are active at the time the data subject submits the form. For more information, see [Workflow Automation in DSR](/v1/docs/workflow-automation-in-dsr) |
| Include Data Systems | Mark the checkbox to associate DSR requests received through the form with specific data systems. Choose one or more data systems to associate with the DSR form. Observe the following caveats: - When you add data systems, you must update and re-publish the form for the changes to take effect. - You must mark the "Include this instance in DSR workflow" checkbox on the Basic Information tab for each associated data system connector. |
| Exclude Data Systems | Choose one or more data systems to explicitly not associate with the DSR form. |
| Delay task creation | Mark the checkbox to make Securiti delay creation of subtasks for the associated data systems. Only applies to scanless and user-defined (webhooks) data system connectors. |
| Select data systems for delay | Enter the number of hours or days to delay subtask creation for the associated data systems. |
| **Request Type** |
| No Privacy Central account creation | Mark the checkbox to skip Privacy Central account creation for request types that do not return a sensitive data report to the data subject, such as Do Not Sell, Do Not Share, and Opt-Out requests. Instead of creating an account and password, Securiti sends the data subject a one-time passwordless login link. **Request Type:** Use this menu to select which request types this setting applies to. Keep these points in mind: - If [tenant-level passwordless login setting](/latest/docs/setting-up-privacy-central-account) is enabled, the form-level configuration is not consulted. Securiti sends a one-time passwordless link for the request, regardless of which request types were submitted. - If both your tenant-level passwordless login setting and your form-level configuration are disabled, Securiti requires standard password-based login for the request. - If your tenant-level passwordless login setting is disabled and every request type submitted is selected in the Request Type field of this setting, Securiti sends a one-time passwordless link for the request. - If your tenant-level passwordless login setting is disabled and at least one request type submitted is not selected in the Request Type field of this setting, Securiti falls back to standard password-based login for the whole request. This includes the request types that were selected. For more information on the login flow, see [How Securiti verifies data subject identity](/latest/docs/how-securiti-verifies-data-subject-identity). |
| Allow choosing multiple request types per DSR | Mark the checkbox to let data subjects submit multiple DSR requests at the same time. Clear the checkbox to only let data subjects submit one DSR request type at a time. When you select this option, the Request Type part of the form is a set of checkboxes of which data subjects can mark more than one. Otherwise Request Type is a set of radio buttons of which data subjects can choose only one. |
| **Rectification Fields** |
| Customize attribute list | Mark the checkbox for Customize Attribute List, click in the Select PD Attributes box, then mark the checkboxes next to the attributes you want available on the form. If you clear the checkbox, the DSR request form offers every available PD attribute for rectification. |
| **Signal to Cookie Consent** |
| Signal to Cookie Consent to turn off non-essential cookies | Mark the checkbox to turn off non-essential cookies on a website once a data subject submits Don’t Sell or Share request type. For more information, see [Sending Do Not Sell or Share Signal for cookie preferences](/latest/docs/configuring-signal-to-cookie-consent-in-dsr-form). |
| **Report Settings** |
| Allow non-digital report access | Mark the checkbox to accept and process DSR requests from data subjects who do not have, or do not want to use, email addresses. This option also accommodates DSR requests for data subjects who want to receive their reports in physical format. See [Accepting non-digital DSR requests](/v1/docs/accepting-non-digital-dsr-requests) for more information. |
| Remove DS Portal Account access for Non-digital DSRs | Mark this checkbox to restrict a data subject's access to Privacy Central, specifically for non-digital reports. This functionality applies in scenarios where you are processing non-digital DSR requests, printing the final reports, and mailing them directly to the individuals instead of granting them portal access for self-download. |
| CSV report delimiter | Use the menu to choose the delimiter used in the .CSV files that Securiti sends to data subjects as parts of DSR reports. |
7. Click **Customize Content**.
8. On the Customize Content page, use the form builder tools to customize the form.
  1. Use the Headline, Body, and Footer tools to customize the text at the top and bottom of the form.
  2. Use the Define Form Fields and Requirements area to customize the fields that data subjects fill out. You can click and drag fields to different locations, or add static and custom fields by dragging them onto the form, as shown below. See [Form Builder Tabs](/v1/docs/form-builder-tabs) for more information about editing the form components.

![Cookie_notice_field.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86bf34ac-d1d2-6ea0-deef-2694b44bed7e.png)

The form display on the right half of the page shows you what the form will look like when you publish it.

> [!NOTE]
> **Note**
> 
> If you want to use enhanced DSR processing using identity PD other than email address, see [Configuring DSR request forms for multiple identifiers](/v1/docs/configuring-dsr-request-forms-for-multiple-identifiers) for more information about configuring DSR request forms.
9. On the Language Translations page, you can configure languages you want to support in your DSR forms. The section also lets you edit system-generated translations.

| **Language Translations** (External forms only) |
| --- |
| Enable Languages Preference | Enable this to let data subjects choose their language preference from a menu on the DSR form. The form appears in the selected language |
| Select languages | From this menu, select languages in which you want to make the form available. For more information, see [Supported languages in Data Subject Rights](/v1/docs/supported-languages-in-data-subject-rights). |
| Default language | Choose the default language in which the form appears when the data subject does not choose a language from the menu. |
| Enable Language Intelligence | Mark the checkbox to translate the DSR form into one of the data subject’s browser languages that align with the language options you've set for language preference. Keep these important points in mind when using the Language Intelligence option in DSR form settings: - If you enable language preference but disable the language intelligence option, then the default language of the form is the one you set during the form setting. - When both the language preference and intelligence options are enabled and the data subject’s browser language matches one of the preferred languages, the form is automatically translated into that language. In this case, the system does not consider the default language set during the form settings. > [!NOTE] > **Note** > > If the browser has multiple languages, the DSR form is translated based on the first language that matches the language preference list. - If both language preference and intelligence are enabled but the data subject's browser language isn't in the preference list, the system uses the default form language. > [!NOTE] > Note > > For Chinese languages, the DSR form maps browser language variants such as Chinese (zh) and Chinese Simplified (zh-CN) to Chinese (Simplified), and Chinese Traditional (zh-TW) and Chinese Hong Kong (zh-HK) to Chinese (Traditional). This ensures consistent language detection when Language Intelligence is enabled. |
| Language Translations | This section shows you machine generated translations for request types and form fields configured on the DSR form. You can further customize these translations as per your need. For more information, see [Customize translations for DSR forms](/v1/docs/customizing-translations-for-dsr-forms). |
10. Use the preview area on the right half of the page to see what the form looks like on computer, tablet, and phone screens, as shown below. You can also hide the preview area by marking **Preview** checkbox.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-10-03 at 7.05.04 PM.png)
11. When you are done, click **Review & Publish**.

> [!NOTE]
> **Note**
> 
> If you switch to another DSR form without reviewing and publishing, Securiti displays a warning that unsaved work will be lost. You must confirm whether to continue or cancel.
12. Review the form, then click **Publish** if it looks OK.

If not, click the **X** in the upper right corner and go back and make any necessary changes.
13. On the DSR Form Builder Page, click the entry for the new form.
14. (External forms only) On the page for the form, copy the published link or embeddable as shown below and record it for later use are the links that you publish or embed on your website for anyone who wants to submit a DSR request.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-10-03 at 7.13.03 PM.png)

Or from the forms dashboard choose the form row and click **More Actions** (3 dots) > **Copy URL** or **Copy Embedded Form URL**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-10-03 at 7.18.52 PM.png)

> [!NOTE]
> **Note**
> 
> Securiti external DSR forms use standard anti-crawling patterns to prevent search engine indexing. If you embed a form on your website, make sure you implement standard anti-crawling patterns to prevent search engines from including the form in search results.
15. (External forms only) Work with your website team to either publish the link to the DSR form, or to embed it in a page on your website.

Securiti uses hCaptcha to prevent bots from submitting DSR requests through hosted or embedded forms, ensuring compliance with privacy regulations.

Securiti lets data subjects use the enhanced accessibility settings to make the published DSR forms usable by individuals of all abilities. They can enable high color contrast to improve visibility, meet WCAG compliance, and support a wide range of users.
  1. At the bottom right corner of the published form, data subjects can click **Accessibility Settings**.
  2. On the Accessibility Settings popup, enable **Enable high contrast for increased visibility** toggle and click **Apply Settings**.

---

### FAQ

#### 1. What additional verification options do we have available? Can additional options be configured?

Apart from the email verification, you can also configure third-party identity verification processes to validate the submitted DSR requests. For more information, see [How Securiti verifies data subject identity](/v1/docs/how-securiti-verifies-data-subject-identity)

#### 2. How does “Allowed Requests” and “Request Cycles” affect the “Allow choosing multiple request types per DSR” toggle?

You can enforce a limit on the number of DSR requests a data subject can submit within a single **Request Cycle**, defined by the **Allowed Requests** value. For instance, if you set the Allowed Requests to 10 and the Request Cycle to 7, the data subject can submit 10 DSR requests within a 7-day period. If the limit is exceeded, the form displays a warning, indicating that you cannot proceed with further requests..

On the other hand, the **Allow choosing multiple request types per DSR** option lets data subjects submit multiple **DSR request types** in a single DSR request. When you select this option, the Request Type section of the form consists of checkboxes, allowing data subjects to mark more than one. Otherwise, the Request Type is a set of radio buttons, and data subjects can choose only one.

In this scenario, if a data subject submits a DSR request of both "access" and "port," Securiti considers the request as one and assigns single ID number to that DSR request.

The California Consumer Privacy Act (CCPA) was the first state-level comprehensive privacy law in the United States. It applies broadly to for-profit businesses that collect personal information from California consumers, creating certain rights for consumers and obligations for businesses in relation to personal data processing. It was amended by the California Privacy Rights Act (CPRA) in 2020.

External ID verification is also called third-party identity verification which refers to verifying the data subject’s identity by an external source. Securiti uses email ID verification as a conventional method for authenticating the identity of data subjects. Additionally, the platform provides three alternative external identity verification options: Unico, [ID.me](http://ID.me), and Jumio.

The California Privacy Rights Act (CPRA) amended the CCPA by adding additional consumer privacy rights and obligations for businesses. It also created the California Privacy Protection Agency (CPPA), tasked with enforcing the law and educating the public on their rights and obligations under the law.

A rule defines the conditions under which one or more task templates or workflows are triggered for incoming DSR requests. Each rule evaluates request metadata, such as request type, data subject type, jurisdiction, location, or specific form fields, and applies the assigned task templates or workflows when all conditions are met.

## Related

- [Form Builder Tabs](/form-builder-tabs.md)
- [Configure DSR form for dynamic request types](/configure-dsr-form-for-dynamic-request-types.md)
- [Configuring rules in the DSR form](/configuring-rules-in-the-dsr-form.md)
- [Customize DSR request summary page](/customize-dsr-request-summary-page.md)
- [Customizing translations for DSR forms](/customizing-translations-for-dsr-forms.md)
