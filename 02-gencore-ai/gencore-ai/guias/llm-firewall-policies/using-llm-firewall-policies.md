---
title: "Using firewall policies"
slug: "using-llm-firewall-policies"
updated: 2026-08-31T08:10:15Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/using-llm-firewall-policies"
stale: true
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Using firewall policies

**Scenario**

As a Data Security Officer, you're tasked with preventing malicious or unauthorized AI interactions. Relying on static filters makes it hard to adapt to new threats like jailbreak prompts. With Gencore AI’s firewall policies, you define custom rules using Rego code and set targeted actions. These policies let you block, log, or alert on risky behavior automatically—ensuring GenAI workflows stay protected and compliant.

A Firewall policy is a collection of rules that enforces policies to ensure compliance across various logical firewalls in pipelines that use artificial intelligence.

A Policy can be referred to as a configurable rule and actions, where:

- Rules detect unwanted interactions, such as jailbreak attempts.
  - Each policy consists of rules.
  - A rule consists of modifiable Rego code.
- Actions are the response of a rule firing. Different rules can have different actions.

A policy dictates how a firewall handles the AI endpoint’s messages and data retrieved by the LLM. It serves as a framework for managing and enforcing security measures to protect the LLM and its data from unauthorized access, malicious activities, and other security threats. The firewall policy defines the criteria for allowing or blocking messages and data.

> [!NOTE]
> **Note**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

To open the **LLM Firewall** **Policies** dashboard, you can follow any of the these paths:

- In Securiti, open Gencore AI, choose **Firewalls** and select **Policies**.
- In Securiti, open Policies and select **LLM Firewall**.

![Overview of LLM Firewall policies, including statuses and violation counts for each policy.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Policies main(1).png)

> [!NOTE]
> **Note**
> 
> When you select a different policy, the UI directs you to the relevant policy tab on the **Policy Center**.

### Prerequisites

Before configuring an LLM firewall policy, ensure the following prerequisite is met:

- You must have access to at least one Firewall rule or exemplar

### Scope

Using the **Policies** dashboard, you can:

- Access, [create](/latest/docs/creating-firewall-policies) and manage firewall policies.
- Create filters to find policies.
- Search for the policies.
- Access the following from the **More Options** menu:
  - Saved Views
  - Profiles
  - Rules
  - Exemplars

![LLM Firewall policies - Options](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLM policies - options.png)

- View existing widgets displaying numbers for the following:
  - Firewall profiles
  - Policies
  - Policies without violations
  - Violations
  - Pipelines

![Firewall policies widgets](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Policies widgets.png)
- Enable or disable the policy by clicking on the **Status** toggle.

![Status toggle for Test Policy 1.1252 with Policy ID 1882 displayed in the interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Policies Status toggle HL.png)
- To view further details about a policy, click the **metadata explorer** to the right side of the policy.

![Policies - instance explorer](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Policies-IE.png)
- It displays the following information:

| Information | Description |
| --- | --- |
| Status | Displays the status as **Active** or **Inactive**. |
| Policy ID | Displays the unique identifier of the firewall policy. |
| Profiles | Displays the list of firewall profiles. |
| Pipelines | Displays the list of pipelines the firewall profile is used in. |
| Rules | Displays the list of firewall rules. |
| Retrieval Violations | Displays the number of violations related to retrieval profiles. Click the number to go to the Findings>LLM Firewalls section. |
| Response Violations | Displays the number of violations related to response profiles. Click the number to go to the Findings>LLM Firewalls section. |
| Prompt Violations | Displays the number of violations related to prompt profiles. Click the number to go to the Findings>LLM Firewalls section. |
| Standalone Violations | Displays the number of violations related to standalone profiles. Click the number to go to the Findings>LLM Firewalls section. |
| Date Created | The date the firewall profile was created. |
| Date Modified | The date the firewall profile was last modified. |
| Owner | The owner of the firewall profile. This can be one of the following: - System - User-defined |

To view the details about the selected policy, click **Details**.

