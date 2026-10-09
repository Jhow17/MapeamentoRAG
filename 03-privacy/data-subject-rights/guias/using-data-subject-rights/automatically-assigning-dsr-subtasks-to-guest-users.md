---
title: "Automatically assigning DSR subtasks to guest users"
slug: "automatically-assigning-dsr-subtasks-to-guest-users"
updated: 2025-10-30T19:13:14Z
published: 2025-11-03T07:39:28Z
canonical: "helpcenter.securiti.ai/automatically-assigning-dsr-subtasks-to-guest-users"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Automatically assigning DSR subtasks to guest users

When Securiti generates a DSR request, by default it assigns its subtasks to the co-owners of each Data System for which it created the tasks. You can also configure specific data systems so that DSR subtasks for them are automatically assigned to specific guest users. You can also configure guidance text that is included in the email notifications sent to the guest users, and also limit their access to specific DSR request types.

1. In Securiti, open **System Settings** and choose **Integrations > Data Systems**, then find and open the Data System instance for which you want to configure guest users.
2. On the Basic Information tab, scroll down to the DSR area, and if necessary mark the checkbox for **Include this instance in DSR workflow**.
3. Use the new Guest Users tools to build a list of guest users assigned as co-owners DSR subtasks as shown below.

![RN_DSR_guest2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-95a9d524-807c-ae5d-81db-fb2bf1b358a5.png)

We recommend customizing Guest user guidance text, which will reflect in the DSR Subtask action panel for their assigned subtasks.
4. To limit guest user access to specific DSR request types, enable the **Limit Guest access to specific DSR types** toggle, then use the Select DSR Types tools to choose the DSR request types.

> [!NOTE]
> **Note**
> 
> The menu displays labels for custom and system request types defined on the Request Types page in DSR settings. For more information, see [Configuring DSR request types](/v1/docs/configuring-dsr-request-types).
5. Near the upper right corner of the page, click **Save**.
