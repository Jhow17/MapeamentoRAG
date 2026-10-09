---
title: "SMB FAQs"
slug: "smb-faqs"
updated: 2026-08-31T08:31:27Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/smb-faqs"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# SMB FAQs

This article answers frequently asked questions about the SMB connector.

****Why do I need to migrate from SMBv1?****

SMBv1 is a legacy protocol with known security limitations and is no longer recommended for secure file-sharing environments.

SMBv2 and SMBv3 provide improved security and performance. SMBv3 also provides additional security capabilities, including stronger encryption support.

****What happens if a scan is running?****

You cannot reconfigure the connector while a scan is in progress.

Wait for the scan to complete, or stop the scan if appropriate, and then reconfigure the connector.

****What should I do if authentication fails?****

Review the connector diagnostics and logs for the reported error.

The results can help identify issues such as missing permissions, authentication failures, connectivity problems, or incorrect configuration.

Resolve the reported issue, and then retry the connection.

****Do I need to contact Securiti support if the migration fails?****

Not necessarily. In most cases, the connector diagnostic utility provides information you can use to identify and resolve the issue.

If you cannot resolve the error using the diagnostic information, contact support and include the relevant error details.

****Does the migration affect my existing data labeling policies?****

No. Migrating the connector to SMBv2 or SMBv3 does not require you to recreate your existing data labeling policies.

After the connector successfully authenticates using the new SMB version, your existing policies continue to operate with the connector.
