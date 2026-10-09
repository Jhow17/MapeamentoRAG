---
title: "Configuring Oracle Object Storage scanning"
slug: "configuring-oracle-object-storage-scanning"
updated: 2026-08-11T11:47:40Z
published: 2026-08-11T11:47:40Z
canonical: "helpcenter.securiti.ai/configuring-oracle-object-storage-scanning"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Oracle Object Storage scanning

After you configure the Oracle Object Storage Connector, Securiti scans your Oracle Object Storage drive to discover your contents and associated information. Securiti then scans the accompanying files to match any identities that it finds with identities discovered in your Structured data systems such as Oracle or Hive. Securiti uses this data to respond quickly to DSR requests submitted by data subjects whose personal data is in the files.

Since your Oracle Object Storage users are constantly adding, editing, and deleting files from their respective drives, the Securiti Connector must regularly re-scan your Oracle Object Storage drives to discover new and updated files, and update its internal inventory.

## Initiating data scan for Oracle Object Storage

After configuring the Connector, start an initial data scan to learn the structure of the data system. For Oracle Object Storage, this is for the object storage, file storage system, and database information that could be used to configure scan policies:

1. On the Connector tab, click **Initiate Data Scan**.

The Connector discovers an object "Object Storage" (and its inclusive File Storage Systems and Database contents). During this process, the state shows as “Learning.” The Connector re-learns this information after every scan interval before a re-scan.
2. If the Oracle Object Storage Connector discovers a change in its contents, it updates its data system:

- For changes in Object Storage:

Securiti scans your Oracle storage and periodically re-scans it to detect and update any changes to your files.

1. Once the Connector comes out of the initial Learning state, the status shows “Learning complete” and the Connector waits for your input to either:

- Scan all discovered users and their folders using the default scan policy: By default, auto-scan is enabled and Oracle Object Storage scans once on a daily basis when prompted.
- Lets you change the scan policy and initiate a full scan followed by rescans at regular intervals.

1. To configure scan policies for subsequent scans:

- Mark the **Auto Scan** checkbox to enable automatic re-scans of your Oracle Object Storage drives.
- Mark the **Track Schema Changes Only** checkbox to configure the Connector to only look for Schema changes. If a new Table gets added, it learns that table, and any new columns added to existing tables. But, if new data is inserted into one or more of existing tables, it isn’t scanned.
- Use the Scan Interval tools to configure how often Securiti does the re-scan.
