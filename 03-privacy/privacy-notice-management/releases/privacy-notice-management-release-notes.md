---
title: "Privacy Notice Management release notes"
slug: "privacy-notice-management-release-notes"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/privacy-notice-management-release-notes"
area: privacy
modulo: privacy-notice-management
tipo: release
data_captura: 2026-10-08
---

# Privacy Notice Management release notes

## 1.151

### Release updates - September 2026

#### Introducing new RBAC for Privacy Notice Management

Securiti has introduced new Role-Based Access Control (RBAC) for Privacy Notice Management, giving you more flexible control over permissions for Securiti users. You can create custom roles with specific permissions that match users’ responsibilities, preventing unauthorized access to module features and actions.

With the new RBAC framework, you can:

- Create custom roles with fine-grained, action-based permissions.
- Assign multiple roles to users or user groups based on their access and responsibilities.
- Control which users can view, create, edit, approve, publish, and manage privacy notices and templates.
- Control access to custom metadata with specific permissions to view, create, update, and upload attachments.
- Grant read-only access to notices, custom metadata, fonts, settings, and templates without providing modification permissions.
- Provide administrative permissions to manage notice settings, module settings, templates, and approval workflows.
- Apply conditional permissions to restrict access to notices and templates based on whether a user is an owner or approver.

> [!NOTE]
> Note
> 
> - Certain permissions in RBAC depend on other permissions. When you assign a permission to a user, Securiti automatically grants access to its dependent permissions.
> - You can also assign Privacy Notice Management roles and permissions to **Service** **Accounts**.

For more information, see [Privacy Notice Management RBAC permissions and roles](/latest/docs/privacy-notice-management-rbac-permissions-and-roles).

#### Adding support for privacy notice archiving

Securiti has introduced the **Archive** feature in Privacy Notice Management that lets you retain a record of a notice instead of deleting it.

You can archive your privacy notice from the **More** menu within the privacy notice editor, as shown below.

![Privacy notice sections include information collection, usage, and data sharing details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/archive_notice_1.png)The notice status changes to **Archived**, as shown below.

![Privacy notice sections detailing information collection, usage, and data sharing practices.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/archive_notice_5.png)

Securiti also lets you unarchive a privacy notice at any time without changing its previously published URL.

> [!NOTE]
> Note
> 
> Securiti prevents you from editing a privacy notice while it is in the **Archived** state to preserve its content. To make changes, first unarchive the privacy notice.

For more information, see [Archiving your privacy notice](/latest/docs/archiving-your-privacy-notice).

### API updates

