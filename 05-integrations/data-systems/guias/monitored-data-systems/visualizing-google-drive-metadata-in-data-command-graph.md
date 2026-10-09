---
title: "Visualizing Google Drive metadata in Data Command Graph"
slug: "visualizing-google-drive-metadata-in-data-command-graph"
updated: 2026-04-28T03:46:29Z
published: 2026-04-28T03:46:29Z
canonical: "helpcenter.securiti.ai/visualizing-google-drive-metadata-in-data-command-graph"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Visualizing Google Drive metadata in Data Command Graph

The discovered metadata as well as the Google Drive labels applied on documents can be viewed and analyzed in the Data Command Graph's Graph Explorer to see which files are discovered during the Data Inventory Sync and understand their properties and relationships. The following graph entities are used to view Google Drive's (Google Workspace) files and applied labels.

- **Files**: Lets you view the discovered Google Drive (Google Workspace) files and their metadata.
- **Scanned Classification Label**: Lets you view the Google Drive labels applied to your files. The labels provide insights into your document classifications.

Securiti displays properties for your Google Drive documents in the Graph Explorer. Key properties include:

- **Top Level Directory**: Displays either the Shared Drive name or your email address (for personal drives) for your scanned documents.

**Top Level Directory** is populated for documents scanned on Pod version 1.130 or later.
- **Resource Path**: Displays the immediate parent directory's name for your scanned documents.
- **Resource URL**: Displays the link to scanned document.

The screenshot below shows a Graph Explorer query that displays the labels in Google Drive (Google Workspace) files and their properties discovered during the Data Inventory Sync.

![Gdrivelabels_graphexplorer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ab1bce9-948a-0db6-e74d-0c867771b87b.png)

For more information, see [Using Graph Explorer](/latest/docs/using-graph-explorer).
