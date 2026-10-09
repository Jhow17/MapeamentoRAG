---
title: "Configuring a template rule in assessments (Rule Engine)"
slug: "configuring-template-rules"
updated: 2026-04-27T21:00:23Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/configuring-template-rules"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Configuring a template rule in assessments (Rule Engine)

This article covers how to configure “Associate Rules” for these supported actions:

- Send follow up assessment
- Invite users
- Tag assessment

To create an assessment template instead, see the following [topic](/v1/docs/creating-custom-assessment-templates-in-securiti).

### Prerequisites

- You must have admin access to the assessment template.
- Ensure the questions relevant to your rule logic already exist.
- Ensure system users relevant to your rule logic exists in the Securiti tenant.
  - You can invite guest users on the fly.

To access Associate Rules:

1. Open the assessment template.
2. On the template header, click **Associate Rules (flowchart icon)**.

![User interface for building an assessment template with sections and questions listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-11-26 at 12.22.35 PM.png)
3. Click **+Associate New Rule**
4. Enter a rule name and provide an optional description.

![No associated rules found for the assessment template; option to associate new rules available.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-11-26 at 1.01.48 PM.png)

![Setup window for creating a new rule with fields for name and description.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-11-26 at 1.02.20 PM.png)
5. Click **Save and continue**. Each rule requires the following configuration:
  1. **When Event -** the trigger event
  2. **If Conditions -** the condition(s) rule must meet
  3. **Then Action -** the action to execute
6. The rule shows the events panel on the right side of the page.
  1. Click the “bin” icon to delete the event
  2. Click “x” icon to close the event panel.
7. In the header, click the **Actions** menu to view these options:
  1. **Edit name / description -** edits the rule
  2. **Set as Active -** activates the rule
  3. **Clone -** clones the rule
  4. **Delete -** deletes the rule

![Workflow diagram showing user invitation triggered by reviewer approval and conditions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-11-26 at 1.06.22 PM.png)

## Send follow up assessment

To send a follow-up assessment based on the response to a specific question or a stage change:

1. Initiate a new rule.
2. Define the trigger (When). Select from an event such as:
  1. Assessment completed
  2. Assessment submitted
  3. Assessment stage change (In Progress to In Review, or In Progress to In Progress).

![Flowchart illustrating assessment submission triggers and conditions for follow-up actions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-11-26 at 1.27.00 PM.png)
3. (Optional) Set the condition (If):
  1. Choose a specific condition
  2. Define the logic (for e.g., response to Q1.2 is “Yes”).
  3. Toggle **AND** \ **OR** if you want the rule to meet one or both conditions. If only a single condition exists, the toggle doesn’t apply.

> [!NOTE]
> Note
> 
> Currently, you can’t configure a conditional logic with options “Unanswered” and “Skipped.”

> [!WARNING]
> Important
> 
> “Set Risk” and “Set Rating” assign qualitative values based on assessment responses. The underlying score is calculated by assigning point values to responses and aggregating them across applicable questions.
> 
> The overall readiness rating is then derived from this calculated score. Rule conditions evaluate against these derived values, not individual response labels.
> 
> For details on how scores and ratings are calculated, see [Readiness Ratings](/latest/docs/answering-assessment-questions-in-securiti#understanding-assessment-details-view).

![Flowchart illustrating conditions and actions for assessment submission automation.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-11-26 at 1.30.13 PM.png)
4. Add the action (Then):
  1. Choose **Launch Follow-up Assessment**.

![Workflow diagram showing conditions and actions for follow-up assessments in automation.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-11-26 at 1.24.25 PM.png)
  2. Select the assessment template to use.
  3. Define:
    1. Reviewers (current reviewers or specify users).
    2. Respondents (current respondents or specify users).
    3. Deadline (time window, for e.g., 7 days from the date of trigger).

![Workflow diagram showing assessment submission triggers and conditions for follow-up actions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-11-26 at 1.32.37 PM.png)
5. Save the rule

## Invite users

To automatically invite users to the current assessment based on conditions:

1. Initiate a new rule.
2. Define the trigger (When). For example, “Respondent Submission.”
3. Choose the question and define the logic. For example, response to Q1.2 is “Yes.”
4. Add the action (Then):
  1. Choose **Invite User**
  2. On the assignment popup, search and select users to assign.
  3. Configure these options:
    1. Assignment type (Respondent or Reviewer)
    2. Permission (View or Edit)
    3. Assignment level (entire assessment or specific questions)

For more information on user assignment, see [here](/v1/docs/section-question-assignment-in-assessment-automation).
  4. Save the rule

## Tag assessment

To automatically apply tags to assessments that meet the ‘When-If’ criteria:

1. Initiate a new rule.
2. Define the trigger (When). For example, “Assessment Submitted (First Time Only)”
3. (Optional) Add or skip the conditional trigger to suit.
4. Add the action (Then):
  1. Choose **Tag Assessment**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-24 at 12.58.12 PM.png)
  2. On Assign Tags, click **+Assign**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-24 at 1.00.39 PM.png)
  3. Configure these options:
    1. Search for existing or create a new tag type (key)
    2. Search for existing or create a new tag (value)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-24 at 1.16.56 PM.png)
  4. Click **Save**, and then again to save the rule. For more information, see [Managing assessment tags](/latest/docs/managing-assessment-tags).

