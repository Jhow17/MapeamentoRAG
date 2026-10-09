---
title: "Managing Securiti users"
slug: "configuring-access-management-managing-securiti-users"
status: "update"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/configuring-access-management-managing-securiti-users"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Managing Securiti users

Securiti administrators can add, update, and deactivate users. For more information, see [Understanding user types and roles](/v1/docs/roles-in-securiti-en).

> [!NOTE]
> **Note**
> 
> An organization admin can only create a user or update users details for “Organization Admin” or “User” roles only.

### Adding or editing an individual user

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. From the Settings menu, choose **Organizational > Access Management > Users**.
4. Do one of the following:
  - To add a new user, near the upper right corner of the user list, click **+ Create User**.
  - To edit an existing user, at the right end of their tile choose **Options** (three dots) **> Edit User**.
5. Use the Create User or User Detail panel to enter or update the user information as shown below. Required fields are marked by asterisks.

| Field | Description |
| --- | --- |
| First Name | Configure to suit. |
| Last Name |
| Email Address | Enter the user email address. For an internal user, the address must be within your primary or secondary domain. For a partner user, the address must be within the primary or secondary domain of the managed services organization's Securiti partner account. |
| Phone Number | Configure to suit. |
| Role | Choose a role. See [Understanding user types and roles](/v1/docs/roles-in-securiti-en). |
| Message Digest | Super Admin users can help other users by configuring their messaging digest settings for them. Each user can also configure their own message digest frequency. Choose the message digest frequency from the menu. |
| User Type | Choose either Internal or Partner. See [Understanding user types and roles](/v1/docs/roles-in-securiti-en). > [!NOTE] > **Note** > > In order for you to add a partner user: > > - The managed services organization must have a Securiti account of type "partner." > - The partner user must have an active user or admin account on the managed services organization's Securiti partner account. |
| Organizations (Except Super Admins) | If you have enabled the Securiti [organization-level access feature](/v1/docs/managing-organizations), use the tools to build a list of organizations to which the user belongs. > [!NOTE] > **Note** > > If you have configured secondary domains, and have restricted organization access by creating an Accessible Domain list for the organization, those settings override the organizations configured for a user. If you try to add an organization for which the user's domain is not allowed, Securiti shows you an error message and does not let you save the new or updated user. |
6. Click **Create User** or **Update User**.

### Viewing user details

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. From the Settings menu, choose **Organizational >Access Managament > Users**.
4. You can view the list of all the users. Against the user name, click on the **metadata icon** to view the details of the user.

![user-details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b12ac42-01a3-a83c-f7e3-443dc926e7f3(3).png)

### Importing multiple users from a .csv file

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. From the Settings menu, choose **Organizational >Access Managament > Users**.
4. Near the upper right corner of the user list, click the **Import users** button.

![import-users-csv.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9c9f6129-1c9f-b5ea-d279-16e15deff718(3).png)
5. On the drag & drop box, click the **Download Template** link to download a template for the .csv file.
6. Use a text editor or spreadsheet app to create a user list in the .csv format shown in the template.

> [!NOTE]
> **Note**
> 
> In your user list, use the names of the roles as shown in the template.
7. Drag the .csv file into the drag & drop box.
8. Click **Upload**.

Securiti uploads the list and creates accounts for the users in it. The new users are in a deactivated state, with blank passwords.

> [!NOTE]
> **Note**
> 
> If an error occurs, you receive an email that explains the issue.
9. Refresh your browser window to see the new users.

### Activating or deactivating a Securiti user

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. From the Settings menu, choose **Organizational > Access Management > Users**.
4. From the users' list select the user you want to activate or deactivate and click the details (three dots) button against the user name.
5. Choose **Settings > Activate** or **Settings > Deactivate Account**.

> [!WARNING]
> **Warning**
> 
> If you attempt to deactivate a user who has provisioned API keys, Securiti warns you as shown below. We strongly recommend that if you see this warning, you change those API keys to ones owned by an active user or (preferably) by a service account before deactivating the user. Doing so helps prevent situations where backend tooling and services fail silently because the owner of the API keys they rely on has been deactivated.
> 
> ![user-settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5dbae6ae-e979-2bba-cfc3-49a9c45a4441(3).png)

> [!NOTE]
> **Note**
> 
> If you attempt to deactivate a user who is owner or co-owner of any of the following Securiti entities, Securiti prompts you to identify a Super Admin to reassign them to:
> 
> - DSR requests, tasks, or subtasks
> - DSR forms
> - Assessments
> - On-premises pods
> - Data systems
> - Consent Website domains
> - Data Mapping Automation catalog entities (assets, processes, etc.)

