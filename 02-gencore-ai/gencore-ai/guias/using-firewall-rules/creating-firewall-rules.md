---
title: "Creating firewall rules"
slug: "creating-firewall-rules"
updated: 2026-01-26T09:06:19Z
published: 2026-02-09T22:00:18Z
canonical: "helpcenter.securiti.ai/creating-firewall-rules"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Creating firewall rules

You can create custom firewall rules to use in your firewall profiles.

### Prerequisites

You must have predefined **Rego** file or code to create the rule definition.

### Creating a firewall rule

To create a rule:

1. On the **Firewall Rules** dashboard, click **Create Rule**. The rule creation form displays.

![Create firewall rule](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Firewall rules - create.png)
2. Enter the **name** for the rule.

![Create_rule_-_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b4b4ecfe-2e0a-e730-5177-555e8621fd28(1).png)
3. Optionally add a **description**.
4. Enter the **tags** to be associated with this rule.

![Create_rule_-_tags.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-286354d8-354e-800f-759a-3c5b66bac0f6(1).png)
5. Define the rule. You can choose from the following options:
  - Upload your Rego file.

![Create_rule_-_rule_definition_Upload.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b703376b-959e-ff7d-1869-ba8f2cb9ceba(1).png)
  - Define the code. You can copy and download the code.

![Create_rule_-_rule_definition.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1b3e1870-a85e-3d2c-6cfb-1487d8132d5c(1).png)

Click the **clipboard** icon to copy the code.

![Create_rule_-_copy_definition.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3884afa9-ba7b-e44f-8416-659a346d4f6b(1).png)

Click the **download** icon to download the code ![Create_rule_-_rule_definition_download.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c1a4bfeb-edd6-81a4-a11e-7d8f1489f375(1).png)
6. To save the changes, click **Create Firewall Rule**.

![Create_FW_rule_-_Save.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d335e719-2b56-8df1-ff3c-ba1459e04023(1).png)

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

## Related

- [Using firewall rules](/using-firewall-rules-1.md)
- [Understanding analyzers, rules, and policies](/understanding-analyzers-rules-and-policies.md)
- [Using Exemplars](/using-exemplars.md)
