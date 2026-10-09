---
title: "Data Subject Rights release notes"
slug: "data-subject-rights-release-notes"
updated: 2026-09-22T04:17:45Z
published: 2026-09-22T04:17:45Z
canonical: "helpcenter.securiti.ai/data-subject-rights-release-notes"
area: privacy
modulo: data-subject-rights
tipo: release
data_captura: 2026-10-08
---

# Data Subject Rights release notes

## 1.151

### Release updates - September 2026

#### Configuring passwordless login for specific request types in a DSR form

Securiti now lets you skip account creation for request types that do not require a sensitive data report, such as Do Not Sell, Do Not Share, and Opt-Out requests. Instead, Securiti sends the data subject a one-time login link for instant portal access.

> [!NOTE]
> Note
> 
> The login link for this setting defaults to a 3-day expiry, matching the existing tenant-level passwordless login default.

Previously, this control existed only at the tenant level, applying to every request type across all of your DSR forms. This release adds the same control at the form level, and lets you configure passwordless login for specific request types within a single form. Other request types on that same form still require an account.

To configure this, open **DSR Form Builder** and create a new form or edit an existing one. In the **Request Type** section, mark the **No Privacy Central account creation** checkbox, then select the request types it applies to.

![Form settings for data requests, highlighting privacy options and required user information fields.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-15 at 4.01.00 PM.png)

Use the following table to understand the resulting behavior when a DSR form mixes request types:

| Tenant-level passwordless login | Form-level configuration | Result |
| --- | --- | --- |
| Enabled | Ignored, even if configured | Securiti sends a one-time passwordless link for the request, regardless of which request types were submitted. |
| Disabled | Not configured | Securiti falls back to the tenant-level setting, which is disabled, so the request requires standard password-based login. |
| Disabled | Configured, and every request type submitted is in the configured list | Securiti sends a one-time passwordless link for the request. |
| Disabled | Configured, and at least one request type submitted is not in the configured list | Securiti falls back to standard password-based login for the whole request, including the request types that were in the list. |

If a data subject submits multiple requests with the same email address, and only some qualify for passwordless access, Securiti still groups all of their requests together in the Privacy Central portal. After the data subject opens the portal through a passwordless link, they can also access requests that would otherwise require an account.

For more information, see [Creating and publishing DSR forms.](/latest/docs/creating-and-publishing-dsr-request-forms)

#### Resolved issue

- Fixed an issue where an audit log message appeared in a popup that closed as soon as users moved the cursor away, before they could read or copy it. Securiti now shows a **Show More** option so users can view and copy the full message (PRIV-260847).

#### API updates