### Deactivating guest users

To remove deactivated users from an assessment collaborator list:

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. From the Settings menu, choose **Organizational > Access Management > Users**.
4. From the users' list select the user you want to deactivate and click the details button against the user name.
5. Click **Yes, continue**, then confirm the deactivation user by clicking **Yes, Continue** . Then choose an admin to whom to transfer ownership of their Securiti resources as shown below.

> [!NOTE]
> **Note**
> 
> Please choose another **Super Admin** user to transfer the resources owned by the user that is being deactivated.

![deactivate-user-settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3f2558e4-7b5e-2af5-f41e-740bc42eff55(3).png)
6. Click **Yes, continue** again to deactivate the user.

Securiti displays "User deleted successfully!" near the top right corner of the page.
7. On the Securiti dashboard, open **Assessment Automation**, then choose **Assessments > Assessments** in the left-hand menu.
8. Select the appropriate Assessment to check.

The assessment header shows the text "None" next to Collaborators.

![None.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c1d590cc-2f68-1fcf-d794-5f08693b95a0(3).png)

### Deleting a user

Securiti lets you permanently delete internal users and partner users you have added to the Platform. Deleting users helps maintain compliance and supports your organization's data retention policies.

> [!WARNING]
> Important
> 
> You cannot restore the user once you delete it from Securiti.

When deleting a user, there are three types of users involved in this process:

| Use type | Description |
| --- | --- |
| Deleted user | User getting deleted from the Securiti Platform |
| Deleting user | User logging in the Securiti portal and performing the User Delete action |
| Inherited user | User receiving the roles of the deleting user |

> [!NOTE]
> Note
> 
> To delete a user, you must meet the following criteria:
> 
> - The deleting user and the inherited user must have equal or higher privileges than the deleted user.
> - All three users must be internal users.
> - The deleting user and the inherited user must belong to all organizations associated with the deleted user.
> - The deleting user must have RBAC permission to delete users.

To delete a user from the platform:

1. On the **Users** page, locate the user you want to delete.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-53XGEXIJ.png)
2. On the right side of your selected user, click **Options** (three dots).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-3CANDJJ9.png)
3. From the options menu, select **Delete**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-AL2EFTEV.png)

A **User Settings** popup appears.
4. On the **User Settings** popup, open the **Delete User Account** section by clicking on the down arrow icon.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RX4ISBI1.png)

It displays more options to fill.
5. From the **Search User** menu, choose the inherited user. When deleting a internal user or a partner user, the inherited user must be a internal user.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6WYT417R.png)
6. Once selected, click **Delete User Account**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NAAW0X9J.png)

This process performs the following actions in your Securiti tenant:

It deletes the user with the following criteria:
  - It deletes the user permanently from your Securiti tenant. You can allocate the deleted email to any new user.
  - It transfers all the permissions, rights, and resources to the inherited user.
  - The deleting user and the inherited user must have equal or higher privileges than the deleted user.
  - All three users must be internal users.
  - The deleting user and the inherited user must belong to all organizations associated with the deleted user.
  - The deleting user must have RBAC permission to delete users.

To understand the criteria of user deletion and the inheritance with examples, see the table below:

| Deleted user | Inherited user | Deleting user | Delete status | Reasoning |
| --- | --- | --- | --- | --- |
| Has **SUPER ADMIN** role | Has **SUPER ADMIN** role | Is **Super Admin** with RBAC permission | ✅ | Accepts because the inherited user contains equivalent privileges as the deleted user. |
| Has **Module Owner DSR User Profile ROLE** role | Has **Gencore Admin** role | Is **Super Admin** with RBAC permission | ❌ | Rejects because it has different privileges from different modules and does not match the same module ownership. |
| Has **Gencore Admin** role with the organization **A** | Has **Gencore Admin** role with the organization **B** | Is **Super Admin** with RBAC permission | ❌ | Rejects because it has different organizations. The inherited user must contain all organizations of the deleted user. |
| Has **SDI Evidence Analyst** role with organization **Default** | Has **SDI Evidence Analyst** role with organization **Default** | Is **SDI Evidence Analyst** but with no RBAC permission | ❌ | Rejects because the deleting user does not have enough RBAC permission to delete any user. |

### Exporting users list

This feature lets you export the list of all users and their relevant details in CSV format. To export it, proceed with the following steps:

1. In Securiti, at the top left corner of the dashboard, click the **Jewel** icon.
2. From the Platform Services section in the new navigation, click **Settings**.
3. From the Settings menu, choose **Organizational > Access Management > Users**.
4. At the top right corner of the screen, click the **Options** button (three dots).
5. From the menu, click **Export**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7H9D5ECR.png)

