---
title: "Using firewall rules"
slug: "using-firewall-rules-1"
status: "update"
updated: 2026-08-31T08:17:29Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/using-firewall-rules-1"
stale: true
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Using firewall rules

**Scenario**

As a Data Security Officer, you need to inspect AI interactions for risks like toxic content or data misuse. Manual reviews can’t scale with real-time AI usage. With Gencore AI’s **firewall rules**, you apply NLP-based analyzers to assess message sentiment, entities, or topics. These insights trigger rule-based actions automatically—helping you catch harmful behavior early and secure both data and AI outputs.

Firewall rules are sets of evaluations within a firewall that analyze the incoming and outgoing messages between the AI Assistant Endpoint and the LLM and between the LLM and the source data (database).

Analyzers generate metadata that rules can evaluate. Text analyzers are used in Natural Language Processing (NLP) to analyze text data. They can perform tasks such as sentiment analysis, topic detection, entity recognition, and syntax analysis. Text analyzers help in understanding, interpreting, and manipulating human language in a way that is useful for further processing and decision-making.

> [!NOTE]
> **Note**
> 
> To learn more about rules, see [Understanding Analyzers, Rules, and Policies](/v1/docs/understanding-analyzers-rules-and-policies).

To open the **Firewalls** **Rules** dashboard, in Securiti, open **Gencore AI**, and choose **Firewalls** > **Rules**.

![Overview of firewall rules, including policies, pipelines, and violation statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FW rules.png)

Using the **Firewalls Rules** dashboard, you can:

- Access, [create](/v1/docs/creating-firewall-rules) and manage firewall rules
- Access [profiles](/latest/docs/using-firewall-profiles)
- Access [policies](/latest/docs/using-llm-firewall-policies)
- Access [Exemplars](/latest/docs/using-exemplars)

![Overview of firewall rules, including policies, pipelines, and violation statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FW rules - Options.png)

You can view a list of rules with relevant details.

- The top of the dashboard displays a widget that shows the total number of rules.
- You can [create](/v1/docs/creating-firewall-rules) and search for rules.
- Under the search box, you can filter the rules on the following columns:
  - Status
  - Rules
  - Policies
  - Pipelines
  - Owner

![FW rules - filters](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FW rules- filters.png)

- You can see the existing widgets displaying numbers for the following:
  - Total rules
  - Policies
  - Pipelines
  - Violations

![FW rules - widgets](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FW rules - widgets.png)

- You can click **Status** to set the status of the rule as active or inactive.

![Firewall rules status](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/firewall rules - status.png)
- You can sort the rules based on the following:
  - Status
  - Rules
  - Policies
  - Pipelines
  - Violations
- To the right of each rule, you can click the **Metadata Explorer** to view more details about the selected rule.

![Firewall rule - metadata explorer](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/firewall rules - metadata explorer.png)
- It displays the following information:

| Information | Description |
| --- | --- |
| Pipelines | Displays the list of pipelines the firewall profile is used in. |
| Profiles | Displays the list of firewall profiles. |
| Policies | Displays the list of firewall policies. |
| Retrieval Violations | Displays the number of violations related to retrieval profiles. Click the number to go to the Findings>LLM Firewalls section. |
| Response Violations | Displays the number of violations related to response profiles. Click the number to go to the Findings>LLM Firewalls section. |
| Prompt Violations | Displays the number of violations related to prompt profiles. Click the number to go to the Findings>LLM Firewalls section. |
| Standalone Violations | Displays the number of violations related to standalone profiles. Click the number to go to the Findings>LLM Firewalls section. |
| Date Created | The date the firewall profile was created. |
| Date Modified | The date the firewall profile was last modified. |
| Owner | The owner of the firewall profile. This can be one of the following: - System - User-defined |

To view more details about the rule, click **Details**.

![Firewall rules - metadata explorer expanded](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Rules - metadata explorer(1).png)

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

An endpoint is a specific URL or URI (Uniform Resource Identifier) that an API exposes for communication.

Natural Language Processing (NLP) is a specialized field within Artificial Intelligence (AI) dedicated to empowering computers to understand, generate, and manipulate human language proficiently.

## Related

- [Using firewall profiles](/using-firewall-profiles.md)
- [Using Exemplars](/using-exemplars.md)
- [Understanding analyzers, rules, and policies](/understanding-analyzers-rules-and-policies.md)
