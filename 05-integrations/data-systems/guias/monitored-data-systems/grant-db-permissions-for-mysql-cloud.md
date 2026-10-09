---
title: "Grant DB permissions for MySQL Cloud"
slug: "grant-db-permissions-for-mysql-cloud"
updated: 2026-07-31T06:52:41Z
published: 2026-07-31T06:52:41Z
canonical: "helpcenter.securiti.ai/grant-db-permissions-for-mysql-cloud"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant DB permissions for MySQL Cloud

Do the following to grant MySQL Connector Database Permissions.

1. Create a user, for example, Securiti, and a secure password:

```plaintext
CREATE USER 'securiti'@'<pod-IP or host>' IDENTIFIED BY '<some-strong-password>';
```
2. Grant SELECT permission on everything within the Database so that you can run a scan for each Database:

```plaintext
GRANT SELECT on <<database>.* to 'securiti'@'<pod-IP or host>';  
```
3. Proceed to [Collect authentication information for MySQL Cloud](/latest/docs/collect-authentication-information-for-mysql-cloud).
