---
title: "Prerequisites for creating a Firebird server"
slug: "prerequisites-for-creating-a-firebird-server"
updated: 2026-07-20T19:51:24Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/prerequisites-for-creating-a-firebird-server"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for creating a Firebird server

To integrate Firebird with Securiti and provide access to scan your databases, you must grant the necessary permissions. Permissions vary depending on your operating system.

- For Linux systems, grant the following permissions

If you want to create a Firebird Database file under */firebird/data -> /firebird/data/mydatabase* make sure the data directory exists under Firebird and file read, write, and execute permissions are available to the Firebird server

Use the following command to give the above permissions in the Linux system.

```plaintext
ubuntu#  sudo chown firebird:firebird /opt/firebird/data/ubuntu#  
sudo chmod 755 /opt/firebird/data/
```
  - **Read**
  - **Write**
  - **Execute**
- For Windows and Mac operating systems, the administrator of the operating system automatically gets the read, write, and execute permissions.
