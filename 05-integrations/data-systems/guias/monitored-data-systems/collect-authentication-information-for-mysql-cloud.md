---
title: "Collect authentication information for MySQL Cloud"
slug: "collect-authentication-information-for-mysql-cloud"
updated: 2026-07-31T06:53:12Z
published: 2026-07-31T06:53:12Z
canonical: "helpcenter.securiti.ai/collect-authentication-information-for-mysql-cloud"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Collect authentication information for MySQL Cloud

Collect the following information that you must have in order to activate the Securiti Connector:

- The IP Address for your MySQL Database
- The port number for your MySQL Database (usually 3306)
- Username for a MySQL account with administrative access
- Password for the account with administrative access
- Name of your MySQL Database

The user account must have access to connect from any host in the case of a MySQL Cloud Connector and from the Pod host in case of a MySQL On-premises Connector. See **https://dev.mysql.com/doc/refman/5.7/en/grant.html** for more information.

An example is, GRANT ALL ON <dbname>.* TO **'<username>' @ '<client_hostname>'**.

Replace <dbname>, <username>, <client_hostname> with appropriate values. <client_hostname> is the name of the client machine from which the Connection is established. Set value to **'%'** to connect from any client machine.

Proceed to [Connecting MySQL (Securiti Cloud) with Securiti](/latest/docs/connecting-mysql-securiti-cloud-with-securiti).