It displays a success message.

It sends the exported CSV file to your email.

You can also access the CSV file in the My Downloads section. To access the file from the Downloads section, proceed with the following steps:

1. At the bottom left of your screen, click your profile avatar icon.
2. From the menu, click **My Downloads**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NQAAWIJO.png)

The files Securiti downloads for you are also available in this section.
3. On the right side of your exported CSV file, click the download icon to download it.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-O01LMDUX.png)

It downloads the file into your directory.

### Converting a system user into a guest user

When you convert a system user into a guest user, Securiti prompts you for a user to which it assigns resources such as DSRs, assessments, data systems, and similar elements solely owned by the user you are converting to a guest user.

- For resources for which the user is a co-owner along with another user, Securiti simply removes them as a co-owner.
- For assessments formerly owned by the user, the user is assigned as a collaborator, and sent passwordless links to the assessments.
- For risks owned by the user, they remain the owner, since guest users can own risks.
- For some resources, Securiti sends email to the new owner to alert them.

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. On the System Users tab, next to the user you want to convert, choose **Options > Convert To Guest User**.
4. Click **Yes, continue** as shown below.

> [!NOTE]
> **Note**
> 
> Please select another user **Super Admin** or **DPO** to transfer the resources owned by the user being converted to guest user.

![convert-t-guest-user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-96279a02-5317-57be-eb74-a178658bfee3(3).png)
5. On the popup, choose a user to whom to assign the resources owned by the system user you are converting into a guest user, then click **Convert to Guest**.

### Converting guest users to system users

You can convert a guest user to a system user but they don't automatically become assessment owners or co-owners of previously assigned assessments. To convert a guest back into an admin user:

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. From the Settings menu, choose **Organizational > Access Management > Users**.
4. On the Guest Users tab, click **Options** (three dots) next to a user and select **Edit User**.
5. In the right-hand side column, under User Detail, choose **Super Admin** for the Role and **Internal** for the User Type, as shown below.

![make-guest-internal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e93d24ed-cc63-1470-dac7-4101beba7d45(3).png)

Click **Save**

> [!NOTE]
> **Note**
> 
> Make sure to enter the last name or you get the following error message:
> 
> "Missing required field: lastname"
6. On the Users page, navigate to the System Users tab to find the new user.

### Generating a new password for a user

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. From the Settings menu, choose **Organizational > Access Management > Users**.
4. At the right end of the card for the user, choose **Options > Generate Password**.

Securiti generates a new password and shows it to you.
5. Send the password to the user, and tell them to update their password as soon as possible.

### Resetting a user password

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. From the Settings menu, choose **Organizational > Access Management > Users**.
4. At the right end of the card for the user, choose **Options > Reset Password**.

Securiti resets the user password, and sends the user an email that instructs them to set a new password.

### Configuring message digest frequency for a user

Super Admin users can help other users by configuring their messaging digest settings for them. Each user can also configure their own message digest frequency.

1. Login to Securiti with your admin credentials.
2. In Securiti, click the jewel at the bottom of the **Dashboard**.
3. From the list of options, select **Settings**.
4. From the Settings menu, choose **Organizational > Users**.
5. On either the System Users tab or the Guest Users tab, choose **Options > Message Digest** for the user.
6. On the panel that slides in from the right, configure the user’s message digest frequency as shown below.

![users_email_diaguest_settings2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4307a647-d2fc-dbed-b8f6-aaf8f1b1891b(3).png)

### Disabling multi-factor authentication for a user

For users that accidentally get locked out of their Securiti accounts by multi-factor verification, a Securiti administrator can disable their multi-factor verification so they can log back in using only their Securiti username and password:

1. Log in to Securiti with your admin credentials.
2. In Securiti, click the jewel at the bottom of the **Dashboard**.
3. From the list of options, select **Settings**.
4. From the Settings menu, choose **Organizational > Users**.
5. Click the card for the locked-out user, then click **Options** (three dots) > **Edit**.
6. Click the **Settings** tab, expand the **Disable MFA** area, and click **Yes, continue** as shown below.

![disable_MFA.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc747995-54c7-359f-f8df-b43e6365e317(3).png)
7. Click **Yes, continue** on the confirmation popup to disable multi-factor verification for the user.

Assessments answer different questions related to an entity, such as purpose, etc. Also, with each assessment, you can associate risks.

Data systems refer to the system where your data is stored. That can be in the form of files (text, audio, video), databases (tables and schemas), and streaming data (data in motion). Securiti supported most of the structured, unstructured, and streaming data systems.

## Related

- [Using Roles in Securiti](/roles-in-securiti.md)
