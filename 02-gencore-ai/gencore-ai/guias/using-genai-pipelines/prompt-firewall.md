---
title: "Prompt Firewall"
slug: "prompt-firewall"
updated: 2025-12-09T09:50:37Z
published: 2025-12-09T09:50:37Z
canonical: "helpcenter.securiti.ai/prompt-firewall"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Prompt Firewall

**Scenario**

As a Data Compliance Officer, you’re responsible for ensuring AI interactions don’t expose sensitive information or produce non-compliant responses. Manual reviews aren’t scalable and leave room for oversights. With the **Prompt Firewall** node, you enforce policies on prompts automatically. It blocks risky inputs and filters harmful outputs, helping you maintain compliance without slowing down AI adoption.

You can configure the Prompt firewall node to enforce policies on prompts received from the assistant and responses sent back. This node helps you implement a firewall for detecting and mitigating potential malicious use. Traditional approaches for this purpose include:

- **Prompt Management**: Engineering mechanism into prompts to capture specific concerning scenarios
- **Proactive Adversarial Tests**: Proactive testing of Pipeline for scenarios of sensitive data leakage

### Defining the Prompt Firewall

To define your Prompt firewall:

1. Click **Add** (+) to enable the **Prompt Firewall** node.
2. Search for the prompt profile.
3. Select the relevant prompt profile.

![Configuration screen displaying various firewall profiles and their details for management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Prompt profile selected.png)

Securiti displays the profile attributes. To view the details, click ​**Details**​​.

![prompt profile details](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Prompt profile selected details.png)
4. When you have selected the prompt profiles, click **Save and Continue** to proceed to the next stage.

This firewall uses policies to assess prompts and access patterns for suspicious or prohibited inputs.

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Using firewall profiles](/using-firewall-profiles.md)
- [LLM Selection](/llm-selection.md)
