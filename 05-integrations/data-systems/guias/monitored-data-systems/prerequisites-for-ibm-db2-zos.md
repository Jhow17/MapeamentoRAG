---
title: "Prerequisites for IBM Db2 zOS"
slug: "prerequisites-for-ibm-db2-zos"
updated: 2026-06-23T09:49:48Z
published: 2026-06-23T09:49:48Z
canonical: "helpcenter.securiti.ai/prerequisites-for-ibm-db2-zos"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for IBM Db2 zOS

Fulfill the following prerequisites to enable Securiti to connect to and scan your IBM Db2 zOS Database successfully.

> [!NOTE]
> **Note**
> 
> A user with administrative privileges must be created to connect to the Database. Avoid changing the username after it has been created.

### Creating a role and granting `SELECT` permission

Securiti requires specific read-only Permissions to the IBM Db2 zOS system catalogs to discover, analyze, and monitor your Database environment.

Follow the procedure below to create a role and assign the necessary Permissions.

1. Create a role such as `ro_securiti`, run the following command:

```plaintext
CREATE ROLE ro_securiti
```
2. Grant `SELECT` permission on each Table within each Schema for scanning a new role:

```plaintext
GRANT SELECT on <<schema>>.<<table>> TO ROLE ro_securiti
```

You must grant `SELECT` access on the `SYSIBM` Schema to enable metadata discovery and optional lineage analysis.

IBM Db2 zOS Connector in Securiti interacts with the following catalog views for metadata retrieval and Row count estimate, as shown in the Table below.

| Metadata retrieval | Row count retrieval |
| --- | --- |
| `SYSIBM.SYSCOLUMNS` | `SYSIBM.SYSTABLES` |
| `SYSIBM.SYSTABLES` | `SYSIBM.SYSTABAUTH` |
| `SYSIBM.SYSINDEXES` |  |

> [!NOTE]
> **Important**
> 
> - Securiti employs a fallback strategy when `SYSTABAUTH` access is not granted. In such cases, it executes direct **COUNT_BIG(*)** queries on individual tables to determine accessibility, as shown below.
> 
> ```plaintext
> SELECT COUNT_BIG(*) FROM {{table}}
> ```
> 
> - Securiti uses standard IBM DB2 JDBC metadata methods, such as `getTables`, `getColumns`, `getPrimaryKeys `that automatically query `SYSIBM `catalog tables. These methods internally query system catalog tables within `SYSIBM`, and are not directly controlled by Securiti.
3. Create an operating system user such as "ibmadmin" with administrative privileges. For more information on creating users manually, see [IBM documentation](https://www.ibm.com/docs/en/samfess/8.2.0?topic=schema-creating-users-manually).
4. Assign **ro_securiti** role to the newly created user and run the following command:

```plaintext
GRANT ROLE ro_securiti TO admin
```

### Acquiring authentication credentials in IBM

Follow the procedure below to acquire the Credentials to authenticate IBM Db2 Connector with Securiti.

> [!NOTE]
> **Important**
> 
> For mTLS Authentication using Certificate Credentials, see this [IBM documentation](https://www.ibm.com/docs/en/db2/11.5.x?topic=clients-configuring-tls-certificate-authentication-non-java) to acquire the **Keystore File** and **Keystore password**,

1. Log in to IBM Cloud as shown.

![login_ibm_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f9f53ac1-f823-8a0d-13ee-3ac3a5cccfc9(1).png)
2. In the **Catalog** field, search for "Db2".

![catalog_search_ibm_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-457317cc-db78-64f4-eae4-08b965898f1b(1).png)
3. Near the bottom of the Summary section, click **Create**.

![create_ibm_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b42aa434-7d91-77fe-dcbe-0fde3ac5f622(1).png)
4. On the left navigation menu, select **Service Credentials > New credential**.

![new_cred_ibm_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-041a669e-2940-ba04-294e-0e21ddbab66c(1).png)
5. Click **Add** without making any changes.

![add_ibm.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d55c2384-064a-7137-4ec9-23312ef827db(1).png)
6. In the Table that follows, click the arrow to view credential details and record the following for later use.

![view_cred_ibm_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5d0ea6b0-1de1-b8b1-a344-d8ec7306a404(1).png)
  - Host
  - Port
  - Database
  - User
  - Password
7. Proceed to [Connecting IBM Db2 zOS with Securiti](/latest/docs/connecting-ibm-db2-zos-with-securiti).
