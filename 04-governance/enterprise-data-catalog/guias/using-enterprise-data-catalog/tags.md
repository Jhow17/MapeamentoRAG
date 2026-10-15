---
title: "Tags"
slug: "tags"
updated: 2026-07-18T09:07:41Z
published: 2026-07-18T09:07:41Z
canonical: "helpcenter.securiti.ai/tags"
stale: true
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Tags

**Scenario**

As a business analyst, you often search for relevant datasets across multiple projects. Without a quick way to identify context, finding the right data is time-consuming. Tags let you label datasets with keywords like marketing, Q4 reports, or trusted. This helps you and your team quickly discover and organize data based on purpose, improving efficiency and reducing search time.

Tags are metadata labels or keywords that help you in search and discovery. They can be associated with datasets, dataset schemas, or containers, for an easy way to label or categorize entities – without having to associate them with a broader business glossary or vocabulary. Tags are typically user-defined and can reflect various aspects of the data, such as its purpose, quality, source, or any other relevant attribute.

Tags can help you in:

- Querying: Tagging a dataset with a phrase that your co-worker can use to query the same dataset.
- Mapping assets to a category or group of your choice.

### **Prerequisites**

To work with tags, you must have the **Manage Tags** permission enabled for your account. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

### **Recommended practice**

If you are registering data assets via discovery scan, then make sure you have created tags ahead of configuring the discovery scan. By doing this, you can have assets in the Enterprise Data Catalog already assigned to the correct owner.

> [!NOTE]
> Note
> 
> You cannot edit existing tags. You can only add or delete tags.

### Using tags

#### Adding a tag

To add a tag at the dataset or container level:

1. Navigate to the dataset or a container page.
2. On the bottom right corner of the page, click **+ Add Tag**.
3. On the Add Tags popup, do one of the following:
  - Type in the name of the tag you want to add (the autocomplete will pull up the tag if it already exists).
  - Write the tag name you want to create.
  - Add a description to the tag.
  - Click **Create**. Your tag gets created and linked to the respective dataset or container.

![EDC_tags_-_Creaitng_tags_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dca6cc96-0f4f-2b6c-928d-14bda0d0cdd3.png)

**Adding tags at the schema level**

1. Hover over the tags column for a schema until the **Add Tag** button shows up.
2. Follow the same flow as mentioned above.

#### Removing the tag

To remove a tag:

1. Open the dataset or a container page from which you want to remove tag.
2. Click on the **X** button within the tag section.
3. On the confirmation popup, click Yes to confirm the removal of the tag.

#### Searching the tag

Enter a tag name in the search bar and even filter entities by the presence of a specific tag through filter sections.

![EDC_tags_-_Filter_panel.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-82a0c4ef-874d-cdb6-cef4-e0291dca6ceb.png)

### Tags URNs

You can uniquely identify any tag in the Enterprise Data Catalog with a URN. URN stands for Uniform Resource Name.

To copy tags URNs:

- On the **Tags** page, click the **Copy** icon located on the left side of **Options (three dots)**.

## FAQs

#### What is the difference between tags and glossary terms?

Tags: Tags are informal, loosely controlled labels that serve as a tool to group assets to assist in search and discovery. Assets may have multiple tags. Although there is no formal, central management, admins may perform tasks to consolidate tags.

Glossary terms: Glossaries contain a list of terms typically organized in taxonomies. They capture business metadata and provide a controlled/governed vocabulary, with optional hierarchy/taxonomy. Terms are typically used to standardize common business terminology and to provide an understanding of data assets.

Refer to loosely defined terms that can be applied to data assets and other catalog entities. These tags make it easier to organize and search for specific assets within the Enterprise Data Catalog.

## Related

- [Glossary terms](/glossary-terms.md)
