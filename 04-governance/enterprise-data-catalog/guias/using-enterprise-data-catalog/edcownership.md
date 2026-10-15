---
title: "Ownership"
slug: "edcownership"
updated: 2026-07-21T12:24:26Z
published: 2026-07-21T12:24:26Z
canonical: "helpcenter.securiti.ai/edcownership"
stale: true
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Ownership

**Scenario**

As a data steward, you need to ensure every dataset has a clear point of responsibility. Without assigned ownership, it is hard to resolve issues or maintain data quality. The ownership lets you assign roles like business owner or technical owner to each dataset. This brings accountability, improves collaboration, and ensures users know who to contact for any data-related concerns.

Owners are individuals responsible for specific datasets within the EDC. They ensure the accuracy, security, and availability of data. They are also the point of contact for any queries or issues related to their data. All EDC users are displayed under the **Settings** **> Ownership Types** section.

The following are the legacy ownership types and their corresponding URNs in the EDC:

| Legacy ownership types | URNs |
| --- | --- |
| Technical owner | `urn:li:ownershipType:__system__technical_owner` |
| Business owner | `urn:li:ownershipType:__system__business_owner` |
| Data steward | `urn:li:ownershipType:__system__data_steward` |

> [!NOTE]
> **Note**
> 
> We recommend avoiding legacy owners. Instead, create your Custom ownership types.

### 

## Custom ownership types

Custom ownership types are an improvement in the way to establish ownership relationships between users and the data assets they manage within EDC.

#### Why are custom ownership types required?

EDC brings a pre-defined opinion on ownership relationships. We are aware that it may not always precisely match what you may need. With this feature, you can modify it to better match the terminology used by stakeholders.

#### Prerequisites

You must have the following permissions enables for your role to create, manage, view, update and delete ownership types.

- Create ownership type
- Manage ownership type
- View ownership type
- Update ownership type
- Delete ownership type

For details, refer to [Enterprise Data Catalog RBAC permissions and roles](/latest/docs/edc-rbac-permissions-and-roles).

#### Creating custom ownership types

To create custom ownership types:

#### 

1. Open Enterprise Data Catalog, then navigate to **EDC** **Permissions > Ownership Types**.
2. On the **Manage Ownership** page, click **+ Create new Ownership Type**.
3. On the **Add a new ownership type** popup, enter the ownership name and its description.
4. Click **Save**.

![Settings page for managing ownership types in an enterprise data catalog.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-30 at 4.07.22 PM.png)

![User interface for adding owners to a data schema in Snowflake platform.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-02 at 4.33.24 PM.png)

#### Custom ownership URNs

You can uniquely identify any custom ownership in the Enterprise Data Catalog with a URN. URN stands for Uniform Resource Name.

To copy URNs:

1. Click **Settings > Ownership Types**.
2. On the ownership types pages, click the **Copy** icon located on the left side of **Options** (three dots).

#### Assigning custom ownership types to entities

You can assign an owner with a custom ownership type to an entity.

1. On the entity's detail page, use the right sidebar to locate the **Owners** section.
2. Click **+ Add Owners**, select the owner, and then search for the custom ownership type you want to add this entity to.
3. Click **Add**.

> [!NOTE]
> Note
> 
> To remove ownership from an asset, click the **x** icon on the Owner label.

#### Deleting and editing custom ownership types

- Click **Options** (three dots) located at the right side of the ownership row that you want to edit or delete.
  - Click **Edit** to edit the ownership.
  - Click **Delete** to delete the ownership.

A URN, or Uniform Resource Name, is a Uniform Resource Identifier (URI) that is used to uniquely identify a resource, but without specifying its location or how to access it.
