---
title: "Microsoft SQL Server FAQs"
slug: "microsoft-sql-server-faqs"
updated: 2026-06-18T08:03:18Z
published: 2026-06-18T08:03:18Z
canonical: "helpcenter.securiti.ai/microsoft-sql-server-faqs"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft SQL Server FAQs

This article answers frequently asked questions about the Microsoft SQL Server connector.

### Authentication and credentials

This section covers the FAQs related to Microsoft SQL Server authentication and activation credentials.

****If Kerberos authentication fails, does the connector automatically switch to NTLM authentication?****

No, the connector does not automatically switch to NTLM Authentication. It strictly follows the configured Authentication method. If Kerberos Authentication fails, the system logs an error instead of falling back to NTLM.

****How can we detect a Kerberos authentication failure if NTLM fallback is not automatic?****

Since NTLM fallback does not occur automatically, you can identify Kerberos Authentication failures by reviewing the detailed error logs in the JDBC proxy container. If Authentication fails, an explicit error message is logged in the **Audit Trail** tab, instead of transitioning to NTLM.

****How can I track Kerberos authentication success, errors, or failures?****

You can review Authentication logs in the JDBC proxy container and Securiti's **Audit Trail** tab for the connector.

****What issues in the Kerberos configuration file (**`krb5.conf`**) can cause authentication failure?****

Authentication failures may occur due to unsupported parameters in the krb5.conf file. See an example below of unsupported parameters:

```plaintext
rdns = false
pkiinit_anchors = FILE:/etc/pki/tls/certs/ca-bundle.crt
spake_preauth_groups = edwards25519
default_ccache_name = KEYRING:persistent:%{uid}
default_tgs_enctypes = aes256-cts-hmac-sha512-256, aes256-cts-hmac-sha256-128
default_tkt_enctypes = aes256-cts-hmac-sha512-256, aes256-cts-hmac-sha256-128
permitted_enctypes = aes256-cts-hmac-sha512-256, aes256-cts-hmac-sha256-128
```

When you authenticate the SQL Server Connector without providing the `krb5.conf` file, by manually specifying the Kerberos Credentials, Securiti automatically generates a Configuration file using minimum Permissions. We recommend that you use the Configuration file format by Securiti as shown below.

```plaintext
   kerberosConfFmt = `
[libdefaults]
forwardable = true
default_realm = {{ .Realm}}
udp_preference_limit = 1
[realms]
{{ .Realm}} = {
  kdc = {{ .ip for kdc server}}
}`
```

Alternatively, you can also follow the format as described in [Microsoft's documentation](https://learn.microsoft.com/en-us/sql/connect/jdbc/using-kerberos-integrated-authentication-to-connect-to-sql-server?view=sql-server-ver16#creating-a-kerberos-configuration-file), as shown below:

```plaintext
[libdefaults]
default_realm = YYYY.CORP.CONTOSO.COM
dns_lookup_realm = false
dns_lookup_kdc = true
ticket_lifetime = 24h
forwardable = yes
[domain_realm]
.yyyy.corp.contoso.com = YYYY.CORP.CONTOSO.COM
.zzzz.corp.contoso.com = ZZZZ.CORP.CONTOSO.COM
[realms]
YYYY.CORP.CONTOSO.COM = {
  kdc = krbtgt/YYYY.CORP.CONTOSO.COM @ YYYY.CORP.CONTOSO.COM
  default_domain = YYYY.CORP.CONTOSO.COM
}
```

****Does Securiti support keyring-based credential caches in the** `krb5.conf` **file?****

No, Securiti does not support the Keyring cache type as the default credential cache.

****What Kerberos encryption types are not supported by Securiti?****

The following Kerberos encryption types are not supported:

- **default_tgs_enctypes:**
  - aes256-cts-hmac-sha512-256
  - aes256-cts-hmac-sha256-128
  - aes256-cts-hmac-sha1-96
- **default_tkt_enctypes:**
  - aes256-cts-hmac-sha512-256
  - aes256-cts-hmac-sha256-128
  - aes256-cts-hmac-sha1-96
- **permitted_enctypes:**
  - aes256-cts-hmac-sha512-256
  - aes256-cts-hmac-sha256-128
  - aes256-cts-hmac-sha1-96

### Diagnostics

This section covers frequently asked questions about the SQL Server connector's auto-diagnostic report.

****What does the SQL Server diagnostic report check?****

The SQL Server diagnostic report runs comprehensive checks after connector activation or reconfiguration. The checks cover the following areas:

- Connectivity to the SQL Server host and port
- KDC connectivity (for Kerberos only)
- Authentication using the configured authentication method (SQL, Kerberos, Windows, or Azure AD)
- Database existence and access
- Metadata retrieval permissions
- `SELECT` permissions on tables
- Permissions on constraints
- Data preparation and table availability
- Overall scan readiness

Securiti displays the result of each step individually. When a step fails, Securiti shows a specific reason to help you identify and resolve the issue.

****Why does the diagnostic report show a failure even though my connector authenticated successfully?****

The diagnostic report runs independently of the authentication result. Authentication only verifies that Securiti can connect to SQL Server using the credentials provided. The diagnostic report goes further and validates all operations the connector depends on, including database access, table permissions, and scan readiness. It is expected for a connector to authenticate successfully while one or more diagnostic steps still fail.

****Which SQL Server authentication methods does the diagnostic report support?****

The diagnostic report supports all authentication methods available for the SQL Server connector, as listed below:

- SQL Server Authentication
- Kerberos Authentication
- Windows Authentication
- Azure AD Authentication

The specific steps that run may vary slightly by authentication method.

****Where can I view the diagnostic report?****

For more information on accessing the report, see [Auto-diagnostic reports in data system connectors](/latest/docs/auto-diagnostic-reports-in-data-system-connectors).
