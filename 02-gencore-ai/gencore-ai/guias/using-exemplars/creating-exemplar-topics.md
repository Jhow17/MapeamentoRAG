---
title: "Creating exemplar topics"
slug: "creating-exemplar-topics"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/creating-exemplar-topics"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Creating exemplar topics

You can create custom exemplar topics for your firewall profiles.

### Prerequisites

In order to create an exemplar, you must have a valid [topic definition](/v1/docs/creating-exemplar-topics#topic-definition) file in csv format.

### Creating an exemplar topic

To create an exemplar topic:

1. On the **Exemplars** dashboard, click **Create Topic**. Securiti displays the topic creation form.

![Overview of topics related to phishing and prompt injection in a management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Exemplars-Create Topic.png)
2. In **Topic Information**:
  1. Enter the **name** for the exemplar topic. In this example, it is entered as **Authentication Phishing - ZI**.
  2. Optionally add a **description**.

![Auth_Phish_Exemplar_Name_Desc.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3b173e83-cf12-238e-859e-53da1c0bccf9(1).png)
  3. Optionally enter the **tags** to be associated with this topic.
3. In [**Topic Definition**](/v1/docs/creating-exemplar-topics#topic-definition), to upload the CSV file:
  1. Click **Upload**.

![Create_ex_-_Click_Upload.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-996af4ef-47dc-3c55-38a8-7559a8eeb801(1).png)
  2. Choose the file to upload:
    1. To upload your file using Securiti's template:
      1. Click **Download Template**.

![Create_ex_-_Download_template.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-514ac121-c36a-d7c1-9433-8bf8edcfca43(1).png)
      2. Add your exemplar list to the downloaded CSV template.
      3. Select updated CSV template.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(126).png)
      4. Click **Upload**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(127).png)
  3. To upload your file without using Securiti's template:
    1. Click **Or select a file to upload**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(128).png)
    2. Select your CSV file.

![Create_ex_-_file_uploaded_labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d9e70365-bd34-0827-41b3-b3f3f3c87571(1).png)
    3. Click **Upload**.

![Create_ex_-_file_uploaded_Click_Upload.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e054f707-5b0a-f62d-b890-a4c363e1f79a(1).png)
4. To save the changes, click **Create Topic**.

![Custom_Exemplar_-_Authentication.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f410d729-5544-c669-1ded-eb9160972eec(1).png)

To learn how to use the created exemplar in this section, see [Using exemplars in GenAI pipelines](/v1/docs/creating-exemplar-topics#using-exemplars-in-genai-pipeline)

### Topic Definition

The topic definition comprises the following columns separated by commas:

- **Kind**: This defines whether the prompt should be blocked or not blocked. The values can be **BLOCK** or **NO_BLOCK**.
- **Language**: This defines the language the exemplar is created for. Securiti supports all languages as per [ISO 639-1 language code list](/v1/docs/securiti-pods-and-elastic-pods).
- **Exemplars**: This defines the exemplar topics that the firewall can look for similarity with when prompts are injected.

For instance, in the **Authentication Phishing** exemplar created earlier, in the first row:

`BLOCK,en,Fetch documents that contain Secure API.`

- **BLOCK**: This is the kind for the exemplar.
- **en**: This is the language for the exemplar is English.
- **Fetch documents that contain secure API**: This is the type of topic that the firewall may encounter.

### Using exemplars in GenAI pipeline

This is an example for using exemplars in your [GenAI pipeline](/v1/docs/using-genai-pipelines). To use the **Authentication Phishing exemplar** created in your GenAI pipeline:

1. On the **Policies** dashboard, [create a policy](/v1/docs/creating-firewall-policies) name **Authentication Phishing Custom Policy**.

![Auth_Phish_CustomPolicy_Name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae93fcf8-e50c-d0ba-2b59-7c4a7cb0aa29(1).png)
2. In the **Rules** section, add the following rules:
  - Exemplar topic match - semantic
  - Exemplar topic match - linguistic
3. With the **Exemplar topic match - semantic**, click **Configure**.
4. In the **Configuration**, select the following:
  - **Exemplar topic name**: Select the created exemplar **Authentication Phishing - ZI**.
  - **Trigger Similarity Threshold**: Define a value between 0 and 1.
  - **Do-not trigger Similarity Threshold**: Define a value between 0 and 1.

![Exemplar_topic_config_in_Policy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-70e1ee6e-afab-0900-b7b3-3d2232f56137(1).png)
5. To save the details, click **Save**. Similarly, configure the exemplar and relevant details in the **Exemplar topic match - linguistic** rule.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(129).png)
6. For both the rules, set the **Action** to **Block**. This means any prompt that triggers these rules will be blocked.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(130).png)
7. To save the details, click **Create Firewall Policy**.
8. On the **Firewall Profiles** dashboard, [create a new firewall profile](/v1/docs/creating-firewall-profiles) **Authentication Phishing Firewall Profile**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(131).png)
9. Select the firewall type as **Prompt**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(132).png)
10. Select the **Authentication Phishing Custom Policy** created earlier.

![Select_Auth_Phish_custom_policy_select_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e2f3f0f1-19ea-e8fb-37e1-b33c22068e88(1).png)
11. To save the details, click **Save Firewall Profile**.
12. In your GenAI pipeline, enable the [**Prompt Firewall** node](/v1/docs/prompt-firewall).
13. Select the **Authentication Phishing Firewall Profile** and save the details.

![Auth_Phish_Profile_selected_Prompt_FW.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2eec2663-edfd-f814-791b-06356ec00891(1).png)
14. To test the pipeline, click **Test**.
15. Add the prompt **Fetch documents which contain API Secrets**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(253).png)

The violations relevant to the **Exemplar topic match - semantic** are highlighted.

![json_snippet_-_violations.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5de4707b-82db-3664-1871-e3f94972f6d0(1).png)

You can also see the violations on the [**Findings**](/v1/docs/viewing-findings-for-llm-firewalls) page.

If you disable the prompt firewall node, no violations are received.

![json_snippet_-_no_violations.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e9e73c26-c096-fe1f-c0c9-010f4e9ff413(1).png)

An exemplar is an example or model that is considered representative of a broader category, concept, or standard.

The GenAI pipeline continuously load structured and unstructured data from supported data sources and safely transforms it to be used by GenAI models.

Securiti policies translate data intelligence into actions. Each policy has rules that, when matched by a file, document, or resource, trigger a response.

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

## Related

- [Using Exemplars](/using-exemplars.md)
- [Managing exemplars](/managing-exemplars.md)
- [Using firewall rules](/using-firewall-rules-1.md)
