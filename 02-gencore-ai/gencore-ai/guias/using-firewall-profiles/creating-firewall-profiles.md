---
title: "Creating firewall profiles"
slug: "creating-firewall-profiles"
updated: 2026-08-24T06:11:03Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/creating-firewall-profiles"
stale: true
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Creating firewall profiles

You can create firewall profiles to be used in your [pipeline creation](/v1/docs/creating-a-new-pipeline) or use them as [standalone firewall profiles](/v1/docs/configuring-firewall-apis).

### Prerequisites

You must have predefined [policies](/latest/docs/using-llm-firewall-policies) to create a firewall profile.

### Creating firewall profile

To create a firewall profile:

1. On the **Firewall Profiles** dashboard, click **Create New Firewall Profile**. Securiti displays the firewall profile creation form.

![Create firewall profile](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FW profiles Create FW profile.png)
2. Enter the **name** for the firewall profile.

![Create_FW_profile_-_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-12beec5a-efd0-72a6-ac78-a7f097f58e3b(1).png)
3. Optionally add a **description**.
4. Enter **tags** to be associated with this firewall profile.

![Create_FW_profile_tags.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d9746bed-5663-ddd8-6038-0656d37ec14b(1).png)
5. To set the profile being created as active, enable the **toggle set the profile status to active**.
6. Select the type of firewall type that this collection applies to.
  - **Prompt**: The prompt profile is used in the [Prompt Firewall node](/v1/docs/prompt-firewall).
  - **Retrieval**: The retrieval profile is used in the [Retrieval Firewall node](/v1/docs/retrieval-firewall).
  - **Response**: The response profile is used in the [Response Firewall node](/v1/docs/response-firewall).
  - **Standalone**: The standalone profile can be used independently in [configuring firewall APIs](/v1/docs/configuring-firewall-apis).

![Firewall_profiles_4_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-42d811c5-ba3e-5ace-bcc9-8480464475bc(1).png)
7. Search for and select the policies to be associated with this Firewall profile.

![Create_profile_policies.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7855569d-aaf8-40ba-e5df-215d0ab32f61(1).png)
8. To create a new policy, click **Create New Policy**. The policy creation form displays.

To learn more about creating policies, visit [Creating a new Firewall Policy](/latest/docs/creating-firewall-policies).

![Create_profile_form_-_Create_New_Policy_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bafe42e7-ef9d-ef73-2ead-4c2437ac3c76(1).png)
9. To save the changes, click **Save Firewall Profile**.

![Create_profile_form_-_Save_FW_profile.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6e3fdcdb-5642-da11-7502-a237e05f0a78(1).png)

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

Securiti policies translate data intelligence into actions. Each policy has rules that, when matched by a file, document, or resource, trigger a response.

## Related

- [Using firewall profiles](/using-firewall-profiles.md)
- [Creating firewall policies](/creating-firewall-policies.md)
- [Configuring firewall APIs](/configuring-firewall-apis.md)