Use the following table to understand the API updates made for Privacy Notice Management in this release:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/privaci/v1/admin/privacy_notices/import` | `POST` | We have added this API endpoint in the current release. It lets you import an existing privacy notice from a file. > [!NOTE] > Note > > This endpoint supports uploading one file per API request with a maximum file size of **5 MB**. |
| `/privaci/v1/admin/privacy_notices/{id}/archive` | `PATCH` | It lets you archive a privacy notice by passing its ID in the `id` path parameter. |
| `/privaci/v1/admin/privacy_notices/{id}/unarchive` | `PATCH` | It lets you unarchive a privacy notice by passing its ID in the `id` path parameter. |

For more information, see [Privacy Notice Management API reference](https://securiti-doc-router.securiti.ai/modules/privacy-notice-management/apidocs/index.html).

---

## 1.150

### Release updates - August 2026

No updates

---

## 1.149

### Release updates - August 2026

#### Introducing Custom Metadata for privacy notices and templates

Securiti has introduced **Custom Metadata** to enhance privacy notice and template management in its Privacy Notice Management module. Custom Metadata lets you add structured, customizable information to privacy notices and templates to capture business-specific information, making it more convenient for you to organize, manage, search, and govern them.

With Custom Metadata, you can:

- Create custom metadata with the following configurable data types:

| Data type | Usage |
| --- | --- |
| Text | Enter short, business-specific information. |
| Paragraph | Add longer, detailed information or notes. |
| Select | Define one or multiple values from a list. |
| Attachment | Upload a supporting file. |
- Mark custom metadata as **required** to ensure that you provide a value before you publish a privacy notice.
- **Enable Auto-Assign** to automatically apply selected custom metadata to all new privacy notices and templates.
- Filter custom metadata by **Organization**, **Owner**, **Data Type**, **Requirement**, and **Auto-Assign** status.
- Edit custom metadata values.

> [!NOTE]
> Note
> 
> Securiti does not let you change the data type of custom metadata after you create it. You can only change its value.
- View all custom metadata and its details, including the metadata name, organization, owner, data type, value, required status, and auto-assign status, as shown below.

![Custom metadata management interface showing options to assign and delete items.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/custom_metadata_rn_1.png)

You can apply custom metadata to your privacy notices and templates in the following ways:

- Apply custom metadata in bulk to one or more privacy notices or templates directly from the **Privacy Notices** or **Templates** dashboard using the **Apply Custom Metadata** option, as shown below.

![Privacy Notice Dashboard displaying draft notices and options for editing and publishing.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/custom_metadata_rn_2.png)

> [!NOTE]
> Note
> 
> You can search for and add existing custom metadata, specify default values, or update custom metadata values directly from the **Apply Custom Metadata** popup in privacy notices or templates, as shown below.
> 
> ![Applying custom metadata fields for privacy notices in a dashboard interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/custom_metadata_rn_4.png)
- Apply custom metadata to an individual privacy notice or template from the **More** menu in the notice or template editor, as shown below.

![Privacy notice document outlining information collection, usage, and data sharing policies.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/custom_metadata_rn_3.png)

You can use the top-level filter on the Privacy Notices or Templates dashboards to search for and conveniently manage privacy notices and templates based on their custom metadata, as shown below.

![Privacy Notice Dashboard displaying filters, custom metadata options, and draft status details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/custom_metadata_rn_5(1).png)

For more information, see [Understanding Custom Metadata](https://helpcenter.securiti.ai/docs/understanding-custom-metadata).

#### Enhanced privacy notice imports with language selection

Securiti now lets you select a language when creating privacy notices using the **Import From File** method. This lets you select the default language before processing the file, so you can create notices in the intended language.

After uploading the file, you can select the language from the **Languages** menu, as shown below.

![Upload documents to generate privacy notices with file format and size specifications.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/default_language(1).png)

For more information, see [Creating a privacy notice using PDF, DOCX, or TXT files](https://helpcenter.securiti.ai/docs/creating-a-privacy-notice-using-pdf-docx-or-txt-files) and [Managing language translations for privacy notices](https://helpcenter.securiti.ai/docs/managing-language-translations-for-privacy-notices).

#### API Updates

Use the following table to understand the API updates made for Privacy Notice Management in this release:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/privaci/v1/admin/custom_metadata` | `POST` | We have added this new API endpoint in the current release. It lets you create custom metadata fields with data types such as `TEXT`, `PARAGRAPH`, `SELECT`, and `ATTACHMENT`. |
| `/reporting/v1/stored_queries/execute` | `POST` | It lets you fetch all custom metadata. |
| `/privaci/v1/admin/custom_metadata/:id` | `GET` | It lets you fetch custom metadata by custom metadata ID. |
| `/privaci/v1/admin/custom_metadata/:id` | `PATCH` | It lets you edit custom metadata. |
| `/privaci/v1/admin/privacy_notices/:notice_id/custom_metadata/link` | `POST` | It lets you link custom metadata to a specific privacy notice. |
| `/privaci/v1/admin/privacy_notices/:template_id/custom_metadata/link` | `POST` | It lets you link custom metadata to a specific privacy notice template. |
| `/privaci/v1/admin/custom_metadata/bulk_delete` | `POST` | It lets you delete multiple custom metadata in a single request. |
| `/privaci/v1/admin/custom_metadata/bulk_auto_assign` | `POST` | It lets you enable auto-assign for custom metadata on all new privacy notices or templates. |
| `/privaci/v1/admin/custom_metadata/bulk_assign` | `POST` | It lets you apply custom metadata to multiple privacy notices or templates in a single API request. |

For more information, see [Privacy Notice Management API reference](https://securiti-doc-router.securiti.ai/modules/privacy-notice-management/apidocs/index.html).

---

## 1.148

### Release updates - July 2026

#### API updates

Use the following table to understand the API updates made for Privacy Notice Management in this release:

| Endpoint | Method | **What’s changed** |
| --- | --- | --- |
| `/privaci/v1/admin/privacy_notices/list` | `GET` | We have added this API endpoint in the current release. It lets you retrieve a paginated list of your organization's privacy notices with support for the following query parameters: - `org_unit_id` : Filters privacy notices by one or more organization IDs. To specify multiple organization IDs, include the `org_unit_id` query parameter for each ID, using the `&amp;` operator, for instance, `org_unit_id=1&amp;org_unit_id=2`. - `limit` : Returns the specified number of privacy notices per page. - `p` : Returns privacy notices from the specified page number. |

For more information, see [Privacy Notice Management API reference](https://securiti-doc-router.securiti.ai/modules/privacy-notice-management/apidocs/index.html).

---

## 1.147

### Release updates - June 2026

No updates