![Firewall policies metadata explorer expanded](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/LLM firewall policy metadata explorer.png)
- Sort the policies on:
  - Status
  - Policies
  - Firewall profiles
  - Pipelines
  - Rules
  - Violations
- To manage a policy, click the **Options** (three-dot menu) to the right of the policy and select one of the following options:
  - View
  - Edit
  - Clone
  - Delete

![custom_policy_options.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2ad7b4b2-c360-47ad-f0bf-353f6d0db6c9(1).png)

To go to the **LLM Firewall Findings**, click **View Findings.**

![View findings in policies](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Policies - View findings.png)

Securiti displays the [**Findings**](/v1/docs/viewing-findings-for-llm-firewalls) page.

### Creating Filters in Policies

To create your filter in LLM Firewall policies:

1. On the **Filters** menu, click **Add**.

![Add filter in Policies](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Policies-Add filter(1).png)
2. Choose your property and relevant actions.
  1. Profile:
    1. Select **Firewall Profile**.
    2. Choose **operation**:
      - is one of
      - is equal to
      - is not equal to
    3. Select one or more firewall profiles.
  2. Type:
    1. Select **Firewall Type**.
    2. Choose **operation**:
      - is one of
      - is equal to
      - is not equal to
    3. Select one or more firewall profile types:
      - Prompt
      - Response
      - Retrieval
      - Standalone
  3. Profile:
    1. Select **Firewall Profile**.
    2. Choose **operation**:
      - is one of
      - is equal to
      - is not equal to
    3. Select one or more firewall profiles.
  4. Owner:
    1. Select **Owner**.
    2. Choose operation:
      - is one of
      - is equal to
      - is not equal to
    3. Select one or more owners.
  5. Policy ID:
    1. Select **Policy ID**.
    2. Choose operation:
      - is one of
      - is equal to
      - is not equal to
    3. Enter **policy ID**.
    4. Press **Enter**.
  6. Rules:
    1. Select **Rules**.
    2. Choose operation:
      - is one of
      - is equal to
      - is not equal to
    3. Select one or more rules.
  7. Status:
    1. Select **Status**.
    2. Choose operation is equal to.
    3. Select one of the following statuses:
      - Active
      - Inactive

A filter for policies is shown where:

- A list of firewall profiles are selected.
- The firewall type is one of Prompt or Standalone.
- The owner is System Defined.
- The profiles are active.

![Policies filter - example](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Policies filter - example.png)

### Saved views for policy filters

You can save policy filters to reuse them. To save your policy filter, on the **Policies** dashboard:

1. Click ​**Options (three-dot menu)​​>​Save view**​​. Securiti displays the **Save view** popup.

![Policies - save view](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Policies - more options - save views.png)
2. Select an existing group or enter a **group name** to create a new group and press **Enter**.

![Save view popup in Policies](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Policies-Save view popup(1).png)
3. Enter a **name** for the view and optionally add a **description**.

![Policies - save view - group and view name](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Save View - Group and view name.png)
4. To save the view, click **Save View**.

![Policies - save](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Save View - save.png)
5. To access your saved views, on the **Policies** dashboard, click ​**Options (three-dot menu)​​>​Saved Views​​**.

![Policies - saved views](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Policies - Saved views.png)
6. To see your custom views, click **Custom Views**.

![Custom Views - Saved view](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saved views - created view.png)

An AI firewall policy is a set of rules that govern how the firewall should handle network traffic based on specific criteria, enhancing network security through artificial intelligence. Policies regarding the data that can be ingested by the LLM, end users can ask the questions in a prompt and the relevant responses that are provided to the end user.

Securiti policies translate data intelligence into actions. Each policy has rules that, when matched by a file, document, or resource, trigger a response.

A firewall that prevents sensitive data from being input into or leaked by LLMs. This involves checking the information going in to make sure it's not sensitive or unauthorized, controlling what the LLMs share, and making sure they follow rules to produce safe and contextually appropriate responses.

System Defined indicates whether a rule is predefined by the system (Yes) or custom-created by users (No). It distinguishes between rules provided by the platform and those created by users.