Use the following table to understand the API updates made for Data Subject Rights in this release:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/privaci/v1/admin/dsr/forms/{id}` | PATCH | **New parameters:** We have added the following new parameters: - `enforce_passwordless_login`: Specify whether to enforce passwordless login for specific request types. - `passwordless_login_enforced_request_types`: Specify the request type(s) that require passwordless login. |

For more information, see [Data Subject Rights API documentation.](https://securiti-doc-router.securiti.ai/modules/data-subject-rights/apidocs/index.html)

## 1.150

### Release updates - August 2026

#### Reopening closed DSRs

Securiti now lets you reopen a closed DSR request instead of creating a new one. For instance, if a data system did not finish processing before you closed the request, you can reopen it to finish fulfilling it.

In the Data Subject Rights module, choose **Settings > DSR Settings**, scroll to the **Reopen DSRs** section, then click **Edit** (pencil icon). Mark the **Allow Reopen of DSRs** checkbox, review the notice on the *Enable DSR reopen* popup, click **Yes, Proceed**, then click **Save**.

![Settings for Data Subject Rights, including options to pause and reopen requests.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-25 at 1.19.20 PM.png)

> [!NOTE]
> Note
> 
> - Only Super Admins can enable this setting for your tenant. This setting is disabled by default, and all other roles have read-only access to it.
> - Once enabled, the following roles can reopen an eligible closed request from the DSR workbench:
>   - Super Admin
>   - Organization Admin
>   - Operator
>   - DPO
>   - Module Owner

To reopen a request, open it in the DSR workbench. Near the upper right corner, click the **More Actions** menu (three dot icon), then click **Reopen DSR**.

![DSR access request details for David Smith, including decline reason and processing information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-26 at 5.11.45 PM.png)

On the popup, choose whether to resume the existing deadline or start a new one. Choose a reason from the **Reason** menu, or add a custom reason. This field is mandatory. Mark the **Re-scan DSR** checkbox to rescan the request as part of reopening it.

> [!NOTE]
> Note
> 
> If you do not mark the **Re-scan DSR** checkbox, Securiti does not automatically rescan a reopened request. Each task and subtask keeps its existing status. You can rescan manually if needed.

Further, mark the **Notify Data Subject about reopening of this DSR** checkbox and edit the email content if needed, then click **Proceed**.

![Confirmation prompt for reopening a Data Subject Rights request with required details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-25 at 1.21.14 PM.png)

> [!CAUTION]
> Caution
> 
> Most privacy laws and regulations do not expressly provide for the retroactive amendment or reopening of completed DSR requests. You are responsible for determining whether reopening a request, and any resulting deadline recalculation, is permitted under the laws that apply to it. Using this feature might require a documented reason for reopening, consideration of the impact on regulatory deadlines, and notification to the data subject.

You cannot reopen a DSR request in the following cases:

- This setting is disabled for your tenant.
- The request is not yet closed.
- The data subject has raised an appeal for the request.
- The data subject has deleted the request from Privacy Central.
- Securiti is still processing a publish or reject operation for the request.

For more information, see [Reopening closed DSR requests](/latest/docs/reopening-closed-dsrs).

#### Filtering data elements in DSR attachments

Securiti now lets you control which data elements appear in the subtask attachment for unstructured data systems. Previously, every discovered data element for a data subject appeared in the attachment, with no way to exclude specific ones.

For instance, if a data system stores a rewards number or a frequent flyer number that you do not want to send, you can exclude that specific element. Every other data element for that data subject still appears.

In the Data Subject Rights module, choose **Settings > Form Builder**, choose the form you want to use or create a new one, then go to the **Rules** tab and click **Add Rules**. On the Rule Details page, mark the **Filter Data Elements for the Report** checkbox, choose **Exclude Data Elements** or **Include Data Elements**, then select the data elements to apply.

![DSR Form Builder interface showing rules and workflows for data management tasks.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-26 at 5.58.21 PM.png)

- If you include data elements, Securiti highlights only those elements and redacts everything else it finds for the data subject.
- If you exclude data elements, Securiti redacts those elements for the data subject and highlights every other data element it finds.

> [!NOTE]
> Note
> 
> The **Select Data Elements** menu lists data elements from your Sensitive Data Intelligence module (**Data Classification > Data Elements**), including any custom data elements you have configured there. If your tenant does not have Sensitive Data Intelligence enabled, this menu shows the standard system data element list instead. For more information, see [Data Elements](/latest/docs/data-elements).

If a DSR request matches more than one rule with this filter configured, and any matching rule excludes data elements, Securiti applies that exclusion and ignores any inclusion rules that also match.

> [!CAUTION]
> Caution
> 
> Global data protection regulations generally require data controllers to provide or act upon all discovered personal data of data subjects in response to data requests and apply exceptions on a case-to-case basis. This feature lets you to generically suppress identified personal data in the disclosure to the data subject. This is why exclusions could lead to non-compliance. You must ensure exclusions meet your legal obligations.

This filter applies only to the data subject's own data, and works independently of the existing DSR Redaction setting, which controls whether Securiti redacts data belonging to other people found in the same file.

In the DSR workbench, the **Subject Details panel** now shows **Data Elements Included in the Report** or **Data Elements Excluded in the Report** sections, listing the data elements the filter applied to for the DSR form used to raise the request.

![Data Subject Rights request overview for Keith Gordon, including tasks and deadlines.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-26 at 6.07.11 PM.png)

Securiti still searches and matches the full record for the data subject, based on the primary identifier such as email. This filter only changes what appears in the final output. It does not change what Securiti searches for or finds. To see this directly, open a subtask for an unstructured data system, scroll down to Object & Data Element discovery, then click **Preview Data Element found in object.**

![Data Subject Rights request dashboard showing tasks and discovered data elements for review.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-26 at 6.13.59 PM.png)

For more information, see [Configuring rules in the DSR form](/latest/docs/configuring-rules-in-the-dsr-form).

#### Overriding the system message across multiple request types

Securiti now lets you override the default "User Not Found" message on DSR requests with multiple request types. Securiti appends this message to a published report when every subtask across the DSR is marked as *No Data*. Previously, this functionality was available only for DSR requests with a single request type.

Open the DSR request in the DSR workbench, then click the **Reports** tab. Once every subtask in the request reaches No Data, click **Approve and Publish Report** or **Reject DSR**. At the top of the popup, mark the **Override the default system message** checkbox. If you leave this checkbox cleared, Securiti appends the default message automatically.

![Approval interface for DSR request with options to customize email notifications and messages.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-26 at 5.07.29 PM.png)

For more information, see [Approving and publishing reports](/latest/docs/approving-and-publishing-reports).

#### Resolved issue

- Fixed an issue where selecting 100 records per page on the DSR Dashboard caused the page to become unresponsive (PRIV-252961).

#### API updates

Use the following table to understand the API updates made for Data Subject Rights in this release:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/privaci/v1/admin/dsr/reopen/config` | GET | We have added this API endpoint in the current release. It lets you fetch the tenant's configuration for reopening closed DSR requests. |
| `/privaci/v1/admin/dsr/reopen/config` | PATCH | We have added this API endpoint in the current release. It lets you update the tenant's configuration for reopening closed DSR requests. |
| `/privaci/v1/admin/dsr/tickets/{id}/reopen` | POST | We have added this API endpoint in the current release. It lets you reopen a closed DSR request to continue fulfilling it. |
| `/privaci/v1/admin/dsr/tickets/{id}/can_reopen` | GET | We have added this API endpoint in the current release. It lets you check whether a DSR request is eligible to be reopened. |
| `/privaci/v1/admin/dsr/forms/{form_id}/rules/create` | POST | **New parameters:** We have added the following new parameters: - `data_element_filter_enabled`: Specify whether to filter data elements in the generated file for this rule. - `data_element_filter_type`: Specify whether to include or exclude the specified data elements. - `data_element_filter_list`: Specify the data element IDs to include or exclude. |
| `/privaci/v1/admin/dsr/forms/{form_id}/rules/update/{rule_id}` | PATCH | **New parameters**: Same as above. |

