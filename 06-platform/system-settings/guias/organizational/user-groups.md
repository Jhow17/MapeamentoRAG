---
title: "User Group"
slug: "user-groups"
updated: 2026-08-27T08:45:05Z
published: 2026-08-27T08:45:05Z
canonical: "helpcenter.securiti.ai/user-groups"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# User Group

User Group in Securiti provides a way to manage and organize users and maintain their roles and access according to your team divisions. You can create one group and add users to it. This lets you categorize users according to their roles, division, location, or your any preferred aspect.

You can also allocate one or multiple roles to the User Group which performs the following actions:

- It assigns the roles of the User Group to all the users who are part of it.
- Users maintain the previous roles and inherit the new role with it.
- When you remove a user from User Group, it only removes the role inherited from the User Group. User’s initial existing role remains same.

See the following scenarios with example:

| User role | User Group role | Action performed | Impact |
| --- | --- | --- | --- |
| Module Owner | Super Admin | Adding user to the User Group | User now contains the following roles: - Module Owner - Super Admin |
| Module Owner | Super Admin | Removing user from User Group | User now contains the following role: - Module Owner |
| Module Owner | None | Adding user to the User Group | User now contains the following role: - Module Owner |

User Group provides efficiency for managing and categorizing the users in Securiti and provides the following usecases:

- Manages to provide roles to large number of users altogether
- Provides temporary high privileged access to a user
- Categorizes users without updating their roles

## Prerequisites

In order to be able to view, create, or edit a User Group, you must provide [**Manage User Access**](/latest/docs/rbac-permissions-with-custom-roles#system-settings) permission by accessing **Roles >** **Securiti Platform** permissions.

For more information on how to create a role and assign a permission, see [Using Roles in](/latest/docs/roles-in-securiti) Securiti.

## Accessing User Group

To open User Group in Securiti, proceed with the following steps:

1. In Securiti, from the upper left corner of the left navigation bar, click the **Jewel** icon.
2. From the Platform Services section in the new navigation, select **Settings**.
3. From the **System Settings**, choose **Organizational > Access Management > User Groups**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-DS8DOV1W.png)

It opens the Users Group homepage.

## Creating a new User Group

To create a new User Group, proceed with the following steps:

1. On User Group home page, on the top right corner of homepage, click **+ Create User Group**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-HZ4Z5RZN.png)

It opens **User Group Editor** page.
2. On **User** **Group Editor** page, add the following data:

| Parameter | Description |
| --- | --- |
| Group Name | Add a title for your User Group. |
| (Optional) Email | Add an email for the users of User Group. |
| (Optional) Roles | Add one or multiple role to associate with this User Group. You can also create a new role. To create a new role, see the next optional step. |
| (Optional) Add Users | Add one or muliple users. Use Search User menu to select users. |

> [!NOTE]
> Note
> 
> When you allocate one or multiple roles to the User Group, it adds these roles to the existing roles the user.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-40A52GLM.png)
3. (Optional) To create a new role and select in the User Group, proceed with the following steps:
  1. On the **User Group Editor** page, under **Roles** section, choose **Create a Role**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-98JGE3I6.png)

It opens **Create a Role** popup.
  2. On the **Create a Role** popup, add the following data:

| Parameter | Description |
| --- | --- |
| Role Name | Add a role title name. |
| (Optional) Description | Add a description to your role. |
| Permissions | Add one or more permissions from each module. From the list of module: 1. From the left section of **Permissions**, select a module name. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-W12DN40W.png) It displays the list of permissions under the selected module. 2. Mark the permissions you wish to include in the role. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-UZ8XF87H.png) 3. (Optional) Select any other module and mark the permissions as per your requirement. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-9SUKTILY.png)

For more information on creating a new role, see [Using Roles in Securiti](/latest/docs/roles-in-securiti).
  3. Once you select all permissions, click **Save Role**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0WUNBDFY.png)

It creates the role.

> [!WARNING]
> Important
> 
> It does not automatically selects the newly created role. You must search and select the your new role.
4. Once added, click **Create Group**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5EJDFQRR.png)

It creates a User Group.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-73HKL9JM.png)

## Editing User Group

Once you create your User Group, you can make changes to it later on. It lets you update all the details you have already added in the User Group. With this, you can add more users to it, or remove users if required. You can also update the roles of your User Group and it applies new roles to all the users added in this User Group.

To edit a User Group, proceed with the following steps:

1. Open the **User Group** homepage and select a User Group to edit.
2. On the right side of your selected User Group, click **Options** (three dots).
3. On the options menu, choose **Edit**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-F9D2HQ5Q.png)

It opens **User Group Editor** page.
4. On the **User Group Editor** page, make your changes in the selected User Group. For more information on all the fields you see on **User Group Editor** page , see [Create a new User Group](/latest/docs/user-groups#create-a-new-user-group).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-H7AESKYM.png)
5. Once you finish your changes and updates on the User Group, save your changes. To save the changes, at the end of this page, click **Edit Group**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZBCI1TKL.png)

It modifies the User Group and saves it.

## Deleting User Group

Once you create a User Group, Securiti lets you delete it. Deleting a User Group removes all users from it and removes any roles inherited from the User Group, leaving users with the roles users had at the time of creation. Also, you cannot recover a User Group once you delete it from Securiti.

To delete a User Group, proceed with the following steps:

1. Open the **User Group** homepage and select a User Group to edit.
2. On the right side of the selected User Group, click **Options** (three dots).
3. On the options menu, choose **Delete**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4BLZ1AXS.png)

It displays a popup.
4. On the popup, click **Delete**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BU7UY0XA.png)

It deletes the selected User Group.

Once you delete a User Group, it performs the following actions:

- It removes all the users from the User Group.
- It removes the roles of User Group from the roles of users that they inherited earlier from this User Group.
- It deletes the User Group.

This process does not delete the users, or their already existing roles.
