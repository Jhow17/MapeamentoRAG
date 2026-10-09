---
title: "Viewing findings for LLM firewalls"
slug: "viewing-findings-for-llm-firewalls"
updated: 2026-01-14T10:05:06Z
published: 2026-01-14T10:05:06Z
canonical: "helpcenter.securiti.ai/viewing-findings-for-llm-firewalls"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Viewing findings for LLM firewalls

Firewalls add an extra layer of security to the pipeline by letting you define policies to protect the LLM from potential user abuse.

AI-powered firewalls use machine learning and artificial intelligence to detect and respond to potential threats in real time.

To view the LLM Firewalls findings:

- On the [**Firewalls Profiles**](/v1/docs/using-firewall-profiles) dashboard, select a firewall profile and click **View Findings**.
- On the [**Policies**](/v1/docs/using-policies) dashboard, click **View Findings**.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

The **Findings>LLM Firewalls** dashboard gives detail about the findings related to LLM firewalls.

![Findings dashboard](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Findings.png)

- You can [create filters](/v1/docs/viewing-findings-for-llm-firewalls#create-filters-in-findings) to view findings.
- You can view the exact number for the following information provided through widgets:
  - Total profiles with findings
  - Retrieval findings
  - Response findings
  - Prompt findings
- You can group the findings by:

![Findings - group by profile](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Findings_groupByProfile.png)
  - Profile
  - Rule
  - Pipeline
  - Policy
- You can click to expand a profile to view the details of the corresponding findings.
- You can view a list of deleted findings by clicking the **Delete** row.

![Findings - deleted row](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Findings_deletedRow(1).png)

##

## Create filters in Findings

1. On the **Filters** menu, click **Add**.

![Findings - Add filter](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Findings-Add.png)
2. Choose your property and relevant actions.
  - Action:
    1. Select **Action**.
    2. Choose operation:
      1. is one of
      2. is equal to
      3. is not equal to
    3. Select one or more actions:
      - Block
      - Log
      - Redact
      - Warn
  - Pipeline:
    1. Select **Pipeline**.
    2. Choose operation:
      - is one of
      - is equal to
      - is not equal to
    3. Select one or more pipelines.
  - Policy:
    1. Select **Policy**.
    2. Choose operation:
      - is one of
      - is equal to
      - is not equal to
    3. Select one or more policies.
  - Profile:
    1. Select **Profile**.
    2. Choose operation:
      - is one of
      - is equal to
      - is not equal to
    3. Select one or more profiles.
  - Rule:
    1. Select **Rule**.
    2. Choose operation:
      - is one of
      - is equal to
      - is not equal to
    3. Select one or more rules.
  - Type:
    1. Select **Type**.
    2. Choose operation:
      - is one of
      - is equal to
      - is not equal to
    3. Select one or more types of firewall profiles:
      - Prompt
      - Response
      - Retrieval
      - Standalone

A filter for findings is shown below where:

- Policies related to Authentication Phishing are selected.
- Firewall profile type is selected as Prompt.

![Findings - filter example](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Findings-filter example.png)

### Saved views for findings

You can save filters for Findings to reuse them. To save your Finding filter, on the ​**Findings**​​ dashboard:

1. Click **Save view**.

![Findings - Save View](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/findings created filter Save View.png)

Securiti displays the **Save view** popup.

![Findings save view popup](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FIndings - save view popup.png)
2. Select an existing group or enter a **group name** to create a new group and press **Enter**.

![Findings - save view group name](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FIndings - group name.png)
3. Enter a **name** for the view and optionally add a **description**.

![Findings - views - group and name](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FIndings - views - group and name.png)
4. To save the view, click **Save View**.

![Findings - save view](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FIndings - save view.png)
5. To access your saved views, on the **Policies** dashboard, click **Saved Views**.

![Findings - Saved Views](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Findings-SavedViews.png)
6. To see your custom views, click **Custom Views**.

![Findings - Custom Views](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Findings - Custom Views - Auth phishing.png)

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

Securiti policies translate data intelligence into actions. Each policy has rules that, when matched by a file, document, or resource, trigger a response.

## Related

- [Using firewall profiles](/using-firewall-profiles.md)
- [Creating firewall policies](/creating-firewall-policies.md)
