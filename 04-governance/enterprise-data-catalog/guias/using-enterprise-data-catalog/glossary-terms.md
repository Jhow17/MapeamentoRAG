---
title: "Glossary terms"
slug: "glossary-terms"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/glossary-terms"
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Glossary terms

**Scenario**

As a data steward, you are responsible for ensuring clarity and consistency in how data is understood across teams. Without standardized definitions, teams often interpret key terms differently, leading to confusion and poor data quality. With EDC’s business glossary, you can define and relate terms to datasets, promoting data literacy and enabling consistent understanding across your organization.

Glossary term is a special vocabulary used to describe the datasets and the hierarchy within the dataset.

To work with the business glossaries and nodes, you must have the platform privilege called **Manage Glossary Nodes** and **Manage Glossary Terms.** For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

![Glossary_Main_Page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4367406b-13a0-713e-4567-6a01c3945430.png)

**Best practice**: If you are registering data assets via discovery scan, then make sure you have created glossary terms ahead of configuring the discovery scan. By doing this, you can have assets in the Enterprise Data Catalog already assigned to the correct domain and owner.

> [!NOTE]
> Note
> 
> You can view unique paths for each glossary term and term group in the sidebar search results. This lets you view the full hierarchy (for example, Glossary / ISO20022 / Product / Goods) and more easily identify the correct term when multiple terms have similar names.

To create a glossary term or a term group:

1. Open **Enterprise Data Catalog**, then choose **Glossary Terms**.
2. On the upper side of the page, click **+ Add Term**.

> [!NOTE]
> **Important**
> 
> - It is recommended to create glossary terms within the same term group using unique names. Unique names ensure that each term clearly represents a distinct concept or entity, reducing ambiguity and enhancing clarity.
> - Using identical names for multiple glossary terms within the same group can cause confusion, making it difficult to determine the correct term to reference. This can result in inconsistent terminology usage across the organization.
> - Securiti validates glossary node names upon creation to ensure each node has a unique name. If you attempt to create a glossary node with a name that already exists, Securiti displays an error message indicating that the name must be unique.

> [!NOTE]
> **Note**
> 
> To create a term group:
> 
> - On the upper side of the page, click **+ Add Term Group**.
3. For the creation of a glossary term, on the **Create Glossary Term** popup, enter the following details:

> [!NOTE]
> **Note**
> 
> The steps mentioned above are the same for creating a term group.
  - **Name** of the glossary term
  - **Parent** of the glossary term (term group). It is an optional field.
  - **SubType** of the glossary term. It is an optional field.

You can create subType aspect for glossary terms and term groups, similar to how datasets can be classified as tables or views. This lets you categorize glossary terms into distinct subTypes such as Policy, Regulation, or Content Profile, enabling structured and intuitive metadata classification.
  - **Documentation** that you can relate to the glossary term.
4. The glossary term has been successfully created. You can find it by entering its name in the glossary search bar at the top left of the page.

> [!NOTE]
> **Note**
> 
> You can also access your glossary from the dashboard.
> 
> - Open the Enterprise Data Catalog dashboard, at the top right of the page, click **Govern > Glossary**.
5. Click on a term to see the details.

![Glossary_Term_Detail_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-23dd7411-e5bb-917e-c948-5dec203b5bb5.png)

| Tab | Description |
| --- | --- |
| Documentation | The description of the term, and related links. |
| Related entities | The entities associated with the glossary term. |
| Related terms | The related terms including inherited terms. |
| Properties | The extracted properties of the term. |
| You can now create, edit, and delete custom properties for both manually created terms in the Enterprise Data Catalog as well as for system-level glossary terms such as data elements, content profiles, data dictionaries, and more. However, the following system-defined properties remain non-editable for system-level glossary terms: - Languages - Type - ​Locality - ​Content profile type - Number of keywords - Data dictionary type - Data element type - ​Identifiability - ​Non-personal sensitive data - Uniqueness - Data system type - ​Personal data To add a new property to the glossary term: 1. Open a glossary term, and click the **Properties** tab. 2. Click **+ Add New Property**. 3. On the **Add a new property** popup, enter a property name and value. 4. Click **Add**. To edit the property of the glossary term: 1. Click the **Edit** button. 2. On the **Edit a new property** popup, enter a property value. 3. Click **Save**. To delete a property of the glossary term: 1. Click the delete icon. 2. On the **Delete Property** popup, click **Delete**. |
| > [!NOTE] > **Important** > > When you delete a content profile from **Table Training**, the associated glossary term is also removed from the dataset in the EDC. This ensures that outdated or irrelevant terms do not persist after removal. > > In addition, glossary terms sourced from connectors or **Table Training** are marked with a non-editable flag. You cannot delete these terms from the dataset, and the system hides the **Remove** (×) option in the UI to prevent accidental deletion. However, glossary terms configured via the **Discovery Scan** under the **Responses** section for metadata ingestion are editable. > [!NOTE] > **Note** > > You can view and edit the custom content profile from the glossary term. Click **Definition** in the Properties tab of the glossary term which redirects you from the current glossary page to **Edit Custom Content Profile** page. |

### Relationships in the glossary data model

### 

The glossary data model lets you create various types of relationships between glossary terms and term groups. This enables you to create structured and meaningful connections. You can choose to:

