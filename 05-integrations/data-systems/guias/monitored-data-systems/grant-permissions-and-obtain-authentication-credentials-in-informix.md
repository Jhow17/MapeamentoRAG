---
title: "Grant permissions and obtain authentication credentials in Informix"
slug: "grant-permissions-and-obtain-authentication-credentials-in-informix"
updated: 2026-07-20T20:04:18Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-authentication-credentials-in-informix"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain authentication credentials in Informix

IBM Informix Data system uses the following minimum Database Permissions or privileges before Connector Activation.

> [!NOTE]
> **Note**
> 
> We assume you have access to a Database running Informix. Otherwise, we suggest you refer to its admin to obtain the "Connect" permission and Table-level privileges (Alter, Index, References), etc., so you can proceed with the Authentication.

1. Connect to the Database using GRANT CONNECT TO PUBLIC or a different Connection statement.

> [!NOTE]
> **Note**
> 
> The GRANT CONNECT TO PUBLIC statements allows permission for all users. If you use GRANT CONNECT TO "USER", the statement allows permission to that particular user.
2. Execute the SELECT statement for the tables.
3. Create views in the underlying tables.
4. Create synonyms
5. Create temporary tables and create indexes on these tables.
6. Grant privileges on a Table or a view.

> [!NOTE]
> **Note**
> 
> As an admin, you can grant privileges using the WITH GRANT OPTION keywords to the user.
7. Once you have (assigned) the required Permissions, record the following parameters:
  - **Host**
  - **Port**
  - **User**
  - **Password**
  - **Database/Schema**
8. Proceed to [Connecting IBM Informix with Securiti](/latest/docs/connect-ibm-informix-with-securiti).
