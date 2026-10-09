---
title: "Privacy Notice Management RBAC permissions and roles"
slug: "privacy-notice-management-rbac-permissions-and-roles"
status: "update"
updated: 2026-09-29T11:47:22Z
published: 2026-09-29T11:47:22Z
canonical: "helpcenter.securiti.ai/privacy-notice-management-rbac-permissions-and-roles"
area: privacy
modulo: privacy-notice-management
tipo: guia
data_captura: 2026-10-08
---

# Privacy Notice Management RBAC permissions and roles

The new Role-Based Access Control (RBAC) framework provides fine-grained permissions for Privacy Notice Management. It lets you create custom roles with specific permissions to control access to privacy notice management activities.

Some permissions in custom roles depend on related permissions, which Securiti automatically includes to maintain the required access. Securiti also provides default roles that automatically inherit their predefined permissions.

> [!WARNING]
> Important
> 
> This feature is available in Securiti SaaS deployments but is not currently available in Securiti Sovereign deployments. Contact your Customer Success Manager or Account Representative for updates on its availability in your tenant.

- [Accessing Privacy Notice Management permissions](/latest/docs/privacy-notice-management-rbac-permissions-and-roles#accessing-privacy-notice-management-permissions)
- [Privacy Notice Management RBAC permissions with default roles](/latest/docs/privacy-notice-management-rbac-permissions-and-roles#privacy-notice-management-rbac-permissions-with-default-roles)
- [Privacy Notice Management RBAC permissions with custom roles](/latest/docs/privacy-notice-management-rbac-permissions-and-roles#privacy-notice-management-rbac-permissions-with-custom-roles)

## Accessing Privacy Notice Management permissions

Follow the steps given below to access the Privacy Notice Management RBAC permissions in the Securiti:

1. In Securiti, from the upper left corner of the left navigation bar, click the **Jewel** icon, and from the navigation menu, choose **Settings**, as shown below.

![Securiti dashboard displaying settings and published notices with relevant metadata.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/creating_role_1.png)
2. In **Organizational**, under the **Access Management** section, click **Roles**, as shown below.

![Roles management interface displaying various user roles and their details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/creating_role_2.png)
3. Near the upper right corner of the page, click **+ Create Role**, as shown below.

![Roles management interface displaying various user roles and their details for access control.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/creating_role_3.png)
4. Under the **Permissions** section, click the **Privacy Notice Management** tab to access the permissions, as shown below.

![System settings interface showing roles and permissions, highlighting Privacy Notice Management option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/rbac_privacy_notice_management.png)

## Privacy Notice Management RBAC permissions with default roles

Use the following table to understand which Privacy Notice Management permissions Securiti lets you use for each system-generated role. A check mark (✅) indicates allowed access, while a cross (❌) represents no access.

| Permission | Super Admin | Org Admin | Operator | Module Owner | DPO | User |
| --- | --- | --- | --- | --- | --- | --- |
| `Create Notices` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Read Notices` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Read Notices Only If Owner Or Approver` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Notices` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Delete Notices` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Approve Notices` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Archive or Unarchive a Notice` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Manage Notice Approvers` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Manage Notice Co-Owners` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Manage Notice Messaging` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Manage Notice Only If Owner Or Approver` | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| `Manage Notice Settings` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Move Notice Org Unit` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Publish Notices` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Revert Notices` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Submit Notice For Approval` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Sync Notice Translations` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Create Notice Reminder Schedule` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Read Notice Reminder Schedule` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Delete Notice Reminder Schedule` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Create Notices Templates` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Read Notices Templates` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Read Notice Templates Only If Owner Or Approver` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Notices Templates` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Delete Notices Templates` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Approve Notice Templates` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Change Notice Templates Version` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Manage Notice Templates Approvers` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Manage Notice Templates Co-Owners` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Manage Notice Templates Only If Owner Or Approver` | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| `Manage Notice Templates Settings` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Revert Notice Templates` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Submit Notice Templates For Approval` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Sync Notices From Templates` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Sync Notice Templates Translations` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Create Privacy Custom Metadata` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Read Privacy Custom Metadata` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Update Privacy Custom Metadata` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Delete Privacy Custom Metadata` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Download Privacy Custom Metadata Attachment` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Upload Privacy Custom Metadata Attachment` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Manage Notice And Templates Custom Metadata` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Read Module Settings` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Manage Module Settings` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create Privacy Fonts` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Read Privacy Fonts` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Update Privacy Fonts` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Delete Privacy Fonts` | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |

## Privacy Notice Management RBAC permissions with custom roles

Use the following tables to understand the details of Privacy Notice Management permissions, including the actions each permission lets you perform and its dependent permissions.

| Permission | Explanation | Dependent permissions |
| --- | --- | --- |
| `Create Notices` | Lets you create a privacy notice. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Read Notices` | Lets you view a privacy notice. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Update Notices` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Read Notices Only If Owner Or Approver` | Lets you view privacy notices and their content. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Update Notices` | Lets you edit a privacy notice, such as formatting, layout, styling and content. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Delete Notices` | Lets you delete a privacy notice. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Approve Notices` | Lets you approve a privacy notice. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Archive Or Unarchive A Notice` | Lets you archive or unarchive a privacy notice. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Manage Notice Approvers` | Lets you add or remove a privacy notice approver. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Manage Notice Co-Owners` | Lets you add or remove privacy notice co-owners. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Manage Notice Messaging` | Lets you tag a user and send, edit or delete messages. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Manage Notice Only If Owner Or Approver` | Lets you manage a privacy notice only when you are its owner or approver. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Create Notice Reminder Schedule` - `Delete Notice Reminder Schedule` - `Read Notice Reminder Schedule` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Manage Notice Settings` | Lets you manage notice settings, such as languages, layout and styling. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Module Settings` - `Read Notices Only If Owner Or Approver` - `Sync Notice Translations` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Move Notice Org Unit` | Lets you change the privacy notice organization unit. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Sync Notice Translations` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Publish Notices` | Lets you publish the privacy notice. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Revert Notices` | Lets you restore the previous notice version from version history. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Submit Notice For Approval` | Lets you submit the privacy notice for approval. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Sync Notice Translations` | Lets you synchronize translations when updates are available after changes are made to the privacy notice content. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Create Notice Reminder Schedule` | Lets you set a reminder for co-owners and approvers for notice approval. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Delete Notice Reminder Schedule` - `Read Notice Reminder Schedule` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Read Notice Reminder Schedule` | Lets you view the privacy notice reminder. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Delete Notice Reminder Schedule` | Lets you delete a privacy notice reminder. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notice Reminder Schedule` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Create Notice Templates` | Lets you create privacy notice templates. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notice Templates Only If Owner Or Approver` - `Update Notices Templates` |
| `Read Notice Templates` | Lets you view privacy notice templates. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Read Notice Templates Only If Owner Or Approver` | Lets you view privacy notice templates and their content only when you are the owner or approver. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` |
| `Update Notice Templates` | Lets you modify the privacy notice templates. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notice Templates Only If Owner Or Approver` |
| `Delete Notice Templates` | Lets you delete privacy notice templates. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notice Templates Only If Owner Or Approver` |
| `Approve Notice Templates` | Lets you approve privacy notice templates. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notice Templates Only If Owner Or Approver` |
| `Change Notice Templates Version` | Lets you restore the previous version of the privacy notice template. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notice Templates Only If Owner Or Approver` |
| `Manage Notice Templates Approvers` | Lets you add or remove privacy notice template approvers. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notice Templates Only If Owner Or Approver` |
| `Manage Notice Templates Co-Owners` | Lets you add or remove privacy notice templates co-owners. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notice Templates Only If Owner Or Approver` |
| `Manage Notice Templates Only If Owner Or Approver` | Lets you create or update notice templates only if you are a privacy notice template owner or approver. | None |
| `Manage Notice Templates Settings` | Lets you update privacy notice template settings. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Module Settings` - `Read Notice Templates Only If Owner Or Approver` - `Sync Notice Templates Translations` |
| `Revert Notice Templates` | Lets you restore a previous version of a privacy notice template. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notice Templates Only If Owner Or Approver` |
| `Submit Notice Templates For Approval` | Lets you submit the privacy notice templates for approval. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notice Templates Only If Owner Or Approver` |
| `Sync Notices From Templates` | Lets you sync privacy notices with their templates. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Sync Notice Templates Translations` | Lets you synchronize translations when updates are available after changes are made to the privacy notice template content. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notice Templates Only If Owner Or Approver` |
| `Create Privacy Custom Metadata` | Lets you create custom metadata for privacy notices and templates. | **Privacy Notice Management:** - `Download Privacy Custom Metadata Attachment` - `Read Privacy Custom Metadata` - `Upload Privacy Custom Metadata Attachment` |
| `Read Privacy Custom Metadata` | Lets you view custom metadata. | None |
| `Update Privacy Custom Metadata` | Lets you edit custom metadata. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Upload Privacy Custom Metadata Attachment` - `Download Privacy Custom Metadata Attachment` |
| `Delete Privacy Custom Metadata` | Lets you delete custom metadata for privacy notices and templates. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` |
| `Download Privacy Custom Metadata Attachment` | Lets you download a custom metadata attachment for privacy notices and templates. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` |
| `Upload Privacy Custom Metadata Attachment` | Lets you upload custom metadata attachment files. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` |
| `Manage Notice And Templates Custom Metadata` | Lets you manage a custom metadata attachment for privacy notices and templates. | **Privacy Notice Management:** - `Read Privacy Custom Metadata` - `Read Privacy Fonts` - `Read Notices Only If Owner Or Approver` - `Read Notice Templates Only If Owner Or Approver` **Sensitive Data Intelligence:** - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) |
| `Read Module Settings` | Lets you view module settings such as, Font Repository, and Color & Styling. | None |
| `Manage Module Settings` | Lets you manage module settings such as **Font Repository**, and **Color & Styling**. | **Privacy Notice Management:** - `Read Module Settings` |
| `Create Privacy Fonts` | Lets you upload custom fonts in `woff2` format. | **Privacy Notice Management:** - `Read Privacy Fonts` - `Update Privacy Fonts` |
| `Read Privacy Fonts` | Lets you view custom fonts. | None |
| `Update Privacy Fonts` | Lets you modify custom fonts, such as font name, type, weight, and file. | **Privacy Notice Management:** - `Read Privacy Fonts` |
| `Delete Privacy Fonts` | Lets you delete custom fonts. | **Privacy Notice Management:** - `Read Privacy Fonts` |