- [Create system-defined relationships](/latest/docs/glossary-terms#create-systemdefined-relationships)
- [Create custom relationships](/latest/docs/glossary-terms#create-custom-relationships)

For system-defined relationships, the following are detailed explanations of each relationship type:

| Type of relationship | Description |
| --- | --- |
| Contains | A **Has A** relationship where a glossary term or term group includes other terms. It also applies when a term group includes or encompasses a glossary term. Example: - The glossary term **Customer Data** can contain terms like **Email Address**. - **Data Protection** term group contains **Encryption** term. |
| Inherits | An **Is A** relationship where a glossary term derives its meaning or attributes from another term. It also applies when a term group inherits characteristics or properties from a glossary term Example: - **Personal Identifiable Information (PII)** inherits from **Sensitive Data**. - **Privacy Framework** inherits from **Compliance Requirements**. |
| Contained by | The reverse of **Contains**. Identifies the glossary terms or term groups that a particular term belongs to. It also applies when a glossary term is part of a term group. Example: - The term **Email Address** is contained by **Customer Data**. - **Encryption** term is contained by **Data Protection** group. |
| Inherited by | The reverse of **Inherits**. Identifies the terms or term groups that derive from a specific term. Now also applies when a glossary term passes on its characteristics or properties to a term group. Example: - **Employee PII** is inherited by **HR Data**. - **Sensitive Data** term is inherited by **Risk Classification** group. |
| Utilized by | Defines how a term is used or applied in different contexts. Example: - The term ​**Encryption**​ is utilized by ​**Data Security**​​. |
| Associated with | Represents a general connection or linkage between terms. Example: ​ - **Customer Data**​ is associated with ​**Compliance Requirements**​​. |
| Type of | This relationship specifies that a term is a specific type of concept represented in a term group. Example: - **Structured Data** is a type of **Data Format**. |
| Has type | This is the reverse of **Type of**. It identifies the specific types or subcategories associated with a term. Example: - **Data Format** has types such as **Structured Data**. |

### Creating related terms and term groups

To create various types of relationships between glossary terms and term groups:

- Open **Enterprise Data Catalog** and choose **Glossary > Related Terms**.

#### Create system-defined relationships

To create a system-defined relationship with another glossary term:

1. On the **Related Terms** page, click **Actions > Add Glossary Term**.
2. On the **Add Terms** popup:
  1. Select one or more glossary terms.
  2. Choose the type of relationship you want to establish. Available relationship types include:
    - Contains
    - Inherits
    - Type of
3. Click **Add** to save the relationship.

To create a relationship with a term group:

1. On the **Related Terms** page, click **Actions > Add Term Group**.
2. On the **Add Term Group** popup:
  1. Select the desired term group or glossary term.
  2. Choose the type of relationship you want to establish. The available types are as follows:
    - Type Of
3. Click **Add** to save the relationship.

#### Create custom relationships

To create a custom relationship with other glossary terms/term groups, open **Enterprise Data Catalog** and choose **Glossary > Manage Relationships**:

1. On the **Manage Relationships** popup, on the upper right, click **Edit**. Securiti displays the **+ Add** button for:
  1. Glossary Terms to Glossary Terms relationship
  2. Glossary Terms to Glossary Nodes relationship
  3. Glossary Nodes to Glossary Nodes relationship
2. For the relevant relationship category, click **+ Add**.
3. To define the relationship:
  1. In the left field, define the forward relationship on the left. For example, **Does not contain**.
  2. In the right field, define the corresponding inverse (reciprocal) relationship. For example, **Is not contained by**.

> [!NOTE]
> Important
> 
> You can not use existing system-defined terminology for custom relationships.
4. To save the relationship, click **Save**.

> [!WARNING]
> Important
> 
> For custom relationships, ensure you have configured the [relevant permission](/latest/docs/glossary-terms#permissions-configuration-for-creating-custom-relationships): Manage Glossary Custom Relationship Types.

#### Permissions configuration for creating custom relationships

To work with custom relationships, you must have **Manage Glossary Custom Relationship Type** permission for your role. For more details, refer to [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

#### Viewing related terms and term groups

Once added, all related terms and term groups appear under the **Related Terms** tab. For each related entity, you can view:

- Name
- Owner
- Link to its related entities
- Type (whether it's a glossary term or a term group)
- Type of relationship

#### Removing a related term or term group

1. Click **Options (three dots**) at the end of the corresponding row.
2. On the confirmation popup, click **Delete**.

> [!NOTE]
> Note
> 
> You can remove any related glossary term or term group from a glossary term without restrictions. This applies to all relationship types, giving you complete flexibility when managing glossary relationships.

### Glossary terms URN

You can uniquely identify any glossary term in the Enterprise Data Catalog with a URN. URN stands for Uniform Resource Name. The sample URN is as follows:

- `urn:li:glossaryNode:70d3c062-a8de-40fc-91cc-bf3c8f16e716`
- `urn:li:glossaryTerm:1558a362-2dd0-47a3-af09-46e4ce80916b`

To copy glossary terms/nodes URNs:

1. Open the glossary term/node page.
2. At the right side of the page, click **Share > Copy URN**.

### Configuring glossary terms

You can configure the glossary terms by adding **documentation, unique owners, links,** and **domains** to group-related entities based on your organizational structure.

### Adding links to glossary terms

To add a link to the glossary term:

1. Open **Enterprise Data Catalog** and choose **Glossary > Add Link**. **Add Link** option is available under **About** and **Documentation** sections.

![adding_links_to_glossary_terms_-_A.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fbac3e8-a08f-2326-7aaa-c5fedeea66e8.png)
2. On the **Add Link** popup, add **URL** and **Label**.
3. Click **Add** to save the link to the glossary term.

![Add_links_to_glossary_terms_-_B.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-399bf1b6-d385-609f-7982-864d7895cefb.png)

If you click the **Cancel**, the **Add Link** popup disappears.

### Adding documentation to glossary terms

To add documentation to glossary term:

1. Open **Enterprise Data Catalog** and choose **Glossary** **> Add Documentation**. **Add Documentation** option is available under **About** and **Documentation** sections.

![Adding_documentation_to_glossary_terms_-_A.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2cdcec75-56a6-76dd-e333-3c82b29d575f.png)
2. Add the relevant documentation in the text editor and click **Save** to add documentation to the glossary term.

![Add_documentation_to_glossary_terms_-_B.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f28eb582-9e32-d096-f892-f7cdb81151af.png)

If you click the **Cancel**, **Discard Changes** popup opens, where you can discard your added documentation.

> [!NOTE]
> **Note**
> 
> Securiti also lets you add the documentation of the glossary term simultaneously while creating a new glossary term.
> 
> ![Add_documentation_while_creating_glossary_terms.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b113f0f8-8e9a-c01e-1092-71cad571530f.png)
> 
> You can add documentation to the term group just as easily as you can for a glossary term.

### Adding owners to glossary terms

To add owners to the glossary term:

1. Open **Enterprise Data Catalog** and choose **Glossary > Add Owners**.

![add_owners_to_glossry_terms_-_A.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c88fe7a6-5cf6-cd9a-330f-77516e0fe0b5.png)
2. On the **Add Owners** popup, select the owner from the **Owner** menu, owner type from the **Type** menu. Click **Done** to add the selected owner to the glossary term. You can view the user's email address alongside their name when you hover over the user badge.

![add_owners_to_glossary_terms_-_B.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b068d130-f14e-cf0e-0756-df0516dbba94.png)

If you click the **Cancel**, the **Add Owners** popup disappears.

> [!NOTE]
> **Note**
> 
> You can link owners to the term group just as easily as you can for a glossary term.

### Adding domains to glossary terms

To set domain to glossary term:

1. Open **Enterprise Data Catalog** and choose **Glossary > Set Domain**.

![Set_domain_to_glossary_terms_-_A.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-37f45679-053e-43c7-3a66-987eb6760cfa.png)
2. On the **Set Domain** popup, select the suitable domain from the menu.
3. On the **Set Domain** popup, select the suitable domain from the menu and click **Add** to link the domain to the glossary term.

![Set_domain_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e4e21662-b3d8-5a98-72b2-7e708e5c444c.png)

> [!NOTE]
> **Note**
> 
> You can set the domain to the term group just as easily as you can for a glossary term.

### Cloning glossary terms

You can clone glossary terms to make it easier to frequently add similar terms to the glossary, when needed. This functionality enhances efficiency by allowing you to duplicate existing glossary terms instead of creating them from scratch.

To clone a glossary term:

1. Open the term you want to clone.
2. Click on the **Options (three dots) > Clone** located to the right of the **Share** button.
3. On the **Clone Glossary Term** popup, configure the following details:
  - Enter the name of the cloned glossary term. By default, the name is shown as <original term name>_copy.
  - Select the parent for the glossary term. By default, the current parent is pre-populated.
  - Mark the aspects that you want to include in the cloned glossary term. You can clone the following aspects:
    - Documentation
    - Related entities
    - Related terms
      - **Type Of** glossary terms and term groups also get cloned.
    - Properties
    - Owners
    - Domain
    - Governance flags
    - Governance status

### Marking glossary nodes and glossary terms as read only

You can mark glossary terms, and glossary nodes as read-only. To do so:

1. Open any term group. or glossary term.
2. From the entity's details page, click **Options** (three dots) > **Mark as read only**.

Once marked as read-only, none of the entity's attributes can be edited, helping you maintain data integrity and ensure consistent governance across your data catalog.

To make a read-only entity editable again:

1. From the entity's details page, click **Options** (three dots) > **Mark as Editable**.

> [!NOTE]
> Note
> 
> - To use this feature, your role requires the **Edit Glossary Node Read Only Status** and **Edit Glossary Term Read Only Status** permission. This permission controls write access to glossary nodes and terms information by determining whether a role can mark glossary nodes and terms as read-only or editable. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).
> - Read-only status is not inherited. If you mark a term group as read-only, the glossary terms within that group are not automatically marked as read-only. You must mark each term individually.

### Deleting a glossary node or glossary term

To delete a glossary node or a glossary term:

1. Open any glossary term/glossary node.
2. Click **Options** (three dots) > **Delete**.
3. On the confirmation popup, click **Delete** to permanently delete the node or term.

> [!NOTE]
> Note
> 
> - Deleting a glossary node permanently deletes all child glossary terms and glossary nodes nested beneath it at every level. This action cannot be undone.
> - A glossary term attached to a read-only asset cannot be deleted.

### Bulk load capabilities for glossaries

You can efficiently bulk load assets into the Enterprise Data Catalog to create new glossaries or update existing ones.

One way to achieve this is by creating YAML or JSON files with the required content and ingesting them using the CLI. However, this method requires technical expertise to ensure proper formatting and syntax compliance with YAML or JSON, making it less user-friendly.

A more accessible approach is to provide you with CSV or XLSX templates that they can populate with new entities or updates.

While CSV-based bulk creation is an option, it comes with limitations—it only supports glossaries with basic aspects such as domains, owners, and properties. In contrast, the enhanced bulk creation process using an XLSX file offers greater flexibility. If a glossary term does not exist, you can create it and associate it with multiple aspects, including domains, properties, governance flags, statuses, related terms, related entities, and owners. Additionally, existing aspects can be updated with new entries provided in the XLSX file.

The following sections provide a detailed explanation of bulk loading glossaries using both CSV and Excel formats.

> [!NOTE]
> **Note**
> 
> You must configure private cloud storage for successfully loading glossaries in bulk into EDC.

#### Scope

- You can upload a CSV file with a maximum of 5MB size.
- You can upload an XLSX file of any size.
- Bulk load capability does minimum file checks on the file format, number of columns, rows and before starting the ingestion job.

#### Creating and updating glossaries using a CSV file

To upload glossary in bulk:

1. In Securiti, open **Enterprise Data Catalog > Dashboard > Glossary Terms**.
2. On the root glossary page, at the middle right corner of the page, click **+ Bulk Load**.

> [!NOTE]
> **Note**
> 
> You can also bulk load glossaries in the term groups.
> 
> 1. Open any term group.
> 2. Click **Options** (three dots) > **+ Bulk Import**.
3. On the **Bulk Import Glossary Term** popup, choose the CSV file to import.

> [!NOTE]
> **Note**
> 
> When you upload a CSV file, you receive notifications about the import process's status (started, failed, completed) in both the **audit trail** and the **messages & notifications** section. If a process is in the started state, you cannot initiate another process simultaneously.
> 
> However, If you upload an incorrect CSV file, you receive a notification in the **audit trail** and the **messages & notifications** section. In that case, you must upload the correct CSV again.

If there is an error in the file, the CSV file verification fails. In that case:

> [!NOTE]
> **Note**
> 
> For a smooth upload, make sure your CSV file follows a specific format. If it doesn't, you might face issues uploading it. To make sure everything works well, download the CSV template from the UI and use it as a guide for how to set up your file.

The acceptable CSV template contains the following columns:

| Column | Required? | Description |
| --- | --- | --- |
| Name | Yes | Provide the name of the glossary term. |
| Description | Yes | Provide the description of the glossary term. |
| OwnersUsers | No | Provide a list of user IDs.Example: workerowner |
| OwnersGroups | No | Present a list of group IDs.Example: workergroup |
| TermSource | Yes | Set it to EXTERNAL or INTERNAL to specify whether the term is coming from an external glossary or one defined in your organization. |
| SourceRef | No | Provide the name of the source from where the glossary term is coming. |
| SourceURI | No | Provide the external source URI if the TermSource is set as External. Example: [www.securiti.ai](/v1/docs/securiti-pods-and-elastic-pods) |
| Inherits | No | Provide a comma delimited list of GlossaryTerm that this term inherits from (use dots to prefix parent nodes). Example: Privacy.PII |
| Contains | No | Provide a comma delimited list of GlossaryTerm that this term contains (use dots to prefix parent nodes). Example: Shipping.CountryCode,Shipping.StreetAddress |
| CustomProperties | No | Provide a map of key/value pairs of arbitrary custom properties. You need to quote the content of the field this way: "prop1:value1,prop2:value2" Example: "contains_PII: true,system: false" |
| KnowledgeLinks | No | Provide a list of KnowledgeCard related to this term. These appear as links on the glossary node's page. Example: [{ “url”: "https://en.wikipedia.org/wiki/Address",”label”: “Wiki link”}] |
| Domain | No | Provide a domain name or domain URN. Domain URN example: urn:li:domain:Logistics |
  1. Click **View Error Log** to view list of error logs.
  2. Click **Retry** to again upload the right file.
4. Once the file gets uploaded successfully, configure the following settings:

| Setting | Description |
| --- | --- |
| Enable auto ID | Enable this option. This enables EDC to automatically generate GUIDs from the provided term names. |
| Version | This value is set to 1. It is the version of the business glossary file. |
| Users | From the **Users** menu, select users to make them glossary owners. The **Users** menu, shows you the list of ID's associated with the Enterprise Data Catalog users. > [!NOTE] > Note > > The ​**Users​​** menu displays only active users and does not include guest users or deactivated users. |
| External URL | Provide the URL that links to an external source where the glossary is defined. Example URL: https://example.com |
5. Click **Import**.

The import process may take a few minutes. Once it gets imported, you can view your glossary terms on the root glossary page or in the term group where you initiated the import process.

> [!NOTE]
> **Note**
> 
> You can monitor import progress on the EDC Ingestion page.
> 
> 1. Open **EDC** **Ingestion** page.
> 2. Under the Sources tab, you can monitor the progress details. See Performing actions on ingestion sources section to get to know what options you can perform on the ingestion.

![EDC_-_BBUlk_glossary_-_EDC_ingestion_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-38667f94-4f88-beab-5e2e-f9a1c2ceb0e2.png)
6. click on the imported glossaries to perform the intended actions.

> [!NOTE]
> **Note**
> 
> You can perform all actions on imported glossaries as you would on glossaries created via the Enterprise Data Catalog UI.

#### Creating and updating glossaries using an Excel file

To upload the glossary in bulk:

1. In Securiti, open **Enterprise Data Catalog > Dashboard > Glossary Terms**.
2. On the root glossary page, at the middle right corner of the page, click **+ Bulk Load**.

> [!NOTE]
> **Note**
> 
> You can also bulk-load glossaries in the term groups.
> 
> 1. Open any term group.
> 2. Click **Options (three dots) > + Bulk Import**.

- On the **Bulk Import Glossary Term** popup, choose the .xlsx file to import.

> [!NOTE]
> **Note**
> 
> For a smooth upload, make sure your .xlsx file follows a specific format. If it does not, you might face issues uploading it. To make sure everything works well, download the sample excel template from the UI and use it as a guide for how to set up your file and read the instructions carefully.
> 
> - On the bottom left of the file import section, click **Download Sample Excel** to download the sample excel file.
- Click **Import**.

> [!NOTE]
> **Note**
> 
> If there is an error in the file, the XLSX file validation fails. In that case:
> 
> - Click **View Error Log** to view a list of error logs.
> - Click **Retry** to upload the right file again.

Once the import is completed, you can open the glossary terms that you added in the .xlsx file to see the updated metadata.

- You can view the audit trails of the glossary terms bulk import activities in the [Audit logs](/v1/docs/securiti-platform-viewing-the-securiti-audit-log) section.
- You can also view the glossary terms bulk import activities in the [Messages & Notifications](/latest/docs/securiti-platform-using-the-securiti-messages-notifications-panel) section.

> [!NOTE]
> **Note**
> 
> When you upload an excel file, you receive notifications about the import process's status (started, failed, completed) in both the audit trail and the messages & notifications section. If a process is in the started state, you cannot initiate another process simultaneously.
- Securiti generates a log file whenever you bulk import glossaries using an Excel file. See [log files](/v1/docs/glossary-terms) for more details.

#### Instructions for importing metadata using an Excel file

> [!NOTE]
> **Note**
> 
> If any mandatory field in any tab is missing, or if any column contains an incorrect format, the corresponding glossary term cannot be created or updated. Therefore, ensure the Excel sheet is populated carefully.

#### Glossary term

To add a new glossary term, fill out the glossary term tab, which includes the following columns:

> [!NOTE]
> **Note**
> 
> To successfully create a new glossary term, the **Glossary URN**, **Parent Node URN**, and **Glossary Term Name** fields are mandatory. However, if you are creating a glossary term at the root level, the **Parent Node URN** field must be left empty. The other two fields remain mandatory regardless.

| Column | Required? | Description |
| --- | --- | --- |
| Glossary URN | No | - Add the URN for the glossary term. This column can be left empty. If left blank, the system automatically generates a Glossary Term URN using a random UUID, based on the provided Glossary Term Name and Parent Node URN, which are the only required fields. However, if you choose to enter a Glossary Term URN manually, follow the formatting guidelines below. Incorrect formatting will cause the bulk upload process to fail. The generic format is as follows: **urn:li:glossaryTerm:d6a2140d-fb53-406f-b820-9cf2d647615a** \| urn:li:glossaryTerm \| This is the **constant component** consisting of urn (This is the prefix indicating that the string is a URN), li (This is a namespace identifier), and glossary term (This specifies the type of resource being identified). \| \| --- \| --- \| \| d6a2140d-fb53-406f-b820-9cf2d64761 \| This is a UUID (Universally Unique Identifier). It provides a globally unique identifier for the specific glossary term within the system. You **must update** this component every time you create a new glossary term. This can also be a string as mentioned in the example below. \| - You can also create a glossary term with a folder structure: **Example**: urn:li:glossaryTerm:Data Classification.Classification Categories.Government Data Classification.Clearance > [!NOTE] > **Note** > > - If you later change the **Glossary Term Name**, this URN will not change. > - There are a few restrictions when creating an URN. Column names are encoded if they contain any of the following reserved characters. To prevent this, it is advisable to avoid using these characters. > - Commas "," are reserved characters in URN fields. > - Parentheses "( , )" are reserved characters in URN fields. > > **Example**: **urn:li:dashboard:(looker,dashboards.thelook)** is a valid urn, but **urn:li:dashboard:(looker,dashboards.the, look)** is invalid. |
| urn:li:glossaryTerm | This is the **constant component** consisting of urn (This is the prefix indicating that the string is a URN), li (This is a namespace identifier), and glossary term (This specifies the type of resource being identified). |
| d6a2140d-fb53-406f-b820-9cf2d64761 | This is a UUID (Universally Unique Identifier). It provides a globally unique identifier for the specific glossary term within the system. You **must update** this component every time you create a new glossary term. This can also be a string as mentioned in the example below. |
| Parent Path | No | - Add the parent path for the glossary term. **Example**: Glossary > Data Classification > Classification Categories > Government Data Classification. - **Glossary**: This is the top-level container. It represents the overall collection of terms or the root of the hierarchy. - **Data Classification**: This is a primary category under the glossary, grouping terms related to how data is classified. - **Classification Categories**: This is a sub-category within Data Classification, further organizing terms into specific classification types. - **Government Data Classification**: This is the specific glossary term. It is nested under Classification Categories, meaning it is a detailed instance or example of a classification category related to government data. |
| Parent Node URN | Yes | - Add the URN for the parent node. Read these [instructions](/v1/docs/glossary-terms) to copy the URN **Example:** urn:li:glossaryNode:Data Classification.Content Profiles |
| Subtype | No | - Add the subtype for the glossary term. **Glossary term: Regulatory Compliance** Example subtypes: - **Policy**: Company policies related to data governance, security, and compliance. - **Regulation**: External regulations such as GDPR, CCPA, or HIPAA. - **Standard**: Industry standards like ISO 27001, NIST, or PCI DSS. |
| Glossary Term Name | Yes | - Add the name for the glossary term. **Example:** Clearance |
| Description | No | - Add the description of the glossary term. **Example:** Clearance is a general classification, that comprises a variety of rules controlling the level of permission required to view some classified information, and how it must be stored, transmitted, and destroyed. Additionally, access is restricted on a "need to know" basis. Simply possessing a clearance does not automatically authorize the individual to view all material classified at that level or below that level. The individual must present a legitimate "need to know" in addition to the proper level of clearance. |
| Domain URN | Yes | - Add the URN for the domain if you want to link the newly created term to a domain. **Example:** urn:li:domain:5c3de873-c9aa-4c9c-98d2-0a71c45e7ecc |
| Domain Name | No | - Enter the domain name. **Example:** Clearance |
| Governance Status | No | - Set the governance status for the glossary term. This is an enum field and only accepts certain values. For details, refer to [governance statuses](/v1/docs/governance-status-for-edc-entities). **Example:** Draft |
| PII Flag | No | - Set the PII flag to either true or false. **Example:** True |
| CDE Flag | No | - Set the CDE flag to either true or false. **Example:** False |

To update the existing glossary, you must:

- Enter the correct **Glossary URN**. Read the [instructions](/v1/docs/glossary-terms) to copy the exact URN. The other fields are dependent upon your use case.

#### Glossary term properties

To add and update properties to the glossary, fill out the glossary term properties tab, which includes the following columns:

| Column | Required? | Description |
| --- | --- | --- |
| Glossary URN | Yes | - Enter the URN of the glossary term you want to add properties to. You can use one of the new URNs from the previous Glossary Term tab or an existing Glossary Term. The Glossary URN column is mandatory. Note that the properties you add here will replace the existing ones. |
| Parent Path | No | - Add the parent path for the glossary term. |
| Glossary Term Name | No | - Add the name for the glossary term. |
| Property Name | Yes | - Enter the property name. **Example:** version number |
| Property Value | Yes | - Enter the property value. **Example:** 2.0 |

> [!NOTE]
> **Note**
> 
> To add multiple properties to a single glossary term, create a separate row for each property while using the same **Glossary URN**.

#### Standard properties

To add and update the standard properties of the glossary terms, fill out the standard properties tab, which includes the following columns:

| Column | Required? | Description |
| --- | --- | --- |
| Glossary URN | Yes | - Enter the URN of the glossary term. You can use one of the new URNs from the previous Glossary Term tab or of an existing Glossary Term. To get the right URN, see these [instructions](/v1/docs/glossary-terms). |
| Parent Path | No | - Add the parent path for the glossary term. |
| Glossary Name | No | - Add the name for the glossary term. |
| Property URN | Yes | - Enter the standard property URN. **Example**: urn:li:structuredProperty:54a6a00b-bdf7-4ba8-9f00-8b93d180bc2d \| urn:li:structuredProperty: \| This is the constant component consisting of urn (This is the prefix indicating that the string is a URN), li (This is a namespace identifier), and structuredProperty (This specifies the type of resource being identified). \| \| --- \| --- \| \| 54a6a00b-bdf7-4ba8-9f00-8b93d180bc2d \| A randomly generated UUID, assigned to this specific standard property. \| |
| urn:li:structuredProperty: | This is the constant component consisting of urn (This is the prefix indicating that the string is a URN), li (This is a namespace identifier), and structuredProperty (This specifies the type of resource being identified). |
| 54a6a00b-bdf7-4ba8-9f00-8b93d180bc2d | A randomly generated UUID, assigned to this specific standard property. |
| Property Name | No | - Enter the standard property name. **Example**: Created Time |
| Property Cardinality | Yes | - Set the cardinality for the standard property as either SINGLE or MULTIPLE. Cardinality is the number of values that can be assigned to a specific standard property. - **Single Cardinality** - Assigns only one value of the standard property to an entity. - **Multiple Cardinality** - Assigns multiple values of the standard property to an entity. |
| Property Value Type | Yes | - Enter the value type of the standard property. The value type specifies the format of data that can be assigned to a property, such as Number, Date, String, or URN. **Example**: STRING |
| Property Value | Yes | - Enter the standard property value. It refers to the specific data assigned to a property based on its value type. **Example**: 2021-01-15 |

#### Glossary term ownership

To add and update ownership to the glossary term, fill out the glossary term ownership tab, which includes the following columns:

| Column | Required? | Description |
| --- | --- | --- |
| Glossary URN | Yes | - Enter the URN of the glossary term. You can use one of the new URNs from the previous Glossary Term tab or of an existing Glossary Term. To get the right URN, see these [instructions](/v1/docs/glossary-terms). |
| Parent Path | No | - Add the parent path for the glossary term. |
| Glossary Term Name | No | - Add the name for the glossary term. |
| Owner Email | Yes | - Enter the owner's email address. The ownership details for the glossary term will be updated only if the email address is valid. **Example:** JohnDoe@securiti.net |
| Ownership Type URN | Yes | - Add the URN for the ownership type. To get the right URN, see these [instructions](/latest/docs/edcownership). **Example:** urn:li:ownershipType:a5a2091e-f2bb-45d8-9744-08992283a3b0 |
| Ownership Type Name | No | - Enter the ownership type name. **Example:** Admin |

> [!NOTE]
> **Note**
> 
> - If you want to add a custom ownership type, then the **Ownership Type URN** field and the **Owner** columns are mandatory where you have to add the ownership type urn and the owner email, respectively.
> - If you want to add a legacy ownership type, add any one of the following options in the **Ownership Type Name** column:
> 
> In this case, both the **Ownership Type Name** and **Owner** columns are mandatory. You must enter the correct names and emails for the action to be successful.
>   - TECHNICAL_OWNER
>   - BUSINESS_OWNER
>   - DATA_STEWARD
>   - NONE
> - To add multiple ownership types to a single glossary term, create a separate row for each ownership type while using the same **Glossary URN**.

Glossary term related entities

To add and update the related entities of the glossary terms, fill out the glossary term related entities tab, which includes the following columns:

| Column | Required? | Description |
| --- | --- | --- |
| Glossary URN | Yes | - Enter the URN of the glossary term. You can use one of the new URNs from the previous Glossary Term tab or of an existing Glossary Term. |
| Parent Path | No | - Add the parent path for the glossary term. |
| Glossary Term Name | No | - Add the name for the glossary term. |
| Entity URn | Yes | - Add the URN for the entity. If the entity is a dataset, then follow these [instructions](/v1/docs/datasets) to copy the dataset URN. **Example:** urn:li:dataset:(urn:li:dataPlatform:snowflake,snowflake-39.SECURITI_DATA_ACCESS_GOVERNESS.SECURITI_USER_GROUP,PROD) |
| Entity Type | No | - Add the type of the entity. **Example:** Dataset |
| Entity Subtype | No | - Add the subtype of the entity. **Example:** Table |
| Entity Name | No | - Add the name of the entity. **Example:** SECURITI_USER_GROUP |

> [!NOTE]
> **Note**
> 
> To successfully add related entities for the glossary term, **Glossary URN** and **Entity** **URN** are mandatory fields.
> 
> To add multiple related entities to a single glossary term, create a separate row for each related entity while using the same Glossary URN.

#### Glossary term related terms

To add and update the related terms of the glossary terms, fill out the glossary term related terms tab, which includes the following columns:

| Column | Required? | Description |
| --- | --- | --- |
| Glossary URN | Yes | - Enter the URN of the glossary term. You can use one of the new URNs from the previous Glossary Term tab or of an existing Glossary Term. |
| Parent Path | No | - Add the parent path for the glossary term. |
| Glossary Term Name | No | - Add the name for the glossary term. |
| Relationship | Yes | - Specify the type of relationship, either **Contains**, **Inherits**, **Type Of**, **​Associated with​​**, and **​Utilized by​​.** |
| Term URN | Yes | - Enter the URN of the glossary term you want to establish a relationship with. **Example:** urn:li:glossaryTerm:Data Classification.Data Elements.CONTACT.CONTACT_PHONE |
| Term Name | No | - Add the name of the term. **Example:** Phone Number |

> [!NOTE]
> **Note**
> 
> To successfully link related terms to the glossary term, you must add valid values for **Glossary URN**, **Relationship**, and **Term URN**.
> 
> To add multiple related terms to a single glossary term, create a separate row for each related term while using the same Glossary URN.

#### Glossary term related nodes

To add and update the related nodes of the glossary terms, fill out the glossary term related nodes tab, which includes the following columns:

| Column | Required? | Description |
| --- | --- | --- |
| Glossary URN | Yes | - Enter the URN of the glossary term. You can use one of the new URNs from the previous Glossary Term tab or of an existing Glossary Term. |
| Parent Path | No | - Add the parent path for the glossary term. |
| Glossary Term Name | No | - Add the name for the glossary term. |
| Relationship | Yes | - Specify the type of relationship. The only allowed relationship is **Type Of**. |
| Node URN | Yes | - Specify the URN of the glossary term node (term group). **Example:** urn:li:glossaryNode:Data Classification.Data Elements.CONTACT |
| Node Name | No | - Specify the name of the node (term group). **Example:** Contact Info |

> [!NOTE]
> **Note**
> 
> To successfully add related nodes for the glossary term, **Glossary URN**, **Relationship**, and **Node URN** are mandatory fields.

#### Sample data

The sample data tab provides example entries for each section to help you understand the correct format. It includes sample data for every tab in the template, letting you reference the examples when populating your sheet.

#### Log files for monitoring the glossary bulk load activities

Securiti generates a log file whenever you bulk import glossaries using an Excel file. This log file provides a detailed overview of the process, including the number of new entries created and any failures encountered during the bulk upload.

To access the log file:

1. Open the **Messages & Notifications** section, where you will receive two messages—one indicating that the bulk upload has started and another confirming its completion. The completion message includes details on any failed rows along with the log file name.
2. Copy the log file name from this message.
3. Click your avatar at the bottom of the left navigation bar and select **My Downloads**.
4. Use the copied log file name to search for the file, then download and open it to review the log details.

The log file typically provides a summary of the bulk import process, highlighting both successful entries and failures.

![Log_files_-_glossary_terms.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5f492455-9879-f759-397d-022fdd4c6eaf.png)

The log file provides a detailed report of the bulk import process across various glossary-related entities. It outlines the success count, data failures, and specific reasons for each failure, helping users debug import issues efficiently.

### Exporting glossary term aspects

You can export glossaries including schema metadata and and various detailed attributes. This capability ensures that the exported data is more useful and actionable for analysis, reporting, or further processing.

The glossary aspects that you can export are listed below.

| Aspects |
| --- |
| Glossary term | - Glossary URN - Parent path - Glossary term name - Description - Domain URN - Domain name - Governance status - PII flag - CDE flag |
| Glossary term ownership | - Glossary URN - Parent path - Glossary name - Owner - Ownership type URN - Ownership type name |
| Glossary term properties | - Glossary URN - Parent path - Glossary name - Property name - Property value |
| Glossary term related entities | - Glossary URN - Parent path - Glossary name - Entity URN - Entity type (for example, dataset, container, data product) - Entity subtype (for example, table, view, schema, database) - Entity name |
| Glossary term related terms | - Glossary URN - Parent path - Glossary name - Relationship - Term URN |

To export glossary term aspects:

1. Open the glossary term page and select the term group/glossary terms you want to export by marking the checkboxes.
2. Click **Export** from the popup menu that appears at the bottom of the page.

> [!NOTE]
> **Note**
> 
> - The export option is also available under the **Actions** button, located on the top right side of the page.
> - The export action honors your [RBAC permissions](/latest/docs/edc-rbac-permissions-and-roles). It includes only the entities you have permission to view. Entities you do not have access to are automatically excluded from the export.

- If the export results contain fewer than 1000 records, the file will start downloading. Once the download is complete, you can view the .xlxs file on your local device.
- When your search results exceed 1000 records, you will receive a message on the screen that says, “Export Started, Once file is ready, we'll email you the link”.
- Check your registered email address for a message containing the requested .xlxs file as an attachment.

### Audit trail for glossary terms and **glossary nodes**

You can view comprehensive insights about how a glossary term or glossary node has changed over time. This can help you make informed decisions and better manage your assets.

To view the audit trail:

1. Open Enterprise Data Catalog, then land on the **Glossary** page.
2. Open any glossary term or glossary node for which you want to see an audit trail.
3. On the upper right corner of the page, click **Change Log** to view the following audit trail details:

| Value | Description |
| --- | --- |
| Time | The time when each change occurred. |
| User | Name of the user responsible for the change. |
| Activity | Nature of the modification (for example, add, edit, delete). |
| Attribute | Specific aspects of the asset that changed. |
| New value | Updated information. |
| Old value | Previous state for a complete historical perspective. |
| Message | Additional context through accompanying messages. |

### Searching data classification in glossary terms

To search data classification in a glossary term:

1. In Securiti, open **Enterprise Data Catalog**, then choose **Glossary Terms**.
2. On the right corner of the page, click **Data Classification** term group.
3. Under the **Contents** tab of the **Data Classification** term group, you can see the following metadata:
  - Classification categories
  - Content profiles
  - Data dictionary
  - Data elements

![Data_classification_-_meta_data_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c21e502e-d847-20e2-f229-662f42f72cf6.png)
4. Click on any metadata to understand them by reading their definitions and see how they relate to other glossary entries.

![EDC_-_Content_profiles_task_ss_update.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-73396def-682e-07e5-9fe1-8ff579f597fc.png)

#### PII flags for data elements classified as glossary terms

Securiti automatically assigns PII flags to data elements classified as glossary terms in the EDC based on their status as personal data.

View PII flags:

1. Open **Enterprise Data Catalog**, then choose **Glossary Terms**.
2. On the right corner of the page, click Data Classification term group.
3. Under the **Contents** tab of the data classification, choose **Data Elements**.
4. Open the data element containing personal data to view the PII flag.

## FAQs

#### Is the glossary meant for business users to search existing data products and define new terms when releasing new data products?

Yes, the Enterprise Data Catalog module's glossary is designed for business users. It lets you search for information about existing data products, allowing easy access to details about the data. Additionally, it lets you define new terms, which is helpful when introducing or releasing new data products. In simple words, the glossary helps business users find information on current data products and create explanations for new terms associated with the release of new data products.

An Enterprise Data Catalog (EDC) is a centralized inventory and metadata management tool for an organization's data assets. It helps organizations manage and govern their data by providing a comprehensive view of data sources, data lineage, data definitions, data usage, and data quality.

A URN, or Uniform Resource Name, is a Uniform Resource Identifier (URI) that is used to uniquely identify a resource, but without specifying its location or how to access it.

Personally Identifiable Information (PII) refers to an information that is highly sensitive in nature as it can be used to accurately identify, contact, or locate an individual. This includes data elements such as names, addresses, social security numbers, email addresses, and biometric records.

Domain is a logical or thematic grouping of related data assets. Domains are used to categorize and organize data assets based on their subject matter or the business context they belong to. For example, you might have a Finance domain that includes data related to financial transactions, reports, and analysis, or a Human Resources domain that encompasses data related to employee information, payroll, and HR processes.

Platform represents the array of supported data systems that encompass structured, unstructured, and streaming data. These systems are compatible with Enterprise Data Catalog capabilities, allowing it to effectively catalog, manage, and analyze data from a diverse range of sources. Examples of such platforms include popular data storage and processing solutions like Snowflake and MySQL.

## Related

- [Curating the business metadata](/curating-the-business-metadata.md)