For more information, see [Data Subject Rights API documentation](https://securiti-doc-router.securiti.ai/modules/data-subject-rights/apidocs/index.html).

---

## 1.149

### Release updates - August 2026

#### Sequential task processing for DSR fulfillment

Securiti now lets you control the order in which a rule's task templates execute. Previously, every template tied to a rule executed together, so all of its tasks and subtasks were created at the same time, regardless of how any of them turned out. This meant later-stage work, like legal review, could start before earlier steps such as verification or retrieval were even resolved, with no way to hold it back.

> [!NOTE]
> Note
> 
> To use this feature, you must upgrade your appliance version to 1.149.0 or later.

Enable **Define Task Sequence** toggle within a rule to organize its templates into up to 4 levels. Level 1 templates execute as they do today. Each level after that executes only once the templates in the level before it reach the status you define, such as approved, declined, error, or no data found. For instance, you can set legal review to execute only after retrieval tasks are approved, instead of running both at once. This lets you sequence dependent work correctly and avoid starting later steps before earlier ones are resolved.

![Task sequence definition for document forms with multiple execution levels and conditions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-04 at 9.35.59 AM.png)

> [!NOTE]
> Note
> 
> Each level supports up to 10 execution blocks, and each execution block can carry multiple conditions through nested rules, so a template's execution can depend on more than one earlier outcome at once. Different templates within the same level can also depend on different templates from the level before, so each one executes independently once its own condition is met.

Once a DSR request is processed as sequential, you can also filter tasks and subtasks by rule and level from the Worklist and Batch Update tabs, making it easier to track progress across levels.

![Dashboard displaying DSR access request with task filters and subtasks overview.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 8.12.11 PM.png)

For more information, see [Configuring sequential task processing in DSR forms](/latest/docs/configuring-sequential-task-processing-in-dsr-forms).

#### Dynamically render request types based on detected residency

Securiti now lets you render request types on a DSR form dynamically, based on the data subject's detected residency, instead of always showing every request type configured on the form regardless of jurisdiction.

> [!WARNING]
> Important
> 
> Do not enable this feature on a form that already uses **Advanced Conditions** with JavaScript to render [request types dynamically](/latest/docs/configure-dsr-form-for-dynamic-request-types). Running both together can produce inconsistent behavior, since each method controls which request types render independently.

If a DSR form's Response Deadline is set to **Auto Detect Source Country based on IP Address**(external forms only) or **Auto Detect DS Residency using Country and State**(external and internal forms), a new checkbox, **Enable Dynamic Rendering of Request Types**, appears in the form settings. This checkbox is cleared by default. When you mark this checkbox, Securiti determines the applicable regulation from the detected IP address or the Country and State the data subject provides. Securiti then renders the request types associated with that regulation from the Regulations Support dashboard. If no regulation applies to the detected location, Securiti falls back to the request types already configured on the form.

![Form section highlighting dynamic rendering of request types for data subject requests.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-04 at 8.08.38 PM.png)

> [!NOTE]
> Note
> 
> With Country and State-based detection, if a data subject already selected a request type before changing Country or State, Securiti keeps that selection only if it still appears among the request types rendered for the new location. Otherwise, the data subject must select a new request type before submitting the form.

For more information, see [Creating and publishing DSR request forms](/latest/docs/creating-and-publishing-dsr-request-forms).

#### Downloading all attachments in a subtask, task, or DSR with one click

Securiti now lets you download a zip file of all attachments in a subtask, task, or DSR with a single click. Securiti processes your request in the background and sends you an email with a download link once the file is ready. This link stays active for 24 hours. Securiti logs every download request in the DSR audit log, including the user, the action, and the timestamp.

![DSR access request interface showing tasks, subtasks, and download options for attachments.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 11.39.11 AM.png)

> [!NOTE]
> Note
> 
> This feature downloads only the attachments visible under subtasks. Securiti excludes all other attachment types, such as those from DSR messages, appeals, and request clarification. If you have access to only some subtasks within a task or DSR, Securiti includes only the files you can access. Downloaded files are not redacted or masked, even if you apply redaction or masking when viewing them in the UI.

For more information, see [Previewing and downloading DSR, DSR subtask reports and attachments](/latest/docs/previewing-and-downloading-dsr-and-dsr-subtask-reports).

#### DSR settings restructured into two consolidated pages

Securiti now lets you manage Data Subject Rights settings from two consolidated pages instead of several separate screens.

**DSR Settings** (System Settings > Data Subject Rights > DSR Settings) contains the following:

- DSR Deadline
- Retention Policy
- DSR Reports
- Rescan Policy
- Encryption Standard
- Module Owner Access Setup
- Task Settings

![Settings for Data Subject Rights, including deadlines and retention policies outlined clearly.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 12.18.50 PM.png)

**Privacy Central Settings** (System Settings > Data Subject Rights > Privacy Central Settings) contains the following:

- Privacy Central Account Setup
- Privacy Central Customization

![Privacy Central Settings interface showing account setup and customization options for data subjects.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 12.47.04 PM.png)

Securiti groups each set of settings into sections on a single scrollable page, so you no longer need to navigate between separate screens to manage them. Your role determines which sections you can view or edit.

#### API updates

Use the following table to understand the API updates made for Data Subject Rights in this release:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/privaci/v1/admin/dsr/forms/{form_id}/rules/create` | POST | **New parameters**: We have added the following new parameters: - `is_sequential_rule`: Specify whether the rule uses sequential task processing. - `steps`: Define up to 4 levels of task templates and execution conditions when `is_sequential_rule` is true. |
| `/privaci/v1/admin/dsr/forms/{form_id}/rules/update/{rule_id}` | PATCH | **New parameters**: We have added the following new parameters: - `is_sequential_rule`: Specify whether the rule uses sequential task processing. - `steps`: Define up to 4 levels of task templates and execution conditions when `is_sequential_rule` is true. |
| `/privaci/v1/admin/dsr/tickets/{id}/rerun` | POST | **New parameter:** - `level`: A new query parameter, applicable only to sequential DSR requests, that lets you restart a rescan from a specific level. |
| `/privaci/v1/admin/dsr/tickets/{id}/applicable_steps` | GET | We have added this API endpoint in the current release. It lets you fetch the levels available to restart a rescan from, for a DSR request that matches one or more sequential rules. |
| `/privaci/v1/admin/dsr/ticket/{id}/tasks/rule_step_info` | POST | We have added this API endpoint in the current release. It lets you fetch the rule and level each specified task belongs to. |
| `/privaci/v1/admin/dsr/tickets/{id}/getTaskIdsByRulesSteps` | POST | We have added this API endpoint in the current release. It lets you filter tasks by rule and level, returning the matching task IDs. |
| `/privaci/v1/admin/dsr/download/config` | POST | **New parameter**: **dsr_allow_attachments_download**: Specify whether to allow downloading of subtask attachments. |
| `/privaci/v1/admin/dsr/subtasks/{id}/download/attachments` | POST | We have added this API endpoint in the current release. It lets you download all attachments for a subtask. |
| `/privaci/v1/admin/dsr/tasks/{id}/download/attachments` | POST | We have added this API endpoint in the current release. It lets you download all attachments for every subtask under a task. |
| `/privaci/v1/admin/dsr/tickets/{id}/download/attachments` | POST | We have added this API endpoint in the current release. It lets you download all attachments for every task and subtask under a DSR request. |
| `/privaci/v1/admin/dsr/forms/{id}` | PATCH | **New parameter:** `enable_dynamic_request_type_rendering`: A policy setting that lets you enable dynamic rendering of request types based on the data subject's jurisdiction. Applicable only when `response_duration_type` is set to `ip_auto` or `location_auto` |
| `/privaci/v1/admin/dsr/forms/{form_uuid}/dynamic_request_types/location` | GET | We have added this API endpoint in the current release. It lets you fetch the request types applicable for a data subject's country and state, when submitting **internal** DSR requests on behalf of a data subject through the authenticated portal. |
| `/api/v1/dsr/{form_uuid}/dynamic_request_types/location` | GET | We have added this API endpoint in the current release. It lets you fetch the request types applicable for a data subject's country and state, for external DSR forms submitted through Privacy Central. |

For more information, see [Data Subject Rights API documentation](https://securiti-doc-router.securiti.ai/modules/data-subject-rights/apidocs/index.html).

---

## 1.148

### Patch 2 - July 2026

#### Resolved issue

- Fixed an issue where the subtask owner could not be updated if the previously assigned user had been deleted from the system. The system was still trying to look up the deleted user's details instead of letting the new assignment go through (PRIV - 252083).

### Release updates - July 2026

#### Resolved issues

- Fixed an issue where the custom data elements displayed incorrect, auto-translated text in DSR PDF reports generated in Portuguese (PRIV-246777).
- Fixed an issue where Do Not Sell or Share consent requests submitted through a Universal DSR iframe form failed silently in Firefox ESR, leaving consent preferences unchanged (PRIV-248015).

---

## 1.147

### Release updates - June 2026

#### Limit Microsoft 365 Outlook search using keywords and mailboxes in internal DSRs

Securiti now lets you limit Microsoft 365 Outlook (Self-Hosted) searches in internal DSRs using keywords and specific mailboxes. This capability is available only with Smart Search and is not supported for Discovery scan.

> [!NOTE]
> Note
> 
> This feature is available only for internal DSRs and is not supported for external DSR forms. In other words, when an internal user is submitting the DSRs on behalf of the data subjects, they can set the scope for search on these DSRs. A data subject cannot set the search scope while submitting the DSRs details to the internal user.

You can define a focused search scope to target relevant communications, such as performance discussions or termination context between managers and HR, by adding keywords such as “Performance” and specifying mailbox addresses for search. For example, you can search emails in a manager’s and HR’s mailboxes that mention an ex-employee and their performance evaluation.

![Form for creating a Data Subject Request with search options and keywords.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-19 at 8.13.53 PM(3).png)

Once you submit an internal DSR with a scope, Securiti sends a scoped request to Robotic Automation. The Outlook smartsearch connector searches only within the specified mailboxes. The connector retrieves data using data subject identifiers defined in the DSR form, such as email, name, phone number, or other configured identifiers. It then filters results using the specified keywords.

Only emails that match both the data subject identifiers and the defined keywords are included in the results.

> [!NOTE]
> Note
> 
> The scope you define applies only to the Microsoft 365 Outlook (Self-Hosted) data system. Securiti creates tasks and subtasks for all other data systems as usual, without applying any scoping. This applies regardless of how your DSR form is configured:
> 
> - If your DSR form uses a form rule with a task template that includes Microsoft 365 Outlook (Self-Hosted) alongside other data systems, scoping applies only to the Outlook connector. Tasks and subtasks for all other data systems in the template are created as normal.
> - If your DSR form uses the **Automation** section to include multiple data systems directly, scoping applies only to the Outlook connector in that list. All other data systems process the DSR request as normal.

**Prerequisites**

- Smart Search is enabled.
- Query scoping is enabled.
- In the Microsoft 365 Outlook (Self-Hosted) connector, select Enable DSR Automation via Scan-less Smart Search.
- Required Microsoft Graph API permissions are configured.
- Appliance version is 1.147.0-01rc or later.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

For more information, see [Opening DSR requests on behalf of data subjects](/latest/docs/opening-dsr-requests-on-behalf-of-data-subjects).

#### DSR regulation updates for Utah, Connecticut, and the Philippines

Securiti has updated the DSR regulation framework to support new request types and configuration changes across three jurisdictions.

- **Utah (UCPA)** — Securiti now supports the rectification request type for the Utah regulation, letting data subjects request correction of inaccuracies in their data.
- **Connecticut (CTDPA)** — Securiti now supports the Disclosure of Sub-processors request type for the Connecticut regulation, letting data subjects request disclosure of entities with whom their data is being shared.
- **Philippines (DPA)** — Securiti has updated the Philippines (DPA) regulation to disable the extension option and set the extension duration to zero. This update applies at both the regulation level in the Regulations Support dashboard and the request type level in the DSR form configuration.

> [!NOTE]
> Note
> 
> If you have previously customized the Utah (UCPA) or Connecticut (CTDPA) regulation, the newly added request types may not appear automatically. To apply the latest standard configuration, choose **Settings > Regulations Support**, locate the regulation, click **More Actions** (3 dots), and select **Revert to Default**. After reverting, review and republish any associated DSR forms.

For more information, see [Using the Regulations Support dashboard](/latest/docs/using-the-regulations-support-dashboard).

#### API updates

Use the following table to understand the API updates made for Data Subject Rights in this release:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/privaci/v1/admin/dsr/create_ticket` | POST | **New parameters:** We have added the following new parameter: - `scope_metadata` : This parameter in the request body lets you define the Smart Search scope in the Microsoft 365 Outlook (Self-Hosted) connector when creating DSR tickets. Use it to limit the search to specific mailboxes and keywords relevant to the DSR request. > [!NOTE] > Note > > If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. |
| `/privaci/v1/admin/dsr/forms/internalform/{form_id}/scope_metadata` | GET | We have added this API endpoint in the current release. Use this API to fetch the scope metadata configured for an internal DSR form. Pass the DSR form ID as a path parameter to retrieve its scope metadata. > [!NOTE] > Note > > If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. |

#### Resolved issue

- Fixed an issue where checkbox selections in Rectification subtasks did not stay in sync and backend errors were not displayed. The "Check All" checkbox now correctly reflects selected checkboxes after refreshes, navigation, and individual selection changes, and users now see an error message when an operation fails (PRIV-244648).
- Fixed an issue where Rectification subtasks displayed errors when the module language was changed from English. Users can now review rectification attributes and approve subtasks successfully across supported languages (PRIV-245914).
