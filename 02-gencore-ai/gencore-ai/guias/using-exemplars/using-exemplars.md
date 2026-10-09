---
title: "Using Exemplars"
slug: "using-exemplars"
status: "update"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/using-exemplars"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Using Exemplars

**Scenario**

As a Data Security Officer, you're responsible for identifying abnormal AI interactions such as manipulated prompts to retrieve exclusive information. Without clear baselines, detection is inconsistent. With the **Exemplars** dashboard, you define and manage exemplar topics—ideal examples of the data expected prompts or responses. Firewall rules use these to flag deviations or abnormal behaviours in real time, helping you spot threats faster and enforce security with greater precision.

Firewall rules leverage analyzers to provide metadata for the rule. These analyzers operate by analyzing messages, such as those from prompts or data retrieval.

Certain types of analyzers compare inputs against a repository of exemplar data, which comprises a vast collection of strings stored in a distinct data file.

Exemplar topics refer to exemplary or representative text that can be used as examples or models in the context of chat prompts.

Topic definitions are used to illustrate and set a standard for what is considered ideal, archetypal, or exemplary within a given context. Exemplar topics help AI firewalls understand what normal and abnormal messages or groups of messages look like, enabling them to make more informed decisions about potential threats.

Using the **Exemplars** dashboard, you can access, create and manage exemplar topics. To open the **Exemplars** dashboard, in Securiti, open **Gencore AI** and choose **Firewalls** > **Exemplars**.

![Overview of topics related to phishing and prompt injection examples in a system interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Exemplars dashboard UI.png)

- The top of the dashboard displays a widget that shows the total number of exemplar topics.

![Overview of topics related to phishing and cybersecurity in a management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Exemplars-Topics widget.png)
- You can [create](/v1/docs/creating-exemplar-topics) and search for topics.
- Under the search box, you can filter the topics on the following columns:
  - Status
  - Topic
  - Owner

![Overview of topics related to phishing and their statuses in a management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Exemplars-filters.png)

- You can access:
  - Profiles
  - Policies
  - Rules

![Overview of topics related to phishing and prompt injection examples in a system interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Exemplars - Options.png)

- You can view widgets that display the following information on topics:
  - Topics
  - Enabled

![Overview of topics with enabled and total counts for security-related issues.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Exemplars-Topics-Enabled.png)

- You can click **Status** to set the status of the topic as active or inactive.

![Exemplar status as inactive](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Exemplar - status.png)
- To the right of each topic, you can click the **Metadata Explorer** to view more details about the selected topic.

![Exemplar metadata explorer](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Exemplar - metadata explorer.png)

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

## Related

- [Using firewall profiles](/using-firewall-profiles.md)
- [Creating exemplar topics](/creating-exemplar-topics.md)
- [Managing exemplars](/managing-exemplars.md)
