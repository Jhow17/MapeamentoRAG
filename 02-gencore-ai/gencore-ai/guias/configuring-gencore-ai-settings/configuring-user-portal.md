---
title: "Configuring user portals"
slug: "configuring-user-portal"
updated: 2026-07-20T05:04:24Z
published: 2026-07-20T05:04:24Z
canonical: "helpcenter.securiti.ai/configuring-user-portal"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Configuring user portals

**Scenario**

As a Data Governance Officer, you’re responsible for making GenAI workflows accessible and manageable for different teams. Without a unified interface, users struggle with scattered tools and inconsistent access. By integrating pipelines into the **user portal**, you centralize access, streamline task initiation, and monitor usage in one place. This improves operational control and creates a smoother, more efficient user experience.

The **User Portal** page lets you define a central place where you can easily access and interact with your organization's GenAI pipelines. To open the **User Portal** page, go to **Settings > Gencore AI > User Portals**.

> [!NOTE]
> **Important**
> 
> You must have [SSO](/v1/docs/configuring-user-portal#configuring-the-user-portal) configured through which users can log in to access and query pipelines.

Integrating your GenAI pipelines into your user portal offers the following capabilities:

| Capability | Description |
| --- | --- |
| Centralized access | It provides a single point of access where you can easily reach and query your s. |
| Streamline workflows | Having your s integrated into a portal, you can streamline complex processes, automate tasks, and improve efficiency. You can initiate processes, monitor progress, and receive outputs without needing to switch between different systems. |
| Improved control and monitoring | Integrating your s into a user portal allows for better monitoring and control of these systems. |
| Enhanced user experience | With all tools and processes in one place, the user experience can be enhanced. This can lead to more effective use of the s. |

## Prerequisites

To configure your user portal, you must have:

- ​​Securiti tenant login: ​​
  - You must have Securiti tenant credentials.
  - The Securiti tenant must have User Portal and custom deployment access.

## Configuring your user portals

To create your user portals, in ​Securiti, click ​**Settings,**​ and choose ​**System Settings > ​​Gencore AI ​> User Portal​​**.

You can configure your user portals in two ways:

| User Portal | Description |
| --- | --- |
| [Default Securiti-hosted user portal](/latest/docs/configuring-securiti-hosted-user-portal) | User portal using the default Securiti environment. |
| [Self-hosted user portal](/latest/docs/configuring-self-hosted-user-portal) | User portal in your own self-hosted environment. > [!WARNING] > Important > > You must have multi-organizational support enabled for your tenant. |

## Managing your user portal

You can perform the following actions on your user portal:

- Edit
- Delete

### Editing your user portal

To edit your user portal:

1. Locate the card for the user portal you want to edit.
2. To the right side of the card, choose **Options** (three dots), and select **Edit**.
3. Update the user portal as required.
4. Save changes.

### Deleting your user portal

To delete your user portal:

1. Locate the card for the user portal you want to delete.
2. On the **User Portals** dashboard, to the right side of the card, choose **Options** (three dots), and select **Delete**.
3. Securiti displays a prompt to confirm deletion.

![Confirmation dialog asking to delete a user portal and its integrated apps.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/148 User Portal - Confirm delete.png)
4. To proceed with the deletion, click **Delete**. To cancel the operation, click **Cancel**.

The GenAI pipeline continuously load structured and unstructured data from supported data sources and safely transforms it to be used by GenAI models.
