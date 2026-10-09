---
title: "Configuring user portal pipelines"
slug: "configuring-user-portal-pipelines"
status: "update"
updated: 2026-09-22T05:22:08Z
published: 2026-09-22T05:22:08Z
canonical: "helpcenter.securiti.ai/configuring-user-portal-pipelines"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Configuring user portal pipelines

To configure your GenAI pipelines with your user portal:

1. In your user portal, on the left panel, click **Portal Pipelines**.
2. [Link your GenAI pipelines](/latest/docs/configuring-user-portal-pipelines#linking-genai-pipelines)
3. Define [Access Exception Rules](/latest/docs/configuring-user-portal-pipelines#defining-access-exception-rules).
4. To save the configuration, click **Save Changes**.

## Linking GenAI pipelines

Under **GenAI Pipelines**, link your GenAI pipelines to your user portal.

1. Select the GenAI pipelines to be bound to your user portal. You can search or filter out required pipelines.

![Overview of the Securiti-Hosted Portal with various pipeline statuses listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/select user portal pipelines.png)

> [!NOTE]
> **Note**
> 
> To allow pipelines to be displayed, in Assistant API node, click **Enable pipeline** in user portal. Only enabled pipelines are displayed.
2. To show only the selected pipelines, click the toggle **Show selected pipelines only**.

![User Portal interface displaying pipeline options and a checkbox for selected pipelines.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/show selected pipelines only.png)
3. To save the pipelines selection, click **Save Changes**.

![Overview of the Securiti-Hosted Portal with pipeline statuses and options for user engagement.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/save portal pipelines.png)

## Defining Access Exception Rules

Under **Access Exception Rules**, define the rules to manage exceptions for pipeline access in the portal. To add a new rule:

1. Click **+Add Rule**.

![Add exception rules.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/portal pipelines - access exception rules.png)
2. In the **Access Exception Rules** popup, under **Pipeline**, select your GenAI pipeline for which you want to implement the access exception rule.

![Access Exception Rules dialog for selecting pipeline permissions in the Securiti-Hosted Portal.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/portal pipelines - access exc rules popup.png)
3. Under **Access Exception Rules**:
  1. Click **Add** to begin defining the rule.

![Add Access Exception Rules](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/portal pipelines - add access exception rules.png)
  2. Click **Edit** to set the attribute name.

![AER_popup_Attribute_labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-972db0ba-8517-0bfb-cdbe-1bf29c7b7d0d(2).png)
  3. Enter the attribute name and click **Save**.

![AER_Update_Attribute_name_Email_labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b53c9244-fea8-5857-c857-6f3610415747(2).png)
  4. Select the operator.

![AER_-_Attribute_Email_addedAtt_Eq_To.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b19a51f2-f0bb-240c-f1ba-18c7e55c4af4(2).png)
  5. Enter the attribute value.

![AER_popup_email_add.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a128f4c2-054e-18ea-2f7b-e686f6918f65(2).png)
  6. Press **Enter** to add the value.

![AER_popup_email_added.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c237f4df-b799-8617-e933-bc602d76dcd7(2).png)
  7. Click **Apply** to apply the rule.

![Assistan_API_Rule_added.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-56c02482-1ea8-fdec-fefb-87ad36b127e7(1).png)

Securiti adds the rule for the pipeline.

The GenAI pipeline continuously load structured and unstructured data from supported data sources and safely transforms it to be used by GenAI models.
