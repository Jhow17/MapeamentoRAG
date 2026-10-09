---
title: "Creating firewall policies"
slug: "creating-firewall-policies"
updated: 2026-05-25T05:21:43Z
published: 2026-05-25T05:21:43Z
canonical: "helpcenter.securiti.ai/creating-firewall-policies"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Creating firewall policies

You can create custom firewall policies using the **Policies** dashboard.

### Creating a firewall policy

To create a new firewall policy:

1. On the **Policies** dashboard, click **Create Policy**. Securiti displays the policy creation form.

![Create firewall policy](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Policies create policy.png)
2. Enter the **name** for the policy.

![Create_policy_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9fe37965-5dbe-b705-858c-8d20117c033e(1).png)
3. Optionally add a **description**.
4. Select **Owner**.
5. Select **Co-owners**.
6. Optionally enter the **tags** for the policy.

![Create_policy_tags.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9f6e3db7-d41d-a8f9-05d8-bc896e4b599f(1).png)
7. Search for and select the **rules** to be linked to this policy. When you select a rule, Securiti activates **Configure**.

![Create_policy_rules_selected.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-72e83bb1-7ca3-10af-f4cc-fb52b1423747(1).png)

> [!NOTE]
> **Note**
> 
> You must select at least one rule to be linked to a policy.
8. To show only the selected rules, click **Show selected rules only**.
9. To configure the rules to allow or deny actions for the firewall, enable the rule by enabling the toggle and click **Configure**.

![Create_policy_Click_Config_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-319cce97-9601-f1a9-aa66-5388d06a3838(1).png)

The rule configuration form displays.
  1. Define the relevant **Configuration options**.

![Create_policy_config_options.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5fde3561-40c1-f0d0-ca86-8f8029c11de4(1).png)
  2. To save the details, click **Save**.

![Create_policy_-_config_rule_-_save.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-19547c0a-28a6-88af-27a4-a77854d8ac21(1).png)
10. Based on the defined configurations, select the **Action** to be triggered for the rule.

| Action | Description |
| --- | --- |
| Block | Prevents content from either a user (prompt firewall), retrieved data (retrieval firewall), or the LLM (response firewall). When blocked, nothing sees that content. |
| Warn | Issues a warning on the requested information based on the prompt. |
| Log | Logs the event without informing the user. |
| Redact | Performs redaction on the information provided based on the prompt. |
  - ![Rules_-_Actions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-74f973ac-033d-7a9e-a163-2802003d0a24(1).png)
11. You can clone the rules to have different configuration for the same rule by defining a different range of different confidence selection with the same or different action for another exemplar topic for the same rule. To clone a rule:
  1. Click **Duplicate** to create a copy of the rule.

> [!NOTE]
> **Important**
> 
> Ensure the rule is active. Securiti does not let you clone an inactive rule.

![Create_policy_-_clone_rule.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3815efb8-974f-3856-40e9-1bb51f04ab7a(1).png)
  2. Define the **Configuration** options.
  3. Define the **Action**.
12. To view the metadata for the rule, click **Metadata Explorer** to the right of the rule.

![Create_policy_meta_data.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e05461b3-04b3-2eae-f53a-eed471aaaa18(1).png)
13. To create a new rule, click **Create New Rule**. The relevant form for creating a rule displays.

To know more about creating a rule, visit [Creating a new Firewall rule](/v1/docs/creating-firewall-rules).
14. To save the details, click **Save Firewall Policy**.

![Create_policy_Save.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-21134167-f867-4bbd-103c-3d7d0ebf752e(1).png)

Once you create a firewall policy, you can select it for [creating firewall profiles](/latest/docs/creating-firewall-profiles).

Securiti policies translate data intelligence into actions. Each policy has rules that, when matched by a file, document, or resource, trigger a response.

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

## Related

- [Managing firewall policies](/managing-firewall-policies.md)
- [Viewing findings for LLM firewalls](/viewing-findings-for-llm-firewalls.md)
- [Using firewall profiles](/using-firewall-profiles.md)