> [!WARNING]
> Important
> 
> For more advanced logic, you can create multiple rules.
> 
> - Securiti doesn’t limit the number of rules you can create.
> - At any given point, you can have all rules activated or none.
> - You must save each configuration for the rule to function. Unsaved changes are lost.

## Caveats

| Supported action | Behavior notes |
| --- | --- |
| Follow up assessment | - A new assessment is launched only if all rule conditions are met. > [!NOTE] > Note > > Condition trigger is optional - Securiti doesn’t support questions such as Object and Field, Informational, etc. for condition trigger. > [!NOTE] > Note > > When configuring a condition, Securiti only shows the sections containing above question response types. - You can copy the selected reviewers or respondents from the current assessment or set them manually. |
| Invite users | - If a user is already assigned to the assessment, the system evaluates question-level and permission changes: - If the rule targets new questions, the user is added to those. - If the user already has edit access, a rule assigning view is ignored. - If the user has view access, a rule assigning edit will upgrade their access. - Mandatory reviewer status is added or removed based on rule configuration. - You can assign users to any question response type. |

### Audit and maintenance

- View rule status and history in “Event Logs” on the Associate Rules dashboard. Logs are only generated for the final outcome, whether a rule executes successfully or fails. Intermediate log information is not visible.

![Event logs displaying assessment details, including IDs, names, and statuses of actions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-11-26 at 1.19.16 PM.png)

![Event logs showing assessment details and execution steps for user invitation process.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-11-26 at 1.38.23 PM.png)
- If the condition criteria are not met, the event is logged as a success because that outcome is expected. No action is executed in this case. If the condition criteria are met but an error occurs while executing the action, the event is logged as a failure. For example, if the system attempts to launch an assessment but cannot fetch the target template because it was deleted, the event is marked as a failure.
- You can also activate a created rule by enabling the toggle next to your rule name. As noted earlier, you can configure rule settings using the Actions menu, or via “Options (three vertical dots)” in the Associated Rules column on the left.

![Workflow diagram showing user invitation process with conditions and actions outlined clearly.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-11-26 at 1.06.00 PM.png)

> [!NOTE]
> Note
> 
> Associated Rules are not shown in the template export. Also, they don’t work when you import or clone the template.

For more information, see the following topics:

- [Creating custom assessment templates](/v1/docs/creating-custom-assessment-templates-in-securiti)
- [Creating questions in template builder](/v1/docs/creating-questions-in-assessment-template-builder)

## Related

- [Assessments list Filter panel and Saved Views](/assessments-list-filter-panel-and-saved-views.md)
- [Navigating assessments dashboard](/navigating-the-assessment-metrics-dashboard.md)
- [Using the Assessments list view](/using-the-internal-assessments-list-view.md)
- [Assessments list (Search and exports)](/assessments-list-search-and-exports.md)
