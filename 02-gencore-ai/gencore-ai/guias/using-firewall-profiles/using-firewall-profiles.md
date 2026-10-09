---
title: "Using firewall profiles"
slug: "using-firewall-profiles"
status: "update"
updated: 2026-08-31T21:00:01Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/using-firewall-profiles"
stale: true
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Using firewall profiles

**Scenario**

As a Data Security Officer, you're responsible for preventing sensitive data leaks in GenAI interactions. Data can be leaked or compromised as a result of malicious attempts such as phishing or jailbreak. Manually reviewing requests in the prompts and the AI responses is slow and unreliable. With **firewall profiles** in Securiti’s Gencore AI, you define policies once and apply them across pipelines. You monitor, test, and enforce checks on inputs and outputs automatically. This ensures consistent protection—without disrupting the speed of AI use.

Enterprises that use LLMs to access their unstructured data must ensure that LLMs access and consume their data in a manner that upholds security, preserves privacy, and adheres to consumption agreements such as licensing (data governance).

The integration of LLMs in business applications introduces a fresh array of challenges in data security, compelling companies to implement strategies to protect sensitive information. This may include:

- **Prohibiting or Restricting LLM Usage**: Enforce bans or limitations on LLM usage to mitigate the risk of data leaks.
- **Implementing Foundational Controls**: Employ basic security controls provided by AI vendors to fortify defenses against potential data breaches.
- **Leveraging Data Security Solutions**: Integrate services like content scanning and LLM-specific firewalls to prevent the input or leakage of sensitive data through LLMs.

> [!NOTE]
> **Note**
> 
> To see how Securiti provides a comprehensive approach to AI System security with firewalls, see [What is an LLM Firewall: Navigating Unprecedented AI Threats](https://securiti.ai/what-is-llm-firewall/).

Securiti’s **Gencore AI** provides firewalls that are easy to configure and monitor, as well as capabilities to test them. This can help you achieve the following:

- Firewalls assess the data prior to giving it to the LLM.
- Prompts and access patterns are assessed for suspicious and prohibited inputs.
- Responses are assessed for prohibited outputs.

> [!NOTE]
> Note
> 
> The firewall location is customer-configurable. It can run in Securiti's SaaS infrastructure or inside the customer's own cloud/on-prem environment.

A Firewall profile is a collection of policies that control how firewalls are configured and dictate how firewalls are configured in pipelines.

To open the Firewall profile dashboard, in Securiti, open **Gencore AI**, and choose **Firewalls** > **Profiles**. Using the Firewalls Profiles dashboard, you can:

- Access, [create](/v1/docs/creating-firewall-profiles) and manage firewall profiles
- View the top indicators on firewalls
- Access list of all firewall policies in the system
- View where and how the firewalls are used

![Overview of firewall profiles, including policies, rules, and violations statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FW profiles main(1).png)

You can access the following pages from the **More Options** menu:

- Pipelines
- Policies
- Rules
- Exemplars

![Firewall profiles options](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FW profiles options menu.png)

The top of the dashboard shows the following widgets:

- Total firewall profiles
- Pipelines using firewalls profiles
- Firewall profiles with violations

On the left side of the dashboard, you can choose to view the profiles as follows:

| Firewall Types | Description |
| --- | --- |
| All Firewall Types | Displays all firewall profiles. |
| Prompt | Displays the [Prompt](/v1/docs/prompt-firewall) profiles. |
| Retrieval | Displays the [Retrieval](/v1/docs/retrieval-firewall) profiles. |
| Response | Displays the [Response](/v1/docs/response-firewall) profiles. |
| Standalone | Displays the [Standalone](/v1/docs/configuring-firewall-apis) profiles. |

![All_firewall_types.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f4dfe659-97bd-e622-ee7f-0e69025f40d2(1).png?sv=2022-11-02&amp;spr=https&amp;st=2025-07-23T07%3A11%3A53Z&amp;se=2025-07-23T07%3A26%3A53Z&amp;sr=c&amp;sp=r&amp;sig=qzsTl9za6SScfUrfGs2LZUrhFjbYIjStV2W22SuQUes%3D)

When you select the type of a profile:

- The widgets display the the count for the following:
  - Policies
  - Rules
  - Violations
  - Pipelines

![Firewall profiles widgets](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FW profiles widgets.png)

- To view findings:
  - for all profiles, click **View Findings**, Securiti displays the **Findings** page where you can view the findings for all profiles.

![Firewall profiles - view findings](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FW profiles View Findings(1).png)
  - for the selected profile, click **View Findings**. Securiti displays the **Findings** page where you can [view the findings for the selected profile](/v1/docs/viewing-findings-for-llm-firewalls).

![Selected firewall profiles - view findings](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FW profiles - selected view findings.png)
- To view the metadata information for the selected profile, click the **Metadata Explorer**.

![Firewall profiles metadata explorer expanded](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PRIV-248911 FW profile metadata explorer.png)

- To view the metadata information for a policy, click the **Metadata Explorer** to the right of the policy.

![FW_profile_policy_metadata_exp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fbbf903-65b5-949f-788d-67ed5a271575(1).png?sv=2022-11-02&amp;spr=https&amp;st=2025-07-23T07%3A11%3A53Z&amp;se=2025-07-23T07%3A26%3A53Z&amp;sr=c&amp;sp=r&amp;sig=qzsTl9za6SScfUrfGs2LZUrhFjbYIjStV2W22SuQUes%3D)

The metadata explorer displays the following information:

| Information | Description |
| --- | --- |
| Policies | Shows the list of policies in the firewall profile. |
| Pipelines | Shows the list of pipelines the firewall profile is used in. |
| Violations | Shows the number of violations related to the firewall profile. Click the number to go to the Findings>LLM Firewalls section. |
| Date Created | The date the firewall profile was created. |
| Date Modified | The date the firewall profile was last modified. |
| Integration ID | The unique identified representing the integration of the firewall profiles |
| Owner | The owner of the firewall profile. This can be one of the following: - System - User-defined |

To view further information, click **Details**.

![Firewall profiles - metadata explorer details](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PRIV-248911 FW profile metadata explorer(1).png)

- To search for policies, enter the policy name in the Search box.
- You can filter the policies as follows:

| Filter | Description |
| --- | --- |
| Status | Filter the firewall profile as **Active** or **Inactive** |
| Policy ID | Filter the firewall profile based on the unique identified of the firewall policy. |
| Policy Name | Filter the firewall profile based on the name of the firewall policy |
| Rule | Filter the firewall profile based on the rule |
| Owner | Filter the firewall profile based on the owner. This can be one of the following: - System - User-defined |
  - ![Firewall profiles filters](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FW profiles Filters(1).png)

- You can sort the policies on the following columns:
  - Status
  - Policies
  - Rules
  - Findings

A firewall profile is a collection of policies that control how firewalls are configured and dictate how firewalls are configured in pipelines.

## Related

- [Creating firewall profiles](/creating-firewall-profiles.md)
- [Creating firewall policies](/creating-firewall-policies.md)
- [Viewing findings for LLM firewalls](/viewing-findings-for-llm-firewalls.md)
- [Configuring firewall APIs](/configuring-firewall-apis.md)
