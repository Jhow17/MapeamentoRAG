---
title: "Prerequisites for IBM Db2"
slug: "prerequisites-for-ibm-db2"
updated: 2026-06-23T09:48:32Z
published: 2026-06-23T09:48:32Z
canonical: "helpcenter.securiti.ai/prerequisites-for-ibm-db2"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for IBM Db2

Fulfill the following prerequisites to enable Securiti to connect to and scan your IBM Db2 Database successfully.

> [!NOTE]
> **Note**
> 
> A user with administrative privileges must be created to connect to the Database. Avoid changing the username after creating a user.

### Creating a role and granting `SELECT` permission

Securiti requires specific read-only Permissions to the IBM Db2 system catalogs to effectively discover, analyze, and monitor your Database environment.

Follow the procedure below to create a role and assign the necessary Permissions.

1. Create a role such as `ro_securiti`, run the following command:

```plaintext
CREATE ROLE ro_securiti
```
2. Grant `SELECT` permission on each Table within each Schema for scanning a new role:

```plaintext
GRANT SELECT on <<schema>>.<<table>> TO ROLE ro_securiti
```

You must grant `SELECT` access on key `SYSCAT` views to enable metadata discovery and optional lineage analysis.

IBM Db2 Connector in Securiti interacts with catalog views for different purposes, as shown in the Table below.

| Metadata retrieval | Row count retrieval |
| --- | --- |
| `SYSCAT.TABLES` | `SYSCAT.TABLES` |
| `SYSCAT.TABAUTH` | `SYSCAT.TABAUTH` |
| `SYSCAT.COLUMNS` |  |
| `SYSCAT.INDEXES` |  |
| `SYSCAT.INDEXCOLUSE` |  |
| `SYSCAT.REFERENCES` |  |
| `SYSCAT.CHECKS` |  |
| `SYSCAT.ROUTINES` |  |
| `SYSCAT.VIEW` |  |
| `SYSCAT.TRIGGERS` |  |

> [!NOTE]
> **Important**
> 
> - Securiti employs a fallback strategy when `SYSCAT.TABAUTH` access is restricted. In such cases, it executes direct **COUNT_BIG(*)** queries on individual tables to determine accessibility, as shown below.
> - Securiti directly queries SYSCAT only, but JDBC metadata functions may internally access SYSIBM objects depending on driver version; this behavior occurs at the driver level and is not controlled by Securiti.
3. Create an operating system user such as "ibmadmin" with administrative privileges. For more information on creating users manually, see [IBM documentation](https://www.ibm.com/docs/en/samfess/8.2.0?topic=schema-creating-users-manually).
4. Assign **ro_securiti** role to the newly created user and run the following command:

```plaintext
GRANT ROLE ro_securiti TO admin
```

### Acquiring authentication credentials in IBM

Follow the procedure below to acquire the Credentials to authenticate IBM Db2 Connector with Securiti.

1. Log in to IBM Cloud as shown.

![login_ibm_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f9f53ac1-f823-8a0d-13ee-3ac3a5cccfc9.png)
2. In the **Catalog** field, search for "Db2".

![catalog_search_ibm_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-457317cc-db78-64f4-eae4-08b965898f1b.png)
3. Near the bottom of the Summary section, click **Create**.

![create_ibm_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b42aa434-7d91-77fe-dcbe-0fde3ac5f622.png)
4. On the left navigation menu, select **Service Credentials > New credential**.

![new_cred_ibm_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-041a669e-2940-ba04-294e-0e21ddbab66c.png)
5. Click **Add** without making any changes.

![add_ibm.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d55c2384-064a-7137-4ec9-23312ef827db.png)
6. In the Table that follows, click the arrow to view credential details and record the following for later use.

![view_cred_ibm_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5d0ea6b0-1de1-b8b1-a344-d8ec7306a404.png)
  - Host
  - Port
  - Database
  - User
  - Password
7. Proceed to [Connecting IBM Db2 with Securiti](/latest/docs/connecting-ibm-db2-with-securiti).
